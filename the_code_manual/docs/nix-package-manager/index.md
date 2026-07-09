# 1\. Introduction

Nix is a powerful, purely functional package manager designed to ensure reproducible and reliable package management. Unlike traditional package managers, Nix allows multiple versions of the same package to coexist without conflicts, prevents dependency issues, and provides strictly isolated development environments.

# 2\. Installation (Multi-User)

The recommended way to install Nix on Linux (including Ubuntu) and Windows (via WSL) is the multi-user installation. It sets up a background daemon to manage package builds securely and efficiently.

- Step 1: Run the Official Installation Script

Open your terminal and execute the following command:  
**sh <(curl -L <https://nixos.org/nix/install>) --daemon**

Alternatively, for systems requiring stricter TLS versions:  
**curl --proto '=https' --tlsv1.2 -L <https://nixos.org/nix/install> | sh -s -- --daemon**

- Step 2: Follow the Prompts

The script will explain the changes it is making and will request sudo (administrator) privileges. Follow the on-screen prompts (typically by typing 'y' and pressing Enter).

- Step 3: Apply Changes

Once finished, restart your terminal or run the following command to apply the Nix environment variables to your current session:

. /etc/profile.d/nix.sh

- Step 4: Verify Installation

To ensure Nix is installed correctly, check the version:

nix-env --version

# 3\. Basic Commands (Classic Nix)

Before Nix Flakes (covered below), users relied on standard nix-env and nix-shell commands to manage packages.

## Package Management (nix-env)

- Search for a package: nix-env -qaP &lt;package_name&gt;
- Install a package: nix-env -iA nixpkgs.&lt;package_name&gt;
- List installed packages: nix-env -q
- Update installed packages: nix-channel --update && nix-env -u
- Uninstall a package: nix-env -e &lt;package_name&gt;

## Isolated Environments (nix-shell)

One of Nix's best features is the ability to use a tool without permanently installing it globally. The nix-shell command builds the dependencies of a specified derivation and starts an interactive shell where those dependencies are available.

### Using nix-shell Ad-Hoc

- To temporarily use a package like 'cowsay', run: nix-shell -p cowsay
- This is perfect for testing tools without cluttering your system profile.

### Using nix-shell in Projects

By default, when you run nix-shell with no arguments, it looks for a file named shell.nix (or default.nix) in the current directory.

- Creating a shell.nix file: You can define a project environment using mkShell. For example, you can specify buildInputs = \[ python310 nodejs \]; to automatically pull in Python and Node.js for your project space.
- Customizing the Shell: You can add a 'shellHook' to your shell.nix. This allows you to automatically run commands or set environment variables (like export API_TOKEN='...') every time you enter the shell.
- Integration: You can use tools like 'direnv' to automatically load the nix-shell environment in the background whenever you 'cd' into your project directory.

### Advanced nix-shell Flags

- \--pure: This flag clears out almost all of your host system's environment variables (except basic ones like HOME and USER) to ensure your project builds in a completely isolated environment.
- \--run "cmd": Executes a specific command in a non-interactive shell and immediately exits.
- \--command "cmd": Executes a specific command in an interactive shell.

# 4\. The Modern Approach: Nix Flakes

Nix Flakes represent the modern, unified command-line interface for the Nix ecosystem. They replace older commands with a standardized approach that relies on an entrypoint file called 'flake.nix'. Flakes ensure absolute reproducibility by pinning exact dependency versions in a 'flake.lock' file.

## Enabling Flakes

Because Flakes are technically experimental, you must enable them by appending the following to your nix.conf:

experimental-features = nix-command flakes

## Core Flake Commands (Replacing Old Tools)

- nix build: Replaces nix-build. It builds a package (e.g., nix build .#hello) and places a 'result' symlink in your directory.
- nix develop: Replaces nix-shell for projects. It reads the devShells output from your flake.nix to prepare a development environment.
- nix run: Replaces running ad-hoc packages. For example, nix run nixpkgs#hello downloads and executes the program without installing it.
- nix profile install: Replaces nix-env -iA for permanently installing packages into your user profile.

## Using Flakes in Your Projects

- Initialization: Run 'nix flake init' to generate a basic flake.nix file.
- Anatomy of flake.nix: It consists of 'inputs' (where dependencies like nixpkgs are fetched from) and 'outputs' (a function that produces packages, apps, or devShells).
- Git Requirement (Crucial!): Flakes only recognize files tracked by Git. If you create a new file, you must at least run 'git add' before Nix commands will acknowledge it.
- Managing Dependencies: Run 'nix flake update' to update all inputs in your flake.lock file to their latest versions.

# 5\. Maintenance and Garbage Collection

Nix keeps older versions of packages so you can always roll back to previous states if something breaks. However, this can consume significant disk space over time. To safely delete packages that are no longer being used by your current environment, run the Garbage Collector:

nix-collect-garbage -d