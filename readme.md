# Why linked open transit data?

This repo explains why we need [linked](https://en.wikipedia.org/wiki/Linked_data) open public transport data.

![CC0-licensed](https://img.shields.io/github/license/public-transport/why-linked-open-transit-data.svg)
[![chat on gitter](https://badges.gitter.im/public-transport/Lobby.svg)](https://gitter.im/public-transport/Lobby)

*Note:* This document is inspired by [*Publishing Transport Data for Maximum Reuse*](https://phd.pietercolpaert.be) by [Pieter Colpaert](https://pietercolpaert.be), which offers a very detailed view on the topic. We recommend to read it!


## Problem

When travelling through larger regions or several countries by public transportation, finding out how and when to get to the destination is hard:

1. People often **need to use multiple, regionally limited apps** to find out which trains/busses/ferries/etc. are available, because these apps often have imprecise (e.g. regarding accessibility), outdated (e.g. construction work) or just no data whatsoever about other regions. Doing this research across operator boundaries involves a lot of manual work. Essentially the user needs to do the job that computers should do: routing through sub-networks.
2. When dealing with large distances (e.g. from Norway to France), this routing work becomes almost impossible for humans to do ad-hoc, because there are so many possible connections. Combined with e.g. cancellations & delays, **users may never find the optimal connection** because of that.
3. **Local, narrow-focused apps are not (as) accessible.** They're often developed with a smaller budget, in some languages, without screen reader & offline support, have a bad UX, are only available for some platforms, etc.
4. **Apps built for current mainstream use cases are not future-proof.** With the ongoing digitisation, diversification and increased on-demand features, they won't be able to deliver on people's mobility needs. (They barely do that *right now*.)


## Data Hubs

**An often-proposed (alleged) solution is to build data exchange hubs**: They collect individual data sets (of both plan & realtime data), integrate them – often using hand-written matching tables and fuzzy matching – and emit one large data merged set. **This doesn't work** for the following reasons:

- **It doesn't scale.** Currently, transportation data hubs process data from *dozens or hundreds* of operators. In Europe, with the on-going heterogenisation of mobility, to really cover *all mobility options*, they would have to integrate *thousands to ten-thousands* of operators.
- Almost always, **the raw & merged data is not (easily) accessible**. This makes it hard to a) integrate more data sources (because of missing openly available examples & APIs) and b) improve the merging algorithms.
- **It is neither fair nor innovative.** Designing centralized systems (including a federation of central hubs) disproportionately helps large transportation operators and app companies (Google Maps), and actively harms small, innovative operators from appearing in people's day-to-day mobility apps.
- **It's not resilient.** With the coming level of technical integration in the mobility sector, large centralized data hubs will a) affect a huge number of people when they're down/malfunctioning, b) make it harder to build offline-capable, data-saving, low-end-devices-compatible (IoT) clients, and therefore encourage the reliance on always-on cloud systems.


## Linked Open Transport Data

Let's solve these problems by designing our public transportation systems *from the start* **with federation, discovery of data sources and caching/offline compatibility in mind**!

We must make our data

- **descriptive** (referencing human- & machine-readable documents on how to parse & interpret it),
- **globally precise** (using IDs that accurately identify transportation infrastructure *without local or operator-specific context*),
- **redistributable** (legally, by putting it in the [public domain](https://en.wikipedia.org/wiki/Public_domain), and technically, by enabling chunking, replication & caching).

We must make our APIs

- **openly documented** (using open standards),
- **publicly available** (without authentication, in the internet, in a best-effort approach),
- **federated** (linking to other APIs instead of aggregating them).

We must develop our **data standards** in the open (allowing barrier-free participation & collaboration), and make them **freely licensed** (to enable wide-spread use). They **should cleanly separate semantics, replication/transport, storage & encoding**. They should not reinvent the wheel, but **rely on existing work** (such as [GTFS](https://gtfs.org)) where applicable.


## Stable Identifiers

Because public transportation *data* reflects strongly interconnected public transportation *systems*, it has many links. **When data by an author/source "A" refers to data from *another* author/source "B", it needs a reliable and precise way to identify items in "B" data.** In federated systems, especially in [linked data](https://en.wikipedia.org/wiki/Linked_data) systems, the need for stable & globally unique IDs is even more significant than in traditional, centralized systems.

*Note:* The aforementioned [*Publishing Transport Data for Maximum Reuse*](https://phd.pietercolpaert.be) has a specific [section on stable identifiers for interoperable data](https://phd.pietercolpaert.be/chapters/measuring-iop).


---

## Contributing

Contributions are welcome! If you have a question or want to propose changes, go to [the Issues page](https://github.com/public-transport/why-linked-open-transit-data/issues). By participating in this project, you commit to the [code of conduct](code-of-conduct.md).
