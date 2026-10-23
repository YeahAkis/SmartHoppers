# Changelog

## 1.0

- First release of SmartHoppers: per-hopper whitelist or blacklist, edited from a menu
- Hold shift while clicking an item into the filter to add it as an exact match right away, so items like player heads are no longer all treated as the same item. Right click an entry in the filter to switch exact match on or off
- Exact match now compares the item itself and ignores the stack size, before a stack of 2 heads never matched a filter entry for 1 head
- Removing an entry from the filter no longer removes other entries that look the same
- Right clicking a hopper no longer throws an error on servers without Nexo
- Works on Paper, Purpur and Folia from 1.21 up to 26.3
