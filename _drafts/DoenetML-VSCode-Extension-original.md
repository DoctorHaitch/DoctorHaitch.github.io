---
author: Kris Hollingsworth
title: "Review of DoenetML VSCode Extension (ORIGINAL)"
subtitle: false
date: 2026-06-26
description: ""
excerpt: "A review and first impressions of the VSCode DoenetML Extension, an excellent addition to both DoenetML and VSCode workflows for creating accessible mathematical content for students and public outreach."
mathjax: true
tags: ["doenet", "accessibility", "tools"]
---

## DoenetML VSCode Extension

<blockquote data-type="fancy-quote" aria-describedby="main-heading">
  <span class="quote-mark" aria-hidden="true">“</span>
  <p>Each new user of a new system uncovers a new class of bugs.</p>
  <br/>
  <p>—
    <cite>Brian Kernighan</cite>,
    co-author of the first book on C programming language.
  </p>
</blockquote>

If you haven't checked it out already, I highly recommend looking up [Distributed Open Education Network (Doenet)](https://beta.doenet.org), currently in Beta, for creating accessible, interactive content and activities for students. While it can be used for any subject, the initial development has focused on mathematics as it is being developed by mathematicians under an NSF grant at the University of Minnesota, led by Duane Nykamp.

Recently, a [VSCode Extension for DoenetML](https://marketplace.visualstudio.com/items?itemName=doenet.doenet-vscode-extension) became available. I've been aware of it for a few weeks, but with getting things ready for the Doenet Community Workshop a few weeks ago, finding time to sit down and play with it was difficult. Well, I finally got around to it as part of my final push to update my Calculus II notes and activities for the Fall 2026 semester, it came at the perfect time as I had a large library of activities I already maintain in VSCode and GitHub to be remotely fetched by my [obsidian-doenet Plugin](https://github.com/DoctorHaitch/obsidian-doenet) into my notes. This gave me a good number of files to quickly test the plug-in on. You can see a few samples on my [teaching](/teaching) page.

Full disclosure, I have been on and off involved with the Doenet development team since I was a postdoc at University of Minnesota from 2020-2022, I serve on the Advisory Board for the ongoing language development, and I am one of the editors for it's currated activity collection.

> ### Conclusion/tl;dr
> 
> This is a great addition to the OER DoenetML Development ecosystem. Unfortunately if you adopt it now, you'll be getting a version with a great many bugs and frustrations built-in, although some of the feature set is quite useful. I'll be using it in a limited capacity for just a few tasks around my workflow (particularly minor edits to my course activities with code-completion and "Pretty Code" auto-formatting). It is also useful for local development, but I already have offline live-previewing of activities in my [obsidian-doenet Plugin](https://github.com/DoctorHaitch/obsidian-doenet/) for embedding DoenetML activities into markdown.
>
> So based on the current state of the plugin, I'd suggest that unless you want to be an early adopter to help identify and squash issues as a contribution to the project, I'd stick to developing through the web interface on [beta.doenet.org](https://beta.doenet.org). I'll probably use a mixture of the two, but due to the inconsistent error/problem identification between the two code linters, I'm going to stick with the web-interface for now and likely be opening a lot of GitHub issues as the VSCode linter throws errors at me.
>
> You can read the details below if you're interested in what specifically led me to these conclusions.
{: .tldr }

### The Pros

Immediately there are several nice features that become available for any `.doenet` file in your workspace once the extension is enabled.

#### Live Previewing

Useful, but this is already built in to [Doenet's online editor](https://beta.doenet.org) and my [obsidian-doenet plugin](https://github.com/doctorhaitch/obsidian-doenet), so it's a "nice" feature, but based on the cons noted below, I don't see VSCode becoming my primary editor. For very small activities (check your work boxes with short/simple answers) I'll just write them in my markdown directly, and for complicated activities I'll be using the web interface for initial development and debugging. I can see this useful for making some small editors to an activity already living locally/on github and checking that you didn't break it.

#### Syntax Highlighting and Autocompletion

Again, useful for quick edits and debugging. Appears to work well, similar to the web-interface, although autocompletion is likely the feature I spent the least time testing.

#### Dark Mode Support

This is a big one for developers. Currently the website **does not have any support for dark mode/themes**. This isn't explicitly listed in WCAG 2.2 AA standards, but supporting light and dark themes based on a user's system preferences is a key component of web accessibility and usability. The irony is of course even websites devoted to [best practices in Dark Mode](https://natebal.com/best-practices-for-dark-mode/) fail to meet the accessibility standards when making statements like "Ensuring Accessibility in Dark Mode

Accessibility isn’t optional; it’s integral to ethical web design. The Web Accessibility Checklist Guidelines (WCAG) mandate a minimum contrast ratio of 4.5:1 for normal text and 3:1 for large text." fail on several elements. So it's non-trivial by far that this plugin is striving to design a dark-mode UI for Doenet (something I have also done in my course notes, you can view my sample Calculus II course materials in both light and dark mode over on my [teaching page](/teaching), including the DoenetML activities UIs.) I do feel like we need to de-duplicate efforts in these veins, so hopefully whoever is doing this on the Doenet Dev team and I can touch base soon, possibly as part of the Accessibility Team on Doenet.

#### Pretty Code
To me, this is one of the best features, as I often make numerous minor edits and remixes of activities directly in VSCode. Note, this is available on the browser based editor as well, although I just discovered it by looking for it after discovering the feature in the VSCode extension. You can access this on the web from the vertical "3-dots" footer menu button at the bottom of the editor view.

![Screenshot showing the location of the footer-menu-button on the Doenet web interface.](/imgs/2026-06-26-FormatOML.png)

### The Cons

Most of the problems come from the fact that the VSCode Extension is still early in the development of the extension, and DoenetML itself is in beta and constantly changing. That said, here are a few frustrations I had on the first pass through.

#### Custom File Extensions

Supposedly there is already custom extension mapping supported by the plugin, but it does not appear to be working when I try and use the context menu to access it following the instructions in the Plugin Documentation. It's easy enough to fix this locally in VSCode though.

> ##### Workaround
> By default, the extension looks for `*.doenet` files to associate with DoenetML. However, (and this is a hill I will die on), I prefer the `*.oml` as my pattern, as the (little doughnut character)ML also maintains a three-character extension pattern that doesn't overlap with any common file pre-existing file extensions. You can register this in VSCode by adding
> ```
> "files.associations": {
>   "*.oml": "doenet"
> }
> ```
> to your `settings.json` file.

#### Many false positives for problems

The first is [syntax checking for custom `<module>` attributes](https://github.com/Doenet/DoenetML/issues/1375) creates false-positives. As one of the primary users of modules, I'm not surprised that this is one of the first things I noticed that hadn't already been reported. I tried several more complicated work-arounds, including trying to dig into the [DoenetML Schema](https://github.com/Doenet/DoenetML/blob/main/packages/static-assets/src/generated/doenet-schema.json) (which will eventually be the correct fix), or look into modifying the DoenetML Extension to allow for custom schema additions. I even tried to write a small VS-Code Extension to remove the extraneous warnings, but unfortunately it turns out VSCode doesn't allow you to remove Problems from another extension.

I was hopeful that the VSCode Extension [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) might succeed where I had failed. Alas, it does not, but it does provide some nice features so I'll be keeping this plugin (immediately useful, problems show up to the right on the same line now, for finding them much more easily.)

All that said, you can manually filter these out with `!module` to remove all error messages involving modules.

I also got additional errors on `<boolean>` tags which the editor on the DoenetML website did not flag. So either the VSCode editor is more strict (possible) or it isn't actually enforcing real constraints as implemented in DoenetML. It does appear likely that the VSCode extension is simply more strict towards best practices, even if they do not impact the output or functionality of the code. This might be useful, but it feels similar to getting my website up to WCAG 2.2 AA rules, the final items are often inconsiquential to the actual rendered output, functionality, or even accessibility concerns, and are falling at the level of pedantry for the sake of automated checkers which are insufficiently implemented to the real standards. Obviously Doenet is a small team, so some level of technical debt is expected, but the mismatch between the extension and the online interface here is particularly striking in code linting.