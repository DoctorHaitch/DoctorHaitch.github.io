---
author: Kris Hollingsworth
title: "Website Accessibility Tools"
subtitle: false
date: 2026-06-24
description: "Collection of free, effective WCAG accessibility tools."
excerpt: "With the looming federal mandate for digital document accessibility for educators, this post collects a number of tools available for checking your web-based materials for compliance. Automated checkers are a great start to ensuring document compliance, but some of the subtle issues are also discussed which I uncovered while designing this website."
mathjax: true
tags: ["accessibility", "web-dev", "visual design", "tools"]
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
- Implement navigation with blog tags.

While the aesthetic choices were my own, the WCAG compliance could not have occurred without numerous tools. I've taken a bit of time to document the ones I found most useful here.

### tl;dr Summary

- Don't rely on autmated checkers for achieving real WCAG 2.2 AA accessibility, but they can be useful in finding some issues and forcing you to think about better design.
- Several good browser extension plug-ins (and the order in which I would try and use them)
  - [Axe DevTools extension](https://www.deque.com/axe/devtools/extension/)
  - [SiteImprove extension](https://www.siteimprove.com/why-siteimprove/integrations/browser-extensions/)
  - [WAVE](https://wave.webaim.org/) (I would recommend both extension and web-tool)
- Use semantic tokens for colors and repeating elements/styles. This let's you explicitly define them on multiple elements, which is often helpful in having the automated checkers sign-off on them as they'll default colors to white and black when they can't resolve them, resulting in many false-positives regarding contrast ratios.
- Some warnings can be ignored. I'd be particularly cautious of web-tools which want you to buy their product to "fix" the accessibility problems, often I was unable to get some of their "non-compliance" issues to resolve even when every other automated checker would give a pass. Some also appear to misinterpret some of the WCAG 2.2 AA standards. This is why I would recommend using the checkers in order, as Axe appears the most permissive, so if it fails there, it will fail every checker and generally appears to catch "real" issues. SiteImprove catches many "technically correct" issues to meet the 2.2 AA specifications, but often these can be achieved with minor changes that don't impact real aesthetic choices. Wave is a good sanity checker that also let's you see element order at a glance to make sure nothing looks out of place for keyboard/screen-reader navigation. These three provide an excellent overall toolkit for making materials AA compliant!
- Keep checking. Every time you change something, it might have unintentional interactions elsewhere.


### Axe DevTools Browser Extension

The [Axe DevTools extension](https://www.deque.com/axe/devtools/extension/) adds an additional page-scan feature to the web-developer tools in your browser of choice (provider that's firefox, chrome, or edge). This allowed for instant scanning and rescanning while locally testing my Jekyll site. It also gave excellent remediation information about exactly which WCAG issue was present, providing contrast ratios from computed values (incredibly useful as my cascades grew more complicated and targetted), and generally was much more useful than external automated page scanners.

This is very convenient as it directly adds a tab into the DevTools you are likely already using to monitor computed styles. Many of the errors I encountered while reaching WCAG compliance was due to accidentally changing or overriding styles between similar components. My general approach to writing my CSS improved throughout the project as a result.

### SiteImprove Browser Extension

Much stricter than Axe DevTools, the [SiteImprove extension](https://www.siteimprove.com/why-siteimprove/integrations/browser-extensions/) gives another resource for checking full page compliance directly in your browser. This one also triggers numerous false-negatives if using "fancy" CSS designs, but once again, balancing the aesthetic with guarenteed WCAG AAA compliance leads to an overall better design. I'd recommend solving all the problems identified by Axe DevTools first, and then moving on to the excruciating process of "technically correct" with SiteImprove afterwards.

### Web Accessibility Evaluation Tools

[WAVE](https://wave.webaim.org/)
Let's you check an url (with nice overlays of the navigation elements for screen-readers displayed as overlays!) as well as a browser extension I haven't tried out yet.

Provided by WebAIM at Utah State University.

### False Positives

Some false positives were benign, for example many errors came from a recent upgrade from MathJax 3 to MathJax 4, which adds the `aria-braillelabel` and `aria-brailleroledescription` tags automatically to any mathematical notation displayed on this site. As a modern feature, not all validators account for these tags yet, even though they are [valid aria tags](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-braillelabel).

Other false positives regularly occurred due to use of gradiants and overlays that automated validators could not properly compute. In general, either some "invisible" changes to how the cascades were written (changing which layer a color/background was defined on, most commonly) allowed validators to correctly review and fix the information. This was often the most frustrating automated error, since it could often be resolved without really changing anything about the aesthetic choices, instead just changing the way cascaded were computed by moving or even repeating definitions that should be inherited. This forced my to work hard to remove any hard-coded color choices though, and instead use semantic tokens for color choices so tweaking styles became unified with much less whack-a-mole of dealing with small outliers.

One useful work-around was to create a "resolved background token" to replace gradients to check specific elements for sufficient contrast in these cases. I usually took a screen-shot, used a color-picker to extract the actual lightest/darkest colors from the subtle gradiants, and set each temporarily to the element's background to ensure it had sufficient contrast. Then I could remove the hard-edges from that hard-coded background and return to my gradiants, even if the automated tools couldn't resolve them.

I also had \\(\mathbb R^{n^2}\\) in a title of one of my papers. If you check this page, you'll see that the corresponding notation fails the automated accessibility check for most tools. The double super-script creates errors in "minimum font-size" for AA compliance, but can be safely ignored. While getting the "green check-mark" on your LMS or accessibility tool makes admin happy and throws a little dopamine hit your way (just like we want our students striving for those in their online homeworks, etc), we've all seen when they over-prioritize the "check-mark/got-it-done" attitude, and not the learning or concepts that were supposed to be reflected by the achievement. Similarly here WCAG doesn’t require every glyph to be at least 9px. Math content falls under `specialized notation where proportional scaling is expected`. What really matters is that
- The content is still understandable
- It can be zoomed/scaled without breaking
- It’s not critical UI text (buttons, labels, nav, etc.)

