# Template

## Secure development practices

* Development Pipeline.  A description of the testing and assessment processes that
  the software undergoes as it is developed and built. Be sure to include specific
information such as if contributors are required to sign commits, if any container
images immutable and signed, how many reviewers before merging, any automated checks for
vulnerabilities, etc.

* Communication Channels. Reference where you document how to reach your team or
  describe in corresponding section.
  * Internal. How do team members communicate with each other?
  * Inbound. How do users or prospective users communicate with the team?
  * Outbound. How do you communicate with your users? (e.g. flibble-announce@
    mailing list)

* Ecosystem. How does your software fit into the cloud native ecosystem?  (e.g.
  Flibber is integrated with both Flocker and Noodles which covers
  virtualization for 80% of cloud users. So, our small number of "users" actually
  represents very wide usage across the ecosystem since every virtual instance uses
  Flibber encryption by default.)

## Security issue resolution

* Responsible Disclosures Process. A outline of the project's responsible
  disclosures process should suspected security issues, incidents, or
  vulnerabilities be discovered both external and internal to the project. The
  outline should discuss communication methods/strategies.
  * Vulnerability Response Process. Who is responsible for responding to a
    report. What is the reporting process? How would you respond?

* Incident Response. A description of the defined procedures for triage,
  confirmation, notification of vulnerability or security incident, and
patching/update availability.

---

# Draft

todo: delete all "reference:" lines when merging draft into self-assessment.md

reference: https://github.com/antrea-io/antrea/blob/main/docs/design/architecture.md
reference: https://github.com/cncf/tag-security/blob/main/assessments/Open_and_Secure.pdf 
reference: see buildpacks, harbor, kyverno, pixie, for lightweight good examples

## Secure development practices

### Development Pipeline
reference: https://github.com/antrea-io/antrea/blob/main/CONTRIBUTING.md
reference: https://github.com/antrea-io/antrea/blob/main/ci/README.md

### Communication Channels
reference: https://github.com/antrea-io/antrea#community
reference: https://github.com/antrea-io/antrea/blob/main/SECURITY.md

### Ecosystem
reference: https://github.com/antrea-io/antrea/blob/main/docs/design/architecture.md 
reference: https://antrea.io/docs/v1.14.0/adopters/


## Security issue resolution

### Responsible Disclosures Process
reference: https://github.com/antrea-io/antrea/blob/main/SECURITY.md

### Vulnerability Response Process

### Incident Response