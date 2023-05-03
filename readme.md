# PIZZA Protocol

PIZZA is a Peer-2-Peer message protocol

## Message Format
| **Desc** | Type | Payload        |
| ---  | ---  | ---            |
| **Size** | u8   | Type Dependent |

### Message Types

#### Text Message

**Type: 0:**

| **Desc** | the length of the payload | the text message in utf8 encoding |
| ---  | ---                       | ---                                      |
| **Size** | u32                       | sizeof(size)                             |

#### Set Username

**Type 1:**

| **Desc** | the length of the name | the name in utf8 encoding |
| ---  | ---                    | ---                       |
| **Size** | u8                     | sizeof(size)              |

#### Peer Sharing

This should be sent to all peers that connect to you

**Type 2:**

| **Desc** | the # of ipv4 peers | the # of ipv6 peers | a list of ipv4 addresses | a list of ipv6 addresses      |
| ---  | ---                 | ---                 | ---                      | ---                           |
| **Size** | u8                  | u8                  | sizeof(u32)*IpV4 Count   | sizeof(u128 + u16)*IpV6 Count |
