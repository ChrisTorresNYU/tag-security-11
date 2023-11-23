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

The Antrea project uses a variety of communication channels for internal,
inbound, and outbound communications. This section lists the communication
channels that are publicly listed on the GitHub project README.

* Internal:
  * Antrea team members communicate through the
    [Antrea channel](https://kubernetes.slack.com/messages/CR2J23M0X)
    on the Kubernetes Slack. The Slack channel is used by the maintainers to post
    announcements and discuss PRs. 
  * The Antrea GitHub project's 
    [issues page](https://github.com/antrea-io/antrea/issues)
    to track feature requests, known bugs, and proposals. The team also uses 
    the GitHub project's
    [PR page](https://github.com/antrea-io/antrea/pulls)
    to manage and review contributions to the project. 
  * Synchronous community meetings are held biweekly on Tuesdays for team 
    members to discuss releases, feature proposals, and user issues. Feature proposals are typically presented in slideshow form. The 
    [minutes](https://github.com/antrea-io/antrea/wiki/Community-Meetings)
    and 
    [recording](https://www.youtube.com/playlist?list=PLuzde2hYeDBdw0BuQCYbYqxzoJYY1hfwv) 
    for each meeting are openly available.
  * The Antrea team uses a 
    [developer mailing list](https://groups.google.com/forum/#!forum/projectantrea-dev) 
    to keep the team updated on daily and weekly Jenkins build failures. The
    mailing list was briefly formerly used for internal development communication.

* Inbound
  * [Live office hours](https://calendar.google.com/calendar/u/0/embed?src=uuillgmcb1cu3rmv7r7jrhcrco@group.calendar.google.com)
    are held biweekly on Tuesdays when community meetings are
    not held. During office hours, users can join and ask Antrea team members
    questions.
  * Users can contact the Antrea team through the 
    [Antrea channel](https://kubernetes.slack.com/messages/CR2J23M0X) 
    on the Kubernetes slack for questions and support.
  * Users can post bug reports, feature requests, and support requests on the
    [issues page](https://github.com/antrea-io/antrea/issues)
    of the project's GitHub repository.
  * Users can report security vulnerabilities by emailing the Antrea maintainers
    at the address cncf-antrea-maintainers@lists.cncf.io.

* Outbound
  * The Antrea team occasionally uses their live office hours time to hold a
    [Antrea LIVE](https://www.youtube.com/@projectantrea/streams),
    a livestream about Antrea (releases and usage) and topics related to Antrea 
    such as Open vSwitch, CNI (Container Network Inferface), and networking
    in Kubernetes.
  * The Antrea team formerly used a 
    [announcement mailing list](https://groups.google.com/g/projectantrea)
    to send project announcements to the community. The team also formerly used a 
    [general mailing list](https://groups.google.com/g/projectantrea) to send
    community meeting reminders and agendas. Usage of this channel was
    discontinued around September 2022. The team now uses 
    [Slack](https://kubernetes.slack.com/messages/CR2J23M0X)
    for these two types of communications.
  * The Antrea team formerly used 
    [X/Twitter](https://twitter.com/ProjectAntrea) 
    to announce Antrea LIVE livestreams and major releases. Usage of this
    channel was discontinued around November 2022.

### Ecosystem
reference: https://github.com/antrea-io/antrea/blob/main/docs/design/architecture.md 
reference: https://antrea.io/docs/v1.14.0/adopters/


## Security issue resolution

### Responsible Disclosures Process
reference: https://github.com/antrea-io/antrea/blob/main/SECURITY.md

### Vulnerability Response Process

### Incident Response