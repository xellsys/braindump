• make it transparent which toggles exist and their setting in each system at the current point in time
• -> this could be a toggle service which has control over all toggles.
• CAUTION: there is a new dimension of release: the deployed version is not a fail safe indicator of what features are released. in addition there is feature toggle settings!
• make it transparent if a feature toggle is actually executed and actually NOT executed: log/metrics? -> log toggle execution and result? redundant?
• provide a clear and simple reference implementation for toggles
• make a distinction between runtime, restart time, build time toggles
• test your toggles!