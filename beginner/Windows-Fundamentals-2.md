# Windows Fundamentals 2

![Windows Fundamentals 2](Windows-Fundamentals-2.png)

## Room Information

| Category | Details |
|------------|----------------|
| Platform | TryHackMe |
| Room | Windows Fundamentals 2 |
| Difficulty | Easy |
| Completion Status | ✅ Completed |
| Room Type | Walkthrough |

---

# Objective

This room explores the internal structure of the Windows operating system and introduces several administrative tools used by both system administrators and cybersecurity professionals.

The room focuses on understanding system configuration, monitoring utilities, file systems, and management tools that are essential when investigating or maintaining Windows environments.

---

# Learning Outcomes

After completing this room I can:

- Navigate built-in Windows administrative tools
- Understand the purpose of Microsoft Management Console (MMC)
- Explore Computer Management features
- Use System Information to gather host details
- Identify important Event Viewer logs
- Understand Task Scheduler and Task Manager
- Explain Windows Registry basics

---

# Task 1 - Introduction

Windows includes numerous built-in tools that simplify system administration and troubleshooting.

These utilities provide information about:

- Hardware
- Software
- System configuration
- Performance
- Security events

Understanding these tools is an important foundation for both IT support and cybersecurity roles.

---

# Task 2 - System Configuration (MSConfig)

System Configuration (msconfig.exe) is a troubleshooting utility that allows administrators to manage startup processes and boot options.

### Features

- Normal startup
- Diagnostic startup
- Selective startup

It can also provide quick access to:

- System Information
- Event Viewer
- Command Prompt
- Registry Editor
- Task Manager

### Why It Matters

System Configuration helps isolate software issues and troubleshoot boot problems without reinstalling Windows.

---

# Task 3 - Microsoft Management Console (MMC)

Microsoft Management Console provides a framework for running administrative tools called snap-ins.

Examples include:

- Device Manager
- Disk Management
- Event Viewer
- Services

MMC allows administrators to customize management consoles for specific tasks.

---

# Task 4 - Computer Management

Computer Management combines multiple administration tools into a single interface.

It contains three major sections:

### System Tools

- Task Scheduler
- Event Viewer
- Shared Folders
- Local Users and Groups
- Device Manager

### Storage

- Disk Management

### Services and Applications

- Windows Services
- WMI Control

This console is commonly used for troubleshooting and system administration.

---

# Task 5 - System Information

System Information (msinfo32.exe) provides a detailed overview of a Windows machine.

Information includes:

- Operating System Version
- BIOS Version
- Processor
- Installed RAM
- Hardware Resources
- Components
- Software Environment

### Cybersecurity Relevance

System Information helps analysts quickly identify:

- Operating system versions
- Hardware configurations
- Installed software
- Potential vulnerabilities

---

# Task 6 - Resource Monitor

Resource Monitor provides real-time information about system resources.

It monitors:

- CPU usage
- Memory usage
- Disk activity
- Network activity

This tool is useful when investigating:

- High CPU usage
- Memory leaks
- Suspicious processes
- Network connections

---

# Task 7 - Command Prompt

Command Prompt (cmd.exe) allows administrators to interact with Windows using commands.

Common commands include:

```
ipconfig
hostname
whoami
systeminfo
tasklist
netstat
```

Command-line skills are essential for system administration and cybersecurity investigations.

---

# Task 8 - Registry Editor

The Windows Registry is a hierarchical database that stores operating system and application settings.

Registry Editor (regedit.exe) allows administrators to:

- View configuration settings
- Modify system behavior
- Troubleshoot software issues

### Main Registry Hives

- HKEY_CLASSES_ROOT
- HKEY_CURRENT_USER
- HKEY_LOCAL_MACHINE
- HKEY_USERS
- HKEY_CURRENT_CONFIG

### Security Note

Incorrect registry modifications can cause system instability, making backups important before making changes.

---

# Task 9 - Conclusion

Windows provides a comprehensive collection of administrative tools that simplify management and troubleshooting.

Understanding these utilities is valuable for:

- IT Support
- System Administration
- SOC Analysis
- Incident Response
- Digital Forensics

These tools are frequently used during investigations to identify system information, monitor activity, and diagnose problems.

---

# Key Cybersecurity Concepts Learned

✅ Windows Administration

Understanding built-in tools used for managing Windows systems.

✅ System Enumeration

Collecting information about hardware, software, and operating system configuration.

✅ Monitoring & Troubleshooting

Using Resource Monitor and Computer Management to investigate system performance.

✅ Registry Awareness

Recognizing the importance of the Windows Registry and its impact on system behavior.

---

# Skills Demonstrated

- Windows Operating System Fundamentals
- System Configuration
- Computer Management
- Event Viewer Navigation
- Resource Monitoring
- Registry Basics
- Command Line Fundamentals

---

# Tools & Technologies

- Microsoft Management Console (MMC)
- Computer Management
- System Information (msinfo32)
- Resource Monitor
- Command Prompt
- Registry Editor (regedit)

---

# Personal Notes

This room expanded my understanding of the administrative utilities built into Windows and how they support troubleshooting and security investigations. I learned how system information, resource monitoring, and registry management contribute to effective endpoint administration and provide valuable information during cybersecurity analysis.

---

## Repository Structure

```


```
