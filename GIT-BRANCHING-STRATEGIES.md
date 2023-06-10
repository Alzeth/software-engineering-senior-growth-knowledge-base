## Trunk/Mainline based flow / Release Flow / One Flow
Branch is created for a release, but only release engineers commit to the release branches. They may also cherry-pick individual commits from the mainline to the release branch if there is a desire to do so, for example in case of a bugfix. This branching model requires a lot of discipline, because a faulty commit almost instantly affects other developers. To maintain the mainline in a constantly healthy state, automatic pre-commit verifications and code reviews are frequently used. The state of the mainline codebase is generally monitored by a dedicated machine.

<img src="https://github.com/alexanderteplov/computer-science/wiki/ci-cd-cd-and-git/images/TrunkBased_flow.png" />

##Feature Branch Workflow
The core idea behind the Feature Branch Workflow is that all feature development should take place in a dedicated branch instead of the main branch. This encapsulation makes it easy for multiple developers to work on a particular feature without disturbing the main codebase.

The Git Feature Branch Workflow is a composable workflow that can be leveraged by other high-level Git workflows.

<img src="https://github.com/alexanderteplov/computer-science/wiki/ci-cd-cd-and-git/images/FeatureBranch_flow.svg" />

## Git Flow
It assigns very specific roles to different branches and defines how and when they should interact. In addition to feature branches, it uses individual branches for preparing, maintaining, and recording releases.

It contains Feature Branch flow.

<img src="https://github.com/alexanderteplov/computer-science/wiki/ci-cd-cd-and-git/images/Git_flow.svg" />

## GitHub flow
In reaction to Git flow a simpler alternative was detailed, called GitHub flow. This flow has only feature branches and a master branch. Anything in the master branch is deployable, so to work on something new, create a descriptively named branch. When it's ready, you create a merge or pull request. After someone else has reviewed and signed off on the feature, it deployed, got feedback, and merged into master.

It contains Feature Branch flow.

<img src="https://github.com/alexanderteplov/computer-science/wiki/ci-cd-cd-and-git/images/GitHub_flow.svg" />

## GitLab flow
The GitLab flow suggests creating environment branches like staging and production. When someone wants to deploy to staging they create a merge request from the master branch to the pre-production branch. And going live with code happens by merging the staging branch into the production branch. This workflow, where commits only flow downstream, ensures that everything has been tested on all environments.

<img src="https://github.com/alexanderteplov/computer-science/wiki/ci-cd-cd-and-git/images/GitLab_flow.svg" />

## Forking Workflow
The Forking Workflow is fundamentally different than other popular Git workflows. Instead of using a single server-side repository to act as the “central” codebase, it gives every developer their own server-side repository. The Forking Workflow is most often seen in public open source projects.

A developer 'forks' an 'official' server-side repository. This creates their own server-side copy.
The new server-side copy is cloned to their local system.
A Git remote path for the 'official' repository is added to the local clone.
A new local feature branch is created.
The developer makes changes on the new branch.
New commits are created for the changes.
The branch gets pushed to the developer's own server-side copy.
The developer opens a pull request from the new branch to the 'official' repository.
The pull request gets approved for merge and is merged into the original server-side repository
