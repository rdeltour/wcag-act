ACT Framework Requirements
==========================

Abstract
--------

The Accessibility Conformance Testing Framework will be a W3C specification, developed by the ACT Taskforce, lead by the WCAG Working Group. This document outlines the requirements for the ACT Framework. The ACT Framework is one part of the deliverables of the ACT Taskforce, for more details on this read [[ACT Deliverables]].

Status of This Document
-----------------------

This is the first draft of this document, it has not yet had the full review of the ACT Taskforce. It is therefore likely to change significantly.


1. Introduction
---------------

There are many accessibility test tools (ATTs). These can be fully automatic, or can prompt a user for specific actions, in order to discover accessibility issues of some digital product. Each of these tools will run one, or a serie of tests to come to some result. These test procedures may be designed to look for violations of WCAG 2.0, or some other accessibility standard, and for some that are highly customizable they can even be used in testing an organization's own accessibility policy. The test procedures used by ATT are often called 'rules'.

The ACT Framework will standardize those aspects all rules have in common that ensure them to be reliable, implementable by different ATTs and transparent for the users of this tool. By standardizing this, the ACT Taskforce aims to promote a common understanding of how accessibility can be tested for certain technologies.

Simply put, the ACT Framework is a standard on how to write test rules. Rules written in conformance to the ACT Framework specification are referred to as ACT Rules. These in turn are test procedures for accessibility, that can be implemented by ATTs or used for testing of accessibility.

The ACT Framework should ensure that:

# ACT Rules should be clear
# ACT Rules are grounded in underlying requirement
# ACT Rules provide correct results
# Accuracy of ACT Rules is measurable
# ACT Rules evolve along side web technologies
# Existing rulesets can be transformed to ACT Rules

2. Requirements
---------------

### 2.1 ACT Rules Should be Clear

ACT Rules have different audiences. These include the developer of test tools, QA testers who may have to run through the rules manually or with the aid of a tool, as well as accessibility experts who should understand what the tools they use can do, so that they can be informed on where a tool might not test, and where potential false positives might occur.

Because ACT Rules both a technical and non-technical audience, the ACT Framework should work out a balance between the two. Tool developers should have a good idea of what the rule should do, without the ACT Rule being written as pseudo code, as this is not well understood by non-technical readers.

### 2.2 ACT Rules Are Grounded In Underlying Requirement

Interpretation difference in web accessibility is a common problem, and one of the motivations behind the ACT Project. It leads to a confusion and wasted effort on the part of teams trying to make their products accessible. The ACT Framework should therefore ensure that ACT Rules are well grounded in the requirements they test. It is insufficient for an ACT Rule to simply claim something violates a requirement. The ACT Framework has to ensure that ACT Rules document why it's claims are in line with the requirement. The ACT Framework steer ACT Rules away from common pitfalls in interpreting accessibility requirements.

### 2.3 ACT Rules Provide Correct Result

The ACT Framework has to ensure that ACT Rules can be implemented in a way that provides consistent results. The ACT Framework has to ensure that if an ACT Rule should not be implemented in a tool, that this is clear to the developer. For example: an ACT Rule that requires testing stylesheets should not be implemented in a tool incapable of doing so. The ACT Framework has to ensure this is clear, both to developers of ATT and to their users.

Additionally, the ACT Framework must make sure that implementors of an ACT Rule can validate that the implementation was correct. This is different from testing the accuracy of the rule. The test procedure in a rule can still lead to false positives, even if the implementation is correct. The important part here is that the ACT Framework ensures that two implementers come to the same conclusion when testing the same content.

### 2.4 Accuracy of ACT Rules is Measurable

Accessibility testing is rarely 100% accurate. Fully understanding the context of the content that is tested can be difficult for anyone who wasn't involved in it's creation. Even more so when writing rules that should be able to test everything it is applicable to. It is important for users of accessibility test tools to know how reliable the rules are that they use. For some ATT users, accuracy may be less of an issue, and by using less accurate rules, greater test coverage can be gained, for others accuracy can crucial as false positives might cause significant holdups or may even have legal consequences.

Because of this, the ACT Framework will need to ensure that ACT Rules can be tested for accuracy. This may be limited to an environment. For example, it is likely an ACT Rule used on Arabic websites from 2001 will have a different level of accuracy then it would for English language web apps. How exactly this will be dealt with is to be decided during the development.

### 2.5 ACT Rules Evolve Along Side Web Technologies

As web technologies change, the rules for testing them should change as well. Rules may require change for many reasons, including changes to the markup language, changes to assistive technologies, even major changes to JavaScript frameworks may require a change to ACT Rules, as perhaps a rare technique that a rule might not have tested for is now much more common.

Because of this it is important that ACT Framework outlines a way to deal with that. Rules should be dated and versioned, so that users of rules can understand that a rule needs to be updated. A possible approach to this could be semantic versioning, although there are many other possibilities.

### 2.6 Existing Rulesets can be Transformed to ACT Rules

There currently exist a number of rulesets with similar functions to what ACT rules would be. Examples of these are the Auto-WCAG Ruleset, the WCAG rules of the Open Ajax Alliance as well as the documentation of rules implemented in specific automated test tools.  The ACT Framework will be designed in a way that these rulesets can be transitioned to the ACT Framework format. The ACT Taskforce will assist organizaitons interested in this effort, as part of the development of the ACT Framework. Doing this, at least once, will be part of the ACT Framework development process.

Definitions
-----------

### Rule

A rule is the description of the procedure used to evaluate the status (pass or fail) of one ore more conditions of a requirement in a given context.

The rule defines:

* the context in which it is applicable (e.g. a set of elements in a DOM)
* a set of assumptions about the environment (e.g. the way in which technologies are used)
* a set of logical steps to carry out the procedure
* a set of possible results

### Test

A test is the application of a rule.

### Requirement

A requirement is a statement of necessity in a given domain (e.g. accessbility). It can be broken down into a set of conditions.