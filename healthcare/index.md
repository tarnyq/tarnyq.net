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
Drug dosing and fluid resuscitation are complex, particularly in pediatric settings.
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
These systems have made improved outcomes through timely
sepsis detection and early prediction.

Our system augments this with treatment advice. This advice is:
a) patient-specific---it takes into account
the patient's medical history and data from monitors, and
b) evidence-based---it is derived from the industry-standard and peer-reviewed
[Surviving Sepsis][surviving-sepsis] guideline.
This keeps care consistent with best practices
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

As shown in [Figure 1](#fig-monitoring), the system prompts the clinician
to enter any pre-existing conditions that affect sepsis risk, such as
cancer, immunosuppression, or congenital heart disease. It then evaluates
real-time data from the bedside monitor and EHR to detect sepsis onset as
defined by the guideline. The system alerts the clinician the moment criteria are
met.

The system presents the relevant patient information on screen, grouped
into buckets of linked parameters. Together, these tell the clinician, at a
glance, whether sepsis onset has occurred. When every bucket contains an abnormal
value, sepsis is flagged. This minimizes the time between sepsis
onset and its detection by the clinical staff — ensuring treatment can
begin without delay.

<figure id="fig-monitoring">
  <video
      src="media/continuous-monitoring.webm"
      autoplay=false
      muted
      loop=false
      playsinline
      controls=true
      >
  </video>
  <figcaption>Figure 1: Continuous Sepsis Monitoring</figcaption>
</figure>

Once sepsis is flagged, the system highlights a
list of time-bound steps for guideline-compliant treatment. As shown
in [Figure 2](#fig-workflows), the attending clinician is expected to check
off each item while directing nursing staff to perform the associated
action. This ensures critical tasks, such as administering high-flow oxygen
and establishing IV/IO access, are completed on time. Two of these, fluid
resuscitation and antibiotic administration, are complex and time-critical
interventions. Each launches a patient-tailored
sub-workflow when the clinician checks it off.

When starting fluid resuscitation, the system accounts for the risk of
fluid overload. It then recommends a guideline-prescribed fluid at a dose
tailored to the patient's weight and condition. Similarly, when starting
antibiotics, the system factors in the patient's history along with
hospital- and area-specific pathogens. It then  recommends an
antibiotic combination that is
broad enough to cover likely pathogens but no broader than necessary.

<figure id="fig-workflows">
  <video
      src="media/fluid+antibiotic-workflows.webm"
      autoplay=false
      muted
      loop=false
      playsinline
      controls=true
      >
  </video>
  <figcaption>Figure 2: Time-bound Treatment Workflows</figcaption>
</figure>

Sepsis treatment is rarely a single-shot intervention. It requires the
clinical staff to periodically assess the patient's response and administer
fluids and inotropes accordingly. As shown in [Figure 3](#fig-reminders),
our system delivers *timely* reminders to support these reassessments. The
reminders contain relevant patient information, such as vital signs graphs,
annotated with prior fluid boluses and inotropic doses. This gives the
clinician a holistic view of the patient's state and treatment progress,
helping them direct care effectively.

Based on the clinician's assessment of patient progress and treatment
history, the system suggests next steps. This keeps multi-step
interventions, such as repeated fluid boluses and inotrope infusions, on
schedule and at optimal dosages.

<figure id="fig-reminders">
  <video src="media/fluid-reminder-workflow.webm"
      autoplay=false
      muted
      loop=false
      playsinline
      controls=true
      >
  </video>
  <figcaption>Figure 3: Reminders with Relevant Information</figcaption>
</figure>

Once initial fluid boluses are administered, our system continuously
evaluates patient parameters for signs of cardiac distress indicative of
septic shock, as shown in [Figure 4](#fig-shock).
If detected, the system first evaluates
the type of shock — cold, warm, normotensive, or indistinguishable. It then
surfaces appropriate shock-related patient parameters to improve the
clinician's awareness. Finally, it recommends an appropriate inotrope
for infusion to address the shock.

Our system reconciles competing recommendations.
The sepsis guideline recommends starting fluids as soon as possible
after sepsis detection. But fluid boluses can decrease cardiac function,
particularly in pediatric cases. If our system detects shock, it adjusts
the recommended fluid dosage to account for reduced cardiac function.
This ensures treatment remains consistent across interventions.

<figure id="fig-shock">
  <video src="media/septic-shock.webm"
      autoplay=false
      muted
      loop=false
      playsinline
      controls=true
      >
  </video>
  <figcaption>Figure 4: Septic Shock Monitoring and Treatment</figcaption>
</figure>

Clinicians are already over-burdened with ever-increasing patient loads.
Our system acts as a smart assistant, presenting the right information and
reminders at appropriate times. The clinician no longer needs to memorize
specific drug dosages and combinations, or track how the guideline evolves
as new evidence emerges. The result is more effective decisions, fewer
errors, and treatment that stays *always timely* and compliant with the
*latest guidelines*.

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
