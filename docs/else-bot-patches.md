# else.bot toolkit patches

The `else/0.8.1-markdown-links` branch starts at upstream commit
`99576db58ec8103417c41a092e891b4022d24e7e`, the published 0.8.1 release.

Only `gpui-base` changes:

- Closing punctuation after inline code joins the preceding wrap fragment,
  including split and Unicode spans. Source text and selection stay intact.
- `TextView::link_tooltip` accepts an application-supplied tooltip builder.
  The preview follows the pointer and clears when the pointer leaves the link.
  The application owns its appearance.
- Regression tests cover punctuation wrapping and native link preview movement
  and dismissal.

The else.bot application patches only `gpui-base` and pins a full Git commit.
Keep the remaining toolkit and GPUI versions aligned with the published release.
When upstream supports these behaviors, remove the patch from the application.
