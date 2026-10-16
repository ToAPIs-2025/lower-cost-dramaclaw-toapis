# DramaClaw integration notes

This is an independent API asset example and integration contract. It is not an official upstream provider, and the contract JSON is not a validated upstream settings import. API output validation is separate from in-app acceptance.

Pinned upstream SHA: 7257dd2c23025eb42d289726dc4bea34ab241887

- [src/novelvideo](https://github.com/dramaclaw/dramaclaw/blob/7257dd2c23025eb42d289726dc4bea34ab241887/src/novelvideo)
- [frontend/src/features/canvas/application/textToVideoSubmit.ts](https://github.com/dramaclaw/dramaclaw/blob/7257dd2c23025eb42d289726dc4bea34ab241887/frontend/src/features/canvas/application/textToVideoSubmit.ts)

Images: authenticate with Bearer, submit once and persist the id, poll the image generations/{id} route, and download result.data[0].url. Resolution fields differ by model; changing Base URL alone is insufficient.

Video: MiniMax-H3, 5s/768p, first frame via image_with_roles, separate videos/generations submit/poll routes. A task id alone is not a successful clip: validate completion, a playable file, and settled billing.

In-app checklist: model selection → duplicate-safe submission → task recovery → save originals → import/display in the original UI → reconcile billing. Full upstream UI acceptance remains pending.
