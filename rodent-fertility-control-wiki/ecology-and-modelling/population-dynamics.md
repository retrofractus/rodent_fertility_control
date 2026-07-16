---
title: Population dynamics of fertility reduction
status: draft
last_updated: 2026-07-16
tags: [ecology, modelling, demography, efficacy]
---

# Population dynamics of fertility reduction

> **Summary.** Whether fertility control *works* is ultimately a population-dynamics
> question, not a pharmacology one. The consistent finding from modelling and field
> demography is that fertility reduction suppresses population growth **only when it
> is sustained over multiple generations and reaches a large fraction of breeders**;
> **episodic or partial application largely fails** because rodents' high
> reproductive rate and compensatory responses erase the effect [Croft2023;
> Massawe2022; JacobLinnert2022]. (High confidence in this qualitative conclusion.)

## Why rodents are a hard target

Pest rodents combine traits that blunt fertility control:

- **High intrinsic growth rate** — early maturity, short gestation, large/frequent
  litters. A few untreated breeders can rebuild a population quickly.
- **Density-dependent compensation** — when density falls, survival and per-capita
  reproduction of the remainder can rise, partly offsetting the intervention (the
  same mechanism that limits lethal control).
- **Immigration** — open populations are refilled from surrounding source areas,
  diluting local treatment.

## What the models and demography show

- **Timing within the life cycle matters.** Fertility reduction applied *early* in
  females' reproductive lives is far more effective at limiting growth than the same
  reduction applied later, in modelled brown rat (*Rattus norvegicus*) and field
  vole (*Microtus agrestis*) populations [Croft2023].
- **Sustained vs. episodic.** Fertility reduction curbs population size **only when
  maintained across multiple generations**; one-off or intermittent application is
  ineffective [Croft2023]. This is the single most important operational takeaway.
- **Fertility vs. mortality control.** Field demography of the multimammate mouse
  (*Mastomys natalensis*) in maize systems has been used to compare fertility-based
  and mortality-based control on the same populations, informing which lever moves
  abundance below damage thresholds [Massawe2022].
- **Coverage threshold.** There is generally a **minimum proportion of the breeding
  population** that must be rendered infertile per unit time to hold growth ≤ 0;
  below that threshold the population still grows. The exact threshold is
  species- and system-specific and is what mathematical models are used to
  estimate.

## A simple mental model

Think of the finite growth rate λ. Lethal control lowers λ by raising mortality;
fertility control lowers λ by cutting recruitment. Because recruitment is
*renewed every breeding cycle*, you must keep suppressing it every cycle — hence
the sustained-application requirement. A knockdown you stop maintaining relaxes
straight back toward λ > 1.

> A small stage-structured (Leslie/Lefkovitch matrix) simulation is a good next
> addition to this page — it makes the coverage threshold and the timing effect
> concrete. This fits a Python/`numpy` workflow well; a worked notebook could live
> alongside this file.

## Framework for evaluating a candidate agent

Massei et al. propose running assessments **iteratively and in parallel**
[Massei2024]:

1. Laboratory / captive efficacy and welfare.
2. Simulation of contraceptive **delivery** (uptake, coverage).
3. **Mathematical models** predicting population outcomes under delivery scenarios.
4. Large-scale, **replicated** field trials.

The recurring gap is step 4: landscape-scale, replicated demonstration of efficacy
is still largely missing for rodents [JacobLinnert2022].

## Open questions
- What coverage fraction and re-dosing interval are needed for common urban and
  agricultural pest species?
- How much does immigration erode local treatment, and over what spatial scale must
  treatment be applied to overcome it?
- Combined fertility + lethal strategies — is there a synergy that beats either
  alone?

## See also
- [Introduction](../overview/introduction.md)
- [ContraPest (VCD + triptolide)](../agents/contrapest-vcd-triptolide.md)
- [Field trials](../evidence/field-trials.md)

## References
- [Croft2023], [Massawe2022], [Massei2024], [JacobLinnert2022] — see
  [bibliography](../references/bibliography.md).
