# SecureAI-OS Repository Server

A comprehensive Docker-based repository server providing offline development resources for SecureAI-OS with full Git functionality, data management, and USB drive support.

## Quick Start

```bash
cd docker/local-repo
docker build -t secureai-local-repo .
docker run -d --name secureai-local-repo \
  -p 8080:80 -p 9418:9418 \
  -v $(pwd)/data:/var/repo \
  -v /run/media:/run/media \
  -v /media:/media \
  -v /mnt:/mnt \
  -v /home:/host/home:ro \
  -v /Users:/host/Users:ro \
  -v /opt:/host/opt:ro \
  -v /var/run/docker.sock:/var/run/docker.sock \
  --privileged \
  secureai-local-repo
```

**For IDE Project Import Support:**
```bash
# Add your specific development directories
-v /path/to/your/projects:/host/projects:ro
-v $HOME/IdeaProjects:/host/idea:ro
-v $HOME/workspace:/host/workspace:ro
```

Access at: **http://localhost:8080**

## Navigation

The web interface features an organized dropdown navigation system with categorized submenus:

- **Dashboard** - Main overview and repository population
- **Git** - Git-related functionality
  - Browse Repositories - View and clone repositories
  - Repository Management - Create, delete, and manage repositories
  - Branch Protection - Configure branch protection rules and policies
  - Merge Requests - Code review and collaboration
- **AI** - Advanced AI build intelligence
  - OS Builder - AI-powered autonomous OS builds with 5 advanced capabilities
  - AI System Status - Monitor AI capabilities and learning progress
- **Tools** - Development tools organized by category
  - **Development** - Core development tools
    - Project Templates - Create new projects from pre-built templates
    - Build Manager - Dependency management and build configurations
    - Code Editor - Built-in code editor with syntax highlighting
    - Sandbox Environments - Isolated execution environments with integrated security
  - **Code Quality** - Code analysis and documentation
    - Code Analysis - Automated linting and code quality analysis
    - Code Review - Manual code review tools
    - Comprehensive Review - Advanced code review features
    - Code Coverage - Test coverage analysis and metrics
    - Documentation Generator - AI-powered automated documentation creation
  - **Infrastructure** - System and service management
    - Terraform State Analyzer - Infrastructure state analysis
    - Container Environments - Multi-container development environments
    - Service Orchestration - Multi-service application management
    - Dependency Management - Cross-platform dependency analysis
  - **Security** - Security analysis tools
    - Vulnerability Assessment - Security scanning and remediation
    - AI Model Security - AI model validation and governance
    - Threat Intelligence - Real-time security threat monitoring
  - **Data & Workspace** - Data and workspace management
    - Workspace - Manage workspace and archive data
    - Data Manager - Import/export data to/from USB drives
    - Resource Monitor - System resource monitoring
    - OS Builder - Complete operating system build environment with advanced AI intelligence (5 capabilities)
- **System** - System monitoring and logs
  - Status - System status and health information
  - Logs - View system and application logs
  - Error Diagnosis - Intelligent error analysis and resolution suggestions

## Features

### 🔧 Core Services
- **Source Packages** - Development dependencies and libraries
- **Git Repositories** - Full Git HTTP backend with web interface
- **AI Models** - Local model cache for offline development
- **Build Cache** - Optimized build artifacts storage

### 📁 Data Management System
- **Archive/Workspace Separation** - Pristine data vs working environment
- **USB Drive Support** - Auto-detection and read/write access to external storage
- **Import/Export** - Transfer data between USB drives and workspace
- **Disk Selection** - Choose storage locations with free space information

### 🌐 Git Integration
- **Web Interface** - Browse repositories, commits, branches, and files
- **HTTP Backend** - Full Git clone/fetch/pull support
- **Repository Management** - Create, delete, and manage Git repositories via web interface
- **Branch Management** - Create branches from any source branch through web UI
- **File Viewer** - Syntax-highlighted code viewing
- **Git Administration** - Complete web-based Git management system
- **🔒 Secure Repository Mirroring** - Mirror external repositories with comprehensive trust and legal analysis
- **🛡️ Branch Protection Rules** - Enforce branch protection policies and merge requirements
- **🤖 AI Code Completion** - CodeLlama-powered intelligent code suggestions and completion

### 🔒 Secure Repository Mirroring
- **Trust Analysis** - Comprehensive evaluation of external repositories before mirroring
- **Country of Origin Detection** - Geographic analysis of repository hosting and contributors
- **Legal Compliance Verification** - License detection, export control compliance, redistribution rights
- **Contributor Trust Assessment** - Analysis of contributor patterns and suspicious activity
- **Security Scanning** - Malware detection, binary analysis, Git hook inspection
- **Read-Only Protection** - External mirrors are strictly read-only to prevent tampering
- **Quarantine System** - Failed repositories isolated with admin override capabilities
- **Configuration Management** - Adjustable trust thresholds and blocked country lists

### 🛡️ Branch Protection Rules & Policies
- **Branch Pattern Matching** - Protect branches using wildcard patterns (main, develop, release/*)
- **Direct Push Blocking** - Require pull requests for protected branches
- **Review Requirements** - Enforce minimum number of code reviews before merge
- **Admin Enforcement** - Apply protection rules to administrator users
- **Stale Review Dismissal** - Automatically dismiss reviews when new commits are pushed
- **Git Hook Integration** - Server-side enforcement via pre-receive hooks
- **Policy Management** - Web-based interface for creating and managing protection rules
- **Push Permission Checking** - Real-time validation of push operations against protection policies

### 🤖 AI Code Completion & Suggestions
- **CodeLlama Integration** - Local AI model for intelligent code completion
- **Multi-Language Support** - Python, JavaScript, Java, C++, Terraform, and 15+ languages
- **Context-Aware Completion** - Understands code context and provides relevant suggestions
- **Real-Time Suggestions** - Instant AI-powered code completion in the editor
- **Code Explanation** - AI-generated explanations of code snippets
- **Code Improvement** - Suggestions for code optimization and best practices
- **Offline Operation** - Fully local AI model, no external API calls required
- **7B Model Optimized** - Designed to work efficiently with CodeLlama-7B models

### 🧠 Advanced AI Build Intelligence
- **Predictive Intervention** - Predicts and prevents build failures before they occur
- **Adaptive Build Strategies** - Dynamically adjusts build approach based on environment and failures
- **Root Cause Analysis** - Traces failures to actual causes instead of symptoms
- **Success Learning Engine** - Learns from successful builds to optimize future builds
- **Context-Aware Fixes** - Applies fixes based on build environment and history
- **Autonomous Build Management** - Fully autonomous AI-driven OS builds with real-time issue resolution
- **Proactive Intelligence** - Shifts from reactive error handling to predictive build optimization

### 🔀 Merge Request/Pull Request System
- **Web-based Code Review** - GitHub/GitLab-style merge request interface
- **Advanced Diff Visualization** - Side-by-side diff with syntax highlighting and inline comments
- **Interactive Comments** - Click-to-comment on any diff line with threading
- **Conversation Threading** - General comments and discussions
- **Merge Conflict Detection** - Automatic conflict checking
- **Multi-format Diff Support** - Git HEAD comparison, file-to-file, custom content

### 🔍 Built-in Linting & Code Analysis
- **Multi-language Support** - Python, JavaScript, TypeScript, C++, Java code analysis
- **Automated Quality Checks** - Style, security, and best practice violations
- **Project-wide Analysis** - Scan entire repositories or individual files
- **Security Scanning** - Built-in security vulnerability detection
- **Linter Integration** - Support for flake8, pylint, bandit, ESLint, cppcheck

### 📦 Multi-Container Development Environments
- **Isolated Workspaces** - Separate containerized environments for different projects
- **Pre-configured Stacks** - Python, Node.js, Java, C++ development environments
- **Container Terminal** - Web-based terminal access to development containers
- **Volume Mounting** - Automatic workspace mounting for persistent development
- **Port Management** - Automatic port mapping for web applications
- **Resource Isolation** - CPU, memory, and network isolation per environment
- **Security Hardening** - Read-only containers with restricted privileges
- **Resource Monitoring** - Real-time resource usage tracking and limits

### 🚀 Project Templates & Scaffolding
- **Pre-built Templates** - Python, Node.js, C++, Flask, Express projects
- **One-click Creation** - Instant project setup with proper structure
- **Dependency Management** - Integrated build configs and package files
- **Git Integration** - Projects created as ready-to-clone repositories
- **Template System** - Extensible framework for custom templates

### 🔧 Build Management & Dependencies
- **Project Type Detection** - Automatic detection of Python, Node.js, C++, Java projects
- **Dependency Installation** - One-click dependency management (pip, npm, cmake)
- **Build Automation** - Automated build processes with real-time output
- **Test Integration** - Run project tests with visual feedback
- **Build Status Tracking** - Monitor dependency and build artifact status

### 🎛️ Service Orchestration & Dependency Management
- **Multi-Service Applications** - Docker Compose support with dependency resolution
- **Service Discovery** - Automatic service registration and health monitoring
- **Dependency Analysis** - Cross-platform dependency resolution (npm, pip, maven, gradle)
- **Conflict Detection** - Automatic detection of version conflicts and circular dependencies
- **Installation Ordering** - Optimal dependency installation sequence
- **Lockfile Generation** - Reproducible dependency resolution with lockfiles
- **Service Scaling** - Dynamic service scaling and resource management
- **Health Monitoring** - Continuous service health checks and status reporting

### 🛡️ Vulnerability Assessment & Remediation
- **Comprehensive Scanning** - Multi-language vulnerability detection (Python, JavaScript, Docker)
- **Advanced Dependency Vulnerabilities** - CVE detection in npm, pip, maven, gradle with version-specific matching
- **Code Security Analysis** - Detection of dangerous functions and patterns
- **Secret Detection** - Identification of exposed credentials and API keys
- **Container Security** - Dockerfile security best practices analysis
- **File-Level Integration** - Real-time dependency scanning in editor and Git file viewer
- **Repository Awareness** - Automatic dependency analysis during repository browsing
- **Remediation Planning** - Automated fix recommendations with version-specific guidance
- **Multi-Source Detection** - Scans requirements.txt, package.json, setup.py, and import statements

### 📊 Code Coverage Reporting & Metrics
- **Multi-Language Support** - Python, JavaScript, Java coverage analysis
- **Test Coverage Analysis** - Line, branch, and function coverage metrics
- **Visual Dashboard** - Interactive coverage reports with detailed breakdowns
- **File-Level Analysis** - Individual file coverage with missing line identification
- **Repository Integration** - Direct Git repository coverage analysis
- **Coverage Grading** - Automated quality grading (A-F) based on coverage percentages
- **Historical Tracking** - Coverage trend analysis and comparison
- **Integration** - Seamless integration with existing build and test workflows

### 🔒 Sandboxed Execution Environments
- **Dual-Mode Operation** - Simplified mode (instant) or Docker mode (full isolation)
- **Multi-Language Support** - Python, Node.js, Java, C++, Terraform development environments
- **Integrated Code Editor** - Built-in editor with syntax highlighting and file management
- **Automatic Linting** - Real-time code quality analysis during execution
- **Vulnerability Scanning** - Automatic security scanning of code and dependencies
- **Resource Isolation** - CPU, memory, and network isolation per sandbox (Docker mode)
- **Security Hardening** - Read-only containers with restricted privileges (Docker mode)
- **Terminal Access** - Web-based terminal access to sandbox environments
- **Bulk Management** - Remove individual sandboxes or all sandboxes at once

### 🚨 Threat Intelligence System
- **Real-time CVE Feeds** - Continuous monitoring of NVD, MITRE, and CISA vulnerability databases
- **Malware Signature Detection** - Pattern-based malware detection with obfuscation and network activity analysis
- **IOC Monitoring** - Indicators of Compromise tracking with threat actor attribution
- **Supply Chain Attack Detection** - Typosquatting detection and suspicious package analysis
- **Dark Web Monitoring** - Credential leak detection and data breach alerts (simulated)
- **Code Threat Scanning** - Real-time scanning of code for malware signatures and IOC matches
- **Automated Threat Updates** - Hourly updates of threat intelligence feeds and signatures
- **Threat Dashboard** - Comprehensive dashboard with metrics, recent threats, and search capabilities

### 🔍 Diff Visualization & Code Review
- **Interactive Diff Viewer** - GitHub/GitLab-style diff visualization with syntax highlighting
- **Inline Comments System** - Click any line to add comments with author attribution
- **Multi-format Comparison** - Git HEAD, saved files, custom content comparison
- **Real-time Statistics** - Addition/deletion counts and change metrics
- **Comment Threading** - Multiple comments per line with timestamps
- **Editor Integration** - Direct access from all code editors

### 🤖 AI Model Security & Governance
- **Model Provenance Tracking** - Complete audit trail of model origins, sources, and download history
- **Integrity Verification** - SHA256 checksums and signature validation for model authenticity
- **AI Safety Guardrails** - Real-time detection of harmful code generation patterns
- **Performance Monitoring** - Drift detection and baseline performance tracking
- **Trust Scoring** - Automated trust assessment based on source reputation and characteristics
- **Violation Detection** - Pattern-based safety violation detection with severity classification
- **Secure Model Registry** - Centralized database for all AI model security metadata
- **Trusted Model Catalog** - Curated collection of AI models from UK-allied countries only
- **Fallback Download Sources** - Multiple verified sources with automatic failover
- **Country-Based Filtering** - Blocks models from untrusted jurisdictions (CN, RU, IR, KP, BY)
- **Federated Learning** - Secure collaborative model training without sharing raw data

### 🏗️ OS Builder with Advanced AI Intelligence & Git-First Build System
- **Complete OS Build System** - Build SecureAI-OS from scratch with Linux kernel, GCC toolchain, and AI integration
- **Git-First Build Sources** - All build files stored in dedicated Git repository with automatic fallback to external sources
- **Resilient Download System** - Continues downloading even if some files fail, with comprehensive error tracking
- **Git Integration** - Automatic Git repository creation for each build with complete source and binary tracking
- **Resume Downloads** - Intelligent resume capability from exact interruption point (8.5%, 25%, 50%, etc.)
- **Multiple Mirror Sources** - 3+ backup sources per package with automatic failover (kernel.org, gnu.org, mirrors.kernel.org)
- **Build Source Manager** - Centralized management of all source files with checksum verification and version control
- **Advanced AI Intelligence** - 5 AI capabilities: Predictive Intervention, Adaptive Strategies, Root Cause Analysis, Success Learning, Context-Aware Fixes
- **Autonomous Build Management** - Fully autonomous AI-driven builds with real-time monitoring and automatic issue resolution
- **Smart Retry System** - One-click retry with enhanced error handling and 30-50% faster rebuilds
- **Build Templates** - Pre-configured templates (minimal-ai, desktop-ai, server-ai, embedded-ai)
- **Storage Flexibility** - Build to internal storage or external USB drives with automatic detection
- **Real-time Monitoring** - Live build progress with 6-step process tracking and failure detection
- **Success Learning Database** - AI learns from successful builds to optimize future build strategies and sequences
- **Comprehensive Documentation** - Auto-generated build reports, security scans, and failure diagnostics

### 🔧 Error Diagnosis & Resolution System
- **Intelligent Error Analysis** - Pattern-based error recognition with 90%+ confidence for common issues
- **Automated Solutions** - Actionable fix recommendations for connection errors, permission problems, and storage issues
- **System Health Monitoring** - Real-time monitoring of disk usage, memory consumption, and service status
- **Pattern Matching Engine** - Recognition of 10+ error types including network failures, authentication issues, and resource constraints
- **Severity Classification** - Automatic categorization of errors by impact level (Info, Low, Medium, High, Critical)
- **Prevention Guidance** - Proactive recommendations to prevent recurring issues
- **Admin-Only Access** - Secure diagnostic tools requiring authentication to protect system information

### ⚙️ Advanced Features
- **Code Editor** - Built-in editor with diff and search functionality
- **Workspace Manager** - Separate archive and working environments
- **System Monitoring** - Resource usage and health monitoring
- **Firefox ESR Compatible** - Works with enterprise browser restrictions
- **Dropdown Navigation** - Organized navigation with grouped functionality
- **API Endpoints** - RESTful APIs for all Git operations

## Usage Guide

### Data Manager
Access: **http://localhost:8080/data-manager/**

**Import from USB:**
1. Insert USB drive (auto-detected)
2. Select USB drive from dropdown
3. Choose target (workspace/archive)
4. Browse and select files
5. Click Import

**Export to USB:**
1. Select source data type
2. Choose USB drive destination
3. Browse target directory
4. Click Export

### Git Repositories
Access: **http://localhost:8080/git-repos/**

**Clone Repository:**
```bash
git clone http://localhost:8080/git/repo-name.git
```

**Web Interface:**
- Browse files and directories
- View commit history and diffs
- Navigate branches and tags
- Download individual files

### Branch Protection Rules
Access: **http://localhost:8080/branch-protection/**

**Create Protection Rule:**
1. Select repository from dropdown
2. Click "Add Protection Rule"
3. Configure rule settings:
   - **Branch Pattern**: `main`, `develop`, `release/*` (supports wildcards)
   - **Block Direct Push**: Require pull requests for changes
   - **Required Reviews**: Minimum number of code reviews (0-10)
   - **Enforce Admins**: Apply rules to administrator users
   - **Dismiss Stale Reviews**: Auto-dismiss when new commits pushed
   - **Admin Users**: Comma-separated list of users who can bypass rules
4. Click "Create Rule"

**Protection Features:**
- **Pattern Matching**: Use wildcards to protect multiple branches (`feature/*`, `hotfix/*`)
- **Git Hook Enforcement**: Server-side pre-receive hooks block unauthorized pushes
- **Admin Bypass**: Designated admin users can override protection rules
- **Review Requirements**: Enforce code review workflows before merging
- **Real-time Validation**: Push operations validated against protection policies

**Common Protection Patterns:**
```bash
# Protect main branch - require reviews, block direct push
Pattern: main
Settings: Block Direct Push ✓, Required Reviews: 2

# Protect all release branches
Pattern: release/*
Settings: Block Direct Push ✓, Required Reviews: 1, Enforce Admins ✓

# Protect development branch with admin bypass
Pattern: develop
Settings: Block Direct Push ✓, Admin Users: admin,maintainer
```

**Git Hook Integration:**
Protection rules are enforced via Git pre-receive hooks that:
- Check branch patterns against protection rules
- Block direct pushes to protected branches
- Validate user permissions and admin bypass
- Provide clear error messages for blocked operations

### AI Code Completion
Access: **Code Editor with 🤖 AI Complete button**

**Setup CodeLlama Model:**
1. Download CodeLlama-7B model (GGUF format)
2. Place in `/var/repo/models/` directory
3. Restart container to detect model

**Using AI Completion:**
1. Open any file in the Code Editor
2. Position cursor where you want completion
3. Click 🤖 AI Complete button
4. Review suggestions and click "Insert" to use

**New File Templates:**
- **Empty Files**: Automatically provides starter templates
- **Terraform**: Complete AWS provider setup with example resources
- **Python**: Module template with main function
- **JavaScript**: Node.js compatible module template
- **Java**: Basic class with main method

**Terraform Resource Completion:**
- **aws_s3_bucket**: Bucket configuration with tags
- **aws_vpc**: VPC with DNS settings and CIDR block
- **aws_instance**: EC2 instance with AMI and instance type
- **aws_security_group**: Security group with ingress/egress rules
- **Variables/Outputs**: Proper Terraform variable and output blocks

**AI Features:**
- **Code Completion**: Context-aware code suggestions with starter templates for new files
- **Code Explanation**: AI explains selected code snippets  
- **Code Improvement**: Suggestions for optimization
- **Multi-Language**: Python, JavaScript, Java, C++, Terraform, Go, Rust, PHP, Ruby, etc.
- **Smart Templates**: Automatic starter templates for empty files
- **Resource-Aware**: Terraform resource-specific completions (AWS S3, VPC, EC2, etc.)

### 📚 Automated Documentation Generation
- **AI-Powered Analysis** - Intelligent code analysis and documentation creation
- **Multi-Language Support** - Python, JavaScript, Java, Terraform, and more
- **Project Documentation** - Complete README, API docs, and architecture documentation
- **File Documentation** - Individual file analysis with functions, classes, and structure
- **Repository Documentation** - Git repository analysis and documentation generation
- **Multiple Export Formats** - Markdown, HTML, and JSON export options
- **Code Structure Analysis** - Automatic detection of functions, classes, imports, and dependencies
- **Template-Based Generation** - Professional documentation templates with consistent formatting

**Model Requirements:**
- **Minimum**: 8GB RAM for CodeLlama-7B
- **Storage**: 4GB for model file (3.8GB download)
- **Format**: GGUF quantized models (automatically downloaded)
- **Network**: Internet connection required for initial download only

### Documentation Generator
Access: **http://localhost:8080/documentation/**

**Generate Project Documentation:**
1. Navigate to Documentation Generator interface
2. Select "Project Documentation" tab
3. Enter project path (e.g., `/var/repo/workspace/my-project`)
4. Click "Generate Documentation"
5. Review generated README, API docs, and analysis
6. Export in desired format (Markdown, HTML, JSON)

**Generate File Documentation:**
1. Select "File Documentation" tab
2. Enter file path (e.g., `/var/repo/workspace/main.py`)
3. Click "Generate Documentation"
4. View detailed function/class analysis

**Generate Repository Documentation:**
1. Select "Repository Documentation" tab
2. Choose repository from dropdown
3. Click "Generate Documentation"
4. Get comprehensive project analysis

**Documentation Features:**
- **Automatic Analysis**: Detects functions, classes, imports, and dependencies
- **Multi-Language**: Python, JavaScript, Java, Terraform, Go, Rust, PHP, Ruby
- **Project Structure**: Analyzes entry points, config files, and project type
- **Professional Templates**: README with installation, usage, and API sections
- **Export Options**: Download as Markdown (.md), HTML (.html), or JSON (.json)
- **Code Insights**: Line counts, complexity analysis, and architectural overview

### Secure Repository Mirroring
Access: **http://localhost:8080/mirror-manager/**

**Mirror External Repository:**
1. Navigate to Mirror Manager interface
2. Enter external repository URL (GitHub, GitLab, etc.)
3. System performs comprehensive analysis:
   - **Trust Analysis** - Geographic origin, contributor patterns
   - **Legal Compliance** - License verification, export control
   - **Security Scanning** - Malware detection, suspicious content
4. Review analysis results with trust/legal scores
5. Approve, reject, or override with warnings
6. Successfully mirrored repositories available as read-only

**Trust Analysis Features:**
- **Geographic Analysis** - Server location, hosting provider identification
- **Contributor Assessment** - Email domain verification, account age analysis
- **License Detection** - Automatic recognition of MIT, Apache, GPL, BSD licenses
- **Security Scanning** - Binary file detection, Git hook analysis
- **Export Control** - Cryptography and dual-use technology detection

**Repository Types:**
- **Local Repositories** - Full read/write access, created via Git Admin
- **External Mirrors** - Read-only clones from external sources with trust verification
- **Quarantined Repositories** - Failed trust analysis, admin override available

**Repository Management:**
Access: **http://localhost:8080/git-admin/**

**Create Local Repository:**
1. Click "Create Repository" button
2. Enter repository name (will auto-add .git extension)
3. Add optional description
4. Click "Create Repository"
5. Repository is immediately available for cloning with **full read/write access**

**Create Branch (Local Repositories Only):**
1. Click "Branch" button on any local repository
2. Enter new branch name (e.g., feature/new-feature)
3. Select source branch from dropdown
4. Click "Create" to create branch
5. **Note:** Branch creation blocked for external mirrors (read-only)

**Delete Repository:**
1. Click "Delete" button on repository
2. Confirm deletion (this action cannot be undone)
3. Repository and all data will be permanently removed
4. **Note:** External mirrors cannot be deleted (use quarantine management)

**Repository Protection:**
- **Local Repositories** - Full modification rights (push, branch creation, deletion)
- **External Mirrors** - Read-only protection prevents all modifications
- **Visual Indicators** - Clear marking of repository types in interface
- **Error Messages** - Informative feedback when attempting blocked operations

**Features:**
- Visual repository overview with statistics
- Real-time repository information (commits, branches, size)
- Copy-paste clone URLs for each repository
- Repository type identification (Local vs External Mirror)
- Trust score display for external mirrors

### Workspace Management
Access: **http://localhost:8080/workspace/**

**Archive → Workspace Sync:**
- Copies pristine data to working environment
- Preserves original archive data
- Creates isolated development space

**Workspace Operations:**
- Edit files without affecting archive
- Test configurations safely
- Export results when ready

### Project Templates
Access: **http://localhost:8080/project-templates/**

**Available Templates:**
- **Python Basic** - Virtual environment, requirements.txt, setup.py
- **Python Flask** - Web application with templates and static files
- **Node.js Basic** - Package.json with npm scripts and dependencies
- **Node.js Express** - REST API with Express framework
- **C++ Basic** - CMake configuration and build structure
- **Terraform Basic** - Basic Terraform configuration with AWS provider
- **Terraform AWS VPC** - Complete VPC setup with subnets and security groups
- **Terraform AWS Lambda** - Serverless API with Lambda and API Gateway
- **Terraform AWS S3 + CloudFront** - Static website with CDN and SSL

**Create New Project:**
1. Browse available templates
2. Click "Create Project" on desired template
3. Enter project name and optional description
4. Click "Create Project" - instant Git repository creation
5. Clone and start developing: `git clone http://localhost:8080/git/project-name.git`

**Template Features:**
- Proper project structure and best practices
- Integrated dependency management (requirements.txt, package.json, CMakeLists.txt)
- Build and setup instructions in README.md
- Appropriate .gitignore files
- Ready-to-run example code

### Build Manager
Access: **http://localhost:8080/build-manager/**

**Supported Project Types:**
- **Python** - Virtual environments, requirements.txt, setup.py
- **Python Flask** - Web applications with Flask dependencies
- **Node.js** - npm package management and scripts
- **C++** - CMake build system configuration
- **Java Maven** - Maven dependency and build management
- **Java Gradle** - Gradle build system support

**Build Operations:**
1. **Project Detection** - Automatically detects project type and dependencies
2. **Install Dependencies** - One-click dependency installation
3. **Build Project** - Execute build commands with real-time output
4. **Run Tests** - Execute test suites with results display
5. **Status Monitoring** - Track build artifacts and dependency status

**Features:**
- Real-time build output in terminal-style interface
- Visual dependency status indicators
- Build artifact detection and tracking
- Error handling with detailed feedback
- Integration with Git repositories

### Merge Requests
Access: **http://localhost:8080/merge-requests/**

**Create Merge Request:**
1. Click "New Merge Request" button
2. Select repository and source/target branches
3. Add title and description
4. Click "Create Merge Request"
5. Share MR link for code review

**Code Review Process:**
1. **View Changes** - Browse commits and file diffs
2. **Add Comments** - General discussion comments
3. **Inline Comments** - Click any line to add specific feedback
4. **Review Status** - Track open/merged/closed states
5. **Merge Decision** - Visual conflict detection

**Features:**
- GitHub/GitLab-style interface
- Side-by-side diff visualization
- Syntax-highlighted code changes
- Line-by-line commenting system
- Conversation threading
- Merge conflict detection
- Multi-repository support

### Service Orchestration
Access: **http://localhost:8080/services/**

**Multi-Service Application Management:**
1. **Load Docker Compose** - Import services from docker-compose.yml files
2. **Dependency Resolution** - Automatic service startup ordering based on dependencies
3. **Service Control** - Start, stop, restart, and scale individual services
4. **Health Monitoring** - Continuous health checks with status reporting
5. **Resource Management** - Monitor and control service resource usage

**Features:**
- Docker Compose file support
- Automatic dependency resolution
- Service discovery and registration
- Real-time health monitoring
- Web-based service management
- Container logs and debugging
- Service scaling and load balancing

### Dependency Management
Access: **http://localhost:8080/dependencies/**

**Cross-Platform Dependency Analysis:**
1. **Project Analysis** - Scan projects for dependency files (package.json, requirements.txt, pom.xml, etc.)
2. **Conflict Detection** - Identify version conflicts and circular dependencies
3. **Resolution Ordering** - Generate optimal installation sequence
4. **Lockfile Generation** - Create reproducible dependency snapshots
5. **Export Options** - Export dependency graphs in JSON, YAML, or DOT format

**Supported Package Managers:**
- **NPM** - package.json, package-lock.json
- **Python** - requirements.txt, setup.py, Pipfile
- **Maven** - pom.xml dependency management
- **Gradle** - build.gradle dependency resolution
- **Composer** - composer.json for PHP projects

**Features:**
- Multi-language dependency analysis
- Version conflict detection
- Circular dependency identification
- Installation order optimization
- Dependency tree visualization
- Lockfile generation for reproducible builds

### Vulnerability Assessment
Access: **http://localhost:8080/security/**

**Comprehensive Security Scanning:**
1. **Project Analysis** - Full project vulnerability assessment with multi-language support
2. **Repository Scanning** - Direct Git repository security analysis
3. **Dependency Vulnerabilities** - CVE detection in npm, pip, and other package managers
4. **Code Security** - Detection of dangerous functions, patterns, and security anti-patterns
5. **Secret Detection** - Identification of exposed API keys, passwords, and credentials
6. **Container Security** - Dockerfile and container configuration analysis

**Vulnerability Types:**
- **Dependency** - Known vulnerabilities in third-party packages
- **Code** - Insecure coding patterns and dangerous function usage
- **Configuration** - Misconfigurations in Docker, CI/CD, and deployment files
- **Secrets** - Exposed credentials, API keys, and sensitive information
- **Container** - Docker security issues and best practice violations

**Remediation Features:**
- Automated fix recommendations with specific guidance
- Priority-based remediation planning (Critical → High → Medium → Low)
- Integration with existing editor security analysis
- Real-time vulnerability detection during file editing
- Comprehensive reporting with severity classification

**Dependency Scanning Features:**
- **Multi-File Detection** - Scans requirements.txt, package.json, setup.py, and source imports
- **Version Analysis** - Precise version matching against vulnerability databases
- **Real-time Editor Integration** - Immediate feedback when editing dependency files
- **Git Repository Scanning** - Automatic dependency analysis during repository browsing
- **Cross-Language Support** - Python (pip), JavaScript (npm), Java (Maven/Gradle)
- **Offline Database** - Built-in vulnerability patterns for offline scanning

### Code Coverage Dashboard
Access: **http://localhost:8080/coverage/**

**Test Coverage Analysis:**
1. **Project Analysis** - Generate comprehensive coverage reports for local projects
2. **Repository Scanning** - Direct Git repository coverage analysis
3. **Multi-Language Support** - Python (coverage.py), JavaScript (nyc/Istanbul), Java (JaCoCo)
4. **Visual Metrics** - Interactive dashboard with coverage percentages and grades
5. **File-Level Details** - Individual file analysis with missing line identification
6. **Coverage Comparison** - Compare coverage reports across different versions

**Coverage Metrics:**
- **Line Coverage** - Percentage of executable lines covered by tests
- **Branch Coverage** - Percentage of code branches executed during testing
- **Function Coverage** - Percentage of functions called by test suites
- **Coverage Grading** - Automated quality assessment (A-F grades)

**Dashboard Features:**
- Real-time coverage percentage display with color-coded indicators
- Detailed file-by-file coverage breakdown
- Missing lines identification for targeted test improvement
- Coverage grade calculation with improvement recommendations
- Export capabilities for coverage reports and metrics
- Integration with existing project build and test workflows

### Threat Intelligence Dashboard
Access: **http://localhost:8080/threat-intelligence/**

**Start Threat Monitoring:**
1. Navigate to Threat Intelligence Dashboard
2. Click "Start" to begin real-time monitoring
3. Monitor CVE feeds, IOC indicators, and supply chain threats
4. Use search functionality to find specific threats
5. Scan code for malware signatures and IOC matches

**Threat Intelligence Features:**
- **CVE Database Search**: Search by severity, exploited status, and keywords
- **IOC Indicator Search**: Filter by type (IP, domain, hash, URL) and threat actor
- **Supply Chain Monitoring**: Detect typosquatting and suspicious packages
- **Dark Web Alerts**: Monitor for credential leaks and data breaches
- **Code Scanner**: Real-time threat scanning of code snippets
- **Automated Updates**: Hourly refresh of threat intelligence feeds

**Dashboard Metrics:**
- Total CVEs tracked with severity breakdown
- High severity and exploited CVE counts
- IOC indicators with confidence ratings
- Supply chain threats and dark web alerts
- Real-time threat feed status and last update times

### Sandbox Environments
Access: **http://localhost:8080/sandbox/**

**Create Sandbox Environment:**
1. **Choose Mode** - Simplified (instant) or Docker (full isolation)
2. **Select Environment** - Python, Node.js, Java, C++, or Terraform
3. **Optional Project Import** - Copy existing project files into sandbox
4. **Code Editor** - Built-in editor with syntax highlighting and file management
5. **Execute Code** - Run code with automatic linting and vulnerability scanning

**Simplified Mode Features:**
- **Instant Creation** - No Docker container startup delay
- **File System Workspace** - Direct file system access for faster operations
- **Full Development Tools** - Same linting and security scanning as Docker mode
- **Project Import** - Copy files from existing projects
- **Recommended** - Faster and more responsive for most development tasks

**Docker Mode Features:**
- **Complete Isolation** - Each sandbox runs in isolated Docker container
- **Resource Limits** - 512MB memory limit and CPU quota restrictions
- **Security Hardening** - Read-only containers with restricted privileges
- **Network Isolation** - Sandboxes cannot access external networks
- **Terminal Access** - Web-based terminal for advanced operations

**Development Tools (Both Modes):**
- **Multi-Language Linting** - flake8/pylint (Python), ESLint (JavaScript), cppcheck (C++), terraform fmt/tflint (Terraform)
- **Vulnerability Detection** - bandit (Python), npm audit (Node.js), tfsec (Terraform)
- **File Management** - Create, edit, and save files within sandbox
- **Code Execution** - Run code with real-time output and error reporting
- **Project Import** - Copy existing projects into sandbox environments

**Sandbox Management:**
- **Individual Removal** - Stop and remove specific sandboxes
- **Bulk Removal** - "Remove All" button to clean up all sandboxes at once
- **Status Monitoring** - View sandbox status (running, stopped, ready)
- **Resource Tracking** - Monitor sandbox resource usage

### Code Editor
Access: **http://localhost:8080/editor/**

**Enhanced Editor Features:**
- **Syntax highlighting** - Multi-language support with color coding
- **Context-sensitive help** - Intelligent autocomplete and documentation
- **Copy/Insert snippets** - One-click code insertion from help suggestions
- **Undo system** - Track and revert edits with Ctrl+Z or undo button
- **Real-time diff** - Show changes against saved file instantly
- **Advanced diff viewer** - Full-featured diff with inline comments
- **Search & replace** - Find/replace with regex support
- **Security analysis** - Real-time vulnerability detection
- **File browser** - Navigate workspace files with tree view
- **Git integration** - Edit files directly from Git repositories

**Context Help System:**
1. **Position cursor** on any code element or select text
2. **Click "Get Help"** to see relevant documentation and examples
3. **Hover over code snippets** to reveal copy/insert buttons
4. **Click 📋** to copy snippet to clipboard
5. **Click ➕** to insert snippet at cursor position
6. **Press Ctrl+Space** for autocomplete suggestions

**Undo Functionality:**
- **Automatic tracking** - Saves undo states after typing pauses
- **Manual operations** - Tracks snippet insertions and replacements
- **Keyboard shortcut** - Ctrl+Z (Cmd+Z on Mac) to undo
- **Visual button** - ↶ Undo button shows available operations
- **Cursor restoration** - Restores both content and cursor position

**Diff System:**
- **Show Diff** - Quick inline diff modal showing changes
- **Advanced Diff** - Full-featured diff viewer in new tab
- **Real-time comparison** - Compare current editor vs saved file
- **Git comparison** - Compare against Git HEAD when available
- **Visual indicators** - Color-coded additions, deletions, and context
- **Change statistics** - Live counts of modifications

**Editor Workflow:**
```bash
# 1. Access editor
http://localhost:8080/editor/

# 2. Select file from recent files or browse workspace
# 3. Edit with full IDE-like features:
#    - Context help for any code element
#    - Copy/insert code snippets
#    - Real-time security scanning
#    - Undo/redo operations
#    - Live diff visualization

# 4. Save changes and view diffs
# 5. Use Advanced Diff for detailed code review
```

### Diff Visualization
Access: **http://localhost:8080/diff-viewer/**

**Interactive Diff Features:**
1. **Generate Diff** - Compare files against Git HEAD, saved versions, or custom content
2. **Visual Comparison** - Side-by-side view with color-coded additions/deletions
3. **Inline Comments** - Click any line to add comments with author attribution
4. **Change Statistics** - Real-time counts of additions, deletions, and modifications
5. **Comment Threading** - Multiple comments per line with timestamps

**Usage:**
- **From Editor** - Click "Advanced Diff" button in any code editor
- **Direct Access** - Navigate to `/diff-viewer/` and enter file path
- **Sandbox Integration** - "Diff" button in sandbox editors
- **API Access** - RESTful endpoints for programmatic diff generation

**Comment System:**
- **Line-specific** - Add comments to any diff line (additions, deletions, context)
- **Author Tracking** - Comments include author name and timestamp
- **Visual Indicators** - Comment icons appear on lines with discussions
- **Toggle View** - Show/hide comment threads as needed

### AI Model Security & Governance
Access: **http://localhost:8080/ai-model-security/**

**Trusted Model Catalog:**
1. Navigate to "Register Model" tab to view AI Model Catalog
2. Browse curated models from trusted sources (US, GB, CA, AU, NZ, DE, FR, etc.)
3. View model details: size, license, vendor, country of origin
4. Click "Download" to get model with automatic fallback sources
5. Click "Sources" to check availability of download mirrors

**Available Trusted Models:**
- **CodeLlama 7B Instruct** (Meta, US) - 3.8GB - Code generation and completion
- **Phi-3 Mini 4K** (Microsoft, US) - 2.3GB - Small but capable language model
- **Mistral 7B Instruct** (Mistral AI, FR) - 4.1GB - Efficient 7B parameter model
- **Gemma 2B Instruct** (Google, US) - 1.4GB - Lightweight instruction-tuned model
- **StarCoder2 3B** (Hugging Face, US) - 1.7GB - Code generation specialist

**Model Security Features:**
- **Country Verification** - Only models from UK-allied countries allowed
- **Vendor Trust** - Verified sources (Meta, Microsoft, Google, Hugging Face, Mistral AI)
- **Multiple Sources** - Automatic fallback if primary download fails
- **Integrity Verification** - SHA256 checksums and file validation
- **Provenance Tracking** - Complete audit trail of model origins
- **Safety Monitoring** - Real-time detection of harmful code patterns
- **Performance Tracking** - Drift detection and baseline monitoring

**Federated Learning:**
1. Navigate to "Federated Learning" tab
2. **Register Participants** - Add trusted organizations with public keys
3. **Start FL Round** - Initiate collaborative training for specific model
4. **Monitor Progress** - Track active rounds and participant contributions
5. **Aggregate Updates** - Combine model improvements securely

**FL Security Features:**
- **Trusted Participants Only** - Country verification (UK-allied nations)
- **Cryptographic Authentication** - Public key verification
- **Privacy Preserving** - Only model deltas shared, never raw data
- **Weighted Aggregation** - Updates weighted by data samples and trust scores
- **Audit Trail** - Complete logging of all federated learning activities

**Federated Learning Workflow:**
```bash
# 1. Register Organization (Admin)
POST /api/federated-learning/participants/register
{
  "participant_id": "university.example.edu",
  "public_key": "-----BEGIN PUBLIC KEY-----...",
  "country_code": "US",
  "organization": "Example University"
}

# 2. Start FL Round (Admin)
POST /api/federated-learning/rounds/start
{
  "model_id": "codellama-7b-001",
  "target_participants": 3,
  "duration_hours": 24
}

# 3. Submit Model Update (Participant)
POST /api/federated-learning/updates/submit
{
  "round_id": "fl_round_abc123",
  "participant_id": "university.example.edu",
  "model_delta": "base64_encoded_model_weights",
  "data_samples": 10000,
  "loss_improvement": 0.05
}

# 4. Aggregate Updates (Admin)
POST /api/federated-learning/rounds/{round_id}/aggregate
# Returns: aggregated_model_hash for distribution
```

**FL Participant Requirements:**
- **Trusted Country** - Must be from UK-allied nation (US, GB, CA, AU, NZ, DE, FR, NL, SE, NO, DK, FI)
- **Public Key Authentication** - RSA/ECDSA public key for cryptographic verification
- **Trust Score ≥30** - Minimum trust threshold for participation
- **Organization Verification** - Valid organization name and contact information

**FL Round Management:**
- **Target Participants** - Configurable (2-10 participants)
- **Duration Control** - Flexible round duration (1-168 hours)
- **Automatic Aggregation** - Triggers when target participants reached
- **Manual Override** - Admin can force aggregation with minimum participants
- **Progress Monitoring** - Real-time tracking of submissions and status

**Safety Violation Detection:**
- **Harmful Code** - Destructive commands (rm -rf, format, DROP DATABASE)
- **Malicious Patterns** - Backdoors, keyloggers, credential exposure
- **Privacy Violations** - Personal data exposure, PII leakage
- **Security Risks** - Code injection, system exploitation attempts

**Trust Assessment Levels:**
- **High Trust (80-100)** - Verified sources, established repositories
- **Medium Trust (50-79)** - Known sources with verification
- **Low Trust (0-49)** - Unknown sources, failed verification

### Error Diagnosis System
Access: **http://localhost:8080/error-diagnosis/**

**Diagnose Application Errors:**
1. Navigate to Error Diagnosis interface (requires admin login)
2. Enter error message or paste error output
3. Click "Diagnose Error" for intelligent analysis
4. Review diagnosis with confidence score and solutions

**System Health Check:**
1. Click "Check System Health" for comprehensive status
2. Review disk usage, memory consumption, and service status
3. Get recommendations for system optimization

**Error Analysis Features:**
- **Pattern Recognition** - Identifies 10+ common error types with 90%+ confidence
- **Intelligent Solutions** - Provides actionable fix recommendations
- **Severity Assessment** - Classifies errors by impact level (Info to Critical)
- **Root Cause Analysis** - Explains underlying causes of issues
- **Prevention Guidance** - Suggests measures to prevent recurring problems

## Architecture

### Container Structure
```
/var/repo/
├── archive/          # Pristine data storage
│   ├── sources/      # Source packages
│   ├── packages/     # Binary packages
│   ├── cache/        # Build cache
│   └── git-repos/    # Git repositories
├── workspace/        # Working environment
│   └── [same structure as archive]
└── flask-app/        # Web application
```

### Volume Mounts
- `/var/repo` - Persistent data storage
- `/run/media` - USB auto-mount detection (RW)
- `/media` - Manual mount points (RW)
- `/mnt` - Additional storage (RW)
- `/host/home` - Host user directories (RO) - for IDE project access
- `/host/Users` - macOS user directories (RO) - for IDE project access
- `/host/opt` - Host optional software (RO)
- `/host/projects` - Custom project directories (RO)

### Network Ports
- **8080** - Web interface (HTTP)
- **9418** - Git daemon (optional)

## Storage Management

### USB Drive Detection
- **Auto-detection** of plugged USB drives
- **Real-time** disk space monitoring
- **Multiple filesystem** support (exFAT, NTFS, FAT32, ext4)
- **Hot-plug** support (no restart required)

### Disk Selection
- **Free space** information for each drive
- **Device type** identification (USB, SD Card, NVMe, etc.)
- **Mount point** display with available space
- **Read/write** access to external storage

## Development

### Container Management
```bash
# View logs
docker logs secureai-local-repo

# Restart services
docker exec secureai-local-repo supervisorctl restart flask

# Shell access
docker exec -it secureai-local-repo bash

# Update application
docker cp flask-app/ secureai-local-repo:/var/repo/
docker exec secureai-local-repo supervisorctl restart flask
```

### API Endpoints
- `GET /api/system/disks` - Available storage devices
- `POST /api/data/import` - Import data from external source
- `POST /api/data/export` - Export data to external destination
- `POST /api/data/browse` - Browse filesystem
- `GET /api/git/{repo}/info` - Git repository information
- `POST /api/git/create` - Create new Git repository
- `POST /api/git/{repo}/branch` - Create new branch in repository
- `DELETE /api/git/{repo}/delete` - Delete Git repository
- `GET /api/templates` - List available project templates
- `POST /api/templates/create` - Create project from template
- `GET /api/build/{repo}/info` - Get project build information and status
- `POST /api/build/{repo}/install` - Install project dependencies
- `POST /api/build/{repo}/build` - Build project with dependencies
- `POST /api/build/{repo}/test` - Run project tests
- `GET /api/merge-requests` - List merge requests with filtering
- `POST /api/merge-requests` - Create new merge request
- `GET /api/merge-requests/{repo}/{id}` - Get specific merge request
- `GET /api/merge-requests/{repo}/{id}/diff` - Get diff and commits
- `POST /api/merge-requests/{repo}/{id}/comments` - Add general comment
- `POST /api/merge-requests/{repo}/{id}/inline-comments` - Add inline comment
- `GET /api/security/scan/project` - Comprehensive vulnerability scanning
- `POST /api/security/scan/dependencies` - Dependency vulnerability analysis
- `POST /api/security/scan/file-dependencies` - Single file dependency scanning
- `GET /api/security/scan/repository/{repo}` - Repository security analysis
- `POST /api/security/remediation` - Generate remediation plans
- `POST /api/coverage/generate` - Generate code coverage reports
- `GET /api/coverage/repository/{repo}` - Repository coverage analysis
- `GET /api/services` - Service orchestration status
- `POST /api/services/compose` - Load Docker Compose services
- `POST /api/services/start` - Start multi-service applications
- `GET /api/dependencies/analyze` - Cross-platform dependency analysis
- `POST /api/dependencies/resolve` - Dependency conflict resolution
- `POST /api/sandbox/create` - Create new sandbox environment (simplified or Docker mode)
- `POST /api/sandbox/{name}/execute` - Execute code in sandbox with linting and vulnerability scanning
- `GET /api/sandbox/{name}/files` - List files in sandbox
- `GET /api/sandbox/{name}/file/{path}` - Read file from sandbox
- `POST /api/sandbox/{name}/file/{path}` - Write file to sandbox
- `GET /api/sandbox/{name}/terminal` - Get terminal access to sandbox
- `GET /api/sandbox` - List all sandbox environments
- `POST /api/sandbox/{name}/stop` - Stop and remove individual sandbox
- `POST /api/sandbox/stop-all` - Stop and remove all sandboxes
- `POST /api/editor/diff` - Generate diff for file with inline comments support
- `POST /api/diff/comment` - Add inline comment to specific diff line
- `GET /api/diff/comments/{file_path}` - Get all comments for a file
- `POST /api/diff/compare` - Compare two different files with diff visualization
- `POST /api/error/diagnose` - Intelligent error diagnosis and solution recommendations
- `GET /api/system/health` - System health check with resource monitoring
- `GET /api/ai-models/list` - List all registered AI models with security status
- `POST /api/ai-models/register` - Register new AI model with provenance tracking
- `POST /api/ai-models/{id}/verify` - Verify AI model integrity and authenticity
- `POST /api/ai-models/safety-check` - Check generated code for safety violations
- `POST /api/ai-models/performance-test` - Test model performance and detect drift
- `GET /api/ai-models/{id}/status` - Get comprehensive model security status
- `POST /api/os-builder/start` - Start OS build with failure recovery
- `POST /api/os-builder/start-ai` - Start AI-controlled build with Git-first downloads
- `POST /api/os-builder/retry` - Retry failed build with resume capability
- `GET /api/os-builder/analyze-failure` - AI-powered failure analysis
- `GET /api/os-builder/status` - Build status with failure detection
- `GET /api/os-builder/build-log` - Build logs with failure analysis
- `GET /api/os-builder/build-sources` - List available build source files in Git repository
- `POST /api/os-builder/download-sources` - Download build sources with Git-first strategy and resilient downloads

**Repository Security Examples:**
```bash
# High Trust Repository (Auto-Approved):
# URL: https://github.com/microsoft/vscode.git
# Trust Score: 95/100 (US hosting, 1000+ contributors, established)
# Legal Score: 95/100 (MIT license, clear redistribution rights)
# Result: ✅ Automatically mirrored as read-only

# Medium Trust Repository (Requires Confirmation):
# URL: https://github.com/newuser/experimental-tool.git
# Trust Score: 65/100 (New contributors, limited history)
# Legal Score: 85/100 (Apache-2.0 license, compliant)
# Result: ⚠️ User confirmation required

# Low Trust Repository (Rejected):
# URL: https://suspicious-domain.com/user/tool.git
# Trust Score: 35/100 (Blocked country, suspicious contributors)
# Legal Score: 40/100 (No license detected, export control concerns)
# Result: ❌ Automatically quarantined

# Quarantine Management:
# - View quarantined repos: /mirror-manager/ → Quarantined section
# - Admin override: "Restore (Admin Override)" button
# - Restored repos remain READ-ONLY for security
```

## Troubleshooting

### Common Issues

**Connection Reset (localhost:8080):**
- Check if Flask application is running: `docker exec secureai-local-repo supervisorctl status`
- Install missing Python dependencies: `docker exec secureai-local-repo pip3 install PyYAML networkx`
- Restart Flask service: `docker exec secureai-local-repo supervisorctl restart flask`
- Use Error Diagnosis System: Navigate to `/error-diagnosis/` for intelligent troubleshooting

**Sandbox Creation Issues:**
- **Simplified Mode Fails:** Check filesystem permissions and available disk space
- **Docker Mode Fails:** Ensure Docker-in-Docker is properly configured with `--privileged` flag
- **Container Access:** Check container has access to Docker socket: `-v /var/run/docker.sock:/var/run/docker.sock`
- **Terraform Issues:** Verify Terraform containers use proper entrypoint override for shell access
- **Performance:** Use Simplified mode for faster sandbox creation (recommended)

**Sandbox Management Issues:**
- **"Remove All" Not Working:** Check Docker daemon status and container permissions
- **Sandbox Not Stopping:** Use "Remove All" button to force cleanup of problematic containers
- **Status Not Updating:** Refresh the page or check container discovery in Docker daemon

**USB Drive Not Detected:**
- Ensure container has `--privileged` flag
- Check volume mounts include `/run/media:/run/media`
- Verify USB drive is mounted on host system

**Git Clone Fails:**
- Check repository exists in `/var/repo/git-repos/`
- Verify Git HTTP backend is running
- Test with: `curl http://localhost:8080/git/repo.git/info/refs`

**Push to Repository Fails:**
- **External Mirrors**: Push operations are blocked by design (read-only)
- **Local Repositories**: Check repository was created via /git-admin/ (not mirrored)
- **Error Message**: "Push to external mirror not allowed" indicates read-only mirror
- **Solution**: Create local repository copy or use original external source

**Mirror Request Fails:**
- **Trust Analysis**: Repository may fail trust/legal thresholds
- **Network Issues**: Check external repository URL accessibility
- **Blocked Country**: Repository hosted in configured blocked countries
- **License Issues**: No approved license detected or export control concerns
- **Solution**: Review analysis details, adjust thresholds, or use admin override

**Repository Modification Blocked:**
- **Branch Creation**: "Cannot create branches in external mirror" - use local repo
- **Repository Deletion**: "Cannot delete external mirror" - use quarantine management
- **File Editing**: External mirror files are read-only - clone to workspace first

**Firefox ESR Issues:**
- JavaScript functionality may be limited
- Use server-side alternatives when available
- Check browser security settings

**Disk Space Full:**
- Clean Docker system: `docker system prune -a -f --volumes`
- Check available space: `df -h`
- Move data to USB drives using data manager

### Health Checks
```bash
# Container status
docker ps

# Service status
docker exec secureai-local-repo supervisorctl status

# Flask application logs
docker logs secureai-local-repo

# Test web interface
curl -I http://localhost:8080

# Disk usage
curl http://localhost:8080/api/system/disks

# Git repositories
curl http://localhost:8080/api/git/

# Mirror management
curl http://localhost:8080/api/mirror/list
curl http://localhost:8080/api/mirror/quarantine
curl http://localhost:8080/api/mirror/config

# Test repository trust analysis
curl -X POST http://localhost:8080/api/mirror/analyze \
  -H "Content-Type: application/json" \
  -d '{"repo_url": "https://github.com/user/repo.git"}'

# Error diagnosis and system health
curl -X POST http://localhost:8080/api/error/diagnose \
  -H "Content-Type: application/json" \
  -d '{"error_message": "Connection refused"}'
curl http://localhost:8080/api/system/health

# Sandbox environments
curl http://localhost:8080/api/sandbox

# Remove all sandboxes
curl -X POST http://localhost:8080/api/sandbox/stop-all
```

## Git Workflow Examples

**Creating and Using a Local Repository:**
```bash
# 1. Create LOCAL repository via web interface at /git-admin/
# 2. Clone the empty repository (FULL READ/WRITE ACCESS)
git clone http://localhost:8080/git/my-project.git
cd my-project

# 3. Add initial content
echo "# My Project" > README.md
echo "print('Hello World')" > main.py
git add .
git commit -m "Initial commit"
git push origin master  # ✅ PUSH ALLOWED (local repository)

# 4. Create and work on feature branch
git checkout -b feature/new-feature
echo "def new_feature(): pass" >> main.py
git add main.py
git commit -m "Add new feature"
git push origin feature/new-feature  # ✅ PUSH ALLOWED

# 5. Switch back to main branch
git checkout master
echo "## Installation" >> README.md
git add README.md
git commit -m "Update README"
git push origin master  # ✅ PUSH ALLOWED
```

**Using External Mirror (Read-Only):**
```bash
# 1. Mirror external repository via /mirror-manager/
# 2. Clone the mirrored repository (READ-ONLY ACCESS)
git clone http://localhost:8080/git/external-project.git
cd external-project

# 3. You can read and build, but NOT push
echo "local changes" >> README.md
git add README.md
git commit -m "Local changes"
git push origin master  # ❌ PUSH BLOCKED - "Push to external mirror not allowed"

# 4. To modify external code, create local copy:
git clone http://localhost:8080/git/external-project.git my-fork
cd my-fork
# Create new local repository via /git-admin/ and push there
```

**Secure Mirroring Workflow:**
```bash
# 1. Request mirror via web interface at /mirror-manager/
# Enter URL: https://github.com/user/repository.git

# 2. System performs comprehensive analysis:
# - Trust Score: 85/100 (Geographic: US, Contributors: 15, Clean)
# - Legal Score: 90/100 (License: MIT, Redistribution: Allowed)
# - Security: No malware detected, 2 binary files flagged

# 3. Repository approved and mirrored as READ-ONLY
# 4. Clone and use safely:
git clone http://localhost:8080/git/user_repository.git
cd user_repository

# 5. All modification attempts blocked:
git push origin master     # ❌ "Push to external mirror not allowed"
# Branch creation via web UI  # ❌ "Cannot create branches in external mirror"
# Repository deletion        # ❌ "Cannot delete external mirror"
```

**Web-Based Repository Management:**
```bash
# Local Repository Operations (Full Access):
# - Create repositories: /git-admin/ → "Create Repository" (read/write)
# - Create branches: /git-admin/ → "Branch" button (local repos only)
# - Delete repositories: /git-admin/ → "Delete" button (local repos only)
# - Browse repositories: /git-repos/
# - View commits: /git/{repo}/commits
# - Browse files: /git/{repo}/tree

# External Mirror Operations (Read-Only):
# - Mirror repositories: /mirror-manager/ → "Analyze & Mirror"
# - View trust analysis: /mirror-manager/ → Analysis details
# - Manage quarantine: /mirror-manager/ → Quarantined repositories
# - Configure thresholds: /mirror-manager/ → Configuration panel
# - Browse mirrors: /git-repos/ (marked as read-only)
```

**Trust Analysis Configuration:**
```bash
# Default Configuration:
# - Trust Threshold: 70/100 (minimum to auto-approve)
# - Legal Threshold: 80/100 (minimum for legal compliance)
# - Blocked Countries: CN, RU, KP, IR
# - Approved Licenses: MIT, Apache-2.0, BSD-3-Clause, GPL-3.0, etc.

# Customizable via /mirror-manager/ interface:
# - Adjust trust/legal thresholds
# - Modify blocked country list
# - Update approved license list
# - Force mirror with admin override
```

**Project Template Workflow:**
```bash
# 1. Create project from template via web interface at /project-templates/
# 2. Clone the generated project
git clone http://localhost:8080/git/my-flask-app.git
cd my-flask-app

# 3. Set up development environment (example for Flask)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# 4. Start developing
python app.py

# 5. Make changes and commit
git add .
git commit -m "Add new features"
```

**Build Management Workflow:**
```bash
# 1. Create or clone a project
git clone http://localhost:8080/git/my-project.git

# 2. Use Build Manager web interface at /build-manager/
# - Project type automatically detected
# - Dependencies listed and status shown
# - One-click operations available

# 3. Install dependencies via web interface
# For Python: python -m venv venv && pip install -r requirements.txt
# For Node.js: npm install
# For C++: mkdir build && cmake .. && make

# 4. Build project via web interface
# Executes appropriate build commands based on project type

# 5. Run tests via web interface
# Executes test commands with real-time output

# All operations provide real-time terminal output and status updates
```

**Enhanced Security Workflow:**
```bash
# 1. Comprehensive vulnerability scanning at /security/
git clone http://localhost:8080/git/my-project.git
cd my-project

# 2. Multi-layer security analysis via web interface
# - Code vulnerabilities: dangerous functions, security anti-patterns
# - Dependency vulnerabilities: CVE detection in requirements.txt, package.json
# - Secret detection: exposed API keys, passwords, credentials
# - Container security: Dockerfile best practices analysis

# 3. Real-time security integration
# - Edit requirements.txt → immediate vulnerability feedback
# - Browse Git repository → automatic dependency analysis
# - View files in editor → real-time security indicators

# 4. Automated remediation
# - Priority-based fix recommendations (Critical → High → Medium → Low)
# - Version-specific upgrade guidance
# - Integration with existing development workflow
```

**Service Orchestration & Dependency Management:**
```bash
# 1. Multi-service application management at /services/
# Load docker-compose.yml → automatic service discovery
# Start services with dependency resolution
# Monitor health and scale services dynamically

# 2. Cross-platform dependency analysis at /dependencies/
# Analyze package.json, requirements.txt, pom.xml
# Detect conflicts and generate installation order
# Export lockfiles and dependency graphs
```

**Code Coverage & Quality Analysis:**
```bash
# 1. Test coverage analysis at /coverage/
# Generate reports for Python, JavaScript, Java projects
# Visual dashboard with A-F grading system
# File-level analysis with missing line identification

# 2. Integration with development workflow
# Repository coverage analysis from Git
# Export coverage metrics and reports
# Compare coverage across versions
```

**Merge Request Workflow:**
```bash
# 1. Create feature branch and make changes
git clone http://localhost:8080/git/my-project.git
cd my-project
git checkout -b feature/new-feature
echo "new feature code" > feature.py
git add feature.py
git commit -m "Add new feature"

# 2. Create merge request via web interface at /merge-requests/
# - Select repository and branches
# - Add title and description
# - Submit for review

# 3. Code review process
# - Reviewers view diff at /merge-requests/{repo}/{id}
# - Add general comments for discussion
# - Click on specific lines to add inline comments
# - Review commits and file changes

# 4. Collaboration and iteration
# - Address reviewer feedback
# - Make additional commits to feature branch
# - Continue discussion in MR comments

# 5. Merge decision
# - Check for merge conflicts (automatic detection)
# - Approve and merge when ready
# - Close MR and clean up branches
```

**Sandbox Workflow:**
```bash
# 1. Create sandbox environment at /sandbox/
# Choose mode: Simplified (recommended) or Docker (full isolation)
# Select environment: Python, Node.js, Java, C++, or Terraform
# Optional: Import existing project files

# 2. Access integrated code editor
# Navigate to sandbox → Click "Editor" button
# Built-in editor with syntax highlighting
# File management within sandbox

# 3. Write and execute code
# Create/edit files in sandbox environment
# Click "Run" for automatic execution with analysis
# View real-time linting and security results

# 4. Simplified mode benefits
# Instant creation (no Docker startup delay)
# Faster file operations and code execution
# Same development tools as Docker mode
# Recommended for most development tasks

# 5. Docker mode security (when needed)
# 512MB memory limit per sandbox
# CPU quota restrictions
# Network isolation (no external access)
# Complete container isolation

# 6. Development tools (both modes)
# Multi-language linting (flake8, pylint, ESLint, cppcheck, tflint)
# Security scanning (bandit, npm audit, tfsec)
# Terminal access for advanced operations (Docker mode)
# Project import from existing repositories

# 7. Sandbox management
# Individual removal: Click "Stop" button on sandbox card
# Bulk removal: Click "Remove All" button to clean up all sandboxes
# Status monitoring: View running/stopped/ready status
```

**Diff Visualization Workflow:**
```bash
# 1. Access diff viewer at /diff-viewer/
# Enter file path and select comparison mode
# Generate visual diff with syntax highlighting

# 2. Interactive code review
# Click any diff line to add inline comments
# View additions (green), deletions (red), context (white)
# See real-time statistics (additions, deletions, changes)

# 3. Comment system
# Add line-specific comments with author attribution
# Multiple comments per line with timestamps
# Toggle comment visibility as needed

# 4. Integration with editors
# "Advanced Diff" button in code editors
# "Diff" button in sandbox environments
# Direct links from file editors

# 5. API usage for automation
# POST /api/editor/diff - Generate structured diff
# POST /api/diff/comment - Add programmatic comments
# GET /api/diff/comments/{file} - Retrieve all comments
```

**Terraform Infrastructure Workflow:**
```bash
# 1. Create Terraform project from template at /project-templates/
# Choose from: Basic, AWS VPC, AWS Lambda, S3+CloudFront
git clone http://localhost:8080/git/my-terraform-project.git
cd my-terraform-project

# 2. Configure variables
cp terraform.tfvars.example terraform.tfvars
# Edit terraform.tfvars with your specific values

# 3. Use Terraform sandbox for safe execution at /sandbox/
# Create Terraform sandbox environment
# Upload project files to sandbox
# Execute Terraform commands in isolated environment

# 4. Terraform operations in sandbox:
# terraform init    - Initialize providers and modules
# terraform validate - Validate configuration syntax
# terraform plan    - Preview infrastructure changes
# terraform apply   - Deploy infrastructure (with approval)

# 5. Code editor integration:
# - Terraform syntax highlighting (.tf, .tfvars, .hcl files)
# - Context-sensitive help for resources and functions
# - Real-time linting with terraform fmt and tflint
# - Security scanning with tfsec
# - Autocomplete for Terraform blocks and AWS resources

# 6. Security and best practices:
# - Automatic tfsec scanning for security issues
# - Terraform fmt for consistent formatting
# - Variable validation and type checking
# - Resource tagging compliance
# - Cost optimization recommendations
```

**Terraform Template Examples:**

**Basic Infrastructure:**
```hcl
# Creates S3 bucket with random suffix
resource "aws_s3_bucket" "example" {
  bucket = "${var.project_name}-${random_id.bucket_suffix.hex}"
}

resource "random_id" "bucket_suffix" {
  byte_length = 4
}
```

**VPC with Subnets:**
```hcl
# Complete VPC setup with public/private subnets
resource "aws_vpc" "main" {
  cidr_block           = var.vpc_cidr
  enable_dns_hostnames = true
  enable_dns_support   = true
}

resource "aws_subnet" "public" {
  count = length(var.public_subnet_cidrs)
  vpc_id                  = aws_vpc.main.id
  cidr_block              = var.public_subnet_cidrs[count.index]
  map_public_ip_on_launch = true
}
```

**Lambda Function:**
```hcl
# Serverless API with Lambda and API Gateway
resource "aws_lambda_function" "main" {
  filename         = data.archive_file.lambda_zip.output_path
  function_name    = "${var.project_name}-function"
  role            = aws_iam_role.lambda_role.arn
  handler         = "index.handler"
  runtime         = "python3.9"
}

resource "aws_api_gateway_rest_api" "main" {
  name        = "${var.project_name}-api"
  description = "API Gateway for ${var.project_name}"
}
```

**Static Website:**
```hcl
# S3 + CloudFront for static website hosting
resource "aws_s3_bucket" "website" {
  bucket = var.domain_name
}

resource "aws_cloudfront_distribution" "website" {
  origin {
    domain_name = aws_s3_bucket.website.bucket_regional_domain_name
    origin_id   = "S3-${aws_s3_bucket.website.bucket}"
  }
  
  enabled             = true
  default_root_object = "index.html"
  aliases             = [var.domain_name]
}
```

### 🏗️ OS Builder - Complete Operating System Build Environment
Access: **http://localhost:8080/os-builder/**

**Build SecureAI-OS from Scratch:**
Complete autonomous intelligence operating system with AI integration, security hardening, and minimal footprint.

**Git-First Build System:**
- **Build Sources Repository**: Dedicated `build-sources.git` repository for all source files
- **Git-First Downloads**: Checks local Git repository before downloading from external sources
- **Automatic Fallback**: Downloads from external mirrors only when files not available locally
- **Resilient Downloads**: Continues with available files even if some downloads fail
- **Version Control**: All source files tracked in Git with checksums and metadata
- **Offline Capability**: Once downloaded, builds work without internet connection

**Enhanced Build Features:**
- **Resume Downloads**: Automatically resume from interruption point (8.5%, 25%, 50%, etc.)
- **Multiple Sources**: 3+ mirror sources per package (kernel.org, gnu.org, mirrors.kernel.org)
- **Checksum Verification**: SHA256 integrity checking for all downloads with manifest tracking
- **Smart Retry**: AI-powered failure analysis with specific recommendations
- **Alternative Sources**: Automatic failover to backup download mirrors
- **Build Source Manager**: Centralized management with comprehensive error tracking

**Start Build:**
1. Select build template (minimal-ai, desktop-ai, server-ai, embedded-ai)
2. Configure kernel version, GCC version, target architecture
3. Choose output storage location (internal or external USB)
4. Click "Start Build" or "Start AI Build" for Git-first downloads
5. System checks `build-sources.git` repository first, then downloads missing files
6. Monitor progress with real-time failure detection and resilient download system
7. Build creates Git repository with complete source and binary tracking

**Git-First Download Process:**
1. **Check Local Git**: System first checks `build-sources.git` for required files
2. **Download Missing**: Only downloads files not available in local repository
3. **Multiple Sources**: Uses 3+ mirror sources with automatic failover
4. **Continue on Failure**: Continues with available files even if some downloads fail
5. **Git Commit**: All successful downloads automatically committed to Git
6. **Manifest Update**: Checksums and metadata tracked in `manifest.json`

**Build Process (6 Steps with Recovery):**
1. **Download Sources** - Linux kernel, GCC, binutils, glibc, BusyBox (5-15 min) **[Resume Capable]**
2. **Build Toolchain** - Cross-compilation tools (10-30 min)
3. **Build Kernel** - AI-integrated Linux kernel (15-45 min)
4. **Build Root Filesystem** - BusyBox utilities with AI services (5-15 min)
5. **Create Initramfs** - Initial RAM filesystem (1-3 min)
6. **Create Bootable ISO** - Final SecureAI-OS image (2-5 min)

**Failure Recovery:**
- **Auto-Analysis**: Automatic failure diagnosis with specific recommendations
- **One-Click Retry**: "Retry Build" button with enhanced error handling
- **Resume Capability**: Continue from exact failure point (no re-downloading)
- **Alternative Sources**: Automatic mirror switching for failed downloads
- **Faster Retries**: 30-50% faster due to resumed downloads and cached data

**Output:**
- **Bootable ISO**: `secureai-os.iso` (50MB - 800MB depending on template)
- **Git Repository**: Complete build history with AIOS-YYYYMMDD-HHMMSS-r1 naming and failure analysis
- **Documentation**: Build reports, security scans, failure diagnostics, and retry recommendations
- **Clone URL**: `http://localhost:8080/git/AIOS-YYYYMMDD-HHMMSS-r1.git`

**Common Issues & Auto-Solutions:**
- **Network Timeouts**: Automatic retry with alternative mirror sources
- **Partial Downloads**: Resume from exact interruption point (8.5%, 25%, etc.)
- **Missing Files**: Git-first system continues with available files, reports missing ones
- **Disk Space**: Automatic detection and storage recommendations
- **Build Failures**: AI-powered analysis with specific fix recommendations
- **Source Integrity**: SHA256 checksum verification with automatic re-download on mismatch

**Build Sources Management:**
Access: **http://localhost:8080/api/os-builder/build-sources**

**Available Build Sources:**
- View all files in `build-sources.git` repository
- Check file checksums and download timestamps
- Browse Git repository at: `http://localhost:8080/git-repos/build-sources/`
- Clone repository: `git clone http://localhost:8080/git/build-sources.git`

**Download Build Sources:**
```bash
# Download default SecureAI-OS source files
curl -X POST http://localhost:8080/api/os-builder/download-sources \
  -H "Content-Type: application/json" -d '{}'

# Download custom file specifications
curl -X POST http://localhost:8080/api/os-builder/download-sources \
  -H "Content-Type: application/json" -d '{
    "file_specs": [
      {
        "filename": "custom-package.tar.xz",
        "urls": [
          "https://primary-source.com/package.tar.xz",
          "https://mirror.com/package.tar.xz"
        ],
        "checksum": "sha256_hash_here"
      }
    ]
  }'
```

## Recent Updates (December 2024)

### 🏗️ OS Builder - Git-First Build System & AI-Powered Recovery
- **Git-First Build Sources** - All build files stored in dedicated `build-sources.git` repository with automatic version control
- **Resilient Download System** - Continues downloading even if some files fail, with comprehensive error tracking and reporting
- **Build Source Manager** - Centralized management of all source files with SHA256 checksum verification and manifest tracking
- **Offline Build Capability** - Once downloaded, builds work without internet using local Git repository
- **Full OS Build System** - Build SecureAI-OS from scratch with Linux kernel, GCC toolchain, and AI integration
- **AI-Powered Failure Recovery** - Automatic failure diagnosis with 90%+ accuracy and specific fix recommendations
- **Resume Downloads** - Intelligent resume from exact interruption point (8.5%, 25%, 50%, etc.) with multiple mirror sources
- **Git Integration** - Automatic Git repository creation for each build with complete source and binary tracking
- **Knowledge Database** - Learning system that stores build patterns, failure analysis, and successful fixes
- **Build Templates** - Pre-configured templates (minimal-ai, desktop-ai, server-ai, embedded-ai) with optimized settings
- **Smart Retry System** - One-click retry with enhanced error handling and 30-50% faster rebuilds
- **Storage Flexibility** - Build to internal storage or external USB drives with automatic detection and space monitoring
- **Real-time Monitoring** - Live build progress with 6-step process tracking, failure detection, and performance metrics
- **Comprehensive Documentation** - Auto-generated build reports, security scans, failure diagnostics, and retry recommendations

### AI Model Security & Governance System
- **Model Provenance Tracking** - Complete audit trail with source URLs, download history, and trust scoring
- **Integrity Verification** - SHA256 checksums, file validation, and signature verification for model authenticity
- **AI Safety Guardrails** - Real-time detection of harmful code patterns with severity classification (low/medium/high/critical)
- **Performance Monitoring** - Baseline tracking, drift detection, and automated performance degradation alerts
- **Trust Assessment** - Automated scoring (0-100) based on source reputation, file characteristics, and verification status
- **Violation Detection** - Pattern-based safety analysis for harmful code, malicious patterns, and privacy violations
- **Secure Registry** - Centralized SQLite database for all AI model security metadata and audit trails
- **Admin-Only Access** - All AI model security features require admin authentication for enhanced security

### Error Diagnosis & Resolution System
- **Intelligent Error Analysis** - Pattern-based error recognition engine with 90%+ confidence for common issues
- **Automated Solutions** - Actionable fix recommendations for connection errors, permission problems, and storage issues
- **System Health Monitoring** - Real-time monitoring of disk usage (81% warning level), memory consumption (24% normal), and service status
- **Pattern Matching Engine** - Recognition of 10+ error types including network failures, authentication issues, and resource constraints
- **Severity Classification** - Automatic categorization by impact level (Info, Low, Medium, High, Critical)
- **Admin Security** - Diagnostic tools require authentication to protect sensitive system information
- **Prevention Guidance** - Proactive recommendations to prevent recurring issues

### Sandbox Environment Enhancements
- **Dual-Mode Operation** - Added Simplified mode for instant sandbox creation alongside existing Docker mode
- **Improved Performance** - Simplified mode eliminates Docker container startup delays (10-30 seconds)
- **Enhanced User Experience** - Mode selection with clear recommendations and timing expectations
- **Bulk Management** - "Remove All Sandboxes" button for efficient cleanup of multiple environments
- **Robust Error Handling** - Fixed KeyError issues with sandbox container management
- **Status Monitoring** - Improved sandbox discovery and status reporting for existing containers

## Previous Updates (September 2025)

### Production Deployment & Stability
- **Flask Application Stability** - Resolved missing Python dependencies (PyYAML, networkx)
- **Docker-in-Docker Support** - Full container isolation with privileged access and Docker socket mounting
- **Terraform Sandbox Fix** - Resolved entrypoint conflicts for proper shell access in Terraform containers
- **Container Health Monitoring** - Enhanced error handling and status checking for sandbox environments
- **Production Ready** - System fully tested and operational at http://localhost:8080

### USB Drive Support
- **Full read/write access** to USB drives and external storage
- **Auto-detection** of newly inserted drives
- **Device type identification** (USB, SD Card, NVMe SSD)
- **Real-time space monitoring** with free space display

### Data Management Enhancements
- **Disk selection dropdowns** with available space information
- **Import/export functionality** between USB drives and workspace
- **Filesystem browser** for navigating external storage
- **Archive/workspace separation** for data integrity

### Git System Improvements
- **Complete Git HTTP backend** with clone/fetch/pull support
- **Web-based repository browser** with file viewing
- **Commit history and branch navigation**
- **Working repository creation and management**
- **Web-based Git administration** - Create/delete repositories via UI
- **Branch management interface** - Create branches from web interface
- **Repository statistics** - Visual overview of commits, branches, size

### Editor and Interface Updates
- **Firefox ESR compatibility** for enterprise environments
- **Enhanced diff functionality** with Git integration
- **Search capabilities** across files and directories
- **Improved navigation** and user interface
- **Dropdown navigation system** - Organized menu structure
- **Responsive design** - Clean, modern interface
- **Interactive forms** - JavaScript-powered Git operations

### System Architecture
- **Container privilege escalation** for hardware access
- **Volume mount optimization** for external storage
- **Service management** with supervisord
- **Health monitoring** and status reporting

### Project Templates & Scaffolding System
- **Built-in templates** - Python, Node.js, C++, Flask, Express project templates
- **One-click project creation** - Instant setup with proper structure and dependencies
- **Template engine** - Placeholder replacement and file generation system
- **Git integration** - Projects created as ready-to-clone repositories
- **Extensible framework** - Easy to add custom templates

### Build Management & Dependency System
- **Project type detection** - Automatic detection of Python, Node.js, C++, Java projects
- **Dependency management** - One-click installation of project dependencies
- **Build automation** - Automated build processes with real-time terminal output
- **Test integration** - Execute test suites with visual feedback and results
- **Build status tracking** - Monitor dependency installation and build artifacts
- **Multi-language support** - Python (pip), Node.js (npm), C++ (cmake), Java (maven/gradle)

### Merge Request/Pull Request System
- **Web-based code review** - GitHub/GitLab-style merge request interface
- **Diff visualization** - Side-by-side diff with syntax highlighting and line numbers
- **Inline commenting** - Click any line to add specific code review comments
- **Conversation threading** - General comments and discussion system
- **Merge conflict detection** - Automatic checking for merge conflicts
- **Multi-repository support** - Works across all Git repositories

### Sandboxed Execution Environments
- **Isolated container environments** - Secure Docker-based execution with resource limits and security hardening
- **Multi-language sandbox support** - Python, Node.js, Java, C++ development environments with pre-installed tools
- **Integrated code editor** - Built-in web-based editor with syntax highlighting and file management
- **Automatic code analysis** - Real-time linting and vulnerability scanning during code execution
- **Resource isolation** - 512MB memory limits, CPU quotas, and network isolation per sandbox
- **Security hardening** - Read-only containers with restricted privileges and no external network access
- **Terminal access** - Web-based terminal interface for advanced operations within sandboxes
- **Project import** - Copy existing projects into sandbox environments for isolated development

### Diff Visualization & Code Review System
- **Interactive diff viewer** - GitHub/GitLab-style diff visualization with syntax highlighting
- **Inline comment system** - Click-to-comment on any diff line with author attribution and timestamps
- **Multi-format comparison** - Git HEAD, saved files, and custom content comparison modes
- **Real-time statistics** - Live addition/deletion counts and change metrics display
- **Editor integration** - Direct access from code editors, sandbox environments, and file viewers
- **API-driven architecture** - RESTful endpoints for programmatic diff generation and comment management

### Advanced Security & Quality Features
- **Enhanced vulnerability assessment** - Multi-source dependency scanning with CVE detection
- **Code coverage reporting** - Multi-language test coverage analysis with visual dashboards
- **Service orchestration** - Docker Compose support with dependency resolution
- **Dependency management** - Cross-platform dependency analysis and conflict detection
- **Real-time security integration** - File-level vulnerability detection in editor and Git viewer
- **Comprehensive remediation** - Automated fix recommendations with version-specific guidance

### Web Interface Enhancements
- **Dropdown navigation system** - Organized menu structure with grouped functionality
- **Git administration panel** - Complete web-based repository management
- **Interactive repository creation** - Forms for creating repositories and branches
- **Visual repository overview** - Cards showing repository statistics and actions
- **RESTful API endpoints** - Programmatic access to all Git operations
- **Project templates interface** - Visual template selection and project creation
- **Merge request interface** - Complete code review and collaboration system
- **Security dashboards** - Comprehensive vulnerability assessment and remediation interfaces
- **Coverage dashboards** - Interactive test coverage reporting with detailed metrics

### 🎯 Editor Usage Examples

**Context Help Workflow:**
```javascript
// 1. Position cursor on 'fetch' and click "Get Help"
fetch('/api/data')
  .then(response => response.json())
  .then(data => console.log(data));

// 2. Help panel shows:
// - fetch() documentation
// - Example code snippets
// - Copy/insert buttons on hover

// 3. Click ➕ on a snippet to insert at cursor
// 4. Use Ctrl+Z to undo if needed
```

**Diff Visualization Workflow:**
```bash
# 1. Make changes to a file in the editor
# 2. Click "Show Diff" for quick inline view
# 3. Click "Advanced Diff" for full-screen analysis
# 4. See color-coded changes:
#    - Green: additions
#    - Red: deletions  
#    - White: context
# 5. View change statistics and line numbers
```

**Undo System Workflow:**
```bash
# 1. Edit file normally - undo states saved automatically
# 2. Insert code snippet - creates immediate undo point
# 3. Use find/replace - creates undo point before operation
# 4. Click ↶ Undo button or press Ctrl+Z to revert
# 5. Button shows count of available undo operations
```

### 💡 Latest Editor Enhancements (December 2024)

**Context-Sensitive Help System:**
- **Intelligent code analysis** - Detects programming language and context automatically
- **Real-time help** - Position cursor anywhere for relevant documentation
- **Interactive snippets** - Copy or insert code examples with one click
- **Multi-language support** - JavaScript, Python, HTML, CSS with extensible framework
- **Autocomplete integration** - Ctrl+Space for smart suggestions
- **Quick reference** - Language-specific reference guides

**Copy/Insert Functionality:**
- **Hover-activated buttons** - Copy (📋) and insert (➕) buttons on code snippets
- **Clipboard integration** - Modern clipboard API with fallback support
- **Direct insertion** - Insert snippets at current cursor position
- **Toast notifications** - Visual feedback for copy/insert operations
- **Context preservation** - Maintains editor state and cursor position

**Advanced Undo System:**
- **Smart state tracking** - Captures meaningful editing operations
- **Debounced saves** - Groups typing into logical undo units
- **Operation-specific tracking** - Tracks snippet insertions, replacements, and manual edits
- **Cursor position restoration** - Restores both content and cursor location
- **Visual feedback** - Undo button shows available operation count
- **Keyboard shortcuts** - Standard Ctrl+Z (Cmd+Z) support
- **Memory efficient** - Limits to 10 undo states to prevent memory issues

**Enhanced Diff System:**
- **Dual diff modes** - Quick inline diff and advanced full-screen diff
- **Real-time comparison** - Compare current editor content vs saved file
- **SessionStorage integration** - Passes editor content to advanced diff viewer
- **Visual diff rendering** - Color-coded additions, deletions, and context lines
- **Change statistics** - Live counts of additions, deletions, and modifications
- **Git integration** - Compare against Git HEAD when available
- **Structured diff output** - Parsed diff data with line-by-line analysis

## License

This project is part of the SecureAI-OS development environment.