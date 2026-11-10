# Web application feature specification

Status: phase 1 web MVP.

## Audience and purpose

Help people discover and share residential and commercial property in Myanmar. Visitors can search without an account; account holders can post and manage their own listings.

## Features

- Responsive landing page and search entry point for Yangon, Mandalay, and Bago.
- Buy, Sell, and Rent intent categories.
- Public keyword, city, township, intent, price, bedroom, and sort filters with paginated API results.
- Listing cards and detail views with price, location, property attributes, photos, description, and poster-provided contact details.
- Email/password sign-up and sign-in, listing creation, and an account dashboard to edit, pause, publish, and remove owned listings.
- Light and dark color modes. Default to the system preference; provide a header toggle and persist the user's choice.
- Demo fallback listings when the API is not available. Clearly label demo listings and use sample contact details only as non-real content.
- shadcn visual system based on preset `b7ClNFsdu`.

## Experience requirements

- Maintain a clear visual hierarchy and responsive layouts for desktop and mobile browser widths.
- Provide visible keyboard focus, accessible labels, alt text, loading and empty states, and clear form errors.
- Theme changes must cover page surfaces, text, inputs, cards, dialogs, and controls while keeping photos legible.
- Browser UI consumes the API; it does not make authorization decisions on behalf of the service.

## Acceptance criteria

- Visitors can search and open published listings without signing in.
- The three target cities and all three transaction intents are represented and filterable.
- Account holders can create listings and manage only their own listings through the UI and API.
- Theme toggle switches between light and dark mode, follows system preference before an explicit choice, and remembers that choice across reloads.
