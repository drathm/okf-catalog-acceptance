# okf-catalog acceptance fixture

A small, entirely fictional knowledge bundle for a bakery that does not exist, kept so that [okf-catalog](https://github.com/drathm/okf-catalog) can prove its publish loop end to end: a push to `main` runs the publish recipe (`.github/workflows/publish.yml`, copied unchanged from the okf-catalog package), which checks the pages with the OKF checkers, packs them, and writes the result to the `published` branch; a running okf-catalog server that polls that branch picks the change up at its next tick, and an agent asking through it answers from the new text with no reinstall. This is acceptance item 5 of okf-catalog's version 0.

Nothing in `kb/` describes a real company, person or product. The pages exist to be searched, promoted and republished.

To serve the published branch from your own machine, with the `okf-catalog` command installed (`npm install -g okf-catalog`), put this `okf-catalog.yaml` in a project folder and run `okf-catalog serve` there, or load the plugin in Claude Code from that folder:

```yaml
company: tidewater
source:
  repository: https://github.com/drathm/okf-catalog-acceptance.git
  branch: published
  bundle_path: .
serve:
  pull_interval: 30s
types: [Term, Guide, Reference]
```
