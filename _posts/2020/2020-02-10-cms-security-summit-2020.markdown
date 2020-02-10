---
layout: post
title: "Web Platform Security @ CMS Security Summit 2020"
tags:
  - security
  - presentation

Teaser:
  "This is a quick summary of a presentation I gave last week at Google's second
   CMS Security Summit, held here in Munich. TL;DR: Injection attacks are bad,
   isolation is lacking, and I'm looking forward to more collaboration on both
   fronts."
---
Last Thursday, I had the opportunity to chat with folks in the CMS community about some client-side
web security topics that I find pretty relevant today. Preparing the talk was a bit of a strange
experience; I think I could have directly copied most of the slides from similar presentations I've
given years ago, and it's a little frustrating that they're _still_ so relevant. That said, this was
a good opportunity to discuss some new bits and pieces that are only now coming into focus after a
lot of design work and discussion.

I aimed to get a few messages across:

1.  My team is focused on two sets of web platform attacks: **script injection** continues to be
    both high risk and pervasive, and we're rapidly discovering the side-channeled consequences of
    insufficient isolation. These are topics I'd love web developers to be paying attention to as
    well.

2.  Injection attacks can be reasonably mitigated today with a reasonably
    [strict Content Security Policy][strict-csp], and I'm hopeful about our ability to more robustly
    address the underlying vulnerability via new tools like [Trusted Types][tt-intro]. I would love
    to see web developers deploy the former, and start playing around with the latter.

3.  Browsers and developers can cooperate to attenuate side-channel attacks by shifting away from
    the web's embed-everything defaults, moving instead towards an opt-in model that more tightly
    constrains attackers' ability to unexpectedly poke at resources. Chrome will be shipping
    `Cross-Origin-Opener-Policy` and `Cross-Origin-Embedder-Policy` shortly, and we intend to ensure
    that they're in place before enabling some APIs that risk aggravating side-channel attacks. To
    make this work at scale, it's critical that we collectively help developers place priority on
    applying `Cross-Origin-Resource-Policy` assertions to intentionally-embeddable resources.

    _Note that Artur Janc, et al. have put together a great [explainer for Cross-Origin
    Resource/Embedder/Opener Policy][coop-explainer] that I'm kicking myself for not linking in the
    talk. So. I'm linking it here, now._

4.  I pointed folks to [Securer Contexts][securer-contexts] as an area where I think browsers can
    revisit the minimum bar for modern applications that we set back in ~2015. Transport security
    seems quite insufficient to mitigate today's threats, and nudging developers more firmly towards
    the tools noted above seems imminently reasonable to me.

I'd appreciate feedback on these priorities, and also on the particular mitigations proposed above.
I'm hopeful that they're generally-applicable and widely-deployable, and would love to hear how
y'all see things.

For completeness, I'll embed the slides below (but I think you'll only get as much out of them as
you've already gotten out of the bullets above). For those of you that were in the room, thanks for
listening!


[strict-csp]: https://csp.withgoogle.com/docs/strict-csp.html
[tt-intro]: https://developers.google.com/web/updates/2019/02/trusted-types
[coop-explainer]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit
[securer-contexts]: https://github.com/mikewest/securer-contexts

Slides
------

<iframe
  src="https://speakerdeck.com/player/0dd492ced8eb4117a573d4e72d018824"
  allowfullscreen="true"
  mozallowfullscreen="true"
  webkitallowfullscreen="true"
  frameborder="0"
  title="Web Platform Security @ CMS Security Summit 2020"
  width="606"
  height="341"></iframe>

Hosted [on Speaker Deck](https://speakerdeck.com/mikewest/web-platform-security-at-cms-security-summit-2020), or [as a PDF](https://speakerd.s3.amazonaws.com/presentations/0dd492ced8eb4117a573d4e72d018824/CMS_Security_Summit__2020-02__1_.pdf).

Links from the presentation
---------------------------

*   Artur Janc and Lukas Weichselbaum's "[Securing Web Apps with Modern Platform Features](https://youtu.be/DDtM9caQ97I) from Google I/O in 2019.
*   Chromium's "[Post-Spectre Threat Model Re-Think](https://chromium.googlesource.com/chromium/src/+/master/docs/security/side-channel-threat-model.md).
*   Google's "[Strict CSP][strict-csp]" recommendations.
*   Christoph Kern's "[Securing the Tangled Web](https://research.google/pubs/pub42934)".
*   Krzysztof Kotowicz' "[Trusted Types Help Prevent Cross-Site Scripting][tt-intro]".
*   The [Trusted Types specification](https://bit.ly/tt-spec).
*   The [Scripting Policy](https://bit.ly/scripting-policy) thought experiment.
*   The [`Cross-Origin-Resource-Policy` specification](https://bit.ly/corp-spec).
*   The [`Cross-Origin-Embedder-Policy` specification](https://bit.ly/coep-spec).
*   The [Fetch Metadata specification](https://bit.ly/fm-spec).
*   Example [Fetch Metadata policies](https://bit.ly/fm-policies).
*   The [`Cross-Origin-Opener-Policy` specification](https://bit.ly/coop-spec).
*   The "[Securer Contexts][securer-contexts]" proposal.
