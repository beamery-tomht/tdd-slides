## False positives and problems

**We didn't verify our tests‼**

**Which can lead to...**

<v-clicks>

- Not testing part of a file
- Not testing whole files!
- Lax or invalid tests
- Hardcoded values
- Act but not assert
- Sequence insensitve
- Source code drives tests
- Coincidences
- ...etc

</v-clicks>

<!--
- File => e.g. order of components in design, nesting structure
- Skip => e.g. connected component, route config, provider, error handling
- Lax => e.g. wrong selector, not testing a11y of a modal, not testing a11y of error page
- Hardcoded => e.g. only ever testing a function with certain value
- Act => e.g. tests not waiting for async code
- Sequence => e.g. some spy called with 'a' -> 'b' -> 'a'
- Source code => importing constants into tests
- Coincidince => e.g. default values are same as test assertions
 -->
