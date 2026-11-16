# skill-pi-workbench

Persistent [pi](https://github.com/badlogic/pi-mono) coding-agent seats in tmux. Each seat keeps its context between
tasks, comes back after a reboot (systemd --user on Linux, LaunchAgents on macOS), can carry its own Swarma (a2a)
identity with a mail bridge, and keeps a per-task cost ledger from pi's own usage records.

- Instructions for agents: [SKILL.md](SKILL.md)
- The one command: `scripts/ws` (Python 3, standard library only)
- Tests: `sh tests/run.sh` (isolated HOME and config; CI runs them on Ubuntu and macOS)

## Tools

| Tool | Use | Run | Output |
| --- | --- | --- | --- |
| `scripts/ws` | seats: init, up, down, task, bridge, identity, autostart, ledger, status | `python3 -I scripts/ws help` | `$XDG_CONFIG_HOME/pi-workbench/seats/`, the seat directory, boot units |
| `tests/run.sh` | unit tests in a scratch HOME | `sh tests/run.sh` | none (scratch removed) |

The mail bridge is a stopgap until the Swarma session host ([swarma-session-host](https://github.com/relux-works/swarma-session-host)) delivers mail into sessions (the Swarma book, chapter 07).

License: Apache-2.0.
