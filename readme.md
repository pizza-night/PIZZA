# PIZZA Protocol

PIZZA is a Peer-2-Peer message protocol

## Message Format
| Header | Payload          |
|--------|------------------|
| Type   | Type Dependent   |
| u8     |                  |

### Message Type

#### Data
| Type   | Size | Payload       |
|--------|------|---------------|
| 0      | u32  | sizeof(size)  |

#### Set Username
| Type   | Size | Username      |
|--------|------|---------------|
| 1      | u8   | sizeof(size)  |

#### Peer Sharing
This should be the first message sent when a peer connects to you

| Type | IpV4 Count | IpV6 Count | IpV4 Addresses               | IpV6 Addresses                |
| ---  | ---        | ---        | ---                          | ---                           |
| 2    | u8         | u8         | sizeof(u32 + u16)*IpV4 Count | sizeof(u128 + u16)*IpV6 Count |
