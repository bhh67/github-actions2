Quickstart for GitHub Actions
In this article
Introduction
Creating your first workflow
Viewing your workflow results
More starter workflows
More complex examples
Next steps
Try out the features of GitHub Actions in 5 minutes or less.

Introduction
You only need a GitHub repository to create and run a GitHub Actions workflow. In this guide, you'll add a workflow that demonstrates some of the essential features of GitHub Actions.

The following example shows you how GitHub Actions jobs can be automatically triggered, where they run, and how they can interact with the code in your repository.

Creating your first workflow
Create a .github/workflows directory in your repository on GitHub if this directory does not already exist.

In the .github/workflows directory, create a file named github-actions-demo.yml. For more information, see "Creating new files."

Copy the following YAML contents into the github-actions-demo.yml file:

YAML
name: GitHub Actions Demo
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v3
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
Scroll to the bottom of the page and select Create a new branch for this commit and start a pull request. Then, to create a pull request, click Propose new file.
Commit workflow file

Committing the workflow file to a branch in your repository triggers the push event and runs your workflow.

Viewing your workflow results
On GitHub.com, navigate to the main page of the repository.

Under your repository name, click  Actions.
Actions tab in the main repository navigation

In the left sidebar, click the workflow you want to see.

Workflow list in left sidebar

From the list of workflow runs, click the name of the run you want to see.

Name of workflow run

Under Jobs , click the Explore-GitHub-Actions job.

Locate job

The log shows you how each of the steps was processed. Expand any of the steps to view its details.

Example workflow results

For example, you can see the list of files in your repository:
Example action detail

More starter workflows
GitHub provides preconfigured starter workflows that you can customize to create your own continuous integration workflow. GitHub analyzes your code and shows you CI starter workflows that might be useful for your repository. For example, if your repository contains Node.js code, you'll see suggestions for Node.js projects. You can use starter workflows as a starting place to build your custom workflow or use them as-is.

You can browse the full list of starter workflows in the actions/starter-workflows repository.

More complex examples
For examples that demonstrate more complex features of GitHub Actions, see "Examples." You can see detailed examples that explain how to test your code on a runner, access the GitHub CLI, and use advanced features such as concurrency and test matrices.

Next steps
The example workflow you just added runs each time code is pushed to the branch, and shows you how GitHub Actions can work with the contents of your repository. But this is only the beginning of what you can do with GitHub Actions:

Your repository can contain multiple workflows that trigger different jobs based on different events.
You can use a workflow to install software testing apps and have them automatically test your code on GitHub's runners.
GitHub Actions can help you automate nearly every aspect of your application development processes. Ready to get started? Here are some helpful resources for taking your next steps with GitHub Actions:

"Learn GitHub Actions" for an in-depth tutorial.
