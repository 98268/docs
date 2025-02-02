---
title: GitHub security features
intro: 'An overview of {% data variables.product.prodname_dotcom %} security features.'
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
type: overview
topics:
  - Repositories
  - Dependencies
  - Vulnerabilities
  - Advanced Security
---

## About {% data variables.product.prodname_dotcom %}'s security features

{% data variables.product.prodname_dotcom %} has security features that help keep code and secrets secure in repositories and across organizations. {% data reusables.advanced-security.security-feature-availability %}

The {% data variables.product.prodname_advisory_database %} contains a curated list of security vulnerabilities that you can view, search, and filter. {% data reusables.security-advisory.link-browsing-advisory-db %}

{% ifversion fpt or ghes or ghae-issue-4864 or ghec %}
## Available for all repositories
{% endif %}
{% ifversion fpt or ghes > 3.0 or ghae or ghec %}
### Security policy

Make it easy for your users to confidentially report security vulnerabilities they've found in your repository. For more information, see "[Adding a security policy to your repository](/code-security/getting-started/adding-a-security-policy-to-your-repository)."
{% endif %}

{% ifversion fpt or ghec %}
### Security advisories

Privately discuss and fix security vulnerabilities in your repository's code. You can then publish a security advisory to alert your community to the vulnerability and encourage community members to upgrade. For more information, see "[About {% data variables.product.prodname_security_advisories %}](/github/managing-security-vulnerabilities/about-github-security-advisories)."

{% endif %}
{% ifversion fpt or ghec or ghes > 3.2 %}

### {% data variables.product.prodname_dependabot_alerts %} and security updates

View alerts about dependencies that are known to contain security vulnerabilities, and choose whether to have pull requests generated automatically to update these dependencies. For more information, see "[About alerts for vulnerable dependencies](/github/managing-security-vulnerabilities/about-alerts-for-vulnerable-dependencies)"
and "[About {% data variables.product.prodname_dependabot_security_updates %}](/github/managing-security-vulnerabilities/about-dependabot-security-updates)."
{% endif %}

{% ifversion ghes < 3.3 or ghae-issue-4864 %}
### {% data variables.product.prodname_dependabot_alerts %}

{% data reusables.dependabot.dependabot-alerts-beta %}

View alerts about dependencies that are known to contain security vulnerabilities, and manage these alerts. For more information, see "[About alerts for vulnerable dependencies](/github/managing-security-vulnerabilities/about-alerts-for-vulnerable-dependencies)."
{% endif %}

{% ifversion fpt or ghec or ghes > 3.2 %}
### {% data variables.product.prodname_dependabot %} version updates

Use {% data variables.product.prodname_dependabot %} to automatically raise pull requests to keep your dependencies up-to-date. This helps reduce your exposure to older versions of dependencies. Using newer versions makes it easier to apply patches if security vulnerabilities are discovered, and also makes it easier for {% data variables.product.prodname_dependabot_security_updates %} to successfully raise pull requests to upgrade vulnerable dependencies. For more information, see "[About {% data variables.product.prodname_dependabot_version_updates %}](/github/administering-a-repository/about-dependabot-version-updates)."
{% endif %}

{% ifversion fpt or ghes or ghae-issue-4864 or ghec %}
### Dependency graph
The dependency graph allows you to explore the ecosystems and packages that your repository depends on and the repositories and packages that depend on your repository.

You can find the dependency graph on the **Insights** tab for your repository. For more information, see "[About the dependency graph](/github/visualizing-repository-data-with-graphs/about-the-dependency-graph)."
{% endif %}

### Security overview for repositories
For all public repositories, the security overview shows which security features are enabled for the repository, and offers the option to configure any available security features that are not currently enabled.

## Available with {% data variables.product.prodname_GH_advanced_security %}

{% data reusables.advanced-security.ghas-availability %}

### {% data variables.product.prodname_code_scanning_capc %}

Automatically detect security vulnerabilities and coding errors in new or modified code. Potential problems are highlighted, with detailed information, allowing you to fix the code before it's merged into your default branch. For more information, see "[About code scanning](/github/finding-security-vulnerabilities-and-errors-in-your-code/about-code-scanning)."

### {% data variables.product.prodname_secret_scanning_caps %}

Automatically detect tokens or credentials that have been checked into a repository. {% ifversion fpt or ghec %}{% data variables.product.prodname_secret_scanning_caps %} finds leaked secrets across all public repositories and informs the relevant service provider that the secret may be compromised. For details of the supported secrets and service providers, see "[{% data variables.product.prodname_secret_scanning_caps %} partners](/code-security/secret-scanning/secret-scanning-partners)."{% endif %}
{%- ifversion ghec or ghes or ghae %}
{% ifversion ghec %}In private repositories, you can view {% elsif ghes or ghae %}You can view {% endif %}any secrets that {% data variables.product.company_short %} has found in your code. You should treat tokens or credentials that have been checked into the repository as compromised.{% endif %} For more information, see "[About secret scanning](/github/administering-a-repository/about-secret-scanning)."

{% ifversion fpt or ghes > 3.1 or ghae-issue-4864 or ghec %}
### Dependency review

Show the full impact of changes to dependencies and see details of any vulnerable versions before you merge a pull request. For more information, see "[About dependency review](/code-security/supply-chain-security/about-dependency-review)."
{% endif %}

{% ifversion ghec or ghes > 3.1 or ghae-issue-4554 %}
### Security overview for organizations{% ifversion ghec or ghes > 3.4 or ghae-issue-6199 %}, enterprises,{% endif %} and teams

Review the security configuration and alerts for your organization and identify the repositories at greatest risk. For more information, see "[About the security overview](/code-security/security-overview/about-the-security-overview)."
{% endif %}

## Further reading
- "[{% data variables.product.prodname_dotcom %}'s products](/github/getting-started-with-github/githubs-products)"
- "[{% data variables.product.prodname_dotcom %} language support](/github/getting-started-with-github/github-language-support)"
