Pull the information about the PR $1 using `gh`.

Use the following set of instructions to review the PR:

* Verify that the build/tests pass
* Read the issue title and description
* Verify that the PR links to an issue for traceability purposes
* New code
	* Understand the feature and associated requirements that are supposed to be implemented
	* Verify code implements the desired feature and that the requirements are completed
* New/Changed code
	* Check code contains tests
		* Is all the new code covered by those tests?
	* Verify the location of new/moved files
		* Are the files in the right directory?
		* Are they appropriately named?
	* Verify classes, methods, functions, parameters naming
		* Are they significant of their purpose?
		* Are they clear enough?
		* Are they respecting the naming convention?
	* Does the code respect [SOLID](https://en.wikipedia.org/wiki/SOLID)?
	* Consider that when functions/methods signature change, code may now be backward incompatible.
		* Discuss whether this is necessary
		* Backward incompatible changes should be documented
	* In a weak typed or type hinted language, are parameters and return of functions/methods typed?
	* Are there TODOs that should be completed within this review?
	* Check code for code style issues
	* Dependencies
		* Are new dependencies justified?
		* Are versions pinned appropriately?
		* Are lock files updated?
	* Is appropriate logging added?
	* Are relevant metrics/traces/alerts for monitoring purposes added?
	* Is the change size appropriate for what is implemented?
	* Are any of the design decisions taken single way doors or reversible?
* Bug fix
	* Verify that the fix is applied at the right location and will not "fix the symptoms, not the cause"

When reviewing
* Provide specific and actionable feedback
* Clearly mark nitpicks and optional comments
	* Alternatively, use an approach such as [RFC2219](https://datatracker.ietf.org/doc/html/rfc2119) where you indicate whether a change is a MUST, SHOULD, or MAY
	* I've used traffic light color emojis to communicate 🔴 MUST, 🟡 SHOULD, 🟢 MAY
	* Another emoji based option is [gitmoji](https://gitmoji.dev/)
* Assume competence
* Provide rationale or context
* Consider how comments may be interpreted
* Don't criticize the person, criticize the code
* Don't use harsh language

When reviewing, write the response to `~/repos/git/shopify-personal-notes/issues/{REPOSITORY}/{PR_NUMBER}/pr-review.md`.

Indicate the date+time the file was generated in the file header.
