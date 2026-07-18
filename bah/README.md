# Central & Eastern Virginia BAH Calculator

Responsive, dependency-free 2026 Basic Allowance for Housing calculator for ABGRE.com. The interface highlights military installations in Hampton Roads, Central Virginia, Quantico, Charlottesville, and the Northern Neck so users can click an installation instead of finding and typing its permanent-duty ZIP code.

## Wix embed

After the pull request is merged and GitHub Pages updates, embed this URL:

```html
<iframe
  src="https://adambgarrett.github.io/us-metro-zillow-widget/bah/"
  title="2026 Central and Eastern Virginia BAH Calculator"
  width="100%"
  height="1100"
  loading="lazy"
  style="border:0; width:100%; max-width:100%;"
  allow="clipboard-write"
></iframe>
```

Recommended Wix HTML embed height: approximately `1100px` on desktop and `1450px` on mobile. Wix may require a separate mobile height adjustment. The widget also emits this message whenever its height changes for parent pages that support automatic iframe resizing:

```js
{ type: "abgre-bah-resize", height: 1234 }
```

## Deep links

Selections are stored in the query string and can be linked directly:

```text
?installation=nas-oceana&grade=E-6&dependents=with
```

## Data source and scope

- Rates: official 2026 Defense Travel Management Office `BAH-ASCII-2026.zip` rate file.
- Installation mappings: each highlighted installation uses its permanent-duty ZIP and the corresponding 2026 DTMO ZIP-to-MHA mapping.
- Pay grades: E-1 through E-9, W-1 through W-5, O-1E through O-3E, O-1 through O-6, and O-7+.
- Dependency status: the two published categories, with dependents and without dependents.
- The calculator is informational and links users to the official DoD lookup for entitlement verification.

## Annual update checklist

1. Download the new annual ASCII ZIP from the official DoD BAH Rate Lookup page.
2. Confirm every highlighted installation's permanent-duty ZIP still maps to the expected MHA.
3. Replace the arrays in `RATES`, update the displayed year, title, metadata, and disclaimer.
4. Spot-check at least E-5 with dependents and O-3 without dependents for every included MHA against the official lookup.
5. Re-test desktop and mobile layouts and update the iframe height recommendation if needed.
