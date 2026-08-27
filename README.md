# ICDFA Web Application Security — Practical Lab 1

## Lab 1: Lab Assurance, HTTP Mapping and Attack-Surface Reconnaissance

**Student:** Muhammad Modu Kunjo  
**Course:** Web Application Security  
**Lab:** Practical Lab 1 of 5  
**Assessment Period:** 24 August 2026 – 6 September 2026  
**Assessment Deadline:** 26 August 2026, 11:59 PM WAT  
**Maximum Score:** 100 marks  
**Lab Category Weight:** 20%

---

## 1. Purpose

This laboratory exercise establishes and validates an isolated web application
security testing environment before exploitation or vulnerability testing.

The exercise focuses on:

- Laboratory isolation and scope validation
- Application readiness and reset verification
- Snapshot/checkpoint validation
- HTTP request and response baselining
- Proxy/interception workflow preparation
- Technology fingerprinting
- Endpoint and input discovery
- Cookie and session identification
- Low-rate content discovery
- Comparative attack-surface mapping of DVWA and OWASP Mutillidae II

All testing is performed only against locally installed vulnerable
applications within the authorised training environment.

---

## 2. Authorised Scope

### In Scope

The following applications are authorised targets:

| Application | URL | Purpose |
|---|---|---|
| Mutillidae II | `http://127.0.0.1/` | Vulnerable web application |
| DVWA | `http://127.0.0.1:8080/DVWA/` | Vulnerable web application |

The following activities are permitted:

- Application navigation
- Normal HTTP request/response inspection
- Passive traffic analysis
- Cookie identification
- Input-point identification
- Technology fingerprinting
- Low-rate content discovery
- Manual validation of discovered resources
- Application reset and baseline verification

---

## 3. Out of Scope

The following are explicitly excluded:

- Public Internet systems
- Hospital production systems
- Office systems and workstations
- Unauthorised hosts
- Third-party systems
- Other users' applications or accounts
- High-rate or disruptive scanning
- Denial-of-service testing
- Testing outside the assigned vulnerable applications
- Any system not explicitly authorised by the course instructions

---

## 4. Stop Conditions

Testing must stop immediately if:

1. Traffic is observed leaving the authorised laboratory environment.
2. An unrelated host or service is discovered as a target.
3. Either vulnerable application becomes unstable or unavailable.
4. The testing environment loses its intended isolation.
5. Credentials or sensitive information belonging to an unrelated system are encountered.
6. An action could affect systems outside the authorised scope.

The environment should be restored to the clean baseline snapshot when necessary.

---

# 5. Laboratory Environment

## Security VM

**Operating System:** Kali Linux  
**Primary Interface:** `eth0`  
**Host-only IP:** `192.168.56.101/24`

### Network Configuration

The Kali VM is configured using a **Host-only Adapter**.

The current routing configuration does not contain a default route.

This configuration is intended to prevent normal external network access while
allowing the VM to communicate with the designated host-only environment.

---

## Local Application Services

### Mutillidae II

```text
URL: http://127.0.0.1/
Port: 80
Deployment: Docker
