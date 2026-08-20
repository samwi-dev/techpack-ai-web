# Project URL import MVP

Open a prepared Techpack project with:

`https://samwi-dev.github.io/techpack-ai-web/project.html?project=<project-id>`

Each project uses `projects/<project-id>.json`, following `projects/template.json`.

The JSON contains the Techpack fields plus ordered views with image URLs and notes. This creates the persistent loading contract: a future site version can continue to load the same project URL without manually re-uploading photos.

## Upload pipeline

Conversation attachments must be copied to a durable image host before creating the project JSON. Notion attachment URLs are not used as production image URLs because their access may be restricted or expire. Recommended next step: connect Cloudflare R2 or Supabase Storage, then upload attachments and write their secure URLs into the project JSON.
