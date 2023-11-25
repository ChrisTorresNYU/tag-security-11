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

Development on Antrea is done on GitHub. To ensure that contributions are
safe and properly reviewed prior to being added to the main branch of the
Antrea repository, the Antrea team follows the secure development practices of:

* Installing 
  [Git client-side hooks](https://github.com/antrea-io/antrea/blob/main/hack/git_client_side_hooks) 
  to:
  * Run golangci-lint to check source code for style and safety before a commit.
  * Run scripts to check 
    [documentation spelling](https://github.com/antrea-io/antrea/blob/main/hack/verify-spelling.sh), 
    [formatting](https://github.com/antrea-io/antrea/blob/main/hack/verify-docs-for-website.sh), 
    and to update 
    [table of contents](https://github.com/antrea-io/antrea/blob/main/hack/update-toc.sh) 
    before a commit.
  * Check that a 
    [Developer Certificate of Origin](https://developercertificate.org/) 
    (DCO) is present for every new commit before a push.
* Making changes in a new branch of a fork of the Antrea repository and
  submitting a pull request (PR) before their change can be integrated into
  the main repository.
* Having multiple reviewers check over a PR and provide feedback before the
  change is merged by a maintainer. Minor changes can be reviewed and approved
  by one team member, but most PRs are reviewed by 2-3 team members.
* Running 
  [GitHub Action and Jenkins continuous integration (CI)](https://github.com/antrea-io/antrea/blob/main/ci/README.md)
  checks relevant
  to their contribution when a PR is made. These include 
  [Go linters](https://github.com/antrea-io/antrea/blob/main/ci/README.md#go-linters),
  unit tests (that use the 
  [Go testing](https://golang.org/pkg/testing/)
  package), 
  [integration tests](https://github.com/antrea-io/antrea/blob/main/test/integration), 
  [end-to-end tests](https://github.com/antrea-io/antrea/blob/main/test/e2e), and 
  [Kubernetes upstream tests](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-testing/e2e-tests.md).
  * Daily and weekly Jenkins tests are automatically run on the main branch of 
    the Antrea repository. Developers are informed of test failures through
    the
    [developer mailing list](https://groups.google.com/forum/#!forum/projectantrea-dev).
* Using a 
  [DCO GitHub App](https://github.com/apps/dco) 
  to check that a DCO is present in every commit of a PR before review of that 
  PR begins.
* Cherry-picking PRs with bugfixes to older, currently-supported releases so
  that every currently-supported version of Antrea benefits from the 
  contribution.

### Communication Channels

The Antrea project uses a variety of communication channels for internal,
inbound, and outbound communications. This section lists the communication
channels that are publicly listed on the GitHub project README.

* Internal:
  * Antrea team members communicate through the
    [Antrea channel](https://kubernetes.slack.com/messages/CR2J23M0X)
    on the Kubernetes Slack. The Slack channel is used by the maintainers to 
    post announcements and discuss PRs. 
  * The Antrea GitHub project's 
    [issues page](https://github.com/antrea-io/antrea/issues)
    to track feature requests, known bugs, and proposals. The team also uses 
    the GitHub project's
    [PR page](https://github.com/antrea-io/antrea/pulls)
    to manage and review contributions to the project. 
  * Synchronous community meetings are held biweekly on Tuesdays for team 
    members to discuss releases, feature proposals, and user issues. Feature 
    proposals are typically presented in slideshow form. The 
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

Antrea is a Kubernetes-native network plugin that implements networking using
Kubernetes' [Container Network Interface](https://github.com/containernetworking/cni) 
(CNI) to manage pod network interfaces. The project is designed primarily for
use in Kubernetes clusters.

Antrea works to expand the cloud native ecosystem by extending the networking
capabilities of Kubernetes. The project adds more network policies, support for
multi-OS clusters (Linux and Windows), plugin-native troubleshooting tools 
(traceflows), offloading networking to hardware on a node, and encrypted 
inter-node networking (IPsec or WireGuard).

Other Kubernetes CNI plugins exist, such as 
[Calico](https://github.com/projectcalico/calico), 
[Flannel](https://github.com/flannel-io/flannel), 
and [Cilium](https://github.com/cilium/cilium). The main benefit to the
cloud-native ecosystem that Antrea provides is an implementation of the CNI
using 
[Open vSwitch](https://www.openvswitch.org/). 
Open vSwitch is a virtual switch that operates in the 
data plane that creates virtual interfaces for pods and tunnels between nodes.
By using Open vSwitch, Antrea can support
[much higher network policy performance, processor utilization, and packet throughput](https://www.vmware.com/products/antrea-container-networking.html) 
than CNI plugins that use more common data plane technology like 
[eBPF](https://ebpf.io/), 
[built-in Linux bridges](https://wiki.linuxfoundation.org/networking/bridge), 
or 
[Host Network Service](https://learn.microsoft.com/en-us/virtualization/windowscontainers/container-networking/architecture)
(for Windows). Another benefit of Open vSwitch is its Windows support -- 
this reduces the complexity of development and usage because only one data
plane technology needs to be supported.

For companies that want to run applications on a cloud environment, 
[VMware offers enterprise-grade technical support](https://www.vmware.com/products/antrea-container-networking.html) 
for companies using Antrea alongside their cloud application on VMware Tanzu
or vSphere. In addition, VMware sponsors development on the Antrea project so
that there is always active work being done on the project. All of the
maintainers and some of the contributors to the project are affiliated with
VMware.


## Security issue resolution

### Responsible Disclosures Process
reference: https://github.com/antrea-io/antrea/blob/main/SECURITY.md

### Vulnerability Response Process

### Incident Response