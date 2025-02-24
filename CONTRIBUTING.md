# Contributing
# Contributing to {{ repo.name }}

Great that you are here and want to contribute to {{ repo.name }} – a project maintained by {{ .org.name }}.

## Table of Contents

- [How to Contribute](#how-to-contribute)
- [Directory Structure](#directory-structure)
- [Development Setup](#development-setup)
  - [Dev Container](#dev-container)
  - [Requirements](#requirements)
    - [Node.js](#nodejs)
    - [pnpm](#pnpm)
    - [Corepack](#corepack)
    - [Build Tools](#build-tools)
  - [Project Setup](#project-setup)
  - [Start](#start)
- [Development Cycle](#development-cycle)
- [Community PR Guidelines](#community-pr-guidelines)
- [Test Suite](#test-suite)
- [Releasing](#releasing)
- [Custom Nodes & Documentation Extensions](#custom-nodes--documentation-extensions)
- [Contributor License Agreement](#contributor-license-agreement)
- [Need Help](#need-help)

## How to Contribute

Contributions are welcome in all forms—code, documentation, bug reports, and feature ideas. As a general guideline, please:

1. **Fork the Project:** Create a personal copy on GitHub.
2. **Clone Your Fork:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/{{ repo.name }}.git
   ```
3. **Create a Feature Branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Make Your Changes:** Implement your new feature or fix.
5. **Push Your Changes:**
   ```bash
   git push -u origin feature/your-feature-name
   ```
6. **Create a Pull Request:** Submit your changes for review.

## Directory Structure

The repository is structured as a monorepo and includes key directories such as:

- `/docker/images` – Dockerfiles for container images.
- `/packages` – The various modules of the project.
  - `/packages/cli` – CLI tools for front- and backend operations.
  - `/packages/core` – Core logic and workflow execution.
  - Other packages (e.g., design-system, editor-ui, nodes-base, etc.).

## Development Setup

### Dev Container

Using VS Code and Docker? Use our preconfigured Dev Container:  
[Open Dev Container](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/{{ .repo.owner.name }}/{{ repo.name }})

### Requirements

#### Node.js
Ensure you are using Node.js version 20.15 or later.

#### pnpm
Install pnpm (version 9.1 or newer) via corepack:
```bash
corepack prepare pnpm@latest --activate
```

#### Build Tools
For Debian/Ubuntu:
```bash
apt-get install -y build-essential python
```
For CentOS:
```bash
yum install gcc gcc-c++ make
```
For Windows:
```bash
npm add -g windows-build-tools
```
For MacOS, no additional packages are required.

### Project Setup

1. **Fork the Repository.**
2. **Clone Your Fork:**
   ```bash
   git clone https://github.com/{{ .repo.owner.name }}/{{ repo.name }}.git
   ```
3. **Set Up Upstream:**
   ```bash
   git remote add upstream https://github.com/{{ .repo.owner.name }}/{{ repo.name }}.git
   ```
4. **Install Dependencies:**
   ```bash
   pnpm install
   ```
5. **Build the Code:**
   ```bash
   pnpm build
   ```

### Start

To run the project:
```bash
pnpm start
```
Or to run with a tunnel:
```bash
./packages/cli/bin/{{ repo.name }} start --tunnel
```

## Development Cycle

- **Development Mode:**  
  Run the following command to watch and rebuild on code changes:
  ```bash
  pnpm dev
  ```
- **Test Production Build:**
  ```bash
  pnpm build
  pnpm start
  ```
- **Run Tests:**
  ```bash
  pnpm test
  ```

## Community PR Guidelines

When submitting a PR, please keep in mind:

- **Keep Changes Focused:** Small, single-purpose PRs are best.
- **Include Tests:** Add unit tests, integration tests, or UI tests as needed.
- **Follow Code Style:** Respect the project's style guidelines and TypeScript rules.
- **Naming Conventions:** See [PR Title Conventions](https://github.com/{{ .repo.owner.name }}/{{ repo.name }}/blob/master/.github/pull_request_title_conventions.md).

For security issues, please contact {{ .teams.security.email }}.

## Test Suite

### Unit Tests
Run all unit tests with:
```bash
pnpm test
```

### E2E Tests
Before running E2E tests, install Cypress:
```bash
pnpm cypress:install
```
Then execute:
```bash
pnpm test:e2e:all
```
Other options include interactive testing modes.

## Releasing

To start a release, trigger the release workflow via [GitHub Actions](https://github.com/{{ .repo.owner.name }}/{{ repo.name }}/actions/workflows/release-create-pr.yml). The workflow will:
1. Bump package versions.
2. Update the changelog.
3. Create a release branch (`release/{{ VERSION }}`).
4. Open a pull request for further changes.

Once approved, merging this PR will automatically build and publish the release.

## Custom Nodes & Documentation Extensions

- **Custom Nodes:**  
  Learn about building custom nodes [here](https://docs.{{ .org.name }}/integrations/creating-nodes/).

- **Documentation:**  
  Extend or update the documentation by referring to our docs site at [docs.{{ .org.name }}](https://docs.{{ .org.name }}/).

## Contributor License Agreement

As part of the process, you will be required to sign a [Contributor License Agreement](CONTRIBUTOR_LICENSE_AGREEMENT.md). An automated bot will remind you if it's not completed. The PR cannot be merged until the CLA is signed.

## Need Help?

For further guidance, please read our [Developer Guide](https://docs.{{ .org.name }}/developer-guide).  
If you have questions or run into issues, contact the support team at [{{ teams.support.name }}](https://docs.{{ .org.name }}/support) or join our Discord community.

Thank you for contributing to {{ repo.name }}!