# AprilTag Unity Runtime Package

This repository contains a standalone Unity Package Manager (UPM) package that exposes AprilTag detection utilities for Unity projects. The runtime embeds the native AprilTag library together with C# bindings and GPU preprocessing kernels so that no additional setup is required inside your project.

## Package contents

- **Runtime scripts** (`Runtime/*.cs`, `Runtime/Scripts/*.cs`)
  - High-level controller and helpers for running AprilTag detection
  - GPU preprocessors and visualization utilities
- **Resources** (`Runtime/Resources`)
  - Compute shaders used to accelerate image preprocessing
- **Embedded AprilTag library** (`Runtime/Library`)
  - Managed bindings, assemblies, and platform-specific native plugins
- **License** (`Runtime/LICENSE`)
  - Upstream license for the embedded AprilTag implementation

## Installation

1. Copy or reference this repository in your project (for example by using `git submodule` or adding the repository URL through the Unity Package Manager).
2. In the Unity editor, open **Window ▸ Package Manager**.
3. Click the **+** button and choose **Add package from disk...**.
4. Select the `package.json` file located at the root of this repository.

Unity will import the package and expose the AprilTag components to your project.

## Usage

1. Add an **`AprilTagController`** component to a GameObject.
2. Configure its detection parameters (tag family, size, decimation, etc.).
3. Optionally add helper components found under `Runtime/Scripts` (for example the webcam pipeline or visualization helpers) depending on your project needs.
4. Drive detection from your own scripts by invoking the public API on the controller and related helpers (start/stop detection, create anchors, update visualizations, etc.).

See the inline XML documentation in the scripts for a detailed description of each component.

## Requirements

- Unity 2021.3 LTS or later
- Platforms supported by the embedded native libraries (Windows, macOS, Linux, Android, and iOS)

## Contributing

Pull requests and issue reports are welcome. Please make sure your contributions focus on AprilTag functionality and keep the repository package-oriented.
