(1) What type of RFC is being requested (BCP, Proposed Standard, Internet Standard, Informational, Experimental, or Historic)? Why is this the proper type of RFC? Is this type of RFC indicated in the title page header?

draft-ietf-anima-grasp-distribution-04
Standards Track is indicated in the heading.
The document Updates *Extends* RFC8990, and should say so.

(2) The IESG approval announcement includes a Document Announcement Write-Up. Please provide such a Document Announcement Write-Up. Recent examples can be found in the "Action" announcements for approved documents. The approval announcement contains the following sections:

Technical Summary:

    This document proposes a set of solutions for information
    distribution in the Autonomic Network Infrastructure (ANI).
    Information distribution is categorized into two different modes:
    1) instantaneous distribution and
    2) publishing for retrieval.

    In the former case, the information is sent, propagated and disposed of after reception.
    In the  latter case, information needs to be stored in the network; additionally,
    conflict resolution is also needed when information stored in the
    network is updated with proposals from two different AFs.

Working Group Summary:

No.

Document Quality:

The use case section is well written, but it is not clear that the use cases are more than hypothetical.  The automotive examples definitely do not seem to have real-world demand at this point, and it is unclear how the an ACP/ANI would be formed among mutually distrustful vehicles.

Section 2.3 describes various 3GPP management functions that could be performed with an ANI, but from reading the section, it appears that 3GPP CT has adopted HTTP2.0/JSON for this use, not GRASP.

Section 2.4 describes In-Network Computing, but seems to lack references for topical things, such as "recently gets lots of attention".

The case for Data Backup would seem to be an interesting ANI/ACP function, as it is often difficult to arrange for the an appropriate level of priviledge to do backups: such an interface is subject to  exploitation and attack.  A system that could back it self up to a dataset that could be then distributed upon demand (fully encrypted) by an ANI would seem like a good thing.  Backups
could migrate from the node on which they are created through the ANI in an asynchronous manner, utilitizing spare bandwidth to move close to the NOC, where they could be placed on disconnectable storage ("tapes").
The example given in section 2.3, point 1) Data Backup, seems to have nothing to do with backups.
Point (2) seems to be about Hadoop.

In general, the use cases presented, aside from Data Backup as I envision it, do not seem to actually be relevant to an ANI and ACP.
I actually said this in January 2020:
   https://mailarchive.ietf.org/arch/msg/anima/hCv5bZxBrzSzA6BjA5DY7_RDo6U

A request was made for more protocol oriented description:
https://mailarchive.ietf.org/arch/msg/anima/7L8SmTZXi4cI2IaE7PD0YX37WWM/

section 3:
    For reasons well-understood,
    this approach has its limits in larger and denser networks.

please cite issue and background here.

I found section 4.2.1 underspecified and too abstract. Mention was made of a Distributed Hash Table, but more detail would certainly be needed to actually implement anything.
The word "can" is used a lot, which is not really helpful.
Superman *can* leap buildings in a single bound, but should he?  Sometimes the front door and the elevator is easier.  The document SHOULD tell me which one to implement.





Personnel:

Who is the Document Shepherd?              Michael Richardson
Who is the Responsible Area Director?      Robert Wilton


(3) Briefly describe the review of this document that was performed by the Document Shepherd. If this version of the document is not ready for publication, please explain why the document is being forwarded to the IESG.

This -04 document was read from beginning to end.

(4) Does the document Shepherd have any concerns about the depth or breadth of the reviews that have been performed?

The document has not received a lot of attention in the WG.
The document does not provide a reasonable Security Considerations examination of what happens with these new GRASP methods.

(5) Do portions of the document need review from a particular or from broader perspective,
    e.g.,   security, operational complexity, AAA, DNS, DHCP, XML, or internationalization?
    If so,   describe the review that took place.

No.

(6) Describe any specific concerns or issues that the Document Shepherd has with this document that the Responsible Area Director and/or the IESG should be aware of? For example, perhaps he or she is uncomfortable with certain parts of the document, or has concerns whether there really is a need for it. In any event, if the WG has discussed those issues and has indicated that it still wishes to advance the document, detail those concerns here.

It's not clear that the document is more than a research paper.
Will it result in any actual running code?
Many protocol parts that should be prescriptive are speculative, using "can" rather than SHOULD/MUST.
No running code is mentioned.

(7) Has each author confirmed that any and all appropriate IPR disclosures required for full conformance with the provisions of BCP 78 and BCP 79 have already been filed. If not, explain why?

Not as yet.

(8) Has an IPR disclosure been filed that references this document? If so, summarize any WG discussion and conclusion regarding the IPR disclosures.

One claim was made in 2016:
https://datatracker.ietf.org/ipr/2915/
The claim relates to an unpublished patent application.
It is now five years later, so the patent should either be visible, or the claim could perhaps be withdrawn.

(9) How solid is the WG consensus behind this document? Does it represent the strong concurrence of a few individuals, with others being silent, or does the WG as a whole understand and agree with it?

It represents the strong concurrence of a few individuals.
Much of the WG has ignored this document.

(10) Has anyone threatened an appeal or otherwise indicated extreme discontent? If so, please summarise the areas of conflict in separate email messages to the Responsible Area Director. (It should be in a separate email because this questionnaire is publicly available.)

No.

(11) Identify any ID nits the Document Shepherd has found in this document. (See http://www.ietf.org/tools/idnits/ and the Internet-Drafts Checklist). Boilerplate checks are not enough; this check needs to be thorough.

  ** The abstract seems to contain references ([RFC8990], [RFC7575]), which
     it shouldn't.  Please replace those with straight textual mentions of the
     documents in question.


(12) Describe how the document meets any required formal review criteria, such as the MIB Doctor, YANG Doctor, media type, and URI type reviews.

None.

(13) Have all references within this document been identified as either normative or informative?

YEs.

(14) Are there normative references to documents that are not ready for advancement or are otherwise in an unclear state? If such normative references exist, what is the plan for their completion?

I think that RFC8994 should be normative.

(15) Are there downward normative references references (see RFC 3967)? If so, list these downward references to support the Area Director in the Last Call procedure.

None.

(16) Will publication of this document change the status of any existing RFCs? Are those RFCs listed on the title page header, listed in the abstract, and discussed in the introduction? If the RFCs are not listed in the Abstract and Introduction, explain why, and point to the part of the document where the relationship of this document to the other RFCs is discussed. If this information is not in the document, explain why the WG considers it unnecessary.

No changes to existing documents are proposed.

(17) Describe the Document Shepherd's review of the IANA considerations section, especially with regard to its consistency with the body of the document. Confirm that all protocol extensions that the document makes are associated with the appropriate reservations in IANA registries. Confirm that any referenced IANA registries have been clearly identified. Confirm that newly created IANA registries include a detailed specification of the initial contents for the registry, that allocations procedures for future registrations are defined, and a reasonable name for the new registry has been suggested (see RFC 8126).

In version -04, the IANA section is still TBD.
As the document updates RFC8990, it will need to make a number of IANA Actions.

(18) List any new IANA registries that require Expert Review for future allocations. Provide any public guidance that the IESG would find useful in selecting the IANA Experts for these new registries.

Unknown.

(19) Describe reviews and automated checks performed by the Document Shepherd to validate sections of the document written in a formal language, such as XML code, BNF rules, MIB definitions, YANG modules, etc.

There is fragmentary CDDL, but it has not been validated.

(20) If the document contains a YANG module, has the module been checked with any of the recommended validation tools (https://trac.ietf.org/trac/ops/wiki/yang-review-tools) for syntax and formatting validation? If there are any resulting errors or warnings, what is the justification for not fixing them at this time? Does the YANG module comply with the Network Management Datastore Architecture (NMDA) as specified in RFC8342?

No YANG module.

