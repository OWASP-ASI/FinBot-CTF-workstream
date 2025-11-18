# Developer Guide

This guide provides the process and resources for developers contributing to the **OWASP FinBot CTF Workstream**.  
It outlines how to set up your environment, work with the repositories, contribute code, and follow our collaboration practices.

---

## Repositories

- **Demo repo** (for reference): [FinBot-CTF-Demo](https://github.com/OWASP-ASI/finbot-ctf-demo)  
  (Demo implementation of the system with Goal Manipulation challenges)

- **Main repo** (future production): [FinBot-CTF](https://github.com/OWASP-ASI/finbot-ctf)
  (Core CTF application and scenarios, incl. issues as stories and/or bugs)

- **Contributor Hub**: [FinBot-CTF-Workstream](https://github.com/OWASP-ASI/FinBot-CTF-workstream)  
  (References, coordination, contributor roles, developer/tester guides)

- **Supporting Tools/Libs**:  
  (utility repos, etc.)


---

## Development Setup and Contribution Workflow


### FinBot CTF – Local Setup at a Glance
Pre-requisites:
[https://docs.astral.sh/uv/getting-started/installation/](https://docs.astral.sh/uv/getting-started/installation/)
[https://redis.io/docs/latest/operate/oss_and_stack/install/archive/install-redis/](https://redis.io/docs/latest/operate/oss_and_stack/install/archive/install-redis/)

Steps:
1. `git clone <your-fork-url> && cd finbot-ctf`
2. `uv venv` and activate (`source .venv/bin/activate`)
3. `uv sync` to install dependencies
4. Start Redis (`redis-server`, must run on localhost:6379)
5. `cp .env.example .env` and add `OPENAI_API_KEY` + `gpt-4.1-mini`
6. Ensure `.env` has `FINBOT_DB_URL=sqlite:///finbot.db`
7. Initialize DB: `python scripts/setup_database.py`
8. Run the app: `python run.py`
9. Open: http://localhost:8000
10. Accept agreement → continue into the FinBot CTF application.
For detailed walkthrough, follow [this recording](https://owasp.slack.com/archives/C09A2MFUXJ9/p1763385678934329).
For questions, reach out to [Sai Modalavalasa](https://owasp.slack.com/team/U096H9N7FCJ).



### Code Review, Testing & Merging

- [ ] Write and run unit tests for your code
- [ ] Review code with your technical lead
- [ ] Verify merge process with your technical lead
- [ ] Once complete, set your stories as ready for testng (coordinate with testing team as needed): [testing.md](https://github.com/OWASP-ASI/FinBot-CTF-workstream/blob/main/process-guides/testing.md)



### Documentation
Before submitting your work, please ensure:

- [ ] Code is commented where logic is non-obvious  
- [ ] Developer Guide updated (if your change affects architecture or workflows)  
- [ ] User Guide updated (if UI/UX or behavior changes)  
- [ ] New env variables or configs documented + added to `.env.example`  
- [ ] Database changes documented + setup script updated (if applicable)  
- [ ] Unit tests and/or test cases updated/added (coordinate with test team as needed) 
- [ ] README sections updated for new modules/features  
- [ ] Code builds and runs locally (`python run.py`)  
- [ ] Redis + DB setup validated on fresh environment  



### Communication& Collaboration

- [ ] Share regular updates (in weekly calls or via Slack)
- [ ] Notify leads early if availability or timelines change
- [ ] Commit only to tasks you can realistically complete
- [ ] Communicate if you become blocked or need support
- [ ] Let the team know if you must pause or drop a task

---
