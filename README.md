<p align="center">
  <img src="assets/continuity-logo.png" alt="Continuity" width="320">
</p>

# Continuity

**Persistent memory. Adaptive learning. Intelligence that can change without starting over.**

Continuity is the durable cognitive layer around AI: a place for your context, decisions, evidence, and accumulated experience to live beyond any single conversation or model. It brings AI-assisted work into one desktop environment while keeping the history and understanding behind that work under your ownership.

The model supplies intelligence. Continuity supplies the structure that makes that intelligence useful over time.

## Remember the work—and why it mattered

Productive work leaves more than a transcript. It leaves constraints, decisions, discoveries, failed approaches, and reasons for choosing one path over another. Continuity's memory architecture preserves those relationships so future work can build on prior understanding.

Historical significance and present relevance have distinct roles: something can remain worth remembering without needing to influence every conversation.

## Build knowledge from experience

Adaptive learning connects experience to evidence. Continuity's learning model distinguishes observations, hypotheses, lessons, and established conclusions, retaining the provenance and conditions behind them. Later outcomes can reinforce an approach, reveal its limits, or provide grounds to revise it.

The aim is cumulative understanding: knowing what worked, why it worked, and when that knowledge applies again.

## Choose the intelligence that fits

Conversations, agent harnesses, research, and background work belong in a coherent workspace. Continuity's architecture separates those replaceable intelligence surfaces from the durable memory and orchestration layer beneath them.

That separation gives the product its central promise: changing a model or provider should preserve the experience that made your AI useful.

## Keep ownership and control

Your accumulated context and knowledge belong to you. Continuity is designed around authenticated ownership, protected credentials, traceable evidence, and explicit authority for actions affecting your resources. Remembering information, proposing an action, and having permission to execute it remain separate responsibilities.

## Desktop application

The Continuity application brings together an assistant, workload planning, agentic harnesses, repositories, shell and browser tools, provider connections, and encrypted messaging. Its shared foundation is designed to carry context and experience across these surfaces while preserving their individual access and execution boundaries.

## Downloads

Installers and release notes are available on the [Releases page](https://github.com/knightsky-cpu/Continuity-App/releases). Each release identifies its available platforms, installation requirements, and verification status. SHA-256 checksums accompany downloadable installers.

This repository hosts public installers, release information, and branding assets. Application source development is maintained separately.


## Getting started

### 1. Install and open Continuity

Download the installer for your operating system and processor from [Releases](https://github.com/knightsky-cpu/Continuity-App/releases). Follow that release's platform-specific installation instructions; availability is listed per release.

On an Apple Silicon Mac running macOS 15 or later, open the `.dmg`, drag **Continuity** to **Applications**, and open it from Applications. When updating, fully quit the previous copy first and replace the application when Finder asks. Keep your existing application data and database.

Packaged releases include the application and pinned agent tools. The first launch can download and prepare a managed runtime, so leave the app open and keep an internet connection available. You do not need a source checkout, a Python or Node installation, or a `.env` file.

### 2. Prepare the local database service

Current desktop releases use Docker for their local database. Docker must be installed, running, and accessible to your ordinary desktop user before setup can finish.

- **macOS:** install and start [Docker Desktop](https://docs.docker.com/desktop/setup/install/mac-install/), or start your existing Colima installation. Wait until its Docker engine is running.
- **Ubuntu:** follow the [Docker Engine installation guide](https://docs.docker.com/engine/install/ubuntu/) and its linked Linux post-installation steps for access without running Continuity as root.
- **Omarchy / Arch:** follow the distribution's [Docker setup instructions](https://wiki.archlinux.org/title/Docker), start its Docker service, and configure access for your desktop user. If you changed group membership, sign out of the graphical desktop and sign back in before opening Continuity.

On Linux, your desktop's Secret Service/keyring must also be available and unlocked so Continuity can protect saved credentials. Package dependencies supply the supporting components; an active graphical keyring session is still required.

If the setup window says **Database service needs attention**, start Docker and select **Check again**. Continuity prepares its database and configuration through the guide. Do not delete database files or Docker volumes to work around a setup error.

### 3. Sign in to Continuity

1. In **Set up Continuity**, choose **Continue setup** when offered.
2. When Gateway sign-in is required, complete the browser sign-in using an account approved for the Continuity service and approve the installation request. Contact the release administrator if your account has not been granted access.
3. Return to Continuity and let enrollment finish. If you closed the authorization page, choose **Continue setup** to resume.
4. When the main application opens, select **Settings** and check **Service status**. This reports the Gateway, local MCP backend, and application relay readiness.

Gateway enrollment and the client connection to the existing tunnel infrastructure are handled by the application. Tester installations do not require Cloudflare configuration, a manually entered workspace ID, or private service configuration files. Gateway sign-in is separate from connecting ChatGPT, Mistral, GitHub, or other services.

## Find your way around

Choose a surface from the left sidebar. Scroll inside that navigation area if a surface is below the visible list. Narrow windows move navigation into a horizontal bar at the top.

| Surface | Where to start |
| --- | --- |
| **Assistant** | Choose a **Provider** and **Model**, then start a conversation. **Projects** opens projects and saved conversations; **Resources** opens attachments and generated files. **Enter** sends; **Shift + Enter** adds a line. |
| **Workload** | Use its tabs to organize tasks, work lists, calendar items, and ideas. Open **Continuitas** for the Workload assistant and choose its provider, model, and context. |
| **Messaging** | Open this surface's **Settings** tab to choose a handle. Use **Channels** to create channels, **Contacts** to manage contacts, **Requests** for invitations, and **Messages** to read conversations. These settings are separate from the main application Settings. |
| **Shell** | Use the integrated local terminal. Commands run on your computer, so review commands before executing them. |
| **Repos** | Choose **Connect GitHub**, then select a repository. Use **Overview**, **Files**, **Diff**, **Changes**, and **Pull Requests** to move between repository views. Review confirmation prompts for operations that change files or Git history. |
| **Agentic Harnesses** | Choose **Codex** or **OpenCode**. Each has its own **Settings** panel and project/session controls. This is where you connect the ChatGPT account used by Codex. |
| **Browser** | Open a tab with **+**, enter an address, and use the navigation controls. **Open in external browser** moves the current page to your system browser. |
| **LLMs** | Choose a hosted chat provider from the tabs and sign in within that provider's page. A hosted website session is separate from Assistant's API/account connection. |
| **Google Services** | Select a service tab and sign in to that service. Use **Open in external browser** when you want the page outside Continuity. |
| **Microsoft Services** | Select a service tab and complete its account sign-in. These embedded sessions are independent of the main Continuity sign-in. |
| **Settings** | Check backend health, choose background intelligence, connect Tavily, change the theme, and manage your profile and notification preferences. |

## Connect your accounts

Connect the services you intend to use. ChatGPT and Mistral are alternative Assistant providers; Tavily supplies web research tools. GitHub is needed for connected repository browsing. You do not need every provider account to begin.

### ChatGPT / Codex

1. Open **Agentic Harnesses → Codex → Settings**.
2. Choose **Sign in with ChatGPT** and complete authentication in the browser. If you choose **Sign in with device code**, follow the displayed code and verification-page instructions privately.
3. Return to the app and confirm the account is connected.
4. Open **Assistant**, select **ChatGPT** under **Provider**, and choose an available **Model**. Use the refresh control if the model list has not loaded.

Continuity reuses this connection for its supported ChatGPT-powered surfaces. Provider access, usage allowance, and available models depend on your account. Signing into the ChatGPT website under **LLMs** alone does not connect Codex or Assistant.

### Mistral: create an account and connect an API key

1. Open **Assistant**, choose **Mistral** in the **Provider** menu, and select **Connect** beside its connection status.
2. In **Connect Mistral**, choose **Open Mistral Studio**. In your browser, create a Mistral account or sign in at [Mistral Studio](https://console.mistral.ai/).
3. Mistral currently enables **Free mode** without a credit card, subject to usage and rate limits. Complete any account-verification prompts shown by Mistral.
4. In Studio, open **API Keys** and choose **Create new key**. Give it a recognizable name, such as `Continuity`, select an expiration, and review any access-scope options. Create the key and copy its full value immediately; Mistral displays it only once. Save it in your password manager if you need to retain a copy.
5. Return to Continuity's **Connect Mistral** dialog. Paste the key into **Studio API key**, then choose **Connect**. Paste the key value itself, without quotation marks or an `Authorization` prefix.
6. Confirm **Mistral connected**, then choose an available **Model**. Use the refresh control if necessary.

The same saved connection is available to Assistant, Continuitas, and supported background work. **Replace key** updates the connection; **Disconnect** removes its saved key. Provider model availability, limits, and privacy settings apply. [Official Mistral account/key guide](https://docs.mistral.ai/getting-started/quickstarts/studio/activate-and-generate-api-key).

### Tavily: create an account and connect web tools

1. Open **Settings → Background learning** and select **Tavily web tools · Connect**.
2. In **Connect Tavily web tools**, select **Open Tavily dashboard**. Create an account or sign in at the [Tavily dashboard](https://app.tavily.com/).
3. Tavily currently offers **1,000 free API credits per month without a credit card**. Confirm the allowance shown in your dashboard; provider plans can change.
4. Find **API keys** in the dashboard. Use the copy control for an existing key, or select **+** to create a named key. If creating one, review its type and monthly usage limit, then copy the complete key value.
5. Return to Continuity's dialog, paste the value into **API key**, and choose **Connect**. Do not include quotation marks or a command around the key.
6. Confirm **Tavily connected · Settings key**. **Tavily usage & Research → Usage** checks the connected account's allowance. One in-app connection serves Assistant, Continuitas, and authorized background web tools.

Use **Tavily web tools · Replace key** to change the key and **Disconnect Tavily** to remove it. Separate named keys can make revocation and administration easier across installations; do not assume that creating another key provides another account allowance. Some Tavily services require a paid plan. [Official Tavily key guide](https://help.tavily.com/articles/9170796666-how-can-i-create-an-api-key) and [current plans](https://www.tavily.com/pricing).

### GitHub

Open **Repos → Connect GitHub**. Complete the **The Repo Bridge** authorization in the browser, entering the device code shown by Continuity if requested. Review the requested access, approve it, and return to Repos. When the connection completes, select a repository from the repository panel. Your GitHub account's repository permissions still apply.

If a saved connection cannot be read, use **Retry saved connection** when offered. Use **Connect GitHub** to authorize again when needed; do not remove application data to repair an account connection.

### OpenCode and Continuity MCP

Open **Agentic Harnesses → OpenCode → Settings**, select a project, and choose **New session** or **Resume session**. Complete the provider connection inside the OpenCode terminal when prompted. OpenCode's `/connect` command opens provider selection, and `/models` selects a model. These harness credentials are separate from the Mistral connection dialog in Assistant. See [OpenCode's provider guide](https://opencode.ai/docs/providers/).

If OpenCode requests authorization for the configured Continuity MCP server, complete its browser sign-in and approval, then return to the terminal and confirm the MCP connection. The packaged application supplies the server configuration; do not invent a server URL or enter private deployment settings.

### Messaging and other services

For encrypted messaging, open **Messaging → Settings → Choose a handle**, enter a handle, and submit the form. Confirm messaging is on before creating or joining channels. Messaging uses your authenticated Continuity installation; it has no separate password. Existing channel membership does not by itself prove that this installation has the keys needed to read encrypted history.

For hosted LLMs, Google Services, and Microsoft Services, open the relevant surface, select the service tab, and sign in through that service's controls. These sign-ins do not automatically connect the API providers or agent harnesses described above.

### Background intelligence

In **Settings → Background learning**, choose **Background provider**, select **Background model**, and choose **Use for background work**. Use **Refresh models** after connecting a provider. This choice is independent of Assistant's model selection; switching a chat model does not select a background model. Background work runs while Continuity is open, and configured provider allowances still apply.

## Connection help

- **A key is rejected:** recopy the full key from the correct provider dashboard, check expiration/revocation and account allowance, then retry the application's Connect control.
- **A usage or rate limit appears:** review that provider's dashboard and wait for its limit to reset or select an appropriate plan. Repeatedly creating keys does not necessarily change account-wide limits.
- **Protected storage is unavailable:** unlock your operating-system keychain/keyring and reopen Continuity. Do not work around this by saving keys in plain text.
- **A browser sign-in did not finish:** keep the application open while authorizing, then return to the app. Retry the offered sign-in control rather than deleting enrollment or database state.
- **Backend health needs attention:** confirm Docker is running and accessible to your signed-in desktop user, then retry the setup check or reopen the application. Report the displayed error if it persists.

Enter passwords and API keys only into the intended application or provider controls. Never include them in chats, issue reports, screenshots, terminal commands, or Git commits. Mistral and Tavily keys entered in Continuity's connection dialogs use protected operating-system storage. Agent harnesses manage their own provider credentials. An account connected in one surface is not automatically connected in every embedded website or harness.

---

**The intelligence may change. Continuity remains.**
