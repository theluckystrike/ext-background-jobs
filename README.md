# ext-background-jobs

[![npm version](https://img.shields.io/npm/v/@theluckystrike/ext-background-jobs)](https://npmjs.com/package/@theluckystrike/ext-background-jobs)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)](https://www.typescriptlang.org/)
[![CI Status](https://github.com/theluckystrike/ext-background-jobs/actions/workflows/ci.yml/badge.svg)](https://github.com/theluckystrike/ext-background-jobs/actions)
[![Discord](https://img.shields.io/badge/Discord-Zovo-blueviolet.svg?logo=discord)](https://discord.gg/zovo)
[![Website](https://img.shields.io/badge/Website-zovo.one-blue)](https://zovo.one)
[![GitHub Stars](https://img.shields.io/github/stars/theluckystrike/ext-background-jobs?style=social)](https://github.com/theluckystrike/ext-background-jobs)

> Background job scheduler for Chrome extensions.

Part of the [Zovo](https://zovo.one) family of privacy-first Chrome extensions and developer tools.

## Overview

`ext-background-jobs` is a powerful background job scheduling library for Chrome extensions. It enables reliable task scheduling, retries, and background processing using Chrome's alarm API and service workers.

## Features

- ✅ **Job Scheduling** - Schedule jobs to run at specific times
- ✅ **Retry Logic** - Automatic retry with exponential backoff
- ✅ **Persistence** - Jobs persist across browser restarts
- ✅ **TypeScript Support** - Fully typed for better developer experience
- ✅ **MV3 Compatible** - Works with Manifest V3 service workers
- ✅ **Privacy-First** - No data collection, all local

## Installation

### From npm

```bash
npm install @theluckystrike/ext-background-jobs
```

### From Source

```bash
# Clone the repository
git clone https://github.com/theluckystrike/ext-background-jobs.git
cd ext-background-jobs

# Install dependencies
npm install

# Build the project
npm run build
```

## Usage

### Scheduling a Job

```typescript
import { BackgroundJobs, Job } from '@theluckystrike/ext-background-jobs';

const jobs = new BackgroundJobs();

// Schedule a one-time job
await jobs.schedule({
  id: 'daily-sync',
  task: () => syncData(),
  delayInMinutes: 60
});

// Schedule a recurring job
await jobs.scheduleRecurring({
  id: 'hourly-backup',
  task: () => backupData(),
  periodInMinutes: 60
});
```

### Job Options

```typescript
const job: Job = {
  id: 'my-job',
  task: async () => {
    // Your task logic
    await doWork();
  },
  delayInMinutes: 5,
  retry: {
    maxAttempts: 3,
    backoffMs: 1000
  },
  onComplete: (result) => {
    console.log('Job completed:', result);
  },
  onError: (error) => {
    console.error('Job failed:', error);
  }
};
```

## API Reference

### BackgroundJobs

| Method | Description |
|--------|-------------|
| `schedule(job)` | Schedule a one-time job |
| `scheduleRecurring(job)` | Schedule a recurring job |
| `cancel(jobId)` | Cancel a scheduled job |
| `getJobs()` | Get all scheduled jobs |
| `pause()` | Pause all jobs |
| `resume()` | Resume paused jobs |

### Job Options

| Option | Type | Description |
|--------|------|-------------|
| `id` | string | Unique job identifier |
| `task` | function | Job function to execute |
| `delayInMinutes` | number | Delay before execution |
| `periodInMinutes` | number | Period for recurring jobs |
| `retry` | object | Retry configuration |

## Related Packages

This package is part of the Zovo extension background ecosystem:

- [ext-background-sync](https://github.com/theluckystrike/ext-background-sync) - Background sync API
- [ext-background-sync-queue](https://github.com/theluckystrike/ext-background-sync-queue) - Sync queue
- [ext-alarms-api](https://github.com/theluckystrike/ext-alarms-api) - Alarms API wrapper
- [ext-scheduler](https://github.com/theluckystrike/ext-scheduler) - Advanced scheduling

## Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/jobs-improvement`
3. **Make** your changes
4. **Test** your changes: `npm test`
5. **Commit** your changes: `git commit -m 'Add new feature'`
6. **Push** to the branch: `git push origin feature/jobs-improvement`
7. **Submit** a Pull Request

### Development Setup

```bash
# Clone the repository
git clone https://github.com/theluckystrike/ext-background-jobs.git
cd ext-background-jobs

# Install dependencies
npm install

# Run tests
npm test

# Build
npm run build
```

## Built by Zovo

Part of the [Zovo](https://zovo.one) developer tools family — privacy-first Chrome extensions built by developers, for developers.

## See Also

### Related Zovo Repositories

- [zovo-extension-template](https://github.com/theluckystrike/zovo-extension-template) - Boilerplate for building privacy-first Chrome extensions
- [zovo-types-webext](https://github.com/theluckystrike/zovo-types-webext) - Comprehensive TypeScript type definitions for browser extensions
- [zovo-permissions-scanner](https://github.com/theluckystrike/zovo-permissions-scanner) - Privacy scanner for Chrome extensions
- [zovo-indexer](https://github.com/theluckystrike/zovo-indexer) - Indexing service for Zovo extensions

### Zovo Chrome Extensions

- [Zovo Tab Manager](https://chrome.google.com/webstore/detail/zovo-tab-manager) - Manage tabs efficiently
- [Zovo Focus](https://chrome.google.com/webstore/detail/zovo-focus) - Block distractions
- [Zovo Permissions Scanner](https://chrome.google.com/webstore/detail/zovo-permissions-scanner) - Check extension privacy grades

Visit [zovo.one](https://zovo.one) for more information.

## License

MIT - [Zovo](https://zovo.one)

---

*Built by developers, for developers. No compromises on privacy.*
