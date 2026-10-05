# captain-search

`<captain-search>` adds a search box with instant results to any website, over a [Captain App Search](https://docs.captain.dev/app-search/overview) index. One script tag, one element, no dependencies.

```html
<script type="module"
  src="https://cdn.jsdelivr.net/gh/runcaptain/captain-search@1.4.0/captain-search.js"
  integrity="sha384-H3KsMSqYaVQoKWMOmai07uN5MebW+NeCuBEP07N3LvcO5Qp1btD1I9sgE2FWnW6i"
  crossorigin="anonymous"></script>

<captain-search
  endpoint="https://YOUR_TENANT.captain.dev"
  index="YOUR_INDEX"
  key="YOUR_SCOPED_KEY"
></captain-search>
```

For a full search page (facets, sort, pagination, URL sync), load `captain-instantsearch.js` instead and put the elements inside `<captain-search-root>`. It includes the search box.

| File | Holds |
|---|---|
| `captain-search.js` | `<captain-search>` and `createSearch` (headless) |
| `captain-search-extras.js` | Recent searches and Query Suggestions rows for the box. `captain-search.js` loads it by itself, only when the box has `recent-searches` or `query-suggestions`, and checks it against a hash built into the box. Never add a script tag for it. |
| `captain-instantsearch.js` | The same, plus `<captain-search-root>`, hits, pagination, stats, refinement list, sort, range and the other search page elements |

Use a **scoped key** with `allowed_origins` set to your site. Never put a search key or a write key in a page.

`@1.4.0` pins this exact file, and the `integrity` hash (one per file, in `integrity.json`) makes the browser refuse any other bytes. `@1` follows the newest 1.x release but cannot carry a hash.

Attributes, styling, events and key setup: https://docs.captain.dev/app-search/search-widget

This repository holds only released builds. Each release is a tag (`v1.4.0`), and `integrity.json` lists each file's SRI hash.
