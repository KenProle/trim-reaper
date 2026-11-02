Find dependencies that introduce large dependency subtrees for functionality we barely
use. Reduce that overhead using supported minimal packages, unused
optional-integration removal, or existing alternatives. Compare the resolved
dependency graph before and after. Remove transitive packages only when no retained
dependency requires them.
