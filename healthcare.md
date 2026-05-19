---
title: Healthcare
---

Our interests lie in building advanced clinical decision support software
with strong correctness guarantees. Our current focus is on systems for use
in Intensive Care, for time-critical conditions like sepsis and cardiac
arrest.

Our safety-first philosophy has two aspects:

1. Designing and implementing systems that can be rigorous analyzed for
   desired safety properties through *formal methods*.
2. Ensuring accuracy of medical knowledge in the system through use of
   *clinician-friendly* domain-specific languages, enabling clinicians to
   verify encoded knowledge matches their expectations.

Sepsis Support System
---------------------

Sepsis is a time-critical condition, and one of the leading causes of
mortality in modern ICUs. Our work on sepsis focuses on providing
clinicians in the ICU with a system that utilizes patient history, and
continuously monitors patient vitals to detect sepsis onset in a timely
manner. The system then supports the clinician with patient-specific
advice consistent with the latest best practice guidelines. Our work
particularly focuses on *pediatric cases*, where treatment workflows are
extremely sensitive to parameters such as the age, weight.

Related Publications
--------------------

*   [MediK: Towards Safe Guideline-based Clinical Decision Support](pubs/MediK-FMCAD-23.pdf)
    Published in [FMCAD 2023](https://ieeexplore.ieee.org/abstract/document/10329373)
