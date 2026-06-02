---
title: Trustworthy Decision Support Systems
---

Clinical guidelines are comprehensive documents with proven efficacy.
The flip-side is that they are complicated.
They must take into account pediatric and geriatric care,
co-morbidities, drug-drug interactions.
They also evolve frequently as new evidence emerges.
This makes following them as written difficult,
especially in high-stress settings.

Can this be made easier?
As a case study, we decided to take a look at
the [Surviving Sepsis][surviving-sepsis] guideline.
Sepsis remains one of the leading causes of mortality in
ICUs across the world.
Sepsis kills in hours, and so a timely response can lead to lives saved.
Drug dosing and fluid resuscitation is complex, particularly in pediatric settings.
It is age- and weight-sensitive,
and mortality climbs sharply with each passing hour.

Our decision support system interprets these guidelines,
taking into account a patient's medical history and condition,
and presents compliant advice.
This enables clinicians to follow the guidelines exactly
with a reduced cognitive load.


Our Approach
------------

Current sepsis support systems are either rigid EHR rule alerts,
or ML/AI-based statistical analyzers for warning of sepsis onset.
These systems have made progress towards improving outcomes by timely
sepsis detection and early prediction.

Our system augments this with treatment advice. This advice is:
a) patient-specific---it takes into account
the patient's medical history and data from monitors, and
b) evidence-based---it is derived from the industry-standard and peer-reviewed
[Surviving Sepsis][surviving-sepsis] guideline.
This enables care delivered to be consistent with best practices
while reducing the clinician's cognitive load.

At the same time, these guidelines are written in a language
that is both comprehensible and machine-interpretable.
This makes it easier for clinicians to inspect and
validate (and therefore trust) the system.
Compare this with an AI-based approach
which is opaque and may be prone to hallucinations.

You may read more about our system and methodology
in the [linked publications](#publications).

Current Progress
----------------

Our current system, built in collaboration with OSF Children's Hospital in
Peoria, Illinois, provides guidance through a tablet at the patient's
bedside. It fuses inputs from the attending clinician, the EHR, and patient
monitors to continuously evaluate the patient for onset of sepsis.

<video
    src="media/continuous-monitoring.webm"
    autoplay=false
    muted
    loop=false
    playsinline
    controls=true
    >
</video>

Once sepsis is detected, the system presents the clinician with
patient-specific advice to administer guideline-compliant treatment,
including time-critical workflows for fluid resuscitation and antibiotic
administration.

<video
    src="media/fluid+antibiotic-workflows.webm"
    autoplay=false
    muted
    loop=false
    playsinline
    controls=true
    >
</video>

Sepsis treatment also requires ongoing assessment as the patient responds.
Our system delivers *timely* reminders and presents the clinician with
patient data annotated with prior interventions such fluid boluses. This
augments the clinician's situation awareness with important
patient-specific data, and ensures treatment remains consistent with
guideline-prescribed timelines and dosages.

<video src="media/fluid-reminder-workflow.webm"
    autoplay=false
    muted
    loop=false
    playsinline
    controls=true
    >
</video>


> Consider adding more information+video on septic shock workflows.

---

<!--

Our next goals are to extend our system to care for cardiovascular and stroke care

https://cpr.heart.org/en/resuscitation-science/cpr-and-ecc-guidelines/algorithms



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

-->



Related Publications { #publications }
--------------------

*   [MediK: Towards Safe Guideline-based Clinical Decision Support](pubs/MediK-FMCAD-23.pdf)  
    Published in [FMCAD 2023](https://ieeexplore.ieee.org/abstract/document/10329373)
*   [Towards Modular and Formally-Verifiable Software Architecture for Clinical Guidance Systems](xxxxx)  
    Published in [SMC 2023]()
*   [A Semantics-First Approach to Safe Guidelines-Based Clinical Decision Support](pubs/Saxena-dissertation.pdf)  
    Published in [Ideals @  Illinois](https://www.ideals.illinois.edu/items/134278), 2024


[formal]: https://en.wikipedia.org/wiki/Formal_methods
[surviving-sepsis]: https://www.sccm.org/survivingsepsiscampaign
