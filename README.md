# ext-background-jobs

A TypeScript library for Chrome extension development. Built by theluckystrike.

## Overview

This library provides foundational types and utilities for building Chrome extensions with TypeScript support. It serves as a starting point for extension development and includes essential exports for type-safe extension development.

## Installation

```bash
npm install @theluckystrike/ext-background-jobs
```

## Usage

```typescript
import { library, VERSION } from '@theluckystrike/ext-background-jobs';

console.log('Library:', library);
console.log('Version:', VERSION);
```

## Building from Source

```bash
git clone https://github.com/theluckystrike/ext-background-jobs.git
cd ext-background-jobs
npm install
npm run build
```

## Development

Install dependencies and build:

```bash
npm install
npm run build
```

Run tests:

```bash
npm test
```

## API Reference

The library exports:

- `library` - Library identifier string
- `VERSION` - Current version number as a string

## Related

This package is part of a collection of Chrome extension tools from theluckystrike.

## About

This project is maintained by theluckystrike. It is part of the zovo.one developer tools ecosystem.

For more information, visit https://zovo.one.

## License

MIT License. See LICENSE file for details.
