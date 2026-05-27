## Summary

- Fix startup peer-dependency check for ESM-only `@earendil-works/pi-ai` by probing with dynamic `import()`.
- Add optional Discord auto-threading via `AUTO_THREAD` / `AUTO_THREAD_ARCHIVE_MIN`; parent channel mentions can spawn per-thread Pi sessions, while thread replies continue without extra mentions.
- Add `prepare` lifecycle script so git+URL installs build `dist/` before the `piscord` bin is used.

## Testing

- `npm run build`
- `npm test` *(initially failed because `better-sqlite3` native bindings were built for a different Node version; after `npm rebuild better-sqlite3`, all 13 test files / 39 tests passed)*

## Notes

This PR contains the fork commits currently ahead of upstream `main`:

- `3e3488a` fix(cli): resolve ESM-only peer dep with dynamic import
- `9820537` feat(discord): optional auto-thread per channel
- `c0ba78b` chore: add prepare script so git+URL installs build dist/
