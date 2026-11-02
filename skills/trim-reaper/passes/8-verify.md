Verify a clean reproducible installation, build, tests, and representative application
flows. Check that manifests, lockfiles, documentation, and any existing SBOM reflect
the final dependency graph. Summarize direct dependencies removed, transitive
dependencies eliminated, production scope changes, and local code added. List retained
dependencies with reasons, and clearly identify any checks you could not complete.
Use this compact report format:
- Changes: dependency, action, rationale, and replacement or local code added.
- Counts: before/after direct and transitive dependencies, with counting method and
  production scope. Distinguish unique packages from resolved versions; avoid double
  counting shared transitive dependencies. Label estimates and unavailable measurements.
- Verification: exact commands, results, and checks not run with reasons.
- Retained dependencies: names and reasons for retention.
- Remaining risks: unresolved questions, compatibility limits, and follow-up work.
Report measured outcomes only as measured; do not invent counts or security improvements.
