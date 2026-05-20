---
title: Healthcare
---

Addressing Sepsis
-----------------

Sepsis remains one of the leading causes of mortality in Intensive Care
Units (ICUs) across the world. Characterized by a dysregulated immune
response, sepsis kills in hours, and remains an
unaddressed problem in modern ICUs.
We're building clinical support software for timely sepsis detection,
enabling clinicians to follow *evidence-based guidelines* exactly.


A System For Managing Pediatric Sepsis, Not Just Detecting It
-------------------------------------------------------------

Building decision support for sepsis, particularly in pediatric settings,
is *challenging*. Drug dosing and
fluid resuscitation is age- and weight-sensitive, and mortality climbs
sharply (roughly 8%) with each passing hour.

Thus, current sepsis support systems are either rigid EHR rule alerts, or
ML/AI-based statistical analyzers that *warn* of sepsis onset, and leave
the critical job of administering *guideline-conformant* care solely to the
attending clinician. This often leads to alert-fatigue, and clinicians are
left with systems they don't trust.


Our Approach: Holistic, Trustworthy Decision Support
----------------------------------------------------

We place *software correctness* and *clinician trust* at the core of our
approach. In particular:

 1. We encode medical knowledge using a *clinician-friendly*
 Domain-Specific Language (DSL) that allows clinicians to *validate* its
 accuracy. The upshot: clinicians can validate and fine-tune every nuance
 of the system's behavior.
 2. We use *formal methods* to *mathematically prove* correctness and
    reliability, ensuring core functionality is maintained at all times.

|                                      | EHR rule alerts | ML/AI sepsis tools | Tarnyq                        |
|--------------------------------------|-----------------|--------------------|-------------------------------|
| Guideline-conformant by construction | partial         | no (statistical)   | **yes**                       |
| Clinician can audit medical logic    | yes (but rigid) | no                 | **yes**                       |
| Pediatric-support                    | no              | rarely             | **yes**                       |
| Support Beyond Onset Detection       | limited         | no                 | **comprehensive**             |
| Formally-verified Correctness        | no              | no                 | **yes - proven reactivity**   |

Our System In Action
--------------------

Built as part of a research collaboration between University of Illinois
Urbana-Champaign and OSF Children's Hospital of Illinois, Peoria, our
demonstrably safe system provides comprehensive decision support.


Related Publications
--------------------

*   [MediK: Towards Safe Guideline-based Clinical Decision Support](pubs/MediK-FMCAD-23.pdf)
    Published in [FMCAD 2023](https://ieeexplore.ieee.org/abstract/document/10329373)
