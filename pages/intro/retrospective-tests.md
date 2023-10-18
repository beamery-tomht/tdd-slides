# Retrospective tests

<v-clicks>

**If the tests are written after the code**

</v-clicks>

<v-clicks>

- You don't know they work
- More of a "milestone" in a process than a craft
- Increases chance of shortcuts in tests
- Increases chance of untested states
- Don't document all the ways an API can be used
- Don't test what is difficult to test
- Revert to E2e tests which are slow, flakey and limited

</v-clicks>

<!--
- Don't know: If you break code, it becomes yours -> therefore we don’t clean it
- Milestone: don't take them as serious...
- Shortcuts: code already works so no pressure ensure tests work
- Shortcuts: no pressure to test all the states
- Document: Some tests are very "clever" but really hard to understand
- Manual: Can't test that 500 server response, a11y test on modal?

#### EXTRA NOTES

- Can have very slow tests
  - We want one click of a button to run tests
  - Should be finished in seconds, nevermind minutes
- "Big cleanups" in hope of productivity improvements
- With quick runtime and high coverage - it's hard to introduce defects
-->
