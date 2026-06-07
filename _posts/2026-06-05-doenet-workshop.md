---
layout: main
title: "Doenet Workshop 2026 Show and Tell"
author: Kris Hollingsworth
date: 2026-06-05
subtitle: ""
description: "Demonstration of tools from the Doenet 2026 Community Workshop."
excerpt: "Overview of my Show and Tell from the end of the Doenet 2026 Community Workshop and some general notes about the workshop. Includes a quick demonstration of accessibility and Doenet tools, including a Python CVD Simulator, the Doenet Spreadsheet component as a work-around for advanced mathematical formulas, and a scaffolded proof for students to complete which reformats and constructs itself as students provide each step. They can transcribe it to have a neat, final version in their notes."

profile: false
---

# [Doenet](https://beta.doenet.org) Workshop 2026 Show and Tell


> Fences are a trick. Fences don't keep people out, they trick people into keeping themselves out.
> 
>   > -- Joey Comeau, Author
>   > {:data-type="author"}
{: data-type="fancy-quote"}

## [`accessible-math`](https://github.com/DoctorHaitch/accessible-math) Resources Github Repo

I quickly shared a few tools content authors could use for creating more accessible math documents:
- [LaTeX templates](https://github.com/DoctorHaitch/accessible-math/tree/main/LaTeX) for TeXLive 2025+ and LuaLaTeX for creating PDF/UA Compliant documents.
- [A collection of accessible fonts](https://github.com/DoctorHaitch/accessible-math/tree/main/fonts) for math, text, and code environments.
- [A collection of colorblind-friendly palettes and a python script for generating palettes](https://github.com/DoctorHaitch/accessible-math/tree/main/color-palettes) with color-vision deficiency simulations of them.

All of these are part of my broader repository where I am regularly updating materials for creating [accessible math documents](https://github.com/DoctorHaitch/accessible-math)

## Github Jekyll Website

With the help of [Dr. Steven Clontz](https://clontz.org) during the "Introduction to Github" section, I was able to setup this Jekyll Github site. It's a work in progress as I continue to update/construct the functioning stylesheet and backend integration to better maintain this site over time. Keep checking back to see continuing progress! I was able to setup this blog in a few hours using these tools. I'll continue working on it throughout the summer.

## Demonstration of Doenet's [Spreadsheet Component](https://docs.doenet.org/reference/spreadsheet)

After working with [Dr. Stephen Frezza](https://snas.franciscan.edu/faculty/frezza-dr-stephen/) on a semantic version of his [8-digit Base 16 Longhand Addition](https://beta.doenet.org/activityViewer/vRGa9Fya9XLg3CXvkmKb4e) Doenet activity, I remembered how I got all my Cryptography activities working 5 years ago teaching Math5248 at the University of Minnesota. As the component never came up during the workshop, I used the Show and Tell as an opportunity to share one of my [old activities on generalizing shift to affine ciphers](https://beta.doenet.org/activityViewer/qDDf1g9cMFz5VrzUikp3qt) as a means of demonstrating the functionality of this component.

```
<spreadsheet name="example">
  <row>
    <cell>Hello</cell>
    <cell>World</cell>
  </row>
  <row>
    <cell>=a1</cell>
    <cell>=a2</cell>
  </row>
  <row>
    <cell>=a1&" "&a2</cell> <!-- concatenate to "Hello World" -->
  </row>
</spreadsheet>
```

This would have made Dr. Frezza's component much easier to code, but it was an interesting challenge to do it using only native Doenet components. I'm sure one of us will rewrite the activity using this in the future, but I'm glad we got it working regardless.

## "Fill in the Blank" scaffolded proof.

I showed an example of my (in progress) pedagogical UI for my lecture notes going forward with a Doenet Activity integrated to construct the proof of the *integration by parts* formula in Calculus II. You can view the [updated version based on feedback from the workshop](/E02-C17-IntegrationByParts.html).

## Demonstration of Writing Answer Validations

I showed how the built-in tools in the Doenet editor's "Submitted Responses" box could be used to create more advanced answer validation and student feedback like the one demonstrated in the prior example. Right-clicking on the MathJax gives you the ability to see exactly what the parsed entry looks like so it can be used in answer validation. See the image below for an example.

![Image showing the location of the Submitted Responses tab in the Doenet editor. The right-click context menu is shown to find the TeX version of the response after being parsed by the parsers.](/imgs/2026-06-05-submittedResponses.png)

## Other Important Details

This workshop used an [AIM-style approach](https://aimath.org/workshops/about/) for fluidly generating working sessions. 

### Working Sessions I participated in

- Tuesday (both sessions): [Getting started with GitHub Collaboration](https://community.doenet.org/t/doenet-workshop-2026-day-2-working-groups/127)
  - We were able to all colloborate on a project, learning from both the owner and contributor views of forking, changing, and submitting a pull request on a project. This was a great, hands-on session for everyone who participated!
- Wednesday Morning: [Doenet Software Development](https://community.doenet.org/t/doenet-workshop-2026-day-3-working-groups/133)
- Wednesday Afternoon: [Accessibility Strategies for Authors](https://community.doenet.org/t/doenet-workshop-2026-day-3-working-groups/133)
  - I'll try and post a follow-up on this. We discussed several challenging situations and came up with general strategies for addressing them in creating accessible course materials with dynamic, interactive elements.
- Thursday Morning: [Value Proposition of Doenet within the Greater Ecosystem](https://community.doenet.org/t/overview-of-the-doenet-cinematic-universe-dcu/138/2)
  - This small session with [Dr. Steven Clontz](https://clontz.org) and [Dr. Lilly Webster](https://earlham.edu/faculty-staff/lilly-webster/) discussed and inventoried many of the current tools available for anyone interested in tools for developing, designing, or using accessible course material in the Open Source ecosystem. We separated them into certain processing layers, and I hope to write a follow-up post on the tools organized in a few different ways in the future.
- Thursday Afternoon: [Misc. Coworking Group](https://community.doenet.org/t/doenet-workshop-day-4-working-groups/137)

### Other Important Ideas/Collaborations

- I had several great conversations with [Dr. Christina Safranski](https://snas.franciscan.edu/faculty/safranski-christina/) about teaching Calculus. Dr. Safranski is one of the contributing authors for the OER Calculus Textbook [Active Calculus](https://activecalculus.org/), which uses Doenet for their "preview" activities and are slowly increasing the incorporation with exercises.
- I spent several hours working with [Oscar Levin, Ph.D.](https://math.oscarlevin.com/) discussing the design of PreTeXt, and possible synergies in the work on my own pedagogical UI with both PreTeXt and DoenetML.
- [Dr. Anurag Katyal](https://www.pitimespi.com/) showed of several interesting Algebraic Geometry activities developed in Doenet. We plan to collaborate on turning several of them into outreach activities appropriate for Math Circles or other community games in the near future, and I hope to develop a future MathPath session around them.

Thanks to the
- The Doenet crew for organizing a great workshop,
- the NSF for providing travel funding,
- and all the great participants this week.

It was great meeting many new colleagues and catching up with old friends this week. Thanks for the numerous interesting problems, intriguing ideas, and camaraderie you all brought to the workshop. I look forward to many future collaborations!