# Linux Learning Curved (HKU InfoSec Track)

This guide is a condensed **beginner → advanced** Linux roadmap for information security study and exam preparation.

---

## How to Use This Document
1. Study one chapter at a time.
2. Run every command yourself on a Linux VM.
3. Complete the chapter activities before moving on.
4. Use the summary checklist to revise before tests/exams.
5. Use the wsl library and starting coding within ubuntu terminal to pratice linux coding
---

## Chapter 1: Linux Fundamentals
### Core topics
- Linux distributions (Ubuntu, Debian, RHEL, Arch) and package ecosystems
- Shell basics (Bash), terminal navigation, files/folders
- Absolute vs relative paths, hidden files, permissions preview

### Must-know commands
`pwd`, `ls`, `cd`, `mkdir`, `rm`, `cp`, `mv`, `cat`, `less`, `man`, `history`

### Trustworthy references
- Linux Journey: https://linuxjourney.com/
- Ubuntu command line intro: https://ubuntu.com/tutorials/command-line-for-beginners
- GNU Bash manual: https://www.gnu.org/software/bash/manual/bash.html

### Stack Overflow examples
- Difference between `./`, `/`, and `~`: https://stackoverflow.com/questions/11744982
- `rm -rf` meaning: https://stackoverflow.com/questions/790686

### Activity
- Create a folder tree for a fake project and practice creating, moving, copying, and deleting files safely.

### Summary
- You should now navigate Linux confidently and read basic docs with `man`.

---

## Chapter 2: Files, Permissions, and Ownership
### Core topics
- File types, inodes, links (hard vs symbolic)
- Permission model: `rwx` for user/group/other
- `chmod`, `chown`, `chgrp`, `umask`, sticky/SUID/SGID basics

### Must-know commands
`stat`, `chmod`, `chown`, `ln`, `umask`, `id`, `groups`

### Trustworthy references
- `chmod` man page: https://man7.org/linux/man-pages/man1/chmod.1.html
- Red Hat permissions guide: https://www.redhat.com/sysadmin/linux-file-permissions-explained

### Stack Overflow examples
- Symbolic vs hard links: https://stackoverflow.com/questions/185899
- Numeric permission notation explanation: https://stackoverflow.com/questions/183527

### Activity
- Build a shared group folder and configure permissions so teammates can edit files but outsiders cannot.

### Summary
- You should be able to read, set, and troubleshoot Linux file permissions.

---

## Chapter 3: Processes, Services, and Scheduling
### Core topics
- Process lifecycle, foreground/background, signals
- `systemd` services and logs
- Job scheduling with cron and at

### Must-know commands
`ps`, `top`/`htop`, `kill`, `pkill`, `nice`, `systemctl`, `journalctl`, `crontab`

### Trustworthy references
- systemd docs: https://systemd.io/
- Cron man page: https://man7.org/linux/man-pages/man5/crontab.5.html

### Stack Overflow examples
- Graceful vs forceful termination (`SIGTERM` vs `SIGKILL`): https://stackoverflow.com/questions/690415
- Cron path/environment gotchas: https://stackoverflow.com/questions/2388087

### Activity
- Create a cron job to back up a directory every hour and verify logs with `journalctl`.

### Summary
- You should now manage running processes and persistent services.

---

## Chapter 4: Package Management and Software Sources
### Core topics
- `apt`, `dnf/yum`, `pacman` basics
- Repositories, signatures, updates, patching
- Building from source (high-level awareness)

### Must-know commands
`apt update`, `apt upgrade`, `apt install`, `dpkg -l`, `dnf check-update`

### Trustworthy references
- Debian apt docs: https://wiki.debian.org/Apt
- Arch package management: https://wiki.archlinux.org/title/Pacman

### Stack Overflow examples
- `apt update` vs `apt upgrade`: https://stackoverflow.com/questions/42875204

### Activity
- Install and remove a package, inspect dependencies, and document rollback steps.

### Summary
- You should maintain systems with safe package and patch practices.

---

## Chapter 5: Networking Essentials for Security Students
### Core topics
- IP, subnet, routing, DNS, ports, sockets
- SSH, firewall basics, network troubleshooting
- Packet inspection introduction

### Must-know commands
`ip`, `ss`, `ping`, `traceroute`, `dig`, `nslookup`, `curl`, `wget`, `ssh`, `scp`, `ufw`/`iptables`

### Trustworthy references
- Arch networking: https://wiki.archlinux.org/title/Network_configuration
- OpenSSH manual: https://man.openbsd.org/ssh
- Wireshark docs: https://www.wireshark.org/docs/

### Stack Overflow examples
- Difference between `netstat` and `ss`: https://stackoverflow.com/questions/11763376
- SSH key permissions issue: https://stackoverflow.com/questions/9270734

### Activity
- Set up SSH key login in a VM and disable password authentication.

### Summary
- You should inspect network state and secure remote access basics.

---

## Chapter 6: Bash Scripting and Automation
### Core topics
- Variables, loops, conditionals, functions, exit codes
- Input/output redirection, pipes, command substitution
- Defensive shell scripting practices

### Must-know commands/tools
`bash`, `grep`, `awk`, `sed`, `sort`, `uniq`, `xargs`, `find`, `cut`

### Trustworthy references
- Bash guide: https://mywiki.wooledge.org/BashGuide
- ShellCheck: https://www.shellcheck.net/

### Stack Overflow examples
- Correct quoting in Bash: https://stackoverflow.com/questions/10067266
- Safe file iteration with spaces: https://stackoverflow.com/questions/301039

### Activity
- Write a script that audits `/etc/passwd` users and outputs a CSV report.

### Summary
- You should automate repeatable administration/security checks.

---

## Chapter 7: Linux Security Hardening
### Core topics
- Least privilege, account policy, sudo hygiene
- File integrity, auditing, logging, patching policy
- SELinux/AppArmor basics

### Must-know commands
`sudo`, `visudo`, `passwd`, `faillock` (distro-dependent), `auditctl`, `ausearch`, `aa-status`, `getenforce`

### Trustworthy references
- CIS Benchmarks: https://www.cisecurity.org/cis-benchmarks
- SELinux project wiki: https://github.com/SELinuxProject/selinux/wiki
- NIST guidance portal: https://csrc.nist.gov/publications

### Stack Overflow examples
- Why editing sudoers requires `visudo`: https://stackoverflow.com/questions/46720411

### Activity
- Harden a fresh VM: disable root SSH login, enforce key auth, tighten sudo and file permissions.

### Summary
- You should apply baseline Linux hardening aligned with security best practices.

---

## Chapter 8: Logs, Monitoring, and Incident Basics
### Core topics
- Log locations (`/var/log`), journal logs, auth logs
- Detecting suspicious behavior from command history, auth attempts, process trees
- Basic incident response workflow: identify, contain, preserve evidence

### Must-know commands
`journalctl`, `tail -f`, `grep`, `last`, `who`, `w`, `uptime`, `dmesg`

### Trustworthy references
- Linux logging guide (RHEL): https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/
- SANS incident handling resources: https://www.sans.org/white-papers/

### Stack Overflow examples
- Following multiple logs efficiently: https://stackoverflow.com/questions/3721239

### Activity
- Simulate failed logins and identify them from logs with timestamps and source IPs.

### Summary
- You should extract actionable security signals from Linux logs.

---

## Chapter 9: Advanced Topics (Exam Advantage)
### Core topics
- Boot process and GRUB/systemd internals
- Filesystems (ext4/xfs), LVM, swap, mount namespaces
- Containers basics (Docker rootless concepts, namespaces/cgroups)
- Kernel module awareness and syscall tracing (`strace`)

### Trustworthy references
- TLDP docs: https://tldp.org/
- Kernel docs: https://www.kernel.org/doc/html/latest/
- Docker security: https://docs.docker.com/engine/security/

### Stack Overflow examples
- Understanding namespaces: https://stackoverflow.com/questions/18431285
- `strace` practical usage: https://stackoverflow.com/questions/15102987

### Activity
- Trace a command with `strace`, explain key syscalls, and map them to file/network actions.

### Summary
- You should connect Linux internals to practical security analysis.

---

## Chapter 10: Exam Strategy + Mastery Plan
### Revision framework
- **Daily (45–90 min):** command drills + one mini-lab
- **Weekly:** one end-to-end scenario (hardening, triage, script automation)
- **Monthly:** mock exam with time limit and no notes

### Self-test checklist
- Can I explain *why* each command is used, not just syntax?
- Can I recover from common mistakes quickly?
- Can I secure a default Linux install in under 60 minutes?
- Can I read unfamiliar logs and identify suspicious events?

### Final summary
- Master fundamentals first, then scripting, networking, and hardening.
- Focus on hands-on repetition in VMs.
- Build an “exam notebook” of commands, flags, and troubleshooting patterns.

---

## Suggested Lab Environment
- VirtualBox/VMware + at least 2 Linux VMs (Ubuntu + one RPM-based distro)
- Snapshot before each lab
- Keep a command journal: command, expected output, actual output, lesson learned
