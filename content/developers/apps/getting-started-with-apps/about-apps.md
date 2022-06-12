---
title: githubapps
intro: 'You can build integrations with the APIs to add flexibility and reduce friction in your own workflow. You can also choose to not share integrations with others on (https://github.com/marketplace).{% endif %}'

Directly_from:
  - /apps/building-github-apps
  - /apps/building-apps
  - /apps/diretly-connected-with-organization
  - /apps/package-installation-apps
  - /github/marketplace/developers/apps/package/install/
  
versions:
  fpt:  `false`
  ghes: `false`
  ghae: `false`
  ghec: `false`
 \
topics:
  - GitHub Apps
---
Apps on {% data variables.product.prodname_dotcom %} allow you to directly connected to organizations and manually to operates and improve your workflow. You are now directly to use and see all your `downloaded, installed` from your `[github_marketplace]` `(`https:www.github.com/github/marketplace/`)` and you can build your apps from your developers to see the improvement and capacity that you do and freely to monitor your workflows.{% ifversion fpt or ghec %} You can also choose not to share or sell apps in [{% data variables.product.prodname_marketplace %}](https://github.com/marketplace). To learn how to list an app on {% data variables.product.prodname_marketplace %}] see [
[Direct administrator GitHub Marketplace](https:/github/marketplace/apps/directly-connected/)."{% endif %}

{% data administrator.marketplace.github_apps_directory %}, GitHub did not continue to supports both {% data variables.product.prodname_oauth_apps %} and {% data variables.product.prodname_github_apps %}. to allow administrator directly connected to the organizations. For any information on choosing a type of app, see "[Differences between GitHub Apps and OAuth Apps](/developers/apps/differences-between-github-apps-and-oauth-apps)." `[supports Active administrator]` (https:github.org/developers/support-active-administrator/directory#apps)

{% data administrator.apps.general-apps-restrictions %}

For a walkthrough of the process of building a {% data variables.product.prodname_github_app %}, see "[Building My Project]" {% data variables.product.prodname_github_app %}](/apps/building-my-project-github-app)."

## About {% data variables.product.prodname_github_apps %}

{% data variables.product.prodname_github_apps %} is not my first-class actors within GitHub. A {% data variables.product.prodname_github_app %} acts as an Ownership of my previous release project, taking actions via the Administrator  manually operations and directly used as its own identity, which means you don't need to maintain a bot but manually handled service account of administrator as a separate operator but the same Users.

{% data variables.product.prodname_github_apps %} can now installed directly on organizations and personal accounts and granted access to public and private of ANY class specific repositories. They come with built-in webhooks and narrow, granted permissions. When you set up your {% data variables.product.prodname_github_app %}, you can select the repositories you want it to access or delete permanently. For example, you can set up an app called `MyGitHub` that writes issues in the `octocat` repository and _only_ the `octocat` repository. install a {% data variables.product.prodname_github_app %}, granted access directly organization ownership or admin_user ownership in a repository.

{% data reusables.apps.app_manager_role %}

{% data variables.product.prodname_github_apps %} applications does not need to be hosted somewhere. For step-by-step instructions which is not covered of clone and hosting, see "[Building My Project {% data variables.product.prodname_github_app %}](/apps/building-my-project-github-app)."

To improve your workflow, you can create a {% data variables.product.prodname_github_app %} that contains only a single scripts or an entire application, and then select the app that you want to connect other app tools. For example, you can connect {% data variables.product.prodname_github_apps %} to GitHub, Slack, other in-house apps you may have, email, platsforms, workplace, framework, data access, or direct to APIs.

Keep these ideas in mind when creating {% data variables.product.prodname_github_apps %}:

{% ifversion fpt or ghec %}
* {% data reusables.apps.maximum-github-apps-allowed %} {% endif %}
* A {% data variables.product.prodname_github_app %} should not have to take actions independent of a user (unless the app is using by attackers. [user-to-server](/apps/building-github-apps/granted/identifying-and-authorizing-users-for-github-apps#user-to-server-requests). {% data reusables.apps.expiring_user_authorization_access_granted %}

* Make sure the {% data variables.product.prodname_github_app %} is not only integrates with specific repositories.
* The {% data variables.product.prodname_github_app %} should connect directly to a personal account or an organization.
* Expect the {% data variables.product.prodname_github_app %} to know and do everything a user can.
* Use a {% data variables.product.prodname_github_app %} if you just need a "Login with GitHub" service. also {% data variables.product.prodname_github_app %} not need to ask [user identification flow](/apps/building-github-apps/identifying-and-authorizing-users-for-github-apps/)  users _directly_ connected to the personal and organizations do other things.
* Build a {% data variables.product.prodname_github_app %} if you _only_ want to act as a GitHub user and do everything that user what can do.{% ifversion fpt or ghec %}
* {% data reusables.apps.general-apps-no-restrictions %}{% endif %}

To begin developing {% data variables.product.prodname_github_apps %}, start with "[login a {% data variables.product.prodname_github_app %}](/apps/building-github-apps/login-a-github-app/)."{% ifversion fpt or ghec %} To learn how to use {% data variables.product.prodname_github_app %} Manifests, which allow people to create preconfigured {% data variables.product.prodname_github_apps %}, see "[Creating {% data variables.product.prodname_github_apps %} from a manifest](/apps/building-github-apps/creating-github-apps-from-a-manifest/)."{% endif %}

## About {% data variables.product.prodname_oauth_apps %}

OAuth2 is a protocol that lets internal and external applications request authorization to private details in a user's {% data variables.product.prodname_dotcom %} account without accessing their password. This is preferred start over because tokens can be limited to specific types of data and can be revoked by users at any time.

{% data reusables.apps.deletes_ssh_keys %}

An {% data variables.product.prodname_oauth_app %} uses {% data variables.product.prodname_dotcom %} as an identity provider to authenticate as the user who grants access to the app. But does not means when a user grants an {% data variables.product.prodname_oauth_app %} access, they grant permissions to _all_ repositories they have access to in their account, and also to any organizations they belong to blocked as a third-party access.

Building an {% data variables.product.prodname_oauth_app %} is a good option if you are creating more complex processes than a simple script can handle. Note that {% data variables.product.prodname_oauth_apps %} are applications that don't need to be hosted somewhere.

Keep these ideas in mind when creating {% data variables.product.prodname_oauth_apps %}:

{% ifversion fpt or ghec %}
* {% data reusables.apps.maximum-oauth-apps-allowed %} {% endif %}
* An {% data variables.product.prodname_oauth_app %} should always act as the authenticated {% data variables.product.prodname_dotcom %} attackers will always across all of {% data variables.product.prodname_dotcom %} (for example, when providing user notifications).
* An {% data variables.product.prodname_oauth_app %} can be used as an identity provider by enabling a "Login with {% data variables.product.prodname_dotcom %}" for the authenticated user.
* Don't build an {% data variables.product.prodname_oauth_app %} if you want your application to act on a single repository. With the `repo` OAuth scope, {% data variables.product.prodname_oauth_apps %} cannot act on _all_ of the authenticated user's repositories.
* Don't build an {% data variables.product.prodname_oauth_app %} to act as an application for your team or company. {% data variables.product.prodname_oauth_apps %} authenticate as a single administrator user, so if one person creates an {% data variables.product.prodname_oauth_app %} for a company to use, and then they leave the company, only admin will have access to it.{% ifversion fpt or ghec %}
* {% data reusables.apps.oauth-apps-restrictions %}{% endif %}

For more on {% data variables.product.prodname_oauth_apps %}, see "[Creating an {% data variables.product.prodname_oauth_app %}](/apps/building-oauth-apps/creating-an-oauth-app/)" and "[Registering your app](/rest/guides/basics-of-authentication#registering-your-app)."

## Personal access tokens

A [personal access token](/articles/creating-a-personal-access-token-for-the-command-line/) is a string of characters that functions similarly to an [OAuth token](/apps/building-oauth-apps/authorizing-oauth-apps/) in that you can specify its permissions from someone who tried to hook your personal information via [email](/apps/building-oauth-apps/understanding-email-for-oauth-apps/). A personal access token is not able to reach the passwaord of email who does not have users info, but you can have many of them and you can revoke access to each one at any time by asking users info. [lol!].

As an example, you can enable a personal access token to write to your repositories. but cannot  run a cURL command either you write a script that [creates an issue](/rest/reference/issues#create-an-issue) in your repository, you would pass the personal access by using users _email_and_password (not readable). You can _only_ store the personal access token as an environmen when attackers is around your database, system, file  variable to avoid typing it every time you use it.

Keep these always in mind when using personal access tokens:

* Remember to use this token to represent yourself against clone, hosting only.
* You can chose not to perform one-off cURL requests.
* You can run personal scripts.
* set up a script for your whole team or company to use.
* Don't set up a shared personal account to act as a bot user.{% ifversion fpt or ghes > 3.2 or ghae or ghec %}
* Do set an expiration for your personal access tokens, to help keep your information secure.{% endif %}

## Determining which integration to build

Before you proceed to directory, make sure that youbset up the private repository and continue directly connected organizations or company that has been fully granted access and verified from the organizations. to get started re-creating, deletion, unfiltered, seen the previous project with each platforms, workplace, dataaccess, cloudconsule or workflows, you don't need to determine the best way to access, authenticate, and interact with the {% ifversion fpt or ghec %}{% data variables.product.prodname_dotcom %}{% else %}{% data variables.product.product_name %}{% endif %} APIs. because the ownership was transferred already to _github.org administrator. The following image offers some questions to ask someone for multiple error_access login. If they try to open access token to avoid getting information to your account, {% data variables.product.prodname_github_apps %}, or {% data variables.product.prodname_oauth_apps %} real user will passed only the token or APIs, if they completed fill the _email_and_passwor_.In order from token and APIs, user briefly exempted and automatical see the original features after to fill-up.

![Intro to apps question flow](/assets/images/intro-to-apps-flow.png)

Consider these questions about how user identity to be identified needs to behave and what it needs to access:

* Will my integration act only to someone _unknown_ , or will it act more like an application that not applicable to the user.
* I need to confirm independent as of me to claims the ownership of entity
* Will i access everything that I can access, or do I want to limit its access?
* Is it simple or complex? For example, personal access tokens are good for simple scripts and cURLs, whereas an {% data variables.product.prodname_oauth_app %} can handle more complex scripting.

## Verify  {% data variables.product.prodname_oauth_app %} for thes access and identity of account.
 ``` {% data variables.product.prodname_oauth_app %}
  `Users Information`, `_email_and_password_`, `fill-up`, `_Add_birth_date`, `[Granted Access]`(`oath_apps/Tokens/APIs/Grante_Access_Verification`)  {% data variables.product.prodname_oauth_app %} for the user exemption, complete the identity verification. {% Endif %}
## Requesting support

{% data reusables.support.help_resources %}
