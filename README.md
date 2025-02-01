# my learning diary

## Overview
This repository tracks my learning journey, focusing on Java, Python, Cloud Computing (AWS), AI tools (ChatGPT API), and other skills. 
Every day is a learning day and having a clean way of reviewing that learnt in days gone by is useful both for myself and perhaps others.




## PNPM
PNPM is a package manager for JavaScript/TypeScript projects that offers several advantages over NPM and Yarn:
**1. Disk Space Efficiency**
Uses a content-addressable store to save disk space
Instead of copying node_modules for each project, it creates hard links
Example: if you have 100 projects using React, PNPM stores React only once on your disk

**2. Strict Dependencies**
```
project/
├── node_modules/
│   ├── .pnpm/
│   │   ├── react@18.2.0/
│   │   └── lodash@4.17.21/
│   ├── react -> .pnpm/react@18.2.0/
│   └── lodash -> .pnpm/lodash@4.17.21/
```

**3. Installation Command Examples**
```
# Install a package
pnpm add react

# Install dev dependency
pnpm add -D typescript

# Install workspace package
pnpm add @your-project/ui --workspace
```

## Monorepo Structure
A typical monorepo structure looks like this:
```
us-procurement-search/
├── apps/
│   ├── web/             # Main web application
│   └── admin/           # Admin dashboard
├── packages/
│   ├── ui/             # Shared UI components
│   ├── database/       # Database schemas and utilities
│   ├── api/            # API clients and interfaces
│   └── config/         # Shared configuration
├── package.json
├── pnpm-workspace.yaml
└── turbo.json
```

## Turborepo Configuration
Turborepo is a high-performance build system for JavaScript/TypeScript monorepos.
Turborepo handles build orchestration and caching. Here's a sample configuration:
```
{
  "$schema": "https://turbo.build/schema.json",
  "globalDependencies": [".env"],
  "pipeline": {
    "build": {
      "dependsOn": ["^build"],
      "outputs": ["dist/**", ".next/**"]
    },
    "dev": {
      "cache": false,
      "persistent": true
    },
    "test": {
      "dependsOn": ["build"],
      "outputs": []
    }
  }
}
```
Intelligent Caching
```
# First run - takes full build time
turbo run build  # ~2 minutes

# Second run - uses cache
turbo run build  # ~0.1 seconds
```
