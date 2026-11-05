# else.bot toolkit patches

The `else/0.9.0-markdown-links` branch starts at upstream commit
`7591a35eced761e3613c01e71ff04c10129dae1a`, the published 0.9.0 release.

Only `gpui-base` changes:

- `TextView::link_tooltip` accepts an application-supplied tooltip builder.
  The preview follows the pointer and clears when the pointer leaves the link.
  Links whose displayed text already equals the URL omit the preview.
  The application owns its appearance.
- Regression tests cover native link preview movement, dismissal, and redundant
  preview suppression, plus punctuation after inline code and split Unicode spans.

GPUI Kit 0.9.0 uses gpui-pre 0.3.11, whose line wrapper keeps inline elements
attached to adjacent words. The fork no longer patches punctuation wrapping.

The else.bot application patches only `gpui-base` and pins a full Git commit.
Keep the remaining toolkit and GPUI versions aligned with the published release.
When upstream supports link previews, remove the patch from the application.
