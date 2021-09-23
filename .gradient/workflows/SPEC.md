# Gradient Workflows

Gradient Workflows let you use GitHub-action style YAML syntax to string together powerful automations.

- **Workflow:** a named or unnamed entity that belongs to a team and project. Named workflows can be re-run with a default workflow spec, or be passed a new spec every time.
- **Workflow Spec:** a YAML list of jobs that is converted into an Argo template and run on the Gradient distributed runtime engine.
- **Job:**
  - self-contained part of a workflow spec that is similar to an Argo step
  - jobs can define inputs, outputs, and their own environment variables
  - jobs can require other jobs via "needs" and collect/pass info between jobs
  - jobs can be implemented with an action via "use"
- **Action:**
  - A self-contained, composable set of code building blocks that can perform specific actions within a machine learning project.
  - actions can receive parameters (e.g. args, image) within the job step via the "with" argument
  - e.g. container@v1 action = run a container, load inputs, and produce outputs
