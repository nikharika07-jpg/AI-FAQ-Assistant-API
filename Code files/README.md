# AI FAQ Assistant API — Modified

Same AI FAQ Assistant topic and MVC architecture, with these modifications:

- FAQ `tags` field for better organization.
- Pagination and `category` filtering on `GET /api/faqs`.
- Search now includes tags.
- AI FAQ generation accepts an optional `category`.
- Added `/health` endpoint and API version.
- Updated API integration tests and Postman collection.

## Setup
Copy `.env.example` to `.env`, set MongoDB/JWT/Gemini values, then run:
```bash
npm install
npm run dev
```

## Main endpoints
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/profile`
- `POST /api/faqs`
- `GET /api/faqs?page=1&limit=10&category=Technology`
- `GET /api/faqs/:id`
- `PUT /api/faqs/:id`
- `DELETE /api/faqs/:id`
- `GET /api/faqs/search?q=keyword`
- `POST /api/ai/answer`
- `POST /api/ai/generate-faq`

FAQ example:
```json
{"question":"What is AI?","answer":"AI is ...","category":"Technology","tags":["ai","intelligence"]}
```

AI FAQ example:
```json
{"topic":"Machine Learning","category":"Technology"}
```

Run integration tests with `npm run test:api`.

Import `AI_FAQ_Assistant_API.postman_collection.json` into Postman. Login stores `token`; Create FAQ stores `faqId`.
