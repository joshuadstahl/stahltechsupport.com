<wizard-report>
# PostHog post-wizard report

The wizard has completed a deep integration of PostHog analytics into this Astro (View Transitions) project. A new `src/components/posthog.astro` component was created containing the PostHog web snippet with an initialization guard (`window.__posthog_initialized`) to prevent stack overflow errors during ClientRouter soft navigation. The snippet is configured with `capture_pageview: 'history_change'` for automatic pageview tracking. The component is loaded in `src/layouts/Layout.astro`, which already uses `<ClientRouter>`, ensuring PostHog is present on every page. Four event tracking integrations were added to key widgets and components.

| Event | Description | File |
|---|---|---|
| `contact_form_submitted` | Fired when a visitor submits the contact form. Key conversion event. | `src/components/ui/Form.astro` |
| `pricing_plan_selected` | Fired when a visitor clicks a pricing plan CTA. Tracks `plan_title` and `plan_price`. | `src/components/widgets/Pricing.astro` |
| `cta_clicked` | Fired when a visitor clicks a button in a CallToAction widget. Tracks `button_text` and `button_href`. | `src/components/widgets/CallToAction.astro` |
| `hero_cta_clicked` | Fired when a visitor clicks an action button in the Hero section. Tracks `button_text` and `button_href`. | `src/components/widgets/Hero.astro` |

## Next steps

We've built some insights and a dashboard for you to keep an eye on user behavior, based on the events we just instrumented:

- [Analytics basics dashboard](/dashboard/1608554)
- [Contact Form Submissions insight](/insights/pfAS5c3L)
- [Pricing Plan Selections insight](/insights/3Jma9uL2)
- [Hero CTA Clicks insight](/insights/UrIz8H6R)
- [CTA Clicks Over Time insight](/insights/tExXe02d)
- [All Engagement Events (overview) insight](/insights/1imcEbgj)

### Agent skill

We've left an agent skill folder in your project. You can use this context for further agent development when using Claude Code. This will help ensure the model provides the most up-to-date approaches for integrating PostHog.

</wizard-report>
