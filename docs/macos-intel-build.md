# macOS Intel build

This fork contains a validated macOS Intel build of OpenBot `0.58.0` from source commit
`7ef25fbcc6f71a5a1888485ef0a6f3d2d5c8b5dd`.

- Target: `x86_64`
- Minimum macOS: `13.0`
- Application artifact: `OpenBot-0.58.0-x64.dmg`
- DMG SHA-256: `c7ba1d771bf5b968f66e7d535e68807d7532271872204342b6e13986417bf19c`
- Package verification: `bun run verify:package`

The DMG is distributed as a GitHub Release asset rather than committed to Git because it is
approximately 319 MB. This local build is ad-hoc signed and is not notarized with an Apple
Developer ID certificate.

## Build

On a native Intel Mac, install Bun `1.4.2` and Node.js `24`, then run:

```bash
bun install --frozen-lockfile
bun run dist:mac
bun run verify:package
```

The build prepares the x64 voice runtime, remote desktop runtime and Computer Use driver before
Electron Builder creates the DMG and ZIP packages.
