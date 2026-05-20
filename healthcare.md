---
title: Healthcare
---

Addressing Sepsis
-----------------

Sepsis remains one of the leading causes of mortality in
Intensive Care Units (ICUs) across the world.
Sepsis kills in hours, and so a timely response can lead to lives saved.
Drug dosing and fluid resuscitation is complex, particularly in pediatric settings.
It is age- and weight-sensitive, and mortality climbs sharply with each passing hour.

Our clinical support system for timely sepsis detection
is a [formal] machine interpretation
of the evidence-based [Surviving Sepsis] guideline,
and takes into account a patients medical history and condition.
This enables clinicians to follow the *guidelines* exactly with a reduced congnitive load.

[formal] : XXXX
[Surviving Sepsis] : XXXX


Our Approach
------------

Current sepsis support systems are either rigid EHR rule alerts,
or ML/AI-based statistical analyzers for warning of sepsis onset.
These systems have made progress towards improving outcomes by timely
sepsis detection and early prediction.

Our system augments this by going beyond detection and issuing treatment advice.
This advice is: a) patient-specific--it takes into account
the patient's medical history and data from monitors, and,
and b) evidence-based--it is based of tried and tested guidelines
issued by [Surviving Sepsis]. This enables care delivered to be
consistent with best practices while reducing the clinician's cognitive load.

We specify guidelines in a language that is both
clinician-friendly and machine-interpretable. This enables clinicians to directly
inspect and validate the medical knowledge powering the system, allowing a
level of trust unavailable from black-box AI approaches, which may hallucinate.
Beyond ensuring the correctness of encoded medical knowledge, we use *formal
methods* to mathematically prove that the system remains reactive for every
admissible input.

---

> Should we reframe the table below?

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
