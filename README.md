# FlameWill download artifact

`actions/download-artifact` (v8, the latest, and v4) with the same inputs and outputs. On a [FlameWill](https://flamewill.com) runner it reads, from FlameWill, an
artifact that [`FlameWill/upload-artifact`](https://github.com/FlameWill/upload-artifact) kept in this run. Everywhere else, and for
anything FlameWill does not keep, this is `actions/download-artifact` itself.

```yaml
- uses: FlameWill/download-artifact@v1   # was: actions/download-artifact@v4 (or @v8)
  with:
    name: test-report
    path: reports/
```

- **From FlameWill:** an artifact named in this run (the newest run attempt that kept it).
- **From GitHub:** every artifact of the run (no `name`), `artifact-ids`, a `pattern`, `skip-decompress: true`, another `repository` or `run-id`, or a name FlameWill does not
  keep in this run. The step says which.
- **`kept-by`** output: `flamewill` or `github`.
