What properties should an observable system fulfil?

• allow trend analysis over the past, present and future
• realising if something is "wrong"/off
• allowing further manual analysis on top of that
• analysis: provide event specific information

Whats an event in an observability sense? An Ovent
• one unit of work (see honeycomb)

Whats an event in a testing sense? A Tevent!
• possibly any more or less atomic action performed on a software by an end user or other system
• whats atomic?
  • a save action, an edit action, an exit action, a create action, a navigation action, a login action, an incoming message, an http request, a scheduled action/job execution a batch job, ...?
  • in a sense of BDD or gherkin its one "block" in the when part?
• whats part of that tevent?
  • all information associated to this tevent
  • all other immediate (more data used which eventually leads to full disk would end up in all events being part of that, a delayed action would otherwise also be part of that) "sub actions" triggered by that tevent?

Can we associate a tevent with an ovent?
• an ovent might be more granular, more technical in most cases
• sometimes a tevent can consist of multiple ovents

What does it boil down to?
• when testing or observing others perform tevents you will want to easily and immediately access all tevent associated information
• it should be displayed, graphed whatever makes sense for its type of data (graph, table, raw, list, word cloud, ...)

How can we achieve this (with current open source tools)?
• logs are "event" (ovent) based: a log message is only written if there is a unit of work happening. there may be multiple log messages associated to the same ovent though!
• tevents required an ID to be individually identified! -> teventId
• tracing provides correlation id's which associate with a transaction -> a transaction can be an event or part of one.
• whats the relation between transactions (by correlation id) and events (by event id)?
  • as a tester there is one or multiple events I am interested in analysing
  • I'd then want to associate each event with correlation ids which allows me to gather tracing data for this particular event
  • within my own system the outer span with it's correlation id should suffice
  • every log message should contain that correlation id in it's structured logs
  • every metric should contain that correlation id as a cardinality
• another option of associating events is time (but not ideal)
  • when there are multiple independent events overlapping in time you have a hard time separating those from each other

• Could an tevent be never ending with our definition above?
  • yes: "endless" loop in the application
  • too closely coupled association of technical events 

Overview:

Tevent (eventId)
1
...
n
Ovent (correlationId)
1
...
n
http/message calls

Ovent
1
...
stateful actions (CRUD, transactional)

A tevent would have to be defined manually with each analysis and given an id at that point. Sometimes multiple tevents are required to describe an unexpected/unwanted behavior of our system. we could group multiple tevents in "happenings"