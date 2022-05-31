# GitHub links configurable via URL query parameters

GitHub allows certain links to be configurable via query parameters but doesn't make it easy to find out the actual query parameters. Here is a collection of such links with all possible options for each.

## How to use

Copy/paste the snippet in your terminal to build the link.

- All parameters are in order of appearance on the corresponding page
- Each `\` on a new line denotes a separate section

> The snippets make use of `echo` and need to be pasted in a terminal, if you find a better way for building the links please let me know

## Create an issue via URL query parameters

[Official documentation](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue#creating-an-issue-from-a-url-query)

> Replace `<owner>/<repo>` with your own

```sh
echo "https://github.com/<owner>/<repo>/issues/new?\
&title=My%20issue\
&body=My%20body\
\
&assignees=octocat,politician\
&labels=bug,help%20wanted\
&projects=my-org/1\
&milestone=my+milestone\
&template=bug_report.yaml\
"
```

> I didn't find how to add it to a **user** project, please make a PR if you find out

Whether the above works or not will depend on your permissions and the existence of the resources.
For example: you cannot assign to a user which is not part of the org, you cannot add to a milestone that doesn't exist, etc.

If you are making use of the new [issue forms](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository#creating-issue-forms), you can assign an `id` to a field and then use this id in the URL query parameters.

## Create a pull request via URL query parameters

[Official documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/using-query-parameters-to-create-a-pull-request)

> Replace `<owner>/<repo>` with your own

```sh
echo "https://github.com/<owner>/<repo>/compare/main...politician-patch-1?\
&quick_pull=true\
&title=My%20issue\
&body=My%20body\
\
&assignees=octocat,politician\
&labels=bug,help%20wanted\
&projects=my-org/1\
&milestone=my+milestone\
&template=pull_request_template.md\
"
```

## Create a personal access token via URL query parameters

[Official documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

```sh
echo "https://github.com/settings/tokens/new?\
&description=My%20token\
\
&scopes=\
\
repo,\
repo:status,\
repo_deployment,\
public_repo,\
repo:invite,\
security_events,\
\
workflow,\
\
write:packages,\
read:packages,\
\
delete:packages,\
\
admin:org,\
write:org,\
read:org,\
\
admin:public_key,\
write:public_key,\
read:public_key,\
\
admin:repo_hook,\
write:repo_hook,\
read:repo_hook,\
\
admin:org_hook,\
\
gist,\
\
notifications,\
\
user,\
read:user,\
user:email,\
user:follow,\
\
delete_repo,\
\
write:discussion,\
read:discussion,\
\
admin:enterprise,\
manage_runners:enterprise,\
manage_billing:enterprise,\
read:enterprise,\
\
codespace,\
codespace:secrets,\
\
admin:gpg_key,\
write:gpg_key,\
read:gpg_key,\
"
```

## Create a GitHub app via URL query parameters

[Official documentation](https://docs.github.com/en/github-ae@latest/developers/apps/building-github-apps/creating-a-github-app-using-url-parameters)

> For an enterprise instance, replace `github.com` by your url.
> For an organization, add `/organizations/<org>` before `/settings`

```sh
echo "https://github.com/settings/apps/new?\
&name=app-name\
&description=App%20description\
&url=https%3A%2F%2Fwww.url.com\
\
&callback_urls[]=https%3A%2F%2Fwww.url.com\
&callback_urls[]=https%3A%2F%2Fwww.url2.com\
&user_token_expiration_enabled=true\
&request_oauth_on_install=true\
&device_flow_enabled=true\
\
&setup_url=https%3A%2F%2Fwww.url.com\
&setup_on_update=true\
\
&webhook_active=true\
&webhook_url=https%3A%2F%2Fwww.url.com\
&ssl_verification=true
\
&actions=write\
&administration=write\
&checks=write\
&security_events=write\
&codespaces=write\
&codespaces_lifecycle_admin=write\
&codespaces_metadata=read\
&codespaces_secrets=write\
&statuses=write\
&contents=write\
&vulnerability_alerts=write\
&dependabot_secrets=write\
&deployments=write\
&discussions=write\
&environments=write\
&issues=write\
&metadata=read\
&packages=write\
&pages=write\
&repository_projects=admin\
&pull_requests=write\
&secret_scanning_alerts=write\
&secrets=write\
&single_file=write\
&single_file_paths[]=README.md\
&single_file_paths[]=LICENSE\
&repository_hooks=write\
&workflows=write\
\
&organization_administration=write\
&organization_user_blocking=write\
&organization_events=read\
&members=write\
&organization_dependabot_secrets=write\
&organization_plan=read\
&organization_projects=admin\
&organization_secrets=write\
&organization_self_hosted_runners=write\
&organization_hooks=write\
&team_discussions=write\
\
&blocking=write\
&codespaces_user_secrets=write\
&emails=write\
&followers=write\
&gpg_keys=write\
&gists=write\
&keys=write\
&interaction_limits=write\
&plan=read\
&profile=write\
&starring=write\
&watching=write\
\
&events[]=meta\
&events[]=security_advisory\
&events[]=branch_protection_rule\
&events[]=code_scanning_alert\
&events[]=check_run\
&events[]=check_suite\
&events[]=commit_comment\
&events[]=create\
&events[]=discussion\
&events[]=discussion_comment\
&events[]=delete\
&events[]=deploy_key\
&events[]=deployment\
&events[]=deployment_review\
&events[]=deployment_status\
&events[]=fork\
&events[]=gollum\
&events[]=issue_comment\
&events[]=issues\
&events[]=label\
&events[]=milestone\
&events[]=member\
&events[]=membership\
&events[]=merge_queue_entry\
&events[]=organization\
&events[]=page_build\
&events[]=project\
&events[]=project_card\
&events[]=project_column\
&events[]=projects_v2_item\
&events[]=public\
&events[]=pull_request\
&events[]=pull_request_review\
&events[]=pull_request_review_comment\
&events[]=pull_request_review_thread\
&events[]=push\
&events[]=registry_package\
&events[]=release\
&events[]=repository\
&events[]=repository_dispatch\
&events[]=secret_scanning_alert\
&events[]=secret_scanning_alert_location\
&events[]=star\
&events[]=status\
&events[]=team\
&events[]=team_add\
&events[]=watch\
&events[]=workflow_dispatch\
&events[]=workflow_job\
&events[]=workflow_run\
&events[]=org_block\
\
&public=true\
"
```
