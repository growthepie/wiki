---
description: Use JavaScript or TypeScript fetch to load growthepie data.
---

# Fetch growthepie Data In JS Or TS

This recipe fetches `master.json` and prints the supported metrics for `arbitrum`. Use this recipe when you want discovery metadata inside a browser app, Node.js tool, or TypeScript project.

## Example

```ts
const url = "https://api.growthepie.com/v1/master.json";

const response = await fetch(url);
if (!response.ok) {
  throw new Error(`Request failed with status ${response.status}`);
}

const master = await response.json();
console.log(master.chains.arbitrum.supported_metrics);
```

## Related Pages

* [Endpoint: master.json](../api-reference/master-json.md)
* [Choose The Right Endpoint](../getting-started/choose-the-right-endpoint.md)
