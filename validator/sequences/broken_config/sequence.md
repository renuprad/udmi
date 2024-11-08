
## broken_config (STABLE)

Check that the device correctly handles a broken (non-json) config message.

1. Wait for config sync
1. Update config enable debug logging:
    * Set `system.min_loglevel` = `100`
1. Wait for initial state synchronized
1. Check that initial stable_config matches last_config
1. Wait for log category `system.config.apply` level `NOTICE` to be logged
1. Wait for config sync
1. Wait for has significant system status
1. Check that significant system status exists
1. Check that status level is error (500)
1. Check that category matches system.config.parse
1. Check that previous good config timestamp matches state last_config
1. Wait for log category `system.config.receive` level `DEBUG` to be logged
1. Wait for log category `system.config.parse` level `ERROR` to be logged
1. Check that log category `system.config.apply` level `NOTICE` not logged
1. Force reset config
1. Wait for config sync
1. Wait for log category `system.config.apply` level `NOTICE` to be logged
1. Wait for restored state synchronized
1. Wait for config sync
1. Update config Before log category `system.config.apply` level `NOTICE` to be logged:
    * Set `system.min_loglevel` = `100`
1. Wait for log category `system.config.apply` level `NOTICE` to be logged
1. Check that log category `system.config.receive` level `DEBUG` not logged
1. Check that log category `system.config.parse` level `DEBUG` not logged
