# Security policy

OpsDeck stores payroll, statutory IDs (PF/ESI/PAN/Aadhaar-linked data) and attendance
for Indian businesses. Treat every report as urgent.

- Report vulnerabilities privately to **security@infoloop.co**, or use GitHub's private vulnerability reporting on public repos.
  Do not open a public issue. We acknowledge reports within 2 business days.
- Never commit secrets. Secret scanning with push protection is enabled org-wide.
- Production credentials live only in GitHub Environment `production` / the cloud secret store.
