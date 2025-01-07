# Initia Rollup Modules audit details
- Total Prize Pool: $60,000 in USDC
  - HM awards: $48,300 in USDC
  - QA awards: $2,000 in USDC
  - Judge awards: $5,800 in USDC
  - Validator awards: $3,900 in USDC
- [Read our guidelines for more details](https://docs.code4rena.com/roles/wardens)
- Starts January 7, 2025 20:00 UTC
- Ends January 21, 2025 20:00 UTC

**Note re: risk level upgrades/downgrades**

Two important notes about judging phase risk adjustments: 
- High- or Medium-risk submissions downgraded to Low-risk (QA)) will be ineligible for awards.
- Upgrading a Low-risk finding from a QA report to a Medium- or High-risk finding is not supported.

As such, wardens are encouraged to select the appropriate risk level carefully during the submission phase.

# Overview

The OPinit Stack is a versatile framework designed for CosmosSDK, facilitating the development of vm-agnostic Optimistic Rollups. 

This framework aligns closely with the interface of Optimism's Bedrock, promoting a straightforward user experience. Leveraging the Initia L1 Governance model, it addresses fraud-proof disputes efficiently.

## Links

- **Previous audits:**  https://github.com/Zellic/publications/blob/master/Initia%20-%20Zellic%20Audit%20Report.pdf
- **Documentation:** https://initialabs-develop.mintlify.app/
- **Website:** https://initia.xyz/
- **X/Twitter:** https://x.com/initia
- **Discord:** https://discord.gg/initia

---

# Scope

**OpInit Modules**
- Source code location: https://github.com/initia-labs/OPinit
- Source code version: [7da22a78f367cb25960ed9c536500c2754bd5d06](https://github.com/initia-labs/OPinit/commit/7da22a78f367cb25960ed9c536500c2754bd5d06)
- Files:
	- x/opchild/**
	- x/ophost/**

**OpInit Bots**
- Source code location: https://github.com/initia-labs/opinit-bots
- Source code version: [640649b97cbfa5782925b7dc8c0b62b8fa5367f6](https://github.com/initia-labs/opinit-bots/commit/640649b97cbfa5782925b7dc8c0b62b8fa5367f6)
- Files:
	- challenger/**
	- executor/**
	- node/** 
	- merkle/** 
	- provider/**

# Additional context

## Main invariants

1. Anyone can initiate an L2 and create a bridge on L1.
2. Governance has the authority to update the L2 bridge owner and challenger.
3. Anyone can submit a governance proposal to challenge or change an abnormal L2 operator or challenger by providing a deposit. (Invalid proposals may result in the forfeiture of the deposit.)

## Attack ideas (where to focus for bugs)

Liveness of OPinit bots

## All trusted roles in the protocol

Governance account (L1 validators)

## Running tests

```bash
# OPinit cosmos modules
git clone https://github.com/initia-labs/OPinit
(cd OPinit && make test)

# OPinit bots
git clone https://github.com/initia-labs/opinit-bots
(cd opinit-bots && make test)
```

## Miscellaneous
Employees of Initia and employees' family members are ineligible to participate in this audit.

Code4rena's rules cannot be overridden by the contents of this README. In case of doubt, please check with C4 staff.
