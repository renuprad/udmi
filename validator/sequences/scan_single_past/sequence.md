
## scan_single_past (ALPHA)

Check that a scan scheduled in the past never starts

1. Wait for config sync
1. Update config before discovery families defined:
    * Add `discovery` = { "families": {  } }
1. Wait for discovery families defined
1. Wait for discovery family keys match
1. Wait for no scans active
1. Wait for config sync
1. Update config Before scan schedule initially not active:
    * Add `discovery.families.vendor` = { "generation": `family generation`, "scan_duration_sec": `20` }
1. Wait for scan schedule initially not active
1. Wait for scan schedule still not active
1. Check that there were no received discovery events