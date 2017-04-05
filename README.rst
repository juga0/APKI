APKI
====

a PKI for anonymity networks [#]_

Problem to solve with this project
-------------------------------------

Anonymity systems like mix networks [#]_ empower civil society by providing
meta-data privacy and encryption for systems like Email communication and
electronic voting.

Recent privacy networks like Loopix [#]_, Dissent [#]_, HORNET [#]_, Vuvuzela [#]_
have not seen much community adoption or development outside academia.

One obstacle is the lack of a flexible Public Key infrastructure (PKI) [#]_
which require features that go beyond X.509 [#]_ or PGP's Web-of-Trust [#]_.
Tor PKI [#]_ offers these features, but it can not be used outside of Tor and
it can still be improved.

How this project solves the problem
---------------------------------------

We will implement a PKI to help privacy and security systems move from
research to deployment more easily. We believe that a modular PKI will
lower the barrier to new volunteer (nodes) to participate in the network
and to build communities of server operators around these systems.

We will create an API to facilitate other projects with other designs to
use this PKI. We will primarily target stratified mix networks like
Loopix, a Possion or Stop-and-Go mix network design since we will
collaborate with researchers working in the area.
Also, stratified mix networks require a similar set of properties from
their PKI as do most other privacy system designs:

- Clients must know about all nodes, perhaps in designated epoch or
  historically.
- Nodes may need to be organized into a specific network topology and/or
  rotate key frequently.
- Nodes might be evaluated for security, trustworthiness, and performance.
- Nodes may have non-independent security properties, like
  being in the same data center. We hope to cover re-encryption mix
  networks as developed by the Panoramix [11] project for e-voting
  security too, but this requires further discussion.

Target group and how it benefits from this project
---------------------------------------------------

-  Developers of privacy tools.
-  Volunteer system administrators of anonymity networks.
-  End users would benefit indirectly when using privacy tools on
   anonymity networks, for instance, delivering Email using mix
   networks.

Status of the idea and new version
------------------------------------

We have discussed it with several projects.
Some new ideas comparing to Tor PKI:

- Both long-term signing and short-term routing key support.
- Hash chain reference to previous epoch.
- Support directory authorities not being directly reachable.
- Consensus fetching indistinguishable from normal traffic.
- Every node should act as a notary.
- Families should be generalized to allow overlaps.
- Support a cothority [#]_ like scheme that can be plugged in later.
- Client side should be simple to allow implementation in different languages.

Important milestones
---------------------

-  Further communication with projects interested in the PKI
   implementation, Tor, Panoramix, LEAP [#]_ and applied-mixnetworks [#]_.
-  Write an specification document about the design.
-  Implement the server side:
   -  Write a flexible API for network node information.
   -  Write node assessor stub or tool for Loopix.
   -  Implement stratified network placer.
-  Create a testbed.
-  Test integration with other projects.
-  Create documentation for end users, system administrators and
   developers.
-  Engineering project summary.
-  Promote the implementation.

Notes
-------

The detailed specifications are going to be developed in mixspecs [#]_
repository


References
----------

.. [#] Anonymous P2P: https://en.wikipedia.org/wiki/Anonymous_P2P

.. [#] Mix Network: https://en.wikipedia.org/wiki/Mix_Network

.. [#] The Loopix Anonymity System,
       paper: https://arxiv.org/abs/1703.00536,
       code: https://github.com/UCL-InfoSec/loopix/

.. [#] Dissent,
       paper: https://www.usenix.org/system/files/conference/osdi12/osdi12-final-115.pdf

.. [#] HORNET: High-speed Onion Routing at the Network Layer,
       paper: https://www.scion-architecture.net/pdf/2015-HORNET.pdf

.. [#] Vuvuzela: Scalable private messaging resistant to traffic analysis,
       paper: https://people.csail.mit.edu/nickolai/papers/vandenhooff-vuvuzela.pdf,
       news: http://news.mit.edu/2015/untraceable-anonymized-communication-guaranteed-1207,
       code: https://github.com/vuvuzela/vuvuzela

.. [#] Public Key Infrastructure: https://en.wikipedia.org/wiki/Public_key_infrastructure

.. [#] X.509 security: https://en.wikipedia.org/wiki/X.509#Security

.. [#] Web of trust: https://en.wikipedia.org/wiki/Web_of_trust

.. [#] Tor protocol specification: https://gitweb.torproject.org/torspec.git/tree/tor-spec.txt,
       Tor directory protocol: https://gitweb.torproject.org/torspec.git/tree/dir-spec.txt>,
       tor-dev proposal Consensus Hash Chaining: https://lists.torproject.org/pipermail/tor-dev/2015-January/008087.html

.. [#] Panoramix: https://panoramix-project.eu/

.. [#] Cothority: https://github.com/dedis/cothority

.. [#] LEAP: https://leap.se,
       LEAP documentation: https://github.com/leapcode/leap_doc

.. [#] applied-mixnetworks: https://github.com/applied-mixnetworks

.. [#] mixspecs: https://github.com/applied-mixnetworks/mixspecs/blob/master/proposals/apki_spec.rst

Other references
-----------------
Sphinx: A Compact and Provably Secure Mix Format,
paper: http://research.microsoft.com/en-us/um/people/gdane/papers/sphinx-eprint.pdf,
code: https://cryps.uwaterloo.ca/software/Sphinx-0.8.tar.gz

Panoramix,
code: https://github.com/grnet/panoramix

Tahoe-Lafs: https://tahoe-lafs.org
