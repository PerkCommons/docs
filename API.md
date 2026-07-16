# API

## Public data

The Git repository is the initial public API. Consumers should pin a commit SHA
when reproducibility matters and read individual JSON objects from `listings/`.
The schema is version controlled beside the records.

No hosted JSON API is required for launch. A hosted API should be added only when
real consumers need query behavior that static Git releases cannot reasonably
provide.

## Submission endpoint

### `POST /api/submissions`

Accepts `multipart/form-data` or URL-encoded form data.

Required fields: `provider`, `title`, `category`, `sourceUrl`, `details`, and
`affiliationConfirmed=true`. `cf-turnstile-response` is required in production.
`email` is optional and is never published without separate consent.

Responses are JSON with a `message`. Expected statuses are `201`, `400`, `415`,
`429`, and `503`. This endpoint is intake only; it exposes no submission lookup or
moderation API.
