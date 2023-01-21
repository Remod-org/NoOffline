# NoOffline
Prevent offline raiding based on privilege owners, members, and friends of those players

This is not for use on PVE servers and/or servers using a PVE plugin.

On every attempt to damage an entity within building privilege, we check for the following:

  1. Any authorized user is currently online
  2. Any friend, clan member, or teammate of an authorized player is online (based on useClans/useFriends/useTeams).

If either of the above are true, damage is allowed.
If all players, members, etc. are offline, damage should be prevented.

## Configuration
```json
{
  "Options": {
    "debug": false,
    "HonorRelationships": false,
    "useClans": false,
    "useFriends": false,
    "useTeams": false
  },
  "Version": {
    "Major": 1,
    "Minor": 0,
    "Patch": 2
  }
}
```

  - `HonorRelationships` -- If set, honor any of the useXXX features to determine online status
  - `useClans` -- Use various Clans plugins for determining relationships.
  - `useFriends` -- Use various Friends plugins for determining relationships.
  - `useTeams` -- Use Rust native teams for determining relationships.
