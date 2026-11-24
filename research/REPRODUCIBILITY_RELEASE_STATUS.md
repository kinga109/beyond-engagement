# Reproducibility Release Status

Last checked: 2026-11-24

## Publicly available now
- Research report, milestone summary, experiment log, claims and limitations, reviewer packet, project overview, and static demo.
- Reviewer response tracker and independent-review findings template.

## Original raw archive release: incomplete
The original ZIPs remain unchanged in the project file library. No public GitHub Release assets are currently published (the repository Releases endpoint returned an empty list on 2026-11-24). Therefore no public raw-archive download URLs are available yet.

## Completed source-archive verification (V5.26–V5.30)
- Exact original archive bytes materialized and SHA-256 calculated for V5.26, V5.27, V5.28, V5.29, and V5.30.
- All five passed local ZIP integrity testing (`unzip -t`).
- Hashes and source file sizes are published in `SHA256SUMS_SOURCE_V5_26_V5_30.txt`.
- This is not a complete V5.5–V5.30 archive manifest.
- No independent download comparison has occurred because the public binary assets are not uploaded.

## Reproduction documentation
`REPRODUCING_V5_26_TO_V5_30.md` documents the available run commands and core dependencies. Exact version pins and clean-environment reruns remain outstanding.

## Release checklist
- [x] Verify five original source ZIPs locally without modifying them
- [x] Calculate outer-archive SHA-256 for V5.26–V5.30
- [x] Publish source hashes and provisional reproduction instructions
- [ ] Identify and hash every original milestone ZIP from V5.5 through V5.30
- [ ] Upload original archives to a public release host
- [ ] Publish direct asset URLs
- [ ] Independently download every public asset and compare SHA-256
- [ ] Pin dependencies per milestone and perform clean-environment reruns
- [ ] Update the six reviewers with the final downloadable artifact links

## Upload limitation
The available connected GitHub actions in this session support repository text and read operations, but do not expose GitHub Release creation or binary release-asset upload. The public repository's Releases endpoint currently contains no releases. I will not claim that binary release publication or independent download verification is complete until the actual upload and separate download test succeed.

## Reviewer response boundary
Six invitations were sent on 2026-11-23. On 2026-11-24, one automatic acknowledgement from Prof. Alexis Hiniker was received. It says the sender receives more email than they can respond to; it is not a substantive review and does not explicitly state a project-specific decline. No substantive criticism has been received as of this check.
