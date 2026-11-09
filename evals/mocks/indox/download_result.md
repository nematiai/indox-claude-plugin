---
expect:
  kind: [image, video, model, pdf, font]
  conversion_id: string
---

{"conversion_id": "{{input.conversion_id}}", "download_url": "https://indox.org/api/v1/pdf_handler/{{input.conversion_id}}/download/?sig=eval", "needs_api_key": false, "expires_at": "2026-12-01T12:00:00Z"}
