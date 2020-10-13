In order to make edits to the website itself, you'll probably want to run the website locally, you must have:
- A Git client installed, to checkout the code from github.com/finos/purelegend (`master` branch); note that the `git` command must be available via command-line, as it's needed to run the `build-site.sh` script
- [Yarn installed](https://yarnpkg.com/lang/en/docs/install)

```
git clone git@github.com:<yourfork>/purelegend.git
git checkout -b feature/myProposedDocChanges
cd purelegend ; ./build-site.sh
cd website ; yarn start
```
This will automatically open a browser, pointing to http://localhost:3000, where the website will be staged; file changes will be live rendered, which speeds up the editorial workflow.

Note: The `build-site.sh` script will pull content from other Git repositories, mapping the `docs` folder into `modules/<repository-name>`; for example, all files and folders under https://gitlab.com/finosfoundation/purelegend-modeling-samples/tree/master/docs are available under the `/models/purelegend-modeling-samples` URL suffix.

Once you are satisfied with your documentation changes, commit and propose them in line with the general process described above. Specifically for documentation edits, it might look like:
* Commit your changes `git commit -am '<short description of what docs you changed/added>'`
* Push to the branch to your forked repo on GitHub `git push origin myProposedDocChanges`
* Review and test your changes in your fork
* If you're happy with the documentation changes, propose a pull request into the [FINOS Legend-PURE/Legend GitHub Repo](github.com/finos/purelegend) from your fork.

To learn more about Docusaurus see
* https://github.com/finos/purelegend/tree/master/website
* https://finosfoundation.atlassian.net/wiki/spaces/FDX/pages/844759075/Using+Docusaurus+recommended
* https://docusaurus.io

*Note* [The documentation build script](https://github.com/finos/purelegend/blob/master/build-site.sh) can be configured to pull in and include files from GitLab.com repositories housing modeling documentation into the GitHub pages / Docusaurus powered site.
