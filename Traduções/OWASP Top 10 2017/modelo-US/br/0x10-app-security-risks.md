# Risk - Application Security Risks

## What Are Application Security Risks?

Attackers can potentially use many different paths through your application to do harm to your business or organization. Each of these paths represents a risk that may, or may not, be serious enough to warrant attention.

![App Security Risks](images/0x10-risk-1.png)

Sometimes, these paths are trivial to find and exploit and sometimes they are extremely difficult. Similarly, the harm that is caused may be of no consequence, or it may put you out of business. To determine the risk to your organization, you can evaluate the likelihood associated with each threat agent, attack vector, and security weakness and combine it with an estimate of the technical and business impact to your organization.  Together, these factors determine your overall risk.

## What's My Risk

The [OWASP Top 10](https://www.owasp.org/index.php/Top10) focuses on identifying the most serious risks for a broad array of organizations. For each of these risks, we provide generic information about likelihood and technical impact using the following simple ratings scheme, which is based on the OWASP Risk Rating Methodology.  

| Threat Agents | Exploitability | Weakness Prevalence | Weakness Detectability | Technical Impacts | Business Impacts |
| -- | -- | -- | -- | -- | -- |
| App Specific | Easy | Widespread | Easy | Severe | App / Business Specific |
| App Specific | Average | Common | Average | Moderate | App / Business Specific |
| App Specific | Difficult | Uncommon | Difficult | Minor | App / Business Specific |

In this edition, we have changed the risk rating system around compared to previous version to assist with our ranking of likelihoods and impacts. This is not an issue within the document, but is clear in the public data analysis.

Each organization is unique, and so are the threat actors for that organization, their goals, and the impact of any breach. If a public interest organization uses a CMS for public information and a health system uses that same exact CMS for sensitive health records, the threat actors and business impacts are very different for the same exact software. It is critical that you apply your custom threat agents and business impacts based upon the data asset criticality.

Where possible, the names of the risks in the Top 10 are aligned with CWE weaknesses to promote generally accepted security practices and to reduce confusion. 

## References

### OWASP

* [OWASP Risk Rating Methodology](https://www.owasp.org/index.php/OWASP_Risk_Rating_Methodology)
* [Article on Threat/Risk Modeling](https://www.owasp.org/index.php/Threat_Risk_Modeling)

### External

* [ISO 31000: Risk Management Std](https://www.iso.org/iso-31000-risk-management.html)
* [ISO 27001: ISMS](https://www.iso.org/isoiec-27001-information-security.html)
* [NIST Cyber Framework (US)](https://www.nist.gov/cyberframework)
* [ASD Strategic Mitigations (AU)](https://www.asd.gov.au/infosec/mitigationstrategies.htm)
* [NIST CVSS 3.0](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator)
* [Microsoft Threat Modelling Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49168)
