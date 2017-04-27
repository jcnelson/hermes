# Hermes

This is a placeholder repository for the peer-to-peer multicast messaging layer for Blockstack Core.

We expect to have this working as a PoC by the end of summer 2017.

# Design Notes

Hermes will let Blockstack applications relay messages to one another via one or more existing message relay services.  A message relay service can be any existing system that can take a (bound-length) message as input and send it to one or more recipients.  Example services include an IRC channel, email, a Twitter feed, a Google Cloud Pub/Sub, and so on.

The existing service does not need to be persistent or reliable.  Messages can get lost, replayed, or re-ordered.  Hermes will ensure that messages are delivered at most once, in the sender-given order.

The existing service is not trusted with authenticity or confidentiality.  The sender's Hermes endpoint will sign messages with the sender's private key, and (optionally) encrypt the message with the recipients' public keys.

A Hermes endpoint will use Chronos to find the recipients' public keys, and then use Atlas to find each recipient's preferred message relay service.

# Deliverables

* A suite of message service drivers
* Code to parse Atlas zone files for message services
* A Websocket server endpoint for sending and receiving messages from Blockstack apps.

# Point of Contact

* Jude Nelson (@jude on blockstack.slack.com)

# How can I help?

Glad you asked!

* Star this repo
* Post questions as Github issues
* PRs are welcome :)
