# RHCSA Practical Administration Lab Framework
**Design date:** 2026-10-11  
**Status:** Proposed learning method; lab execution and mastery NOT yet demonstrated  
**Environment:** Existing RHEL 10 virtual machine, Red Hat Developer subscription  
**Scope:** RHCSA-centered Linux system administration practice; retain broader RHCA aspirations without confusing current certification stage.

## Problem this framework solves

Knowing what `chmod`, `chown`, `chgrp`, and `usermod` mean is not the same as independently deciding which operation to use, in what order, and how to verify that the intended system state exists. Multiple-choice recognition cannot substitute for actual administration.

**Training objective:** progressively transform an unfamiliar system requirement into a reasoned plan, executed commands, authentic system evidence, and a verified resolution.

## Relationship to existing learning

- **Current priority:** NOS-120 Chapter 4 and upcoming assessments. This plan is parked until practice time is available.
- **Guided foundation:** DO → SEE → NAME → REMEMBER (type a command; observe realistic output; name each part; reinforce/retest).
- **Practical progression:** PROBLEM → INSPECT → PLAN → EXECUTE → TROUBLESHOOT → VERIFY → DOCUMENT → RETEST.
- **Course/cert alignment:** Map tickets to current NOS-120 topics and the official RHCSA EX200 exam objectives. Verify the relevant exam version before claiming coverage. Sander van Vugt course material can guide sequencing.
- **Do not misidentify Red Hat's generic Interactive Labs catalog as a complete RHCSA lab curriculum.** No AI command assistant is required to administer the VM; independent command selection is the point.

## Six-stage administration cycle

1. **Understand the request:** Rewrite the desired final state and constraints. Identify what counts as success.
2. **Inspect:** Determine current users, groups, filesystem ownership, permissions, services, configuration, and other relevant state; don't assume the starting condition.
3. **Plan:** Select operations based on observed state. Explain why each operation is necessary before issuing it.
4. **Execute and troubleshoot:** Type commands on the real VM; distinguish syntax errors, permission failures, wrong targets and partial success. Consult local `man` and built-in help as appropriate.
5. **Verify:** Collect authentic terminal output. Test behavior as the intended user or process; where relevant, test persistence after reboot. A successful command exit is not sufficient evidence of the requested outcome.
6. **Document and retest:** Keep a dated engineering record, return with changed names/conditions after a delay, and eventually solve a new ticket without hints.

## Four training modes

| Mode | Assistance | Evidence of competence |
| --- | --- | --- |
| Guided | Full DO → SEE → NAME → REMEMBER scaffolding | Exposure/understanding; NOT independent mastery |
| Assisted | Related task; hints available when requested | Partial performance; record hints |
| Independent | State the business/technical requirement and constraints; no command recipe | Working system state plus independently collected verification |
| Timed exam-style | Unfamiliar multi-step objective-mapped tasks; no outside hints | Reliable completion, troubleshooting, verification and time management |

Avoid switching a learner to independent mode before the underlying mechanism has been taught. Separate **coverage failure** (not yet taught) from **retrieval failure** (taught but forgotten).

## Example seed scenario: employee access to a shared directory

**Scenario:** A new employee requires appropriate access to a shared project directory.

**Learner's questions:** Does the account already exist? Which group should govern access? Is the employee a member? Who owns the directory? Which mode/ACL applies? Can the employee enter, list and perform authorized actions? Can unauthorized users be excluded?

**Teach first as atomic operations:** inspecting accounts and identity, checking group membership, reading permissions, creating/managing groups and users, changing directory group ownership, setting safe access modes, testing access. **Only then** combine into an independent ticket.

**Sample independent ticket, after prerequisites are covered:** “Ensure account `analyst1` can enter `/srv/teamshare` and create files there through the `teamshare` group, while an unrelated ordinary user cannot create files there. Preserve existing approved access. Demonstrate both outcomes using authentic system evidence.” This is a proposed design example, not an exercise already performed.

## Standard ticket fields

- Ticket ID, title, date, Linux/RHEL version, objective alignment, prerequisites
- Starting state and safe snapshot/reset point
- Desired state, constraints, success/failure tests
- Guided/assisted/independent mode and hints used
- Commands typed, actual output, errors, diagnosis and repair
- Verification commands, observed evidence, persistence checks where relevant
- Final result: achieved, partial, failed, or unknown
- Next varied/delayed retest and engineering lessons


## Engineering competency evidence and learning progression

A completed guided lab, a high quiz score, and an independently administered system are **different forms of evidence**. Record them honestly; do not infer independent mastery from task completion alone.

For each practical ticket, record:

- **Starting capability and prerequisites:** what concepts or atomic operations were already taught, and whether this is first exposure, practice, or retest.
- **Assistance level:** Guided, Assisted, Independent, or Timed Exam-Style; note each substantive hint or supplied command without treating help as failure.
- **Operator decisions:** the requested end state, initial observations, proposed steps, why each was selected, and any choice to execute discrete operations with verification between them.
- **Authentic evidence:** commands actually run, relevant output, errors, corrections, final system state, and tests that demonstrate success or failure. Never manufacture results or present examples as executions.
- **Competency status:** exposed, completed with assistance, completed independently, independently reproduced on a varied scenario, or not yet demonstrated. Include the date and environment, not just a percentage.
- **Follow-up:** what remains uncertain and which changed-condition or delayed retest will establish retention and transfer.

Progress from guided to assisted to independent work **only after the required mechanisms have been introduced and practiced**. Record insufficient instructional coverage separately from a failure to recall something already taught. Timed performance is an additional skill, not a substitute for untimed competence. Prefer one operation and verification at a time when learning or troubleshooting; teach combined commands only when their behavior and trade-offs are understood.

The long-term portfolio should show **how independent operating competence was acquired, tested, verified, and improved**, including unsuccessful attempts and troubleshooting—not merely a collection of completed assignments. This framework complements the separate adaptive knowledge-tutoring method; neither replaces the other.

## Student authorship and cross-session continuity

**Documentation is itself a skill to be learned and demonstrated.** The assistant may initially model how to write a professional lab or incident entry, but must progressively shift responsibility to the student: **demonstrate → co-write → student drafts with review → independent documentation**. Distinguish assistant-written examples or earlier polished records from student-authored, verified entries. Give specific feedback on clarity, evidence, reasoning and reproducibility rather than silently rewriting the student's work as the default.

**Continuity across conversations:** Treat this repository's README, practical framework, current objective-mapped exercises and dated results as durable instructional context. When resuming in a new chat, review those records, identify what was taught versus independently demonstrated, what help was needed, the last verified machine state, unresolved issues and next exercise. Do not assume the assistant retains prior conversation state, and do not treat old VM state as current without checking. Update progress records following real work while preserving failures, evidence and history. Never include secrets or sensitive personal information.

The practical administration framework complements, rather than replaces, the separate adaptive knowledge-tutoring methodology. The aim is independent Linux administration **and** independent technical documentation.

## Safety and integrity

Use a **dedicated nonproduction RHEL VM** rather than graded coursework systems. Snapshot before high-risk storage, boot, firewall or network changes. Never commit passwords, tokens, account secrets or sensitive personal records. Use placeholder names and illustrative data in published labs. Keep genuine terminal evidence distinct from example output. Do not run learner commands automatically or present an exact string match as verified administration.

## Initial rollout (not started)

1. Preserve this learning design without interrupting the current midterm study.
2. Check the existing RHEL 10 VM, tool access and snapshot workflow.
3. Create the first small, objective-mapped lab from already-taught concepts.
4. Work through it with one instruction at a time; journal the actual result and mistakes.
5. Issue a varied task without command hints; repeat after a delay.
6. Expand by RHCSA objective domain (users/groups, permissions, files, services, processes, networking, storage/LVM, SELinux, boot, containers, etc.) as applicable to the current official exam blueprint.

**Success standard:** Independently diagnose and administer a running Linux system—not merely remember command names or earn a high score on recognition questions.
