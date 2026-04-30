Login System with Attempt Blocking
A C++ console application that simulates a secure login system with user blocking, security alerts, and a detailed failure rate report.

*Description

This program implements a multi-user login system that tracks failed login attempts per user, detects suspicious activity across sessions, and generates a security report when the failure rate exceeds a defined threshold.

* Features

Multi-user login with predefined credentials
Per-user attempt tracking — blocks a specific user after 3 failed attempts
Global session tracking — monitors every login attempt across all users
Security alert — triggers after 5 consecutive attempts in a session
Failure rate calculation — if the failure rate exceeds 60%, the system locks down and prints a full security report
Login history log — stores usernames, passwords, and status (CONFIRMED / FAILED) for each attempt

* Requirements

A C++ compiler (g++, clang++, or MSVC)

* Valid Credentials (for testing)

Username   Password
admin      HardPass123*
user1      Pass456!
user2      Secret789!


Security Rules
RuleBehavior3 failed attempts for a userThat user gets flagged as blocked5 consecutive attempts in sessionSecurity alert is displayedFailure rate > 60%System shuts down and prints full security reportFailure rate ≤ 59%Counters reset, session continues normally

Security Report Example
When the failure rate exceeds 60%, the system outputs a report like this:

========== SECURITY REPORT ==========
--- Record #1 ---
 User: admin
 | Password: wrongpass
 | Status: FAILED

-----------------------------------------

Successful attempts: 1
 Failure rate: 80%
 ***ALERT: HIGH FAILURE RATE - POSSIBLE ATTACK***

 Limitations

Credentials are hardcoded in the source file
History log is limited to 5 entries per session (array size)
No persistent storage — all data is lost when the program exits
No password hashing (this is a learning/demo project)

Concepts Practiced

Arrays and loops in C++
Boolean logic and conditionals
String comparison
Security concepts: attempt limiting, failure rate, session tracking
