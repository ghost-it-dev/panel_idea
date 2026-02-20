# ServerPanel

A modern, lightweight server management panel built on top of existing,
mature infrastructure APIs (Docker and KVM/QEMU).

Instead of reinventing orchestration, ServerPanel acts as a clean
orchestration layer that leverages Docker and virtualization APIs
directly --- keeping the system stable, maintainable, and
future-friendly.

------------------------------------------------------------------------

## 🚀 Overview

ServerPanel is designed to function similarly to tools like
**Pterodactyl** or **Pelican**, but with a simplified architecture:

-   Built directly on Docker API
-   Supports QEMU/KVM virtual machines
-   Designed for reverse proxy environments (Nginx/Apache)
-   Focused on maintainability and minimal long-term overhead
-   Lightweight alternative to Kubernetes for small-to-mid deployments

------------------------------------------------------------------------

## ✨ Core Features

### 🔧 Server Management

-   Create, start, stop, restart, and delete servers
-   Per-server resource control (CPU, RAM, storage)
-   User-level permissions for individual server management
-   Multi-node support

### 🐳 Docker Integration

-   Direct Docker API integration
-   Deploy servers using existing Docker images (e.g. LinuxServer.io)
-   Resource limits set during creation
-   Node-based architecture using native Docker functionality
-   No custom container runtime logic

### 💻 Virtual Machine Support

-   QEMU/KVM integration via existing APIs/sockets
-   Create and manage VMs from the panel
-   Designed for automated dedicated VM deployments
-   VM support kept intentionally separate from container plugin logic

### 🌐 Reverse Proxy Support

-   Runs over HTTP/HTTPS
-   Proper reverse proxy header support
-   Designed for:
    -   Nginx
    -   Apache
-   No complex web stack required

### 🎨 Customizable UI

-   Clean interface inspired by Unraid
-   Resource-focused dashboard
-   Custom CSS support
-   Visual theming and branding capability

------------------------------------------------------------------------

## 🧠 Architecture Philosophy

ServerPanel is not a container runtime or virtualization manager.

It is an orchestration layer.

### Node Responsibilities

-   Manage storage
-   Run Docker containers
-   Run KVM/QEMU VMs
-   Enforce resource usage

### Panel Responsibilities

-   Set limits during creation
-   Issue API calls
-   Handle user authentication & permissions
-   Coordinate automation logic

This separation: - Reduces complexity - Makes updates easier - Keeps
maintenance minimal - Avoids Kubernetes-level overhead

------------------------------------------------------------------------

## 🔌 Lightweight Plugin System

Inspired by Pelican, but intentionally simplified.

### Example: Minecraft Mod Management

-   Central mod/plugin directory on panel host
-   Mods downloaded once
-   Versioning handled through structured folder layout
-   Docker volume mounts automatically mapped per service
-   Works with official Java containers
-   Minimal maintenance required
-   Designed to remain stable across upstream image updates

This approach: - Prevents duplicate downloads - Simplifies version
management - Keeps implementation update-resistant

Note: Plugin-style automation is intended for container services, not
VMs.

------------------------------------------------------------------------

## 🔐 Authentication

Planned support for modern identity providers such as:

-   Pocket ID
-   Other OAuth/OpenID-compatible providers

------------------------------------------------------------------------

## 📦 Why This Approach?

Instead of building custom infrastructure:

-   Uses mature Docker API
-   Uses stable KVM/QEMU APIs
-   No custom orchestration engine
-   Less maintenance burden
-   Easier long-term sustainability

Compared to Kubernetes: - Far simpler - Easier to understand - Lower
operational overhead - Better suited for small-to-medium deployments

------------------------------------------------------------------------

## 🎯 Goals

-   Lightweight but powerful
-   Easy to deploy
-   Reverse-proxy friendly
-   Open-source and extensible
-   Resume-worthy demonstration of:
    -   Docker API integration
    -   KVM/QEMU control
    -   Infrastructure orchestration
    -   Reverse proxy handling
    -   Automation design

------------------------------------------------------------------------

## 📜 License

Open-source (license to be determined).

------------------------------------------------------------------------

## 🚧 Status

Early concept / in development.
