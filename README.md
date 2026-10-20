# quote-builder-demo

A quote builder for a made-to-order manufacturer, as a single HTML file with vanilla JavaScript. Live demo: [nicolasbagatini.dev/demo/cotacao](https://nicolasbagatini.dev/demo/cotacao/).

All data is fictional: products, costs, margins and the sample customer. The interface is in Portuguese.

## What it does

- Step-by-step quote: pick a product, quantity ranges, finishing, closures and accessories.
- Prices per quantity range, built from unit cost and margin per component, with minimum order rules per product and per accessory.
- Payment terms (cash, 28, 28/56 and 28/56/84 days) that add their own financial cost to the final price.
- A live summary while the quote is being built, a list of all quotes, and a print layout (A4) that turns the quote into a document for the customer.

## Worth a look

- The catalog is plain data (`PRODUTOS`, `COMPS`, `FATURAMENTO`): changing products or margins never touches the rendering code.
- The UI re-renders from one state object (`S`), with step validation (`podeAvancar`) gating each step.
- `@media print` with `@page A4` produces the customer document from the same markup, with no PDF library.
