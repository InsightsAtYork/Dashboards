[README.md](https://github.com/user-attachments/files/33256975/README.md)
# Diocesan Dashboards — Parish Overview

A public-facing landing page for the **Diocesan Dashboards: Parish Overview** report. The page embeds an interactive Power BI dashboard and provides links to related Church of England mapping tools, Parish Returns, and the diocesan data team.

## What the page includes

- **Embedded Power BI report** with an option to open it in a separate browser tab.
- **Version 3 announcement** and a summary of the dashboard's recent changes.
- **Quick links** to the Community Insights Map, Advanced Parish Mapping, Parish Returns, and the data team.
- **Responsive layout** that positions the dashboard and quick links side by side on wider screens and stacks them on smaller screens.
- **Accessibility provisions**, including a skip link, labelled sections, visible keyboard focus, descriptive iframe text and reduced-motion support.

The Version 3 notes in the HTML describe accessibility improvements, updated Indices of Multiple Deprivation (IMD) and Lowest Income Communities Fund (LICF) data, cross-page filtering, simpler navigation, and underlying data improvements. These describe the **linked Power BI report**, not functionality implemented by this HTML file itself.

## Technical overview

| Component | Implementation |
| --- | --- |
| Page structure | HTML5 |
| Styling | CSS embedded in the `<style>` element |
| Typography | Google Fonts: Cabin, with Arial/sans-serif fallback |
| Dashboard | Power BI report embedded via an `<iframe>` |
| External resources | Power BI, ArcGIS mapping services, Church of England Parish Returns, and Google Fonts |
| JavaScript | None |
| Build process | None — a single static HTML page |

No package manager, framework, database, API keys or server-side code is required for the landing page itself.

## Running locally

1. Save the supplied HTML code as `index.html`.
2. Open `index.html` in a modern web browser.
3. Ensure you have an internet connection to load the Power BI report, fonts and linked external services.

The page can also be served by a basic local HTTP server, for example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Publishing

Upload `index.html` to any host that serves static websites, such as GitHub Pages or an existing web server. No compilation or deployment build is required.

**Important:** This page is intended for public access. The embedded Power BI URL is included directly in the HTML, so visitors can view and share it. Confirm that the report's publishing settings and underlying data are appropriate for public disclosure before deployment. Hosting the page does not itself manage the Power BI report's data, refresh schedule or access controls.

## Updating the page

Edit `index.html` directly:

| To change | Find in the HTML |
| --- | --- |
| Browser tab title | `<title>Diocesan Dashboards – Parish Overview</title>` |
| Page heading | `<header class="site-header">` |
| Version announcement | `<section class="announcement-banner">` |
| Embedded dashboard | The `src` attribute of the Power BI `<iframe>` |
| Open-in-new-window dashboard link | The matching `href` on the dashboard link |
| Community Insights Map | The `href` in the **Community Insights Map** section |
| Advanced Parish Mapping | The `href` in the **Advanced Parish Mapping** section |
| Parish Returns | The `href` in the **Parish Returns** section |
| Contact email | `mailto:insights@yorkdiocese.org` |
| Version 3 change list | The **What's New in Version 3** section |
| Colours, typography and spacing | CSS variables in `:root` and the related style rules |

**Keep both Power BI URLs in sync:** When replacing the report, update both the iframe `src` and the **Open dashboard in a new window** link `href`. Otherwise the two actions may open different reports.

The main theme variables are `--red`, `--yellow`, `--navy`, `--page-background`, `--text` and `--content-width`. Responsive rules are defined at **1000px** and **600px** viewport widths.

Version announcements and release notes are **manually maintained** in the HTML. They do not automatically update when the Power BI report changes.

## External destinations

The source currently points to:

- **Power BI:** a public Power BI report URL used by both the iframe and the open-in-new-window link.
- **Community Insights Map:** `https://experience.arcgis.com/experience/5ff5e9d07eab4ce28543fca4da46044d`
- **Advanced Parish Mapping:** `https://c-of-e.maps.arcgis.com/apps/instant/basic/index.html?appid=123773d4cbd44be6ba5c546404989078`
- **Parish Returns:** `https://parishreturns.churchofengland.org/home/`
- **Data team:** `insights@yorkdiocese.org`

These addresses are documented from the supplied HTML; their current availability has not been independently tested.

## Accessibility and maintenance

The page includes semantic headings and landmarks, a keyboard-accessible skip link, high-visibility focus outlines, a descriptive iframe title, and a CSS preference for reduced motion. The embedded Power BI report is a separate interface and may have its own accessibility behaviour. These provisions are **not a substitute for accessibility testing**.

Before publishing changes, check:

1. The dashboard loads and the separate-window button opens the **same** report.
2. All four quick links/contact actions go to the expected destination.
3. The page remains usable on desktop and mobile screens.
4. Keyboard navigation, the skip link and visible focus indicators work.
5. Version messaging matches the actual published report.
6. No confidential or restricted data is exposed through the public Power BI report.

## Troubleshooting

| Issue | Check |
| --- | --- |
| Dashboard is blank or unavailable | Internet connection, Power BI publishing status, report permissions and any browser restrictions on embedded content |
| Dashboard opens but shows outdated data | Power BI dataset refresh and source data; these are not controlled by this HTML page |
| Open-in-new-window report differs from the embedded one | Make the iframe `src` and dashboard link `href` identical |
| Maps or Parish Returns links fail | Whether the external service or destination URL has changed |
| Font looks different | Google Fonts availability; the page falls back to Arial/sans-serif |
| Layout is cramped on a phone | Review the CSS media queries at 1000px and 600px |

## Ownership and licence

For dashboard questions, corrections and improvement suggestions, contact **insights@yorkdiocese.org**.

No licence information is included in the supplied source. Do not assume the page or the third-party reports and services are available for unrestricted reuse.
