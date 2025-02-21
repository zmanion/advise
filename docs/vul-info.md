# Vulnerability Information Element Mapping

VINCE-NT can export and publish in multiple formats.  This document explains how vulnerability information elements in VINCE-NT are mapped to external formats, primarily the [CVE Record Format](https://github.com/CVEProject/cve-schema), the [CSAF VEX Profile](https://docs.oasis-open.org/csaf/csaf/v2.0/os/csaf-v2.0-os.html#45-profile-5-vex), and [OpenVEX](https://github.com/openvex).

This is a work in progress.

A CSAF document contains one or more vulnerabilities.

## Acknowledgments

OpenVEX is not a full vulnerability advisory format and does not support credit or acknowledgments.

| VINCE-NT | CVE | CSAF | Notes |
| :--- | :--- | :--- | :--- |
| | [credits](https://cveproject.github.io/cve-schema/schema/docs/#oneOf_i0_containers_cna_credits) | [Acknowledgments Type](https://docs.oasis-open.org/csaf/csaf/v2.0/os/csaf-v2.0-os.html#311-acknowledgments-type) | |
| Case, CSAF settings, Acknowledgments | N/A | `.document.acknowledgments[]`| |
| Case, Vulnerability | `.containers[].cna.credits[]` | `.vulnerabilities[].acknowledgments[]` | |
| Default `en-US` | `.lang` | | |
| Name | `.value` | `.names` | CVE `.value` can include CSAF `.names` and `.organization` |
| Organization | `.value` | `.organization` | CVE `.value` can include CSAF `.names` and `.organization` |
| N/A | `.user` | N/A | Not currently used by CVE |
| (add this) | [`.type`](https://cveproject.github.io/cve-schema/schema/docs/#oneOf_i0_containers_cna_credits_items_type) | |
| N/A | N/A | `.summary`| |
| (add this) | N/A | `.urls`| |
