# ADP Jira Search Issues Action

Executes a Jira Cloud JQL query and returns:

- `issues`: compact JSON array
- `total`: number of issues returned
- `issues-table`: Markdown table suitable for CloudBees evidence

## Example

```yaml
- name: Search Jira
  id: jira-search
  uses: https://bitbucket.org/adp-uat/adp-jira-search-issues@v1.0.0
  with:
    jira-url: https://adp-uat.atlassian.net
    jira-email: ${{ secrets.JIRA_EMAIL }}
    jira-api-token: ${{ secrets.JIRA_API_TOKEN }}
    jql: project = "ONECICD" ORDER BY created DESC
    max-results: "10"
```

Do not print or publish the `jira-api-token` input.

