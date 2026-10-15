# MarginPilot

**Know Your Costs. Protect Your Margins. Make Smarter Moves.**

For the ITBT exercise, the selected business is **Supply Chain Consulting Company**. MarginPilot is its proposed logistics finance support service for freight forwarders and transport operators. It is a static educational business app, not an established company or a live consulting provider.

## The business problem

A shipment can bring in substantial revenue and still produce a weak contribution after carrier, inland transport, handling, documentation, terminal, delay, and other attributable costs. Even a shipment with positive contribution can create a liquidity squeeze if supplier payments fall due before customer collections arrive. MarginPilot demonstrates a consistent way to evaluate those financial questions before a decision is made.

## Exercise sections and app modules

- **Home:** business name, logo, purpose, short description, and links to start using the tools.
- **About business:** proposed business model, target users, problem and technology context.
- **Services:** four example consulting services with clearly labelled fictional classroom prices.
- **Dashboard:** six calculated KPIs, visualizations, shipment filters, recent records, and generated priority actions.
- **Contact / enquiry:** visible demo contact placeholders and a locally validated enquiry form. It does not claim to send data.
- **Other decision modules:** shipment profitability, carrier comparison, working capital, what-if scenarios, and decision center.

The Home page and Contact page each provide more than five working internal hyperlinks to relevant sections and tools. Dashboard filters, profitability, carrier comparison, and the enquiry form provide interactive business features.

The exercise requires GitHub Pages publication and submission of a live URL. This project has not been published yet; follow the deployment steps below after uploading it to a repository.

### Decision modules

- **Profitability:** itemized cost calculator, contingency, break-even price, required selling price for a target contribution margin, validation, recommendations, and CSV export.
- **Carrier comparison:** three editable quotations ranked by cost, contribution, reliability, transit speed, or an explained normalized weighted score.
- **Working capital:** a 30-day, event-based cash plan with daily projected balances, weekly summaries, reserve breaches, guidance, chart, and CSV export.
- **What-if scenarios:** editable base, cost-pressure, and improved-operations cases with contribution, margin, modeled working capital, funding gaps, and objective-based scenario selection.
- **Decision center:** current sample shipment performance, cash pressure, carrier result, prioritized actions, and an exportable action report.
- **About business:** project context and a feedback form that prepares an email draft or saves locally in the current browser.

## Financial formulas

### Shipment profitability

`Total revenue = customer freight revenue + other service revenue`

`Base operating cost = sum of entered attributable cost components`

`Contingency = base operating cost × contingency percentage ÷ 100`

`Total estimated cost = base operating cost + contingency`

`Estimated contribution = total revenue − total estimated cost`

`Contribution margin (%) = estimated contribution ÷ total revenue × 100`

`Break-even selling price = total estimated cost`

`Required selling price = total estimated cost ÷ (1 − target margin ÷ 100)`

The required-price calculation requires a target margin below 100%. At zero revenue, the margin is not calculated. Contribution is not net profit: corporate overhead, taxes, financing, and costs not entered are excluded.

### Dashboard

The average contribution margin KPI is an aggregate margin: `sum of contribution ÷ sum of revenue`. It is not an unweighted average of shipment percentages. The working-capital KPI is a simple timing estimate derived from shipment costs and the difference between collection and carrier payment days; it is not a cash forecast.

### Carrier comparison

`Estimated cost = freight + surcharges + other costs + delay allowance`

`Expected contribution = entered revenue − estimated cost`

The balanced score normalizes the alternatives on the current quote range: 40% lower cost, 35% higher recorded on-time rate, and 25% shorter stated transit. A tie across a measure gives all alternatives the same full score for that measure. This score is a comparison aid, not a predicted service outcome. The pre-collection cash display counts the estimated total quote cost when its payment day is earlier than the assumed 30-day customer collection day, and zero otherwise. Actual split invoices and payment schedules can differ.

### Cash planning

`Closing cash = opening cash + cumulative collections − cumulative payments`

`Available after reserve = closing cash − minimum cash reserve`

Events are applied on their stated day and in listed order for same-day events, including events on Day 0. The first reserve breach and the maximum daily amount below reserve are identified from the daily balances. This peak gap is a planning estimate, not a borrowing recommendation.

### Scenarios

`Revenue = selling rate per shipment × shipment volume`

`Total costs = (carrier cost + other costs + delay cost) × volume`

`Working capital estimate = per-shipment modeled costs × volume × min(max(collection days − payment days, 0), 30) ÷ 30`

This simplified peak-timing estimate excludes opening cash, other company obligations, and within-period event detail. Scenario selection uses the chosen objective and available funding; verify the displayed assumptions before using it.

## Data, limitations, and privacy

All eight shipment records, carrier quotations, event dates, and scenario values are illustrative. They do not represent live customers, carrier rates, invoices, payments, or bank balances. Data entered in calculators is held in the open page; the feedback “Save locally” option uses browser local storage on that device. No account, backend, accounting connection, carrier API, bank connection, GPS feed, or automatic email sending is provided. Browser storage can be cleared by the user. Recommendations are indicative educational examples, not accounting, tax, credit, investment, or professional financial advice.

## Project files

```text
index.html       Application structure and accessible controls
style.css        Responsive visual design and print styles
script.js        Demo data, calculations, rendering, validation, exports
README.md        Setup, formulas, limitations, and deployment guide
images/          Reserved for local visual assets (logo is inline SVG)
```

No external chart library is required. Charts are rendered with HTML and inline SVG. A Google Fonts import is used for typography; the application remains usable with system fonts if the font service is unavailable.

## Run locally

1. Download or unzip the project.
2. Open `index.html` in a modern browser. The core app runs without a local server.
3. Use the navigation to visit each module. Try **Load example**, edit the assumptions, and use **Recalculate** or change a value to refresh the views.
4. Use CSV export buttons to download reports, or the print button for a browser print view.
5. To run the built-in calculation checks, open the browser developer console and call `MarginPilotChecks()`. It returns the passed and failed check names. This is a small calculation checklist, not comprehensive browser/device testing.

## Publish on GitHub Pages

1. Create a GitHub repository named `StudentName-BusinessApp` (or another name you choose).
2. Upload `index.html`, `style.css`, `script.js`, and `README.md` to the repository root.
3. Open **Settings → Pages**.
4. Under build and deployment, select deployment from the **main** branch and the **root** folder.
5. Save the settings and wait for GitHub Pages to publish the site.
6. Open the URL shown by GitHub Pages. Check each navigation section, edit a calculator, export a CSV, and test the layout at desktop and mobile widths.

No published URL is included because this project has not been deployed. Relative asset paths make the site compatible with a repository subpath.

## Verification checklist

The built-in `MarginPilotChecks()` function checks positive contribution, a loss result, the target-price calculation, zero-revenue division handling, an invalid 100% target, and a cash reserve breach that occurs before a later collection. The source also validates nonnegative monetary inputs, target margin, payment/event ranges, and zero-revenue margin display. For academic review, manually change each module's assumptions and compare the displayed outputs to the formulas above. A full cross-browser, mobile-device, and hosted GitHub Pages test still needs to be performed after publication.

## Two-minute ITBT presentation

> My business application is MarginPilot, a finance-driven logistics decision-support prototype. Logistics companies often quote and operate shipments using separate spreadsheets, so the full cost of carrier charges, handling, documentation, inland transport, delays, and cash timing can be hard to see together.
>
> MarginPilot is designed for freight forwarders, transport operators, logistics managers, and commercial pricing teams. It helps answer whether a shipment earns enough contribution, what selling rate meets a target margin, which carrier quote best fits the business priority, and whether cash is available before upcoming payments are due.
>
> The application has six working modules: a financial overview, a shipment profitability calculator, carrier comparison, working-capital planner, scenario simulator, and decision center. The dashboard provides six manager KPIs: total shipment revenue, total logistics costs, total contribution, aggregate contribution margin, number of shipments below target margin, and an estimated working-capital requirement. Filters update the selected shipment view.
>
> The calculations are visible and use illustrative sample data. For example, shipment contribution equals total revenue minus attributable costs, while contribution margin is contribution divided by revenue. The cash planner puts collections and payments on a shared timeline, because a profitable shipment can still cause a short-term cash shortage. MarginPilot is an educational static website; it does not connect to live business systems, and managers should verify assumptions before acting.
