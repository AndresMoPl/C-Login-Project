[C-Login-Project-README.md](https://github.com/user-attachments/files/32221658/C-Login-Project-README.md)
# C++ Login System with Attempt Blocking

A C++ console application that simulates a secure login system with per-user attempt blocking, session-wide security alerts, and an automatic failure-rate security report — built as an introduction to core cybersecurity concepts in C++.

## Description

This program implements a multi-user login flow that:

- Tracks failed login attempts **per user**
- Detects suspicious activity **across the whole session** (not just per user)
- Automatically generates a detailed security report when the overall failure rate crosses a defined threshold

## Features

- **Multi-user login** with a set of predefined credentials
- **Per-user attempt tracking** — a user is flagged/blocked after 3 failed attempts
- **Global session tracking** — every login attempt across all users is monitored
- **Security alert** — triggered after 5 consecutive failed attempts in a session
- **Failure-rate calculation** — if the failure rate exceeds 60%, the system locks down and prints a full security report
- **Login history log** — records username, password entered, and status (`CONFIRMED` / `FAILED`) for each attempt

## Security rules

| Rule | Behavior |
|---|---|
| 3 failed attempts for a user | That user is flagged as blocked |
| 5 consecutive failed attempts in the session | Security alert is displayed |
| Failure rate > 60% | System locks down and prints the full security report |
| Failure rate ≤ 60% | Counters reset, session continues normally |

## Example security report

When the failure rate exceeds 60%, the system prints a report like this:

```
========== SECURITY REPORT ==========
--- Record #1 ---
User: admin | Password: wrongpass | Status: FAILED
...
Successful attempts: 1
Failure rate: 80%
ALERT: HIGH FAILURE RATE - POSSIBLE ATTACK
```

## Getting started

### Requirements

A C++ compiler (`g++`, `clang++`, or MSVC).

### Build & run

```bash
git clone https://github.com/AndresMoPl/C-Login-Project.git
cd C-Login-Project
g++ Login.cpp -o login
./login
```

### Test credentials

| Username | Password |
|---|---|
| `admin` | `HardPass123*` |
| `user1` | `Pass456!` |
| `user2` | `Secret789!` |

## Concepts practiced

- Arrays and loops in C++
- Boolean logic and conditionals
- String comparison
- Basic security concepts: attempt limiting, failure-rate analysis, session tracking

## Known limitations

This is a learning/demo project, not production security software:

- Credentials are hardcoded in the source file
- The history log is limited to 5 entries per session (fixed-size array)
- No persistent storage — all data is lost when the program exits
- No password hashing

## Author

**Andrés Mora** — [@AndresMoPl](https://github.com/AndresMoPl)
