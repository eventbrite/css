Accessibility
=============

## Table of Contents

1. [Overview](#overview)
1. [Tools](#tools)
1. [How To Test](#how-to-test)
1. [Checklist: What to Look For](#Checklist-What-to-Look-For)

# Overview

Accessibility compliance is important beacause it allows *all* people to use our website. It is also legally obligated in some countries - see [Wikipedia about WCAG] and [ADA 2010 Standards]. We follow (Web Content Accessibility Guidelines) [WCAG 2.0 AA compliance].

Below are presentations about the benefits of accessbility and general accessbility guidelines by Alli:

-   [Consumer Accessibility Benefit Presentation] (Q1 2016)
-   [How to be Accessible Slides]

# Tools

-   [WCAG 2.0 AA Checklist][WCAG 2.0 AA compliance]
-   [Tota11y Plugin]
-   [WAVE Chrome Extension]
-   [SSA Standard Keyboard Shortcuts]

The [Web Content Accessbiility Guidelines] is developed by World Wide Web Consortium (W3C). Tota11y is now installed on all EVB Dev and EVBQA pages (thanks Amira!) for testing. Download WAVE at the link above for use on Chrome.

# How To Test

### Validators

-   Install WAVE and/or open Tota11y (installed on Dev and QA)
-   Open one of the validators (Tota11y or WAVE)
-   See the Checklist below for more details

### Tab Through

-   Tab through the page using only a keyboard.
    -   Can you do all the interactions you want?
    -   Try some of the SSA keyboard shortcuts from above.

### Automation Tests

-   Add accessibility checks to automation tests by calling:

``` sourceCode
Accessibility(self.driver).full_accessibility_audit()
```

### VoiceOver

VoiceOver is a screenreader built into Mac computers. Check out this [VoiceOver Tutorial]

> header
> “keyboard shortcut”, “action”
>
> widths
> 20, 20
>
> “Command-F5”, “On/Off” “Ctrl”, “Pause/Unpause” “Ctrl + Option + A”, “Start Reading” “Ctrl + Option + U”, “View page navigation” “Ctrl + Option + U + arrows”, “Change navigation type” “Ctrl + Option + arrows”, “Read previous/next”

-   Do your headings make sense?
-   Do your your icons get read?
-   Can you find everything you would want to?

# Checklist: What to Look For

> **warning**
>
> This is not complete. For a full overview, read the [WCAG 2.0 AA guidelines][WCAG 2.0 AA compliance].

### Images

All `<img>` tag

  [Wikipedia about WCAG]: https://en.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines#Legal_obligations
  [ADA 2010 Standards]: http://www.ada.gov/2010ADAstandards_index.htm
  [WCAG 2.0 AA compliance]: https://www.w3.org/WAI/WCAG20/quickref/?currentsidebar=%23col_customize&levels=aaa
  [Consumer Accessibility Benefit Presentation]: https://docs.google.com/a/eventbrite.com/presentation/d/1tfRxOJ1N6MAWLo6Mey2TSqFvpD5d1sOKm6ssYJNE5tA/edit?usp=sharing
  [How to be Accessible Slides]: http://slides.com/alacker/how-to-accessible#/
  [Tota11y Plugin]: http://khan.github.io/tota11y/
  [WAVE Chrome Extension]: http://wave.webaim.org/extension/
  [SSA Standard Keyboard Shortcuts]: https://www.ssa.gov/accessibility/keyboard_nav.html
  [Web Content Accessbiility Guidelines]: https://www.w3.org/WAI/intro/wcag
  [VoiceOver Tutorial]: http://webaim.org/articles/voiceover

