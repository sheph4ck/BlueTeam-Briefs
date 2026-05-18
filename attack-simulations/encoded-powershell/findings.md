# Encoded PowerShell Execution Detection

## Objective

The goal of this lab was to simulate suspicious PowerShell activity and investigate how the activity appeared in Sysmon and Splunk logs.

This type of activity is commonly associated with attacker obfuscation and malicious script execution.

---

## Attack Simulation

The following PowerShell command was executed on the Windows test machine:

```powershell
powershell.exe -enc ZQBjAGgAbwAgACIASABlAGwAbABvACI=
```

This command launches PowerShell using an encoded command argument.

---

## Telemetry Observed

### Sysmon Event ID
- Event ID 1 (Process Creation)

### Important Indicators
- powershell.exe
- -enc
- Encoded command execution

### Relevant Log Fields
- Image
- CommandLine
- ParentImage
- User

---

## Splunk Investigation

### Splunk Search Query

```spl
index=* EventCode=1 Image="*powershell.exe*" CommandLine="*-enc*"
```

### Findings

The encoded PowerShell execution was successfully captured by Sysmon and ingested into Splunk.

The CommandLine field clearly showed the use of the `-enc` argument.

This type of execution may indicate:
- obfuscation
- malware execution
- attacker tradecraft
- defense evasion

---

## Detection Opportunities

Monitoring for encoded PowerShell execution can help identify suspicious scripting activity on Windows systems.

Potential detection opportunities include:
- Base64 encoded commands
- Hidden PowerShell execution
- PowerShell spawned from Office applications
- Unusual parent-child process relationships

---

## MITRE ATT&CK Mapping

### Technique
- T1059.001 — PowerShell

### Tactic
- Execution

---

## Lessons Learned

This lab demonstrated how Sysmon process creation logging can be used to detect suspicious PowerShell activity.

It also reinforced the importance of centralized logging and command-line visibility for Blue Team investigations.