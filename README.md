# extport

Making PHP extensions installable via [PIE](https://github.com/php/pie) today.

> **Disclaimer:** This project is not affiliated with or endorsed by the PHP project or the official PIE team. It is an independent effort to make extensions available through PIE before they add native support. For official PIE, see [php/pie](https://github.com/php/pie).

## Quick install

```bash
pie install extport/protobuf
```

## Currently mirrored extensions

<!-- extensions-table-start -->

<!-- extensions-table-end -->

See [`registry.json`](registry.json) for the full list. See [`.extport.example.json`](.extport.example.json) for all available mirror configuration options.

## How it works

1. A **daily cron** checks each upstream repo for new releases
2. When a new release is found, it **dispatches a sync** to the corresponding mirror repo
3. The mirror repo runs [mirror-action](https://github.com/extport/mirror-action), which syncs the release, creates a tagged release with PIE-compatible `composer.json`, and builds binaries
4. A **weekly health check** detects stale or broken mirrors and opens issues

## Request a new extension

Want an extension added? [Open an extension request](https://github.com/extport/core/issues/new?template=extension-request.yml).

## Questions & discussion

For questions, ideas, or anything that isn't an extension request, head to [GitHub Discussions](https://github.com/extport/core/discussions).

## Related repositories

- [extport/mirror-action](https://github.com/extport/mirror-action) — composite action that handles sync, release, and binary builds
- [extport/builder](https://github.com/extport/builder) — builds PHP extension binaries for multiple platforms
- [extport/mirror-template](https://github.com/extport/mirror-template) — template repo used when creating new mirrors

## License

[MIT](LICENSE)
