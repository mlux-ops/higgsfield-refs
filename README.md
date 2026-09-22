# Higgsfield Refs

Public media bucket for [`higgsfield-tasks`](https://github.com/mlux-ops/higgsfield-tasks).

The Higgsfield REST API's documented input shape only accepts image/video/audio
references by URL (`{type: "image_url", image_url: "..."}`), not local file
uploads — and the undocumented upload endpoint the JS SDK's legacy client
points at (`/files/generate-upload-url`) returns presigned S3 URLs that
reject every signing attempt we tried (`SignatureDoesNotMatch`, header value
we can't determine). So local files that need to go into a Higgsfield
generation via the direct API get pushed here first, and referenced by their
raw GitHub URL instead.

This repo is **intentionally public** — Higgsfield's servers need to fetch
the URL over the open internet. Files under `media/` are content that will
be used as generation reference input; do not add anything sensitive here.

Files are named by content hash to avoid collisions and avoid meaningful
filenames leaking into a public URL.
