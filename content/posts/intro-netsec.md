---
title:  "Why Network Security belongs in every Data Engineer's Toolkit"
date: 2026-09-15T09:00:00+02:00
draft: false
tags: 
    - "Data Engineering"
    - "Network Security"
    - "ETH Zurich"
categories:
    - "Security"
    - "Infrastructure"
---


Starting this fall, I'm taking the **Network Security** master module as part of my CAS in Computer Science at ETH Zurich. 
I'm genuinely excited to deep dive into network security techniques and network attack vectors, and refresh my core understanding of network protocols and cryptography.

> ***Every data pipeline is only as trustworthy as the network it runs on.***


## Securing Network Layers in Modern Data Stacks

Historically, network security in data infrastructure was largely handled through perimeter defense. Today, however, modern data stacks are often decentralized across multi-cloud environments with data infrastructure, storage services, orchestration tools, and APIs communicate across network boundaries.

Understanding where security mechanisms live across the network layers fundamentally changes how we design robust and secure data architectures. Here are a few topics I'm particularly looking forward to:

* **BGP (Boarder Gateway Protocol) Security:** The moment data crosses network boundaries, you rely on inter-domain routing between Autonomous Systems (AS). Unsecured BGP puts data replication at risk of traffic hijacking.
* **IPsec & VPN Tunnels:** Encrypted tunnels for network to network communication (IPsec Tunnel Mode).
* **Network Segmentation:** Isolation via virtual networks or subnets allows to isolate ingestion and to restrict lateral movement after a breach.
* **(D)DoS Attacks & Defenses:** Availability is a core data SLA. Ingestion via e.g webhooks or streaming endpoints are targets for resource exhaustion attacks.
* **TLS & Mutual TLS (mTLS):** Standard TLS only authenticates the server. Moving to mTLS establishes identities of the peers. In distributed systems, mTLS guarantees that services don't just encrypt payloads, they continuously authenticate both ends of the connection.
* **DNS Security:** Poisoned DNS caches can misroute sensitive ETL jobs.

### Quick Recap: 7-Layer Network Model

Internet protocols are typically discussed along the OSI model (7 layers) which is an ISO standard or the more condensed TCP/IP model with 4 layers. These layers establish the necessary mental framework to pinpoint the exact **level of abstraction** for a given architectural challenge. Below the OSI model:

* Layer 7: Application Layer (HTTP, DNS)
* Layer 6: Presentation Layer (e.g. data encryption, TLS)
* Layer 5: Session Layer (session management)
* Layer 4: Transport Layer (TCP, UDP)
* Layer 3: Network Layer (IP, BGP)
* Layer 2: Data Link Layer (Ethernet, Switch)
* Layer 1: Physical Layer (Hardware, optical fiber, datacenter infrastructure)


## Data Platform Implications

As data pipelines scale, network context become just as critical as storage and compute ressources.

1. **Certificate lifecycle management** replaces static API keys for service-to-service identity.
2. **Traffic monitoring** becomes a key observability metric alongside query latency and throughput.
3. **Zero trust & network Encryption** for all data in transit.


I'll be sharing key architectural takeaways and lessons learned as the semester progresses. 
Stay tuned as the state changes :)

### Sources

* Module Description Network Security, https://vvz.ethz.ch/Vorlesungsverzeichnis/lerneinheit.view?semkez=2026W&ansicht=KATALOGDATEN&lerneinheitId=204555&lang=en (July 2026, online)
* OSI Model. https://en.wikipedia.org/wiki/OSI_model (July 2026)
* What is IPsec. https://www.cloudflare.com/learning/network-layer/what-is-ipsec/ (July 2026)
* BeyondCorp. Zero Trust Computer Security concepts. https://en.wikipedia.org/wiki/BeyondCorp (July 2026)
* DNS Spoofing. https://en.wikipedia.org/wiki/DNS_spoofing (July 2026)
