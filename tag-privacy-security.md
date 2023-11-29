# TAG Security & Privacy Questionnaire Answers #

* **Author:** amaliev@google.com
* **Questionnaire Source:** https://www.w3.org/TR/security-privacy-questionnaire/#questions

## Questions ##

* **What information might this feature expose to Web sites or other parties, and for what purposes is that exposure necessary?**
  * We are not directly exposing new information. We are permitting third-party cookie access based on certain user behavior, however, and this runs the risk of leaking information about that user behavior. Site A could use the presence of third-party cookies from Site B to determine that the user has recently interacted with Site B via a popup/redirect from Site A. But these flows would be initiated by Site A, so Site A could already detect this in most cases (e.g. if the user logs in manually on Site B).
* **Is this specification exposing the minimum amount of information necessary to power the feature?**
  * Yes. The popup/redirect flow and the presence of user activation are necessary to narrow down the use cases for heuristics with a strong signal of user intent.
* **How does this specification deal with personal information or personally-identifiable information or information derived thereof?**
  * This proposal does not deal with PII.
* **How does this specification deal with sensitive information?**
  * It doesn’t.
* **Does this specification introduce new state for an origin that persists across browsing sessions?**
  * No. Only concurrent interactions are considered, which may be cleared across sessions. Storage access grants persist across sessions but they already exist for features such as Storage Access API.
* **What information from the underlying platform, e.g. configuration data, is exposed by this specification to an origin?**
  * None.
* **Does this specification allow an origin access to sensors on a user’s device**
  * No.
* **What data does this specification expose to an origin? Please also document what data is identical to data exposed by other features, in the same or different contexts.**
  * None.
* **Does this specification enable new script execution/loading mechanisms?**
  * No.
* **Does this specification allow an origin to access other devices?**
  * No.
* **Does this specification allow an origin some measure of control over a user agent’s native UI?**
  * No.
* **What temporary identifiers might this this specification create or expose to the web?**
  * It exposes when an eTLD+1 site is interacted with in a popup or redirect context. This is not directly exposed to the web, but may be leaked to attackers who can observe third-party cookie access in certain scenarios (i.e. due to xsleaks).
* **How does this specification distinguish between behavior in first-party and third-party contexts?**
  * The change affects only third-party cookie access. It permits third-party cookie access where it was previously blocked due to third-party cookie deprecation. It has no effect on first-party cookie access.
* **How does this specification work in the context of a user agent’s Private \ Browsing or "incognito" mode?**
  * A user’s Private Browsing mode may have more restrictive settings to block third-party cookies. This proposal does not change that behavior or create new differences.
* **Does this specification have a "Security Considerations" and "Privacy Considerations" section?**
  * Yes.
* **Does this specification allow downgrading default security characteristics?**
  * No.
