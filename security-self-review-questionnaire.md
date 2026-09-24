# [Self-Review Questionnaire: Security and Privacy](https://w3c.github.io/security-questionnaire/)

The full questionnaire is at https://w3c.github.io/security-questionnaire/.

---

01.  What information does this feature expose, and for what purposes?

Global Privacy Control (GPC) is a mechanism for expressing a person's
general universal preference for a do-not-sell-or-share interaction.

GPC exposes one bit of information: either a "1" if the preference is set, or nothing otherwise.

02.  Do features in your specification expose the minimum amount of information
     necessary to implement the intended functionality?

Yes.

03.  Do the features in your specification expose personal information,
     personally-identifiable information (PII), or information derived from
     either?

No.

04.  How do the features in your specification deal with sensitive information?

n/a

05.  Does data exposed by your specification carry related but distinct
     information that may not be obvious to users?

No. GPC reveals one preference that must be set by the user, either
as a stand-alone choice or as part of a bundled set of privacy choices.

06.  Do the features in your specification introduce state
     that persists across browsing sessions?

Yes. The GPC preference is set by the user once, then conveyed in future sessions.

07.  Do the features in your specification expose information about the
     underlying platform to origins?

No. A GPC setting might be the default for a particular client that turns on GPC as
part of a privacy stance that is communicated to users. But other uses of GPC might
be as the result of a manual preference change by the user. GPC set as a client
default is indistinguishable from GPC set as a preference change.

08.  Does this specification allow an origin to send data to the underlying
     platform?

No.

09.  Do features in this specification enable access to device sensors?

No.

10.  Do features in this specification enable new script execution/loading
     mechanisms?

No.

11.  Do features in this specification allow an origin to access other devices?

No.

12.  Do features in this specification allow an origin some measure of control over
     a user agent's native UI?

No.

13.  What temporary identifiers do the features in this specification create or
     expose to the web?

None.

14.  How does this specification distinguish between behavior in first-party and
     third-party contexts?

It does not.  A Global Privacy Control preference should be conveyed
for all HTTP requests.

15.  How do the features in this specification work in the context of a browser’s
     Private Browsing or Incognito mode?

This specification does not include any different behavior in
Private Browsing or Incognito modes.

16.  Does this specification have both "Security Considerations" and "Privacy
     Considerations" sections?

Yes.

17.  Do features in your specification enable origins to downgrade default
     security protections?

No.

18.  What happens when a document that uses your feature is kept alive in BFCache
     (instead of getting destroyed) after navigation, and potentially gets reused
     on future navigations back to the document?

If a document was requested with GPC off, then the user turned GPC on, then a cached version
of the document was used, it is possible that a user could interact with a document that
reflects their previous GPC setting.

The `globalPrivacyControl` property reflects the Sec-GPC header field value that was sent
when loading the top-level browsing context's active document.

19.  What happens when a document that uses your feature gets disconnected?

The GPC setting that was in effect at the time of disconnection will remain in effect.

20.  Does your spec define when and how new kinds of errors should be raised?

No.

21.  Does your feature allow sites to learn about the user's use of assistive technology?

No, if clients have appropriate accessibility for the GPC setting. If a client prevents a user
of assistive technology from changing the GPC setting, then a site might infer the absence
of assistive technology from a non-default setting.

22.  What should this questionnaire have asked?

n/a

