# Automation
Application CI/CD

**What is Automation?**

Doing things by machine/script/tool instead of humans.

**Example:** Instead of logging into 10 servers one by one to install updates, you run one command for all servers update.

**Why Automation?**

manual work is:

- slow
- Error possibility
- Not scalable (imagine 1000 servers)

Automation makes it:
- Fast
- Consistent
- Cheaper

**When Automation?** Don’t automate if it’s a rare one-time job or too complex for little benefit.

- Task is repeated often.
- Same result every time.
- If need to scale (more servers, more apps).
- Less human mistake.

**Automation Architecture**

**Developer**
- Writes code → pushes to Git repository (GitHub, GitLab, Bitbucket).

**Git (VCS - Version Control System)**
  - Stores the code.
  - A Webhook triggers Jenkins when new commits are pushed.

**Jenkins (CI)**
- Pulls code from Git.
- Runs tests (unit, integration, security scans).
- Builds Docker image.
- Pushes image to Container Registry.

**Terraform (Provision Infra)**
- Creates servers, Kubernetes cluster, network, database, load balancer.

**Ansible (Configuration + Deployment)**
- Configures infra (install dependencies, update configs).
- Deploys Docker image from Registry to target (VMs or Kubernetes).

**Kubernetes (or VM Infra)**
- Runs the containerized app.
- Manages scaling, load balancing.

**Monitoring & Logging**
- Prometheus/Grafana → metrics & dashboards.
- ELK/Graylog → centralized logs.
- Alertmanager → sends notifications (Slack, Email, Teams).
