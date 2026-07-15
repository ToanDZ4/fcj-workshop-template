---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives
* Understand AWS identity and access management (IAM) and the shared responsibility model.
* Learn about users, groups, roles, and policies, and how to apply the principle of least privilege.
* Practice securing the root account and creating scoped IAM identities for the capstone project.

> Note: 30/04 and 01/05 are public holidays in Vietnam, so this week the practical work was scheduled around them.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Learn the shared responsibility model <br> - IAM users, groups, roles, policies | 27/04/2026 | 27/04/2026 | <https://docs.aws.amazon.com/IAM/> |
| Tue | - Enable MFA on the root account <br> - Create an admin IAM user and group <br> - Set a password policy | 28/04/2026 | 28/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Wed | - Learn policy structure (Effect, Action, Resource, Condition) <br> - Write custom JSON policies | 29/04/2026 | 29/04/2026 | <https://docs.aws.amazon.com/IAM/> |
| Thu | Public holiday (Reunification Day) | 30/04/2026 | 30/04/2026 | |
| Fri | Public holiday (International Labour Day) | 01/05/2026 | 01/05/2026 | |

### Week 2 Achievements
* Understood the shared responsibility model — what AWS secures vs. what the customer secures.
* Secured the account: enabled MFA on root, stopped using root for daily work, created an administrator IAM user/group and a strong password policy.
* Learned IAM policy anatomy and wrote least-privilege JSON policies scoped to specific resources.
* Created the first service roles needed later for the capstone (for example an `ecsTaskExecutionRole` for ECS tasks), and understood the difference between IAM users and IAM roles.
* Practiced testing effective permissions with the IAM Policy Simulator.
