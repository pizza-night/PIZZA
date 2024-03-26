# 🍕 PIZZA Protocol

PIZZA is a Peer-2-Peer message protocol

## Message Format

| Type | Payload        |
| ---  | ---            |
| u8   | Type Dependent |

## Message Types

#### Text Message (**Type: 0**)

| the length of the payload | the text message in utf8 encoding |
| ---                       | ---                               |
| u32                       | sizeof(size)                      |

#### Set Username (**Type: 1**)

| the length of the name | the name in utf8 encoding |
| ---                    | ---                       |
| u8                     | sizeof(size)              |

#### Peer Sharing (**Type: 2**)

This should be sent to all peers that connect to you

| the # of ipv4 peers | the # of ipv6 peers | a list of ipv4 addresses | a list of ipv6 addresses |
| ---                 | ---                 | ---                      | ---                      |
| u8                  | u8                  | sizeof(u32)*IpV4 Count   | sizeof(u128)*IpV6 Count  |


# Diagram

![diagram](./pizza-protocol.drawio.svg)
