Reduce this project's dependencies while preserving behavior, error handling,
security, public API and downstream consumer compatibility, and supported runtimes.
Follow the project's contributor instructions and use its existing toolchain and
package manager. Work in small,
reviewable changes and preserve unrelated work. Establish the build and test baseline
before editing; if required checks fail or cannot run, report the blocker and stop
changes.

Investigate uncertain usage rather than guessing. Verify each change; undo
your candidate changes if verification fails or cannot be completed. Do not weaken
tests or security controls to make a removal pass.

Retain specialized libraries when replacing them would introduce security, correctness,
or maintenance risk, especially cryptography, authentication, and complex parsing.
Report actual commands and results,
including checks not run. Fewer dependencies is useful only when the resulting project
is better. If a pass introduces or upgrades a package, apply the third-party library
policy above first. If that policy is not available in the session, request it before
proceeding with the addition or upgrade.
