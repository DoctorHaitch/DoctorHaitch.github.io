---
author: Kris Hollingsworth
title: "Website Accessibility Tools"
subtitle: false
date: 2026-06-24
description: "Collection of free, effective WCAG accessibility tools."
excerpt: "With the looming federal mandate for digital document accessibility for educators, this post collects a number of tools available for checking your web-based materials for compliance. Automated checkers are a great start to ensuring document compliance, but some of the subtle issues are also discussed which I uncovered while designing this website."
---

## Website Accessibility Tools

<blockquote data-type="fancy-quote" aria-describedby="main-heading">
  <span class="quote-mark" aria-hidden="true">“</span>
  <p>Inclusion is not a strategy to help people fit into the systems and structures which exist in our societies. It is about transforming those systems and structures to make it better for everyone.</p>
  <p>—
    <cite>Diane Richler</cite>,
    former chair of the International Disability Alliance
  </p>
</blockquote>


There has been a constant tension in designing this site between [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/) compliance and visual aesthetics. In the end, I think the quote from Diane Richler is accurate, the overall aesthetic was forced to improve in finding creative ways to solve WCAG compliance issues. Automated checkers or AI might recommend one path for resolution, but ultimately small, intentional decisions arose at each step as often these would meet the *compliance* concern, but fail to meet my own personal *aesthetic* concerns. This forced me to develop additional tools, more flexible cascades, and more refined stylistic choices to achieve both goals. There are still several things I need to clean-up from an *aesthetic* and *semantic* view-point:
- Extend and complete the icon system for presentations and lists with well-defined semantic meaning between
  - talks
  - posters
  - organizing and facilitation
- Document color palettes and ensure no more hard-coded colors exist in the cascades.
- Clean up and remove depracated or extraneous code.

While the aesthetic choices were my own, the WCAG compliance could not have occurred without numerous tools. I've taken a bit of time to document the ones I found most useful here.

### Axe DevTools Browser Extension

The [Axe DevTools extension](https://www.deque.com/axe/devtools/extension/) adds an additional page-scan feature to the web-developer tools in your browser of choice (provider that's firefox, chrome, or edge). This allowed for instant scanning and rescanning while locally testing my Jekyll site. It also gave excellent remediation information about exactly which WCAG issue was present, providing contrast ratios from computed values (incredibly useful as my cascades grew more complicated and targetted), and generally was much more useful than external automated page scanners.

This is very convenient as it directly adds a tab into the DevTools you are likely already using to monitor computed styles. Many of the errors I encountered while reaching WCAG compliance was due to accidentally changing or overriding styles between similar components. My general approach to writing my CSS improved throughout the project as a result.

### SiteImprove Browser Extension

Much stricter than Axe DevTools, the [SiteImprove Browser Extension](https://www.siteimprove.com/why-siteimprove/integrations/browser-extensions/) gives another resource for checking full page compliance directly in your browser. This one also triggers numerous false-negatives if using "fancy" CSS designs, but once again, balancing the aesthetic with guarenteed WCAG AAA compliance leads to an overall better design. I'd recommend solving all the problems identified by Axe DevTools first, and then moving on to the excruciating process of "technically correct" with SiteImprove afterwards.