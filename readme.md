# PIZZA Protocol

PIZZA is a Peer-2-Peer message protocol

## Message Format
| Header | Payload          |
|--------|------------------|
| Type   | Type Dependent   |
| u8     |                  |

### Message Type
#### Data
| Size | Payload      |
|------|--------------|
| u32  | sizeof(size) |
