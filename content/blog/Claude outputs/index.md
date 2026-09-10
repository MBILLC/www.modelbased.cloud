---
title: "When Checking Becomes Cheap: Agentic AI and the New Economics of Model Credibility"
date: 2026-09-10
type: news
params:
  author: Hubertus Tummescheit
  summary: "After 25 years of modeling and simulation, the most thoroughly validated library I have built was developed entirely with AI agents. Part 1 of a series on how agentic AI changes the way we build and trust simulation models."
  tags: ["Modelica", "Agentic AI", "Verification and Validation", "Credible Simulation Process", "Predictive Maintenance", "Digital Twin"]
---

# When Checking Becomes Cheap: Agentic AI and the New Economics of Model Credibility

*This is Part 1 of a series on agentic AI in modeling and simulation.*

### A confession from a V&V veteran

I have been building simulation models for more than 25 years. Some of the models I developed during my PhD are still in use today for simulating nuclear power plants. In that world, verification and validation is not a checkbox. It is the job. I thought I knew what thorough looked like.

This year I built a new Modelica library in [Modelon Impact](https://www.modelon.com/modelon-impact/), and it is the most thoroughly validated piece of modeling work I have ever produced. It was developed entirely with AI agents.

That sentence would have sounded absurd to me not long ago. Here is why I now think it describes a real shift in how modeling and simulation work gets done.

### The library

The library covers rotating machinery: rotor dynamics, gearboxes and planetary gear stages. Its purpose is signal analysis. Rotating machines announce their failures long before they fail: a cracked tooth, a worn bearing or an unbalanced rotor each leave a characteristic fingerprint in vibration signals. The problem for predictive maintenance is data. Real failure data is rare, expensive and often confidential, because nobody wants to run a gearbox to destruction just to record it.

Physics-based models can fill that gap. A well-validated model generates synthetic signals, both healthy and faulty, under controlled conditions, which digital twins can then use to learn what failure looks like. The key word is *well-validated*. Synthetic data from a model you cannot trust is worse than no data at all.

### What changed: rigor, not just speed

Most of the conversation about AI in engineering is about speed. Speed was real here too, but it is not the interesting part.

The interesting part is that my validation became more thorough.

Every modeler knows the pattern. You think of a check: does energy balance hold, do the gear mesh frequencies land where theory says they should, does the model behave correctly in the limiting cases? Each check costs time to set up, run and interpret. So you prioritize. Some checks get done carefully, some get done quickly, and some never get done. Validation has always been bounded by the modeler's hours.

With agentic AI, that bound moves. I can send an agent to check anything that comes to mind, and it does the setup, the runs and the first-pass interpretation. My hours go into deciding *what* should be checked and judging the results, not into the mechanics.

### Expertise as rules: skills

The piece that makes this work is what I call skills: explicit, written rules that the agent follows. Over the course of this work I condensed a good part of my 25 years of modeling experience into skills for equation-based modeling and for verification and validation.

A skill does not get tired at the end of the day. It does not skip the boring limiting case because the deadline is close. It applies the same standard to the fiftieth model as to the first. In effect, it turns tacit expertise, the kind that usually lives only in a senior engineer's head, into something that is applied consistently and can be reviewed.

### The economics of credibility

This matters beyond my own library. In parallel, I am working on a future standard for archiving behavioral models in the aerospace industry (see my [LOTAR P520 series](/blog/lotar-520-simulation-models-are-evidence/)). It builds on the [Credible Simulation Process](https://setlevel.de/en/results/credible-simulation-process-framework) developed jointly by [prostep ivip](https://www.prostep.org/en/projects/smart-systems-engineering-smartse-gb) and PDES, Inc., the European and US industry organizations, and draws on NASA-STD-7009 and its handbook as well as the ASME VVUQ terminology.

These frameworks are an excellent foundation. The Credible Simulation Process and the Credible Modeling Process describe what it takes for a simulation result to deserve trust. But following them fully is a substantial amount of work, and in practice that effort is often where good intentions stall.

Agentic AI changes that equation. When the cost of checking drops, a process that used to be aspirational becomes affordable. Combining the process knowledge of prostep ivip, PDES and NASA with long practical experience in Modelica, I have been able to follow a much more rigorous path for developing and testing models than I could have justified before.

### The question you are probably asking

If you have read this far, you likely have an objection, and it is a good one:

**If an AI built the model, and an AI checked the model, why should anyone trust it?**

It is the right question. My answer is not "because the AI said so," and it is not "because I looked at it." It rests on two legs.

The first is **process**: a clear definition of what evidence a model must carry before it can be called credible for a given purpose, and who (or what) gets to make that call. The Credible Simulation Process gives a strong starting point, but agentic development raises new questions about roles, reviews and independence that the process has to answer.

The second is **tooling**: the machinery that makes producing, recording and checking that evidence routine instead of heroic, so that the evidence travels with the model, from requirements through to the archive, and anyone can inspect it later.

I am building both right now, and neither is finished. That is where this series goes next. In the coming parts I will open the hood on how the library was built and validated, what the skills actually contain, and what the process and the toolchain behind it look like as they mature.

In the meantime, I would like to hear from you. How are you handling verification and validation as AI enters your modeling work? What would it take for *you* to trust an AI-built model?

For more info, please fill in the [contact form](/Company/) or {{< appointment >}}
