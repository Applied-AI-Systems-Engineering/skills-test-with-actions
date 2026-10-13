# Test with Actions — verified course completion

This is an attributed copy of the [GitHub Skills Test with Actions exercise](https://github.com/skills/test-with-actions). Instructor MIT licensing is preserved in [LICENSE](LICENSE). Sample application, workflow examples, and exercise tests are instructor practice, not an original capability showcase.

## Execution and substitution

Completed 2026-10-13 via GitHub connectors and GitHub hosted runners. The baseline used Python 3.13, the instructor virtual environment/dependencies, and the exact `pytest --cov=src --verbose` command. It substituted a public hosted-runner workflow for Codespaces, with authorization. **No Codespace or VS Code session was used**. Instructor teaching recap text is generic and its interface claims do not describe this execution. No external secrets, paid compute, or new accounts were introduced.

## Evidence

| Stage | Commit / run | Verified result |
| --- | --- | --- |
| Unchanged sample baseline | `6af4761225ab6ff1406e6f033e89e51574e6ce59`; [run 38394487001](https://github.com/Khemology/skills-test-with-actions/actions/runs/38394487001) | 4 passed; 62% rounded coverage; 16 statements, 6 missed |
| Reenabled incorrect instructor test | `c5048af97cac74939938833f8d61a6542fad669a`; [coverage 38394905647](https://github.com/Khemology/skills-test-with-actions/actions/runs/38394905647), [matrix 38394905787](https://github.com/Khemology/skills-test-with-actions/actions/runs/38394905787) | Actual assertion `55 == 89` failed; 1 failed / 4 passed; Python 3.9, 3.10, 3.11 tests failed |
| Corrected expectation | `87f73e97d7d330d5aafbc78ecf314027be188ed5`; [coverage 38395188946](https://github.com/Khemology/skills-test-with-actions/actions/runs/38395188946), [matrix 38395189055](https://github.com/Khemology/skills-test-with-actions/actions/runs/38395189055) | 5 passed; all matrix jobs passed; exact 87.5% coverage still failed 90% threshold |
| Added negative-input tests | `8fb28fab6a4b20aab8831df290816274975f1f5f`; [coverage 38395871682](https://github.com/Khemology/skills-test-with-actions/actions/runs/38395871682), [matrix 38395871713](https://github.com/Khemology/skills-test-with-actions/actions/runs/38395871713) | 7 passed; 100% statement coverage (16 statements, 0 missed); threshold step and all Python 3.9/3.10/3.11 jobs passed |

The sample recurrence starts F0=0 and F1=1, so F10=55 and F11=89. The implementation was correct; the disabled test expectation was incorrect. The remaining uncovered statements raised ValueError for negative circle radius and negative Fibonacci index; the instructor manual tests now exercise both.

Actual job logs were read for baseline, assertion failure, threshold failure, and final coverage success. The [coverage bot comment](https://github.com/Khemology/skills-test-with-actions/pull/3#issuecomment-6145212308) updated from 87.5% to 100%.

## Merge gate and completion

The supervising agent independently saved and observed the `Protect main` ruleset through GitHub UI: Active, targets default branch and `main`, no bypass, required `python-coverage` from GitHub Actions. While coverage failed, its fresh PR view displayed the required failed check and disabled Merge pull request button. This browser observation was performed by the supervising agent; the learner worker did not operate Chrome or change settings.

After final green checks, [PR #3](https://github.com/Khemology/skills-test-with-actions/pull/3) merged with expected head `8fb28fab6a4b20aab8831df290816274975f1f5f`, merge commit `4b93b30fa26c915de277299fc8a22ec27117ffb3`. The supervising agent independently verified final logs, matrix results, and merge.

[Teaching issue #1](https://github.com/Khemology/skills-test-with-actions/issues/1) is closed as completed. [Instructor finish comment](https://github.com/Khemology/skills-test-with-actions/issues/1#issuecomment-6145325685) confirms exercise completion.

## Limits and next step

This demonstrates real CI, matrix testing, two distinct failure causes, diagnosed recovery, coverage reporting, and a required-check merge gate on synthetic instructor code. 100% statement coverage does not prove all behavior is correct or constitute AI/production validation. Codespaces use and independent human peer review were not demonstrated. The extra baseline workflow is path-filtered to its own file.

Next: [Review pull requests](https://github.com/skills/review-pull-requests), in a separate attributed exercise repository.
