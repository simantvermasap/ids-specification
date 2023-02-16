# International Dataspaces (IDS) - Version X

### Working Draft 1 February 2023

> __NOTE:__ These specifications are working drafts and subject to change.

## Abstract

IDS is a set of specifications designed to facilitate interoperable data sharing between entities governed by usage control and based on Web technologies. These specifications
define the schemas and protocols required for entities to publish data, negotiate usage agreements, and access data as part of a federation of technical systems termed a
__*dataspace*__.

## Introduction

Sharing data between autonomous entities requires the provision of metadata to facilitate the transfer of assets by making use of a data transfer (or application layer) protocol.
IDS defines how this metadata is provisioned:

1. How data assets are deployed as [DCAT Catalogs](https://www.w3.org/TR/vocab-dcat-3/) and usage control is expressed as [ODRL Policies](https://www.w3.org/TR/odrl-model/).
2. How contract agreements that govern data access are syntactically expressed and electronically negotiated.
3. How data assets are accessed using data transfer protocols.

These specifications build on protocols located in the [ISO OSI   model (ISO/IEC 7498-1:1994)](https://www.iso.org/standard/20269.html) layers, like HTTPS.
The purpose of this specification is to define interactions between systems independend of such protocols, but describing how to implement it in an unambigious and extensible way.
To do so, the messages that are exchanged during the process are described in this specification and the states and their transitions are specified as state machines, based on the key terms and concepts of a data space.
On this foundation the binding to data transfer protocols, like HTTPS, is described.

The specifications are organized into the following documents:

* A __*Dataspace Information Model*__ document that defines key terms.
* __*Catalog Protocol*__ and __*Catalog HTTPS Binding*__ documents that define how DCAT Catalogs are published and accessed as HTTPS endpoints respectively.
* __*Contract Negotiation Protocol*__ and __*Contract Negotiation HTTPS Binding*__ documents that define how contract negotiations are conducted and requested via HTTPS endpoints.
* __*Transfer Process Protocol*__ and __*Transfer Process HTTPS Binding*__ documents that define how transfer processes using a given data transfer protocol are governed via HTTPS
  endpoints.

This specification does not cover the data transfer process as such.
While the data transfer is controlled by the __*Transfer Process Protocol*__ mentioned above, the data transfer itself and especially the handling of technical exceptions is an obligation to the Transport Protocol.
As an implication, the data transfer can be conducted in a separated process if required, as long as this process is to the specified extend controlled by the __*Transfer Process Protocol*__.

### Context of this specification

The __*Name of the protocol goes here*__ is used in the context of data spaces as described and defined in the subequent sections with the purpose to support interoperability.
In this context, the specification provides fundamental technical interoperability for particiants in data spaces and therefore the protocol specified here is required to join any data space as specified [here]().
Beyond the technical interoperability measures described in this specification, semantic interoperability should also be addressed by the participants. On the perspective of the data space, interoperability needs to be addressed also on the level of trust, on organizational level and on legal level.
The aspect of cross data space communication is not subject of this document, as this is addressed by the data spaces' organizational and legal agreements.

The interaction of participants in a data space is conducted by the participant agents, so called Data Connectors, which implement the protocols described above.
While most interactions take place between data connectors, some interactions with other systems are required.
The figure below provides an overview on the context of this specification.

An Identity Provider realizes the required interfaces and provides required information to implement Trust Framework of a data space.
The validation of the identity of a given participant agent and the validation of addtional claims is the fundamental mechanism. The strucutre and content of such claims and identity may vary between different data spaces, as well as the structure of such an Identity Provider, e.g. a centralized system, a decentralized system or a federated system.

A connector will implement addtional internal functionalities, like monitoring or Policy Engines, as appropriate. It is not covered by this specification, if a connector implements such or how.

The same applies for the data, which is transfered between the systems. While this document does not define the transpprt protocol, the structure, syntax and semantics of the data, a specification for those aspects is required and subject to the agreements of the participants or the data space.

![Overview on protocol and context](./figures/ProtocolOverview.png)
