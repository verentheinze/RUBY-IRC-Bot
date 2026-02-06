[![Vercel Status](https://api.vercel.com/api/v1/badges/f9c3b877-992c-5812-9700-2c758e95cc88/deploy-status)](https://app.vercel.com/sites/solanaorg/deploys)
[![All Contributors](https://img.shields.io/github/all-contributors/solana/solana-org-website?color=orange&style=flat-square)](#contributors-)
[![Discord](https://img.shields.io/discord/428295358100013066?color=1C1CE1&label=solana.org%20%7C%20Discord%20%F0%9F%91%8B%20&style=flat-square)](https://discord.gg/solana)
[![Twitter Follow](https://img.shields.io/twitter/follow/solanadotorg.svg?style=social)](https://twitter.com/solanadotorg)
[![Crowdin](https://badges.crowdin.net/solana-org/localized.svg)](https://crowdin.com/project/solana-org)
[![gitpoap badge](https://public-api.gitpoap.io/v1/repo/solana/solana-org-website/badge)](https://www.gitpoap.io/gh/solana/solana-org-website)

<div align="center" style="margin-top: 1em; margin-bottom: 3em;">
  <a href="https://solana.org"><img alt="solana logo" src="./sol-transparent.png" alt="solana.org" width="125"></a>
  <h1>👋 Welcome to solana.org!</h1>
</div>

This is the repo for the [solana.org](https://solana.org) website, a resource for the Solana community. The purpose of the site is to _"Be the best portal to Solana for our growing global community"_ - read more about what this means [here](https://solana.org/en/about/).

[solana.org](https://solana.org) is improved and changed over time through the contributions of community members who submit content, give feedback, or volunteer their time to managing its evolution. If you're interested in helping to improve [solana.org](https://solana.org), find out [how to contribute](https://solana.org/en/contributing/).

## Looking for the Solana blockchain's code?

If you're looking for the Solana blockchain itself, there is no single repo. Instead, Solana has multiple implementations of the protocol written in different programming languages for security and diversity. [Check out the different implementations](https://solana.org/en/developers/docs/nodes-and-clients/#validator-clients)

<hr style="margin-top: 3em; margin-bottom: 3em;">

## Table of contents

- [How to contribute](#how-to-contribute)
- [Translation Program](docs/translation-program.md)
- [The solana.org website stack](docs/stack.md)
- [Website conventions / best practices](docs/best-practices.md)

## How to contribute

This project follows the [all-contributors](https://allcontributors.org/docs/en/overview) specification. Contributions of any kind are welcome!

### 1. Submit an issue

- Create a [new issue](https://github.com/solana/solana-org-website/issues/new/choose).
- Comment on the issue (if you'd like to be assigned to it) - that way [our team can assign the issue to you](https://github.blog/2019-06-25-assign-issues-to-issue-commenters/).

### 2. Fork the repository (repo)

- If you're not sure, here's how to [fork the repo](https://help.github.com/en/articles/fork-a-repo).

### 3. Set up your local environment (optional)

If you're ready to contribute and create your PR, it will help to set up a local environment so you can see your changes.

1. [Set up your development environment](https://nextjs.org/docs/getting-started/installation)

2. Clone your fork

If this is your first time forking our repo, this is all you need to do for this step:

```sh
$ git clone git@github.com:[your_github_handle]/solana-org-website.git && cd solana-org-website
```

If you've already forked the repo, you'll want to ensure your fork is configured and that it's up to date. This will save you the headache of potential merge conflicts.

To [configure your fork](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork):

```sh
$ git remote add upstream https://github.com/solana/solana-org-website.git
```

To [sync your fork with the latest changes](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork):

```sh
$ git checkout main
$ git fetch upstream
$ git merge upstream/main
```

3. Install dependencies

We recommend using a node manager to use multiple node versions in your system. We use [Volta](https://volta.sh/). In case you don't use a manager or you use `nvm`, you can check the currently supported versions under the `"volta"` section on our `package.json` file.

```sh
$ npm install
```

### 4. Make awesome changes!

1. Create new branch for your changes

```sh
$ git checkout -b new_branch_name
```

2. Start developing!

```sh
$ npm run dev
```

- Open this directory in your favorite text editor / IDE, and see your changes live by visiting `localhost:3000` from your browser
- Pro Tip:
  - Explore scripts within `package.json` for more build options
  - Get **faster** local builds by building only one language. E.g. in your `.env` file, set `NEXT_BUILD_LANGS=en` to build the content only in English

By default the script will build all the languages (complete list in `data/translations.json`) and will ignore the `/docs` and `/guides` folders. To control this behavior you can play with the `NEXT_BUILD_LANGS` and `IGNORE_CONTENT` env variables. Check out `.env.example` to read more about them.

3. Commit and prepare for pull request (PR). In your PR commit message, reference the issue it resolves (see [how to link a commit message to an issue using a keyword](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword)).

```sh
$ git commit -m "brief description of changes [Fixes #1234]"
```

4. Push to your GitHub account

```sh
$ git push
```

### 5. Local development with API functions

There may be times where you develop features that make external API requests to other services. For these we write API functions to obfuscate API keys.

To use an existing function locally you don't need to do anything. Just check that you have set the necessary ENV variables in the `.env` file.

To create a new function, you will need to create the file in `pages/api` where the logic will live. These functions follow [Next.js API format](https://nextjs.org/docs/pages/building-your-application/routing/api-routes).

Typically, you will develop and test functions by running `npm run dev`.

### 6. Submit your PR

- After your changes are committed to your GitHub fork, submit a pull request (PR) to the `main` branch of the `solana/solana-org-website` repo
- In your PR description, reference the issue it resolves (see [linking a pull request to an issue using a keyword](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword))
  - ex. `Updates out of date content [Fixes #1234]`
- Vercel (our hosting service for build previews) deploys all PRs to a publicly accessible preview URL, e.g.:
  ![Vercel deploy preview](./vercel-preview-deploy.png)
- _Confirm your Vercel preview deploy looks & functions as expected_
- Why not say hi and draw attention to your PR in [our discord server](https://discord.gg/solana)?

### 7. Wait for review

- The website team reviews every PR
- See [how decisions are made on content changes](https://solana.org/en/contributing/#how-decisions-about-the-site-are-made)
- Acceptable PRs will be approved & merged into the `main` branch

### 8. Release

- `production` is continually synced to Vercel and will automatically deploy new commits to solana.org
- The [website team](https://solana.org/en/contributing/#how-decisions-about-the-site-are-made) will periodically merge `main` into `production` (typically multiple times per week)
- You can [view the history of releases](https://github.com/solana/solana-org-website/releases), which include PR highlights

<hr style="margin-top: 3em; margin-bottom: 3em;">

![POAP Logo](src/assets/poap-logo.svg)

## Claim your POAP!

### What is POAP?

> The Proof of Attendance Protocol is a dapp that distributes badges in the form of SPL tokens to prove you participated in an event. [More on POAPs](https://www.poap.xyz/).

### solana.org 2024 Contributor POAP

- If you have committed any changes in 2024 so far that were merged into our repo, you have a POAP waiting!
- This includes our dedicated translators on Crowdin

  [![Discord](https://img.shields.io/discord/428295358100013066?color=1C1CE1&label=Claim%20Your%20POAP!%20%7C%20Discord%20%F0%9F%91%8B%20&style=flat)](https://discord.gg/solana)

- 👆 To claim your Contributor POAP, join our Discord server and paste a link to your contribution in the `#🏆 | poaps` [channel](https://discord.com/channels/428295358100013066/805007654322209822)

- A member of our team will verify the request and DM you with a personalized link to claim your own freshly minted POAP collectible!

- To help with verification we request GitHub contributors connect their GitHub account with their Discord account (Discord > Settings > Connections > GitHub). Crowdin contributors will be verified directly through Crowdin by our team.

- If you haven't contributed yet and would like to earn a POAP to show your loyalty to the Solana space, head over to the [issues](https://github.com/solana/solana-org-website/issues/) tab to get started!

<hr style="margin-top: 3em; margin-bottom: 3em;">

## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/SolanaDevX"><img src="https://avatars3.githubusercontent.com/u/34992008?v=4?s=100" width="100px;" alt=""/><br /><sub><b>SolanaDevX</b></sub></a><br /><a href="#content-SolanaDevX" title="Content">🖋</a></td>
    <td align="center"><a href="https://github.com/BlockchainBuilder"><img src="https://avatars0.githubusercontent.com/u/33698952?v=4?s=100" width="100px;" alt=""/><br /><sub><b>BlockchainBuilder</b></sub></a><br /><a href="#content-BlockchainBuilder" title="Content">🖋</a></td>
    <td align="center"><a href="http://decentralized.design"><img src="https://avatars1.githubusercontent.com/u/28689401?v=4?s=100" width="100px;" alt=""/><br /><sub><b>DecentralDesign</b></sub></a><br /><a href="#design-DecentralDesign" title="Design">🎨</a> <a href="https://github.com/solana/solana-org-website/issues?q=author%3ADecentralDesign" title="Bug reports">🐛</a></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/web3dev"><img src="https://avatars1.githubusercontent.com/u/134680?v=4?s=100" width="100px;" alt=""/><br /><sub><b>web3dev</b></sub></a><br /><a href="#content-web3dev" title="Content">🖋</a></td>
    <td align="center"><a href="https://github.com/CryptoArchitect"><img src="https://avatars2.githubusercontent.com/u/6407008?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Crypto Architect</b></sub></a><br /><a href="https://github.com/solana/solana-org-website/commits?author=CryptoArchitect" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/smartcontractdev"><img src="https://avatars2.githubusercontent.com/u/9073706?v=4?s=100" width="100px;" alt=""/><br /><sub><b>smartcontractdev</b></sub></a><br /><a href="#content-smartcontractdev" title="Content">🖋</a> <a href="https://github.com/solana/solana-org-website/pulls?q=is%3Apr+reviewed-by%3Asmartcontractdev" title="Reviewed Pull Requests">👀</a></td>
    <td align="center"><a href="https://github.com/blockchainengineer"><img src="https://avatars2.githubusercontent.com/u/11519649?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Blockchain Engineer</b></sub></a><br /><a href="#content-blockchainengineer" title="Content">🖋</a></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/SolDeveloper88"><img src="https://avatars.githubusercontent.com/u/107551539?v=4?s=100" width="100px;" alt=""/><br /><sub><b>SolDeveloper88</b></sub></a><br /><a href="https://github.com/solana/solana-org-website/commits?author=SolDeveloper88" title="Documentation">📖</a></td>
    <td align="center"><a href="https://github.com/Web3Architect"><img src="https://avatars.githubusercontent.com/u/1122363?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Web3 Architect</b></sub></a><br /><a href="https://github.com/solana/solana-org-website/commits?author=Web3Architect" title="Documentation">📖</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

### Join our Discord server

We have a space to discuss all things solana.org – share your ideas or just say hi over [on Discord](https://discord.gg/solana).
