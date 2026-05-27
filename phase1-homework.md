# SEAS-8414 Phase 1 Homework
## Blackboard Multiple-Choice Assessment: Network Discovery and Asset Inventory

**Due:** Before Class 2, 9:00 AM ET
**Total Points:** 100
**Format:** 50 single-correct-answer multiple choice questions, 2 points each
**Audience:** Doctoral students and senior cybersecurity practitioners

This homework is designed for Blackboard delivery. Every item is multiple choice
with exactly one correct answer. The assessment is closed book: do not use the
textbook, notes, internet search, lab files, scanners, AI tools, or outside
incident writeups while answering.

Each question includes a scenario-provenance label. That label is a citation
trail for instructors and is never required to choose the answer. If a stem names
a CISA advisory, DOJ release, public incident report, or research source, treat
that name as non-examinable provenance only; all facts and rules needed to
answer are inside the question.

Each stem states the discovery-stage cyber-analytics constraint needed to answer
the item: the analyst is measuring host existence, observability, provenance,
vantage point, method contribution, completeness, soundness, discovery gap,
negative evidence, phantom-host risk, and bounded handoff evidence for IoT, OT,
embedded, or operational platforms. Do not answer by relying on product
identification, exploit claims, credential testing, remediation planning, or
downstream prioritization.

---

### Question 1

**Scenario provenance only (not needed to answer):** U.S. Senate Commerce Committee staff report on the
Target breach.

A retailer reviews a store IoT/OT subnet containing freezer monitors, HVAC
controllers, cameras, and badge readers after learning that contractor access
was relevant in a public breach. A row has a current DHCP lease in the store
subnet, a successful TCP connection from the management collector, and no local
ARP entry from a store-floor laptop. The scored cyber-analytics population is
"current networked store operational devices," and the discovery stage may
admit host-existence claims only when evidence, vantage, and uncertainty are
preserved.

Apply that admission rule. Which inventory action is correct?

(a) Reject the row because local ARP is missing.
(b) Admit the row, preserving the management vantage and missing local-ARP note.
(c) Merge the row into the contractor-support population because contractor
access was relevant to the review.
(d) Exclude the row because TCP evidence is later-analysis-only evidence.

### Question 2

**Scenario provenance only (not needed to answer):** U.S. Senate Commerce Committee staff report on the
Target breach.

A branch facilities scanner looking for smart-building IoT devices sees
`10.20.4.255` as the source address on one SSDP-like message. No DHCP lease,
router ARP, switch table entry, local ARP, or TCP response supports that address.
The inventory may admit only host-existence claims with at least one current
non-broadcast evidence source, not broadcast or multicast artifacts.

Using that artifact rule, which inventory action is correct?

(a) Admit it because SSDP is a discovery method.
(b) Admit it only if the packet includes a vendor-like string.
(c) Reject it as a broadcast-artifact risk, while retaining the raw observation
for audit.
(d) Count it as separate infrastructure outside the denominator.

### Question 3

**Scenario provenance only (not needed to answer):** U.S. Senate Commerce Committee staff report on the
Target breach.

A store cyber-analytics run measures IoT/OT devices such as cameras, HVAC
controllers, and freezer monitors. The manually validated in-scope denominator
has 64 devices. Discovery admits 70 rows; 58 admitted rows are later confirmed
as real in-scope devices. Use these definitions: completeness = confirmed real
admitted rows / true in-scope denominator; soundness = confirmed real admitted
rows / admitted rows.

Which metric pair is correct?

(a) Completeness 58/64, soundness 58/70.
(b) Completeness 58/70, soundness 58/64.
(c) Completeness 70/64, soundness 64/70.
(d) Completeness 64/70, soundness 70/58.

### Question 4

**Scenario provenance only (not needed to answer):** U.S. Senate Commerce Committee staff report on the
Target breach.

Two store IoT/OT discovery methods are compared in the same 20-minute window.
DHCP plus router ARP sees 46 hosts. A local collector using ARP and limited TCP
connect sees 51 hosts. The overlap is 39. Use the simple capture-recapture
estimate `N_hat = (A * B) / M`, where A and B are method counts and M is their
overlap; treat the result as an audit signal unless the stem proves stable,
independent sampling.

Using the formula and caveat stated above, which answer is correct?

(a) 39 hosts; use it as the final denominator.
(b) 46 hosts; use the infrastructure source as authoritative.
(c) 51 hosts; use the larger count as ground truth.
(d) About 60 hosts; use it as an audit signal, not proof.

### Question 5

**Scenario provenance only (not needed to answer):** U.S. Senate Commerce Committee staff report on the
Target breach.

In a store cyber-analytics baseline for embedded operational devices, a
corporate reporting server outside the store subnet is contacted by store HVAC
and freezer-monitor devices. It is clearly real, but the assignment denominator
is "networked devices located in the store operational subnet."

Which classification matches the stated denominator?

(a) Admit it because store devices contact it.
(b) Treat it as separate infrastructure or out of scope for the scored
denominator.
(c) Reject the row as false because it is not local.
(d) Convert it into a store host if the server has a store label.

### Question 6

**Scenario provenance only (not needed to answer):** CISA advisory AA21-042A on the 2021 U.S. water
treatment facility compromise.

A water utility wants to run a broad active scan first because leadership wants
fast coverage numbers. The OT control network includes fragile controllers and
one operator workstation. The cyber-analytics discovery stage measures
host existence with minimal disturbance before escalating to traffic-generating
methods.

Which sequence satisfies that measurement rule?

(a) Start with all-port active probing, then inspect passive evidence.
(b) Start with DHCP, gateway ARP, switch tables, local ARP, and approved logs;
escalate only to scoped active checks if uncertainty remains.
(c) Skip passive evidence because it cannot prove device identity.
(d) Run a narrow TCP pilot first, then inspect passive and infrastructure
evidence after the pilot finishes.

### Question 7

**Scenario provenance only (not needed to answer):** CISA advisory AA21-042A on the 2021 U.S. water
treatment facility compromise.

Two controllers appear in switch MAC tables during the maintenance window but do
not answer ICMP or sampled TCP connect probes. The collector is on a routed
management segment. Rule for this item: a current switch MAC-table observation
inside the window is host-existence evidence; failed ICMP and sampled TCP from a
routed collector are negative evidence but not proof of absence.

Which evidence statement is supported?

(a) The controllers are absent because both active methods failed.
(b) The controllers are compromised because they are silent.
(c) The controllers remain supported host claims; negative evidence is
ambiguous under this vantage and method set.
(d) The controllers are excluded because switch evidence is administrative
inventory only.

### Question 8

**Scenario provenance only (not needed to answer):** CISA advisory AA21-042A on the 2021 U.S. water
treatment facility compromise.

The same water utility has a jump host that appears in DHCP and gateway ARP, but
not in local ARP from an engineering laptop.

Which note is required for an auditable host record?

(a) Record the DHCP and gateway vantage, the missing engineering-laptop local
ARP, and the time window before deciding confidence.
(b) Delete the row because local ARP is the only accepted evidence.
(c) Mark it as a later-stage finding, not discovery evidence.
(d) Infer that the jump host is reachable from every plant network.

### Question 9

**Scenario provenance only (not needed to answer):** CISA advisory AA21-042A on the 2021 U.S. water
treatment facility compromise.

A control-room workstation has remote-access software installed. During the
current OT discovery window, the workstation itself is not seen in DHCP, ARP,
switch tables, logs, multicast, ICMP, or TCP connect. The analytics table may
admit current host claims only from current host-existence evidence.

Which answer is consistent with that discovery-stage rule?

(a) Admit the host as provisional because remote-access software is an indirect
signal for a workstation role.
(b) Admit the host with an assumption flag because the role is expected in the
control room.
(c) Reject all historical records for the workstation.
(d) Treat the software record as insufficient for a current host claim without
current existence evidence.

### Question 10

**Scenario provenance only (not needed to answer):** CISA advisory AA21-042A on the 2021 U.S. water
treatment facility compromise.

For a plant network, DHCP sees 9 addresses, gateway ARP sees 12, local ARP sees
7, and an approved TCP connect pilot sees 3 additional addresses not in the
passive sources.

Which reporting format preserves the observed method contributions?

(a) Report only the 12 gateway ARP rows because that is the largest passive set.
(b) Report only the 3 active rows because active evidence is freshest.
(c) Report a merged inventory with per-host source provenance and method
contribution, separating unique active admissions from passive confirmations.
(d) Average the four counts and report 8 devices.

### Question 11

**Scenario provenance only (not needed to answer):** CISA alert on heightened DDoS threats from Mirai and
related botnets.

An ISP reviews customer-premises IoT devices after public botnet activity. The
cyber-analytics task is discovery only: record host existence and observed
reachability, but do not test passwords or infer compromise. A device responds
to TCP connect on Telnet and appears in router ARP.

Which host-record conclusion is supported?

(a) The device is a vulnerability candidate because Telnet is reachable.
(b) The device is a host claim with reachability evidence; credential state is
not decided here.
(c) The router ARP row must be ignored because customer-premises gateways are
not endpoint sensors.
(d) The device is excluded until Chapter 2 identifies vendor and model.

### Question 12

**Scenario provenance only (not needed to answer):** DOJ public reporting on Mirai-related guilty pleas.

A discovery run over an IoT segment finds 180 admitted rows. Later validation
confirms 153 are real in-scope devices. The known denominator is 170. False
positives are admitted rows that are not real in-scope devices; false negatives
are real in-scope devices that were missed.

What are false positives and false negatives?

(a) 27 false positives and 17 false negatives.
(b) 17 false positives and 27 false negatives.
(c) 10 false positives and 27 false negatives.
(d) 27 false positives and 10 false negatives.

### Question 13

**Scenario provenance only (not needed to answer):** CISA alert on heightened DDoS threats from Mirai and
related botnets.

Two IoT discovery methods are likely dependent because both rely on remotely
reachable management surfaces. Method A sees 90 devices, Method B sees 80, and
their overlap is 72.

Which statement follows from the stated method dependence?

(a) The capture-recapture estimate is exact because overlap is high.
(b) High overlap proves no hidden devices exist.
(c) Method dependence is disclosed because the estimate may understate
quiet devices missed by both methods.
(d) Dependence does not matter when both methods are active.

### Question 14

**Scenario provenance only (not needed to answer):** CISA alert on heightened DDoS threats from Mirai and
related botnets.

An analyst is building the discovery input table for an IoT cyber-analytics
pipeline. At this stage the table may contain only host-existence evidence,
source provenance, uncertainty, and metrics about coverage or contamination; it
may not contain final product families, credential exposure, or risk ranking.

Which output matches that discovery table contract?

(a) A final product-family map with downstream risk ranking.
(b) A credential exposure table.
(c) A provenance-bearing host inventory with uncertainty notes and observed
existence evidence.
(d) A remediation backlog grouped by device type.

### Question 15

**Scenario provenance only (not needed to answer):** DOJ public reporting on Mirai-related guilty pleas.

An IoT row appears only in a week-old scan output. It has no current DHCP lease,
no current router ARP, no switch entry, and no current response. The assessment
is measuring current host existence, and stale unsupported rows can become
phantom hosts.

Which treatment follows from the current-evidence rule?

(a) Admit it because botnet incidents show old devices matter.
(b) Review it as historical evidence, not as a current admitted host claim,
because stale evidence creates phantom-host risk.
(c) Admit it if the old hostname looks like a camera.
(d) Move it directly to later analysis.

### Question 16

**Scenario provenance only (not needed to answer):** Verkada March 2021 security incident report.

A hospital camera program has a cloud console export with 210 camera serial
numbers and last-check-in times, but no local IP addresses or VLAN context. The
assignment is to discover cameras currently present on clinic networks.

Which source contract follows from the assignment scope?

(a) Treat the console export as administrative and operational context, not by
itself a local network host claim.
(b) Treat all console rows as admitted local hosts.
(c) Reject the console export because it is not a packet capture.
(d) Use the console export as final device identity and skip network discovery.

### Question 17

**Scenario provenance only (not needed to answer):** Verkada March 2021 security incident report.

Clinic DHCP lists 92 camera-like leases. Local network discovery sees 61 hosts
with local ARP and TCP connect on a camera management port. Facilities lists 14
decommissioned cameras.

Which rule follows from those source types?

(a) Admit all 92 DHCP rows and all 14 facilities rows.
(b) Exclude the 61 local rows until the cloud console confirms them.
(c) Admit rows with local ARP plus TCP evidence, review DHCP-only rows with
timestamp and scope, and exclude decommissioned rows unless current network
evidence reappears.
(d) Count only the facilities spreadsheet because it names the cameras.

### Question 18

**Scenario provenance only (not needed to answer):** Verkada March 2021 security incident report.

A camera is seen by local ARP at 09:02 and TCP connect at 09:03 from the clinic
collector. The cloud console shows its serial last checked in yesterday from a
different site label.

Which host-record action preserves both pieces of evidence?

(a) Discard the network evidence because the cloud label conflicts.
(b) Admit the network host claim and preserve the cloud-label conflict for
review.
(c) Merge the row silently into the other site.
(d) Prefer the cloud-console site label and suppress the local network
observation.

### Question 19

**Scenario provenance only (not needed to answer):** Verkada March 2021 security incident report.

A security leader asks whether a camera-fleet discovery report can prove there
is no privileged-account exposure. The discovery report can measure evidence for
which camera hosts exist on clinic networks, but account exposure is part of a
later authorized analysis stage.

Which response separates discovery analytics from later account analysis?

(a) Yes, if every camera responds to local ARP.
(b) Yes, if the cloud console list is complete.
(c) No, and the analyst therefore stops without producing an inventory.
(d) No, but discovery can produce the evidence-backed device population that
later controls must reason over.

### Question 20

**Scenario provenance only (not needed to answer):** Verkada March 2021 security incident report.

The camera program reports 210 cloud serials, 92 DHCP leases, and 61 local
network host claims. The overlap between cloud serials and DHCP leases is
unknown.

Which claim is supported by the missing-overlap condition?

(a) The three counts cannot be reconciled into a rule-compliant denominator until
overlap, scope, timestamp, and source semantics are recorded.
(b) The denominator is 363 because all counts are added.
(c) The denominator is 61 because local network evidence is always complete.
(d) The denominator is 210 because cloud consoles are authoritative.

### Question 21

**Scenario provenance only (not needed to answer):** FDA consumer update on medical device cybersecurity.

A biomedical IoT VLAN is safety-sensitive. Passive observation sees 44 gateway
ARP entries, 39 DHCP leases, and 9 mDNS announcements. No active probing has
been authorized. The analytics goal is to establish an evidence-backed device baseline
without overstating coverage or identity.

Which statement follows from the stated authorization and evidence?

(a) The VLAN has exactly 44 devices.
(b) The 9 mDNS devices are the only devices with meaningful evidence.
(c) Passive evidence establishes a bounded baseline, but it does not prove
complete discovery or device identity.
(d) The missing active scan invalidates all passive evidence.

### Question 22

**Scenario provenance only (not needed to answer):** CISA advisory ICSA-15-174-01 on Hospira infusion
systems.

An infusion pump does not answer ICMP. It appears in DHCP and switch MAC tables
within the same 5-minute window. The discovery analyst may admit a host claim
from current infrastructure evidence while treating nonresponse as negative
evidence whose force depends on method and vantage.

Which action follows from that evidence rule?

(a) Admit the host claim and note ICMP silence as ambiguous negative evidence.
(b) Reject the host because ICMP failed.
(c) Admit the host but set the device model from the MAC/OUI vendor field.
(d) Defer the host claim until local ARP also observes the pump.

### Question 23

**Scenario provenance only (not needed to answer):** FDA consumer update on medical device cybersecurity.

Clinical engineering provides a spreadsheet of 120 expected biomedical IoT
devices. Network evidence supports 93 current host claims. The spreadsheet has
not been validated since a ward relocation.

Which denominator statement follows from the validation status?

(a) The denominator is 120 because clinical engineering owns the devices.
(b) The denominator is 93 because network evidence is always true.
(c) The denominator is 213 because expected and observed rows are added.
(d) The spreadsheet is a denominator candidate and gap-finding source, not
ground truth until reconciled with current evidence.

### Question 24

**Scenario provenance only (not needed to answer):** CISA advisory ICSA-15-174-01 on Hospira infusion
systems.

Gateway ARP and DHCP show a pump address. A nursing-workstation local ARP cache
does not show it.

Which factor explains why the negative local result is weak?

(a) DHCP and gateway ARP must be discarded whenever a workstation cache is
available.
(b) Local ARP depends on recent local-link interaction and vantage.
(c) Gateway ARP is always stale.
(d) The absence from one local cache proves the pump left the subnet.

### Question 25

**Scenario provenance only (not needed to answer):** FDA consumer update on medical device cybersecurity.

Before active probing a biomedical VLAN, the analyst records method, vantage,
timestamp, address, MAC where available, and uncertainty notes for every passive
row.

Why is this necessary?

(a) It proves the devices are safe to probe.
(b) It replaces later device classification.
(c) It preserves the evidence contract that later analysis depends on.
(d) It converts passive evidence into complete ground truth.

### Question 26

**Scenario provenance only (not needed to answer):** NSA/CISA advisory AA23-278A on common
misconfigurations.

An office floor contains IoT and embedded platforms: printers, scanners, VoIP
phones, and cameras. A manager asks discovery staff to "find every
default-password device," but the assigned cyber-analytics stage is discovery:
build a provenance-bearing host inventory and defer credential-state claims.

Which response follows from that assigned scope?

(a) Run login attempts because office devices are low risk.
(b) Report only devices that expose web interfaces.
(c) Exclude printers and VoIP phones from discovery.
(d) Produce a provenance-bearing inventory and defer credential-state questions
to later analysis.

### Question 27

**Scenario provenance only (not needed to answer):** NSA/CISA advisory AA23-278A on common
misconfigurations.

A networked printer row has DHCP, mDNS `_ipp._tcp`, and TCP connect on 631 and
9100. No SNMP credentials are available. The discovery-stage task is to decide
whether there is enough evidence for host existence, not to complete device
identity.

Which classification matches the host-inventory task?

(a) Review only, because no SNMP data exists.
(b) Admit the host claim while preserving the evidence as support for later
identity work.
(c) Reject it because print protocols are not discovery evidence.
(d) Mark it as a completed device identity profile.

### Question 28

**Scenario provenance only (not needed to answer):** NSA/CISA advisory AA23-278A on common
misconfigurations.

A procurement spreadsheet lists a network scanner used by an office operations
team. During the current discovery window, no DHCP, ARP, switch, multicast,
ICMP, or TCP evidence supports it. Administrative records can guide
reconciliation, but they do not automatically prove current network presence.

Which inventory action follows from that evidence rule?

(a) Review it as administrative inventory, not a clean current host claim.
(b) Admit it because procurement records are authoritative.
(c) Reject the entire spreadsheet.
(d) Convert it into a phantom host automatically.

### Question 29

**Scenario provenance only (not needed to answer):** NSA/CISA advisory AA23-278A on common
misconfigurations.

A VoIP phone appears in DHCP and a switch MAC table, but sampled TCP ports do
not respond. The analyst is deciding host existence for an embedded office
device, not weak-configuration status.

Which conclusion is supported by the evidence?

(a) The phone is absent.
(b) The phone is fully identified.
(c) The phone is an accepted host claim, with TCP silence noted as method
uncertainty.
(d) The phone is tested for weak configuration immediately.

### Question 30

**Scenario provenance only (not needed to answer):** NSA/CISA advisory AA23-278A on common
misconfigurations.

One stale ARP entry from three weeks ago names a printer IP. There is no current
DHCP lease and no current response. Soundness measures how much of the admitted
inventory corresponds to real current in-scope devices.

Which metric is harmed by admitting it?

(a) Lowering the discovery gap.
(b) Improving completeness too much.
(c) Losing method provenance.
(d) Creating a phantom host that reduces soundness.

### Question 31

**Scenario provenance only (not needed to answer):** Maersk public cyber-attack update following NotPetya.

During recovery, a shipping site has three cyber-analytics baselines for
warehouse IoT and operational systems: central routed scan 380, local collectors
410, and central scanner plus gateway exports 395. Time windows and overlaps
differ.

Which board-facing claim follows from the conflicting baselines?

(a) The true denominator is 410 because it is largest.
(b) The baseline is not yet stable; counts are shaped by method, vantage, time,
and overlap.
(c) The central scan is authoritative because local collectors are noisy.
(d) The average of the three counts is the correct denominator.

### Question 32

**Scenario provenance only (not needed to answer):** Maersk public cyber-attack update following NotPetya.

Site owners disclose 35 shadow operational systems for label printing,
handheld-device staging, and warehouse environmental monitoring. Some may
overlap with discovered rows. The inventory can use the disclosure for gap
analysis, but overlap must be reconciled before denominator admission.

Which discovery action follows from that overlap rule?

(a) Treat the list as gap-finding evidence and reconcile overlap before adding
to the denominator.
(b) Add all 35 to the admitted inventory immediately.
(c) Ignore the list because it is not scanner output.
(d) Treat the list as proof that discovery failed completely.

### Question 33

**Scenario provenance only (not needed to answer):** Maersk public cyber-attack update following NotPetya.

A recovery dashboard for warehouse IoT and operational technology shows
"400 assets found" but does not record method, timestamp, site, or collector
vantage. A cyber-analytics baseline must support later audit of coverage and
contamination.

Which missing field set makes the count non-auditable?

(a) The count is too low for a shipping company.
(b) The count lacks product identity.
(c) The row population lacks provenance, making completeness, soundness, and
overlap unverifiable.
(d) The dashboard did not include later-stage risk scores.

### Question 34

**Scenario provenance only (not needed to answer):** Maersk public cyber-attack update following NotPetya.

Local collectors find warehouse handheld staging systems that the central routed
scan missed.

What does this show?

(a) Central scans are useless.
(b) Local collectors always find all devices.
(c) Handheld staging systems are compromised.
(d) Vantage point and topology alter observability, so method contribution must
be reported.

### Question 35

**Scenario provenance only (not needed to answer):** Maersk public cyber-attack update following NotPetya.

A site count drops from 82 to 68 after a shift change. Several warehouse devices
sleep when not docked.

Which inventory rule preserves the observed time pattern?

(a) Preserve the time window and presence pattern instead of silently treating
the lower count as disappearance.
(b) Delete the higher count because it is older.
(c) Admit all historically seen devices as current forever.
(d) Infer that the site decommissioned 14 devices.

### Question 36

**Scenario provenance only (not needed to answer):** CISA alert on the 2015 Ukraine power-grid
cyberattack.

A control-center VPN scan sees 18 substation hosts. Local passive collectors in
two substations see 27. Gateway exports show 22 addresses with timestamps
ranging from 5 minutes to 9 hours.

Which statement follows from the evidence freshness and vantage?

(a) The VPN count is the measured population.
(b) The gateway export is invalid because timestamps differ.
(c) The measured population is unresolved; each source must be interpreted by
vantage, freshness, and scope.
(d) The local collector count is guaranteed complete.

### Question 37

**Scenario provenance only (not needed to answer):** CISA alert on the 2015 Ukraine power-grid
cyberattack.

Serial-to-Ethernet gateways appear in router ARP but do not answer ICMP.

Which conclusion is supported by the evidence?

(a) They are absent from the substation.
(b) Router ARP supports host existence; ICMP silence remains negative evidence
with limited force.
(c) ICMP silence proves the gateways are not networked.
(d) The gateways are removed from the denominator automatically.

### Question 38

**Scenario provenance only (not needed to answer):** CISA alert on the 2015 Ukraine power-grid
cyberattack.

Active probing is approved only during a substation maintenance window. Passive
sources already show 23 probable OT hosts, but 7 expected devices remain unseen.
The discovery stage starts from passive evidence but may use scoped active
checks when they are authorized and needed to reduce uncertainty.

Which plan satisfies that constraint?

(a) Probe immediately because unseen devices are high risk.
(b) Exclude the 7 expected devices permanently.
(c) Stop discovery because passive evidence is safer.
(d) Use passive evidence as the baseline, then run scoped active checks during
the approved window and preserve method contribution.

### Question 39

**Scenario provenance only (not needed to answer):** CISA alert on the 2015 Ukraine power-grid
cyberattack.

A board asks whether the substation discovery report proves the substations are
secure. The report's scope is only cyber-analytics discovery: a bounded,
evidence-backed population with named uncertainties for later analysis.

Which board response matches that report scope?

(a) No; it proves only a bounded, evidence-backed population and its
uncertainties for later analysis.
(b) Yes, if all substation hosts appear in router ARP.
(c) Yes, if the VPN scanner reaches the subnet.
(d) No, because discovery cannot produce any useful evidence.

### Question 40

**Scenario provenance only (not needed to answer):** CISA alert on the 2015 Ukraine power-grid
cyberattack.

Two substation discovery methods show A = 30, B = 25, overlap M = 15. Use the
simple capture-recapture estimate `N_hat = (A * B) / M`.

What is the simple capture-recapture estimate?

(a) 25
(b) 30
(c) 50
(d) 70

### Question 41

**Scenario provenance only (not needed to answer):** Public reporting on the Darktrace casino aquarium
sensor case.

A gaming company scores "networked facilities and environmental devices in the
lobby network." A temperature sensor is in facilities DHCP and gateway ARP, but
the casino payment network scanner cannot see it.

Which treatment matches the stated facilities denominator?

(a) Reject it because the payment scanner cannot see it.
(b) Admit it to the facilities denominator with provenance; payment-network
visibility is a different vantage.
(c) Treat it as payment infrastructure.
(d) Move the sensor to the payment-network denominator because that scanner
failed to observe it.

### Question 42

**Scenario provenance only (not needed to answer):** Public reporting on the Darktrace casino aquarium
sensor case.

Facilities IoT DHCP and gateway ARP see 17 environmental devices. A local
collector sees 23. Their overlap is 10. Use the simple capture-recapture
estimate `N_hat = (A * B) / M`.

What is the simple capture-recapture estimate?

(a) 17.0
(b) 23.0
(c) 28.0
(d) 39.1

### Question 43

**Scenario provenance only (not needed to answer):** Public reporting on the Darktrace casino aquarium
sensor case.

The facilities spreadsheet lists 28 expected devices, but it has not been
validated in six months.

Which use matches that validation status?

(a) Use it as a stale administrative source to guide reconciliation, not as
ground truth.
(b) Treat 28 as the final denominator.
(c) Reject all network observations that do not appear in it.
(d) Count every spreadsheet row as a current host claim.

### Question 44

**Scenario provenance only (not needed to answer):** Public reporting on the Darktrace casino aquarium
sensor case.

One smart-building IoT sensor announces itself through mDNS only on the local
lobby VLAN. The routed central scanner sees no multicast traffic. The analyst
must explain the difference using observability, method, and vantage rather than
outside incident details.

Which explanation follows from local-link observability?

(a) Treat mDNS as administrative inventory unless a routed scanner repeats it.
(b) Treat the central scanner as authoritative and downgrade the local mDNS row
to historical context.
(c) Local-link discovery can reveal devices that a routed vantage misses; record
the vantage and method.
(d) Replace the local collector result with the central scanner denominator.

### Question 45

**Scenario provenance only (not needed to answer):** Public reporting on the Darktrace casino aquarium
sensor case.

The local collector reports 4 new lobby devices after a private event. By the
next morning, all 4 are gone from DHCP and ARP.

Which host-record treatment preserves the time-bound observation?

(a) Delete all traces because they are not current.
(b) Preserve them as time-bound observations and avoid counting them as current
without renewed evidence.
(c) Admit them permanently because they once existed.
(d) Treat them as false positives automatically.

### Question 46

**Scenario provenance only (not needed to answer):** FDA consumer update on medical device cybersecurity.

A hospital cyber-analytics project merges DHCP, local ARP, gateway ARP, and
switch MAC evidence for biomedical IoT devices. The merge key is only IP
address, even though DHCP reuse is common on that VLAN.

Which failure mode follows from IP-only merging?

(a) Active scans will be too slow.
(b) The inventory will contain too much device identity.
(c) Completeness will always be zero.
(d) Distinct observations may be merged incorrectly, erasing provenance and
creating false host claims.

### Question 47

**Scenario provenance only (not needed to answer):** NSA/CISA advisory AA23-278A on common
misconfigurations.

A scanner returns fewer office IoT and embedded devices after multicast
discovery is run from a VPN interface than when the collector is plugged into
the office VLAN.

Which explanation follows from multicast observability?

(a) Interface binding and routed boundaries can change multicast observability.
(b) The office devices were remediated between runs.
(c) The lower VPN count proves the devices left the office VLAN during the scan.
(d) Discard local VLAN evidence because the VPN is the central collection path.

### Question 48

**Scenario provenance only (not needed to answer):** CISA alert on heightened DDoS threats from Mirai and
related botnets.

An IoT discovery table has a high row count but many rows are stale, duplicated,
or broadcast artifacts. Soundness is the fraction of admitted rows that are real
current in-scope devices.

Which metric is harmed by these admitted-row defects?

(a) Completeness only.
(b) Discovery gap only.
(c) Soundness.
(d) Time-to-first-host only.

### Question 49

**Scenario provenance only (not needed to answer):** Maersk public cyber-attack update following NotPetya.

During rebuilding, the first warehouse-device host record appears in 12 seconds,
but the inventory keeps changing for 30 minutes as more discovery methods
finish. The cyber-analytics system streams provisional host records before the
full measurement run is complete.

How is the moving inventory interpreted under streaming discovery?

(a) Early rows are invalid until the final method ends.
(b) Streaming discovery can provide provisional partial truth, but the moving
inventory must be read with explicit incompleteness.
(c) The first host record is the entire baseline.
(d) Time-to-first-host replaces completeness and soundness.

### Question 50

**Scenario provenance only (not needed to answer):** Verkada March 2021 security incident report.

A camera host record contains IP address, MAC address, source methods,
timestamps, collector vantage, observed reachability, and uncertainty notes. It
does not contain final product identity or downstream risk ranking. The
discovery-stage handoff is supposed to preserve host-existence evidence for
later cyber analytics without pretending to finish later stages.

Which answer matches the stated handoff contract?

(a) The record is incomplete because discovery must finish downstream analysis.
(b) The record is invalid because uncertainty notes are removed.
(c) The record is rejected unless it includes all cloud account details.
(d) The record is a correct discovery-stage handoff artifact.
