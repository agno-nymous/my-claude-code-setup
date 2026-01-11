# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-01-11

### Added
- Initial release of My Claude Code Setup workflow
- **Brainstorm skill**: Conversational refinement with targeted questions and codebase exploration triggers
- **Create Plan skill**: Atomic implementation steps with intelligent model selection (haiku/sonnet/opus)
- **Execute Plan skill**: Parallel execution with embedded TDD and dependency management
- **Master Explorer agent**: Orchestrates code and library exploration
- **Code Explorer agent**: Deep codebase analysis with architecture mapping
- **Library Explorer agent**: External library research with documentation parsing
- **Envision command**: Quick access to the full envision workflow
- marketplace.json for easy one-command installation
- Complete documentation and usage guides

### Features
- TDD integration at the planning level (complexity-based test approach)
- Parallel execution of independent steps
- Model selection per step (haiku for simple, sonnet for standard, opus for complex)
- Behavior-based test specifications (refactoring-proof)
- Educational insight blocks throughout the workflow
- Progress tracking with TodoWrite
- Dependency graph building for optimal execution order

## [Unreleased]

### Planned
- Web UI for visualizing plans and execution progress
- Integration with GitHub for automatic PR creation
- Plan templates for common patterns (API endpoints, database migrations, etc.)
- Metrics collection on execution times and success rates
