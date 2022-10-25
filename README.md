<p align="center">
  <a href="https://minnekdigital.com/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://assets.minnekdigital.com/logo-md.jpg">
      <img alt="Minnek Logo" src="https://assets.minnekdigital.com/logo-md.jpg">
    </picture>    
  </a>
</p>

---

# Jira Deployment Actions

This is a reusable GitHub Action uploads deployment information to specified Jira issues belonging to a connected Jira Cloud instance. To enable the deployments tab on a Jira project follow the [documentation](https://support.atlassian.com/jira-cloud-administration/docs/what-is-the-deployments-feature/).

## Setup Production

```yml
name: Deployment to Production

on:
  push:
    branches:
      - 'release/*'
      - 'hotfix/*'

jobs:
  deployment-prod:
    uses: Minnek-Digital-Studio/jira-action/.github/workflows/jira-deployment-prod.yml@master
    secrets:
      CLIENT_ID: ${{ secrets.JIRA_CLIENT_ID }}
      CLIENT_SECRET: ${{ secrets.JIRA_CLIENT_SECRET }}
```

## Setup Test

```yml
name: Deployment to Test

on:
  push:
    branches:
      - 'test/*'
      - 'test'
      - 'testing'
      - 'staging'

jobs:
  deployment-test:
    uses: Minnek-Digital-Studio/jira-action/.github/workflows/jira-deployment-test.yml@master
    secrets:
      CLIENT_ID: ${{ secrets.JIRA_CLIENT_ID }}
      CLIENT_SECRET: ${{ secrets.JIRA_CLIENT_SECRET }}
```

## About

<a href="https://minnekdigital.com/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://assets.minnekdigital.com/logo-sm.jpg">
    <img alt="Minnek Logo" src="https://assets.minnekdigital.com/logo-sm.jpg">
  </picture>
</a>

This project is maintained and funded by Minnek.

We ❤️ open source and do our part in sharing our work with the community!
See [our other projects][community] or [hire our team][hire] to help build your product.

Want to join? [Check out our Jobs][jobs]!

[community]: https://github.com/Minnek-Digital-Studio
[hire]: https://minnekdigital.com/
[jobs]: https://minnekdigital.com/careers
