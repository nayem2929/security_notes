Processes are programs running on a machine. They are managed by the kernel. Each process have a PID associated with them.

**Commands**:
1. ps: shows a list of processes run by the user.
2. ps aux: shows list of every process currently running on the system.
3. top: shows real-time statistics

Below are some of the signals that we can send to a process when it is killed:
- SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
- SIGKILL - Kill the process - doesn't do any cleanup after the fact
- SIGSTOP - Stop/suspend a process

The process that starts first when a system boots up has the PID 0, started by systemd.

We can manage processes using `systemctl [options] [service]`. The following options exist:
- start: Manually start a service
- stop: Manually stop a service
- enable: set to start on boot
- disable: undo enable
- status: check status

`&`: To make processes run in background we can add the `&` operator at the end of the command.
`T^Z`(Control Z): Use this to make a script that's currently running in the foreground to run in the background.
`fg`: Use this to get the aforementioned background script execution back into foreground.
