# Reproducibility Release Status

## Publicly available now
- Research report and milestone summary
- Experiment log
- Claims and limitations
- Reviewer packet
- Project static demo and overview

## Archives not yet published as downloadable raw artifacts
The original experiment ZIPs are present in the project file library but have not all been transferred to the public GitHub repository or a public release host. This status page deliberately avoids claiming a complete raw-data release.

## Release checklist
- [ ] Identify exact original archives and versions
- [ ] Verify original files have not been modified
- [ ] Create SHA-256 checksums from exact archive bytes
- [ ] Upload archives to a public release host (GitHub Releases preferred)
- [ ] Publish checksums and archive manifest
- [ ] Document OS/Python versions, dependencies, commands, expected outputs and known limitations
- [ ] Independently download release files and verify checksums
- [ ] Add release URLs here

## Technical constraint
Current GitHub connector access supports repository text/API operations but does not provide a binary GitHub Release asset upload operation. Raw archive publication requires a supported upload path or user-assisted upload. The checksum must be computed from the exact archive bytes, not from a filename or previous checksum text.
