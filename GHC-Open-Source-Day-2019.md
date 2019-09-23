# Getting Ready for Open Source Day

## Table Of Contents
* [How To Get Started](#how-to-get-started)
* [Setting Up Before Open Source Day](#setting-up-before-open-source-day)
* [Some Useful Links](#some-useful-links)
* [Making A Code Change](#making-a-code-change)
* [What To Do When You Are Stuck](#what-to-do-when-you-are-stuck)
* [List Of Projects](#list-of-projects)

## How To Get Started
Welcome to Oppia! This wiki page aims to provide a quick-start guide to Oppia and guide you in making your first changes to Oppia's codebase. For a longer, more comprehensive guide to getting started, please see our [full "Getting Started" page](https://github.com/oppia/oppia/wiki/Contributing-code-to-Oppia#setting-things-up).

Some background info about the project:
* The Oppia codebase sits in Github at https://github.com/oppia. Some knowledge of Github would be useful to make changes to the repository. Take a look at the [Github guides](https://guides.github.com/activities/hello-world/) for a brief introduction to Github along with some common methods! 
* AngularJS (v1) is used for Oppia's frontend. A nice youtube video tutorial can be found [here](https://www.youtube.com/watch?v=nO1ROKMjPqI&list=PLvZkOAgBYrsS_ugyamsNpCgLSmtIXZGiz). For an outline of AngularJS, please see this [short overview](https://egghead.io/articles/new-to-angularjs-start-learning-here) with pointers to other resources. 
* If you are new to HTML, some useful tutorials are [Mozilla's guide](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML) (which includes some practice assessments), as well as [this tutorial for beginners](http://htmldog.com/guides/html/beginner/).
* Some new features will require backend work. Oppia's backend is written in Python 2.7.

## Setting Up Before Open Source Day

### Sign the CLA

Oppia is licensed under Apache v2. Please [sign the CLA](https://goo.gl/forms/AttNH80OV0) so that we can accept your contributions and redistribute the code you contribute under this license.

Once you've done this, you'll receive a confirmation email which includes some suggestions for next steps! These are completely optional, but if time permits, it might not be a bad idea to try a [starter project](https://github.com/oppia/oppia/wiki/Contributing-code-to-Oppia#finding-something-to-do) to get familiar with the codebase and development workflow.

### Create a GitHub account

To make code changes, you will require a Github account with 2 factor authentication set up.

* [Install Github](https://help.github.com/articles/set-up-git/).
* [Set up 2FA](https://help.github.com/articles/securing-your-account-with-two-factor-authentication-2fa/) on your GitHub account. This is important to prevent people from impersonating you.
  * You might need to create a [personal access token](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/) so you can log in from the command line.
* Go to your settings page (click the Settings option under the profile menu in the top right), then go to 'Notifications' and ensure that everything's as you want it.
* (Optional) Consider setting up [automatic auth](https://help.github.com/articles/caching-your-github-password-in-git/) so you don't have to type in a username and password each time you commit a change.
* (Optional) Go to the [Oppia repo](https://github.com/oppia/oppia), and click 'Watch' at the top right. Ensure that you're not 'ignoring' the repo, so that you'll be notified when someone replies to a conversation you're part of.

### Install Oppia on your machine
* Create a new, empty folder called `opensource/` in your computer's home folder. Navigate to it (`cd opensource`), then [fork and clone](https://help.github.com/articles/fork-a-repo/) the Oppia repo so that it gets downloaded into `opensource/oppia`.
* Then follow the appropriate installation instructions -- [Linux](https://github.com/oppia/oppia/wiki/Installing-Oppia-%28Linux%29), [Mac OS](https://github.com/oppia/oppia/wiki/Installing-Oppia-%28Mac-OS%29), [Windows](https://github.com/oppia/oppia/wiki/Installing-Oppia-%28Windows%29). (If you run into any problems during installation, please read [these notes](https://github.com/oppia/oppia/wiki/Issues-with-installation%3F).)

### Join the Gitter channel
* Join the GHC open source day chatroom at https://gitter.im/oppia/ghc2018 to meet other mentors and participants!

## Some useful links
_Gitter_ [GHC chatroom](https://gitter.im/oppia/ghc2018) | [General chatroom](https://gitter.im/oppia/oppia-chat)

_Oppia_ [Wiki Page](https://github.com/oppia/oppia/wiki) | [Documentation](https://oppia.github.io/#/) | [Full "Getting Started" page](https://github.com/oppia/oppia/wiki/Contributing-code-to-Oppia#setting-things-up)

_Github_ [Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) | [Guide](https://guides.github.com/activities/hello-world/)

_AngularJS_ [Tutorial](https://docs.angularjs.org/tutorial/index) | [Guide](https://docs.angularjs.org/guide)

_Python 2.7_ [Introduction](https://docs.python.org/2/library/intro.html) | [Tutorial](https://docs.python.org/2/tutorial/index.html) | [Documentation](https://docs.python.org/2/index.html)

_Bash_ [Introduction](http://cs.lmu.edu/~ray/notes/bash/)

## Making A Code Change
Our central development branch is **develop**, which should be clean and ready for release at any time. In general, all changes should be done as feature branches based off of _develop_. For a more detailed explanation on how to make a code change, please take a look at [this wiki page](https://github.com/oppia/oppia/wiki/Contributing-code-to-Oppia#instructions-for-making-a-code-change). 
In order to make a change in the repository, you can follow the steps below:

1. Sync with the _develop_ branch and create a new branch, starting from _develop_ (e.g. _your-branch-name_). The branch name should be descriptive, lowercase, and hyphen-separated. It shouldn’t start with the words _hotfix_ or _release_.
```bash
git fetch upstream
git checkout develop  
git merge upstream/develop 
git checkout -b your-branch-name
```

2. Make commit(s) to your feature branch. Each commit should be self-contained and have a descriptive commit message that helps other developers understand why the changes were made.
   * Before your code gets uploaded to GitHub, a script is automatically executed that checks the styling of all changed files and runs some front-end tests. **Run the 'push' command in command line** as the script needs access to other tools like pip.
   * If any of the tests fail, the push will be interrupted. If this happens, fix the issues that the tests tell you about and repeat the instructions above ('commit' and then 'push').

3. When your feature is ready to merge, create a pull request on Github. When you create a pull request, you will be assigned a reviewer who will take a look at your code.

4. **Address review comments until all reviewers give LGTM ('looks good to me').**
   * Resolve any merge conflicts that arise.
   * Run `bash scripts/start.sh` and play with the dev server in order to make sure that everything still works, and also to install any new dependencies that have been added since you last synced the repo.
   * WARNING: Do not make changes using the online GitHub editor -- this bypasses lint/presubmit checks, and will cause the code on GitHub to diverge from the code on your machine. Always make commits locally, and then push to GitHub.

5. Tidy up! After the PR status has changed to "Merged", delete the feature branch from both your local clone and the GitHub repository

6. Celebrate. Congratulations, you have contributed to Oppia!

## What to do when you are stuck
Oppia has a [Gitter chat room](https://gitter.im/oppia/oppia-chat) where everyone can post their questions and help each other out! The organizers and mentors will also be walking around to help with any questions. We also have a dedicated [GHC Open Source Day chatroom](https://gitter.im/oppia/ghc2018) that you can use too!

## List of Projects

For this open source day, we tried to shortlist projects that are fairly self contained, and can be completed within 3-4 hours by a group of 2-3 people. We also tried to pick those projects from our issue tracker itself so that you get an idea of what it’s like to contribute to Oppia on a regular basis. 
Each project has a brief explanation, a link to the issue tracker, the skills required, and some deliverables. We encourage you to look at the [issue tracker](https://github.com/oppia/oppia/issues) link for the project that interests you. You can comment expressing interest in that project (and mention you will be working on it for OSD). You can also gain more context and ask questions to help get a kickstart for the day. Please work in groups of 2-3 people. We also recommend everyone to try any one file within Project 8 (unit tests) before taking on larger projects, to get a feel for the codebase.
This list is not an exhaustive list of projects. If none of these projects appeal to you, you can take a look at our issue tracker and comment on the issue that interests you. (also mention that you will be working on it during the OSD event so that we are aware). 
Please tag us (**@dchen97** and **@vinitamurthi**) in any comment expressing interest in a project so that we get notified about this!
If you would like to understand the vocabulary and general structure of content in Oppia, you can take a look at this document.

***
### Project 1: Change the Style of Playthrough Buttons in Improvements Tab

**Context**

The “View Playthrough” button in our Improvements tab currently is shaped like a hexagon, which doesn’t fit the overall style of the page anymore. We need a new design and implementation for this button that better suits the broader styling of the Lesson Improvements tab.
 // TODO(vinitamurthi): Add a picture

[Issue 7334](https://github.com/oppia/oppia/issues/7334)

**Deliverables**
* Create design for new “View Playthrough” button style
* Change the styling for the “View Playthrough” button to match the new style

**Required Skills**

AngularJS, Web Development, UX Design, JavaScript

**Difficulty**

Easy 

***

### Project 2: Render Suggested Changes in Suggestion Improvement Cards

**Context**

Suggestion Improvement cards only render the latest message of the associated thread:
 
// TODO(vinitamurthi): Add the picture

To view the actual suggestion, creators must click the "Review Thread" button and then the "Review Suggestion" button from the thread modal:
 
 // TODO(vinitamurthi): Add the picture

 // TODO(vinitamurthi): Add the picture

We'd like to render the suggestion (and possibly the current version) directly on the card to minimize the indirections that creators need to step through when trying to understand what the suggested improvement requires from them.

[Issue 7156](https://github.com/oppia/oppia/issues/7156)

**Deliverables**

* Modify the Suggestion Improvement card to display the suggestion directly on the card
* (optional) Modify the Suggestion Improvement card to display the current version of the message directly on the card

**Required Skills**

AngularJS, Web Development, UX Design, JavaScript

**Difficulty**

Intermediate 

***


### Project 3: Limit questions requested to a specific amount in the question player

**Context**
The question player is a reusable element that is used anywhere we would like to show tests to the user (currently in practice sessions, and in review tests). Fetching questions from the database can be expensive so we would like to set a limit on the number of questions we request in any test. Currently users of the question player can ask for an infinite number of questions. However, we would like to limit that down to 20 questions. For that we need to add checks to the frontend controller and backend controller to limit the number of questions we can request in the question player. Both the frontend controller and the backend controller should return an error message to callers of the question player if they ask for > 20 questions.

[Issue 6928](https://github.com/oppia/oppia/issues/6928)

**Deliverables**

Throw an error in the backend controller of the question player if the number of questions requested is greater than 20.
Throw an error in the frontend API of the question player if the number of questions is > 20. 

**Required Skills**

Python

**Difficulty**

Easy

***

Project 4: "Card is too long" warning is not prominent enough, and isn't shown when the RTE is closed

Context
Whenever a card in a lesson is too long, a warning should display prominently enough that the lesson editors know to adjust this content (i.e. split up between multiple cards, shorten text, etc.). However, right now, this warning is only displayed when you open up the Rich Text Editor (RTE) for the card and this warning is buried at the bottom of the editor in a way that users do not immediately see or notice the warning. Additionally, when you close the RTE, this warning disappears altogether. 

Steps to reproduce the behavior:
Log in and create an exploration.
Type lots of text in the content card
View the blue text at the bottom of the Rich Text Editor (RTE): 




We need this warning to be redesigned such that it is more prominently displayed when users view the card outside of the RTE and inside of the RTE.

Issue #6292

Deliverables
Design the new way in which users will see the “Card too long” warning both inside and outside of the RTE.
Change the “Card too long” warning to match this new style

Required Skills
AngularJS, Web Development, UX Design, JavaScript

Difficulty
Intermediate 

Project 5: Lint check to ensure a single space after yield keyword in python and to avoid inline styling
 
Context
For a project as large as Oppia, code health is extremely important. We have a style guide that we expect new developers to read and follow, however it is equally important to have tests that enforce this style guide. That’s where our lint checks come in. Currently we have several lint checks, we would like to improve them by adding two more checks: Ensuring a single space is present after the ‘yield’ keyword in python files (#6276), and ensure that we do not have any inline styles in HTML pages. Instead we would like to have CSS classes wherever there are inline files(#6212). This project needs to add the lint check, as well as fix any parts of the code base that violate these new checks.
Issues: #6276, #6212
 
Deliverables
Remove all cases where there is more than 1 space after the yield keyword in python files
Add a lint check to enforce this
Replace all cases of inline styles with CSS classes
Add a lint check to stop allowing inline styles.
 
Required Skills
Python
 
Difficulty
Easy
 
Project 6: Convert frontend dicts to domain objects

Context
We want to represent objects in the frontend using frontend domain objects rather than raw, opaque JS dicts. For example, here are some frontend domain objects for Explorations (see the *ObjectFactory.js files): https://github.com/oppia/oppia/tree/develop/core/templates/dev/head/domain/exploration.

The aim of this issue is to convert remaining frontend objects that are still represented as dicts to actual domain objects. Ideally, for each object, a single PR should be created that updates the entire frontend to replace references to the old JS dict with the new domain object instead.

Issue #3968

Deliverables
Change “Change” (the objects in core/templates/dev/head/pages/exploration_editor/ChangeListService.js) to domain objects
Change “Link” (cf., e.g., core/templates/dev/head/components/VersionDiffVisualizationDirective.js and other graph visualizations: look for objects that have a "source" and a "target" field) to domain objects

Required Skills
JavaScript

Difficulty
Easy

Project 7: Capture screenshot in Travis e2e tests 

Context
Considering the size of the codebase, maintaining end to end tests is important to ensure that new changes don’t break our old functionality. We use protractor end to end tests to ensure all our critical flows aren’t broken. It tests every flow and performs all the tasks that a normal user would perform in order to interact with oppia. The e2e tests take time to run and usually run on Travis (or continuous build system) anytime we create/update a PR. Whenever a test fails, a user has to manually rerun the test in their system in order to see what point in the flow the test fails. Instead we would like to capture a screenshot anytime the test fails and then report that in Travis. This is so that the PR author can quickly identify the error and work on fixing it. (Useful Link)

Issue #7276

Deliverables
Capture a screenshot when the test fails and report it

Required Skills
Javascript, Protractor JS

Difficulty
Intermediate

Project 8: Resolve styling for card view on creator-dashboard 

Context
Currently, card views on our creator dashboard look like the following:


We need to adjust the styling for the cards to look like the following:


Issue #7083

Deliverables
Change the card views on the Creator Dashboard to follow the desired styling

Required Skills
AngularJS, Web Development, JavaScript

Difficulty
Easy

Project 9: Convert questionSummary dict to a frontend domain object

Context
Currently in questions-list.directive.ts, the elements in ctrl.questionSummaries are still backend dicts, which are never converted to a frontend domain object. We should convert the backend dict to a domain object and pass the domain object around instead.
Issue #6994

Deliverables
Convert the questionSummary dictionary into a frontend domain object

Required Skills
Angular JS

Difficulty
Easy

Project 10: Remove underscores in routes to improve SEO

Context
If possible underscores should be avoided within a URL. These URLs should be replaced with Hyphens if possible. The underscores make it harder for the search engine to determine site relevance to the searched.

For example, ‘oppia.org/get_started’ should be ‘oppia.org/get-started.’

In order to maintain consistency, not only should URLs be changed to this standard, but all routes in the codebase should follow this standard (e.g. ‘’’r'/preferenceshandler/profile_picture', profile.ProfilePictureHandler’’’ in main.py).

Additionally, we should ensure that all old URLs redirect to the new pages to minimize any broken links.

Issue #6772

Deliverables
Change all routes in the codebase to use hyphens (‘-’) rather than underscores (‘_’)

Required Skills
Python, JavaScript

Difficulty
Easy 
Project 11: E2E Tests
Multiple people can work on this
Context
This project is aimed to complete writing all e2e tests for functional capabilities. The general procedure to write such tests is as follows:
Try manually doing the action you are trying to test.
Get a list of smaller actions needed by the user to complete the action (like, click button X to navigate to page Y, then input "text" in component Z)
At each stage, there should be some way to assert that the smaller action has completed. (This includes waiting for a page to load, waiting for a button to become clickable, etc).
The e2e test written must perform the exact same set of smaller actions, and verify that the action is completed.
More details and guidelines for writing an e2e test can be seen in the Github issue.
Issue #6240

Deliverables
Pick up and complete any of the pending e2e tests mentioned in #6240

Required Skills
JavaScript

Difficulty
Varying difficulty 
Project 12: Refactor dicts in the frontend to use camel case key

Context
At present many dicts in frontend have underscore_cased keys which prevent explicit typing of the object as it raises tslint errors regarding the casing. All of these dicts should camel case (Example: camelCase) instead.

The following files use the underscore_case dicts and need to be refactored:
core/templates/dev/head/domain/feedback_message/FeedbackMessageSummaryObjectFactory.ts
 core/templates/dev/head/domain/feedback_thread/FeedbackThreadObjectFactory.ts
core/templates/dev/head/domain/learner_dashboard/LearnerDashboardActivityIdsObjectFactory.ts
 core/templates/dev/head/domain/skill/SkillRightsObjectFactory.ts
 core/templates/dev/head/domain/suggestion/SuggestionObjectFactory.ts
 core/templates/dev/head/domain/user/UserInfoObjectFactory.ts
 core/templates/dev/head/domain/utilities/AutogeneratedAudioLanguageObjectFactory.ts
 core/templates/dev/head/domain/exploration/AnswerStatsObjectFactory.ts
 core/templates/dev/head/services/StateTopAnswersStatsServiceSpec.ts
 core/templates/dev/head/domain/collection/CollectionRightsObjectFactory.ts
 core/templates/dev/head/domain/collection/CollectionPlaythroughObjectFactory.ts
 core/templates/dev/head/domain/statistics/PlaythroughIssueObjectFactory.ts
 core/templates/dev/head/domain/editor/undo_redo/ChangeObjectFactory.ts
 core/templates/dev/head/domain/exploration/ParamChangeObjectFactory.ts
 core/templates/dev/head/domain/exploration/ParamTypeObjectFactory.ts
 core/templates/dev/head/domain/exploration/VoiceoverObjectFactory.ts
core/templates/dev/head/domain/learner_dashboard/LearnerDashboardActivityIdsObjectFactory.ts
 core/templates/dev/head/domain/skill/SkillRightsObjectFactory.ts
 core/templates/dev/head/services/ImprovementsService.ts
 core/templates/dev/head/services/StateTopAnswersStatsServiceSpec.ts
 core/templates/dev/head/pages/exploration-editor-page/history-tab/services/version-tree.service.ts
 core/templates/dev/head/domain/topic/TopicRightsObjectFactory.ts
 core/templates/dev/head/domain/classifier/ClassifierObjectFactory.ts
 core/templates/dev/head/domain/exploration/WrittenTranslationObjectFactory.ts
 core/templates/dev/head/domain/exploration/RuleObjectFactory.ts
 core/templates/dev/head/services/ExplorationFeaturesService.ts
 core/templates/dev/head/domain/exploration/SubtitledHtmlObjectFactory.ts
 core/templates/dev/head/domain/exploration/RecordedVoiceoversObjectFactory.ts
 core/templates/dev/head/domain/topic/SubtopicPageContentsObjectFactory.ts
 core/templates/dev/head/domain/topic/SubtopicPageObjectFactory.ts
 core/templates/dev/head/domain/exploration/ParamSpecObjectFactory.ts
 core/templates/dev/head/domain/exploration/WrittenTranslationsObjectFactory.ts
 core/templates/dev/head/domain/exploration/HintObjectFactory.ts
 core/templates/dev/head/domain/statistics/LearnerActionObjectFactory.ts
 core/templates/dev/head/domain/story/StoryNodeObjectFactory.ts
 core/templates/dev/head/domain/collection/CollectionNodeObjectFactory.ts
 core/templates/dev/head/domain/exploration/AnswerGroupObjectFactory.ts
 extensions/interactions/Continue/directives/ContinueValidationService.ts
 extensions/interactions/ImageClickInput/directives/ImageClickInputValidationService.ts
 extensions/interactions/EndExploration/directives/EndExplorationValidationService.ts
 extensions/interactions/GraphInput/directives/GraphInputValidationService.t
 extensions/interactions/CodeRepl/directives/CodeReplValidationService.ts
 extensions/interactions/PencilCodeEditor/directives/PencilCodeEditorValidationService.ts
extensions/interactions/MathExpressionInput/directives/MathExpressionInputValidationService.ts
 extensions/interactions/SetInput/directives/SetInputValidationService.ts
extensions/interactions/DragAndDropSortInput/directives/DragAndDropSortInputValidationService.ts
 extensions/interactions/MusicNotesInput/directives/MusicNotesInputValidationService.ts
 extensions/interactions/NumericInput/directives/NumericInputValidationService.ts
 extensions/interactions/MultipleChoiceInput/directives/MultipleChoiceInputValidationService.ts
 extensions/interactions/LogicProof/directives/LogicProofValidationService.ts
 extensions/classifiers/SVMPredictionService.ts
 core/templates/dev/head/domain/story/StoryContentsObjectFactory.ts
 core/templates/dev/head/domain/collection/CollectionObjectFactory.ts
 core/templates/dev/head/domain/topic/StoryReferenceObjectFactory.ts
 core/templates/dev/head/components/state-editor/state-editor-properties-services/state-editor.service.ts
 core/templates/dev/head/domain/topic/TopicObjectFactory.ts
 core/templates/dev/head/domain/skill/ConceptCardObjectFactory.ts

Issue #7176

Deliverables
Change files listed above so that all dicts use camel case

Required Skills
JavaScript, Python

Difficulty
Intermediate 

Project 13: Add a lint check to ensure require(…) statements are alphabetized

Context
At Oppia, we have a style guide that we expect new developers to read and follow, however it is equally important to have tests that enforce this style guide. We use lint checks to ensure that the oppia codebase follows the style guide. In this project, we would like to add another lint check to ensure that all require(...) statements are in alphabetical order. 
Issue #6748
 
Deliverables
Remove all cases where the require statements are not alphabetized in the code base 
Add a lint check to enforce this

Required Skills
Python

Difficulty
Easy

Project 14: Enable animated GIFs in the lessons 

Context
Animated GIFs provide a powerful way of conveying information in the lessons. However, currently animated GIFs do not play in any of the lessons. In this project, we would like to enable animated GIFs in lessons. In order to test out this behavior you can: 
Create an exploration
Add an animated GIF with several frames to the content section of the exploration
Play the exploration
When the exploration is played you will notice that the GIF will not animate.
Issue #6546

Deliverables
Investigate the root cause of why the animated GIFs are not animating
Enable animated GIFs in explorations

Required Skills
HTML, CSS, Angular JS

Difficulty
Intermediate

Project 15: Disable the ‘Save and Publish’ button in the question editor when the question doesn’t have an interaction

Context
When creating a question for a skill, the creator can try to go ahead and create the question without filling any details by clicking on the ‘Save and Publish’ button. Clicking on the button causes an error, but the fact that the button is green indicates that the question can be created without any interaction being filled. This is at odds with other publish/save buttons in Oppia editors which only turn green once all errors are resolved.

Issue #6482 

Deliverables
Ensure the ‘Save and Publish’ button is enabled only after the question has an interaction in the question editor

Required Skills
Angular JS

Difficulty
Easy
Project 16: Add a tutorial for the topic editor on first visit

Context
Currently, the topic editor, accessible through the topics and skills dashboard, does not have a tutorial for first time visitors. So, this issue aims at adding that, similar to the one in exploration editor, to the topic editor.

Issue #6367

Deliverables
Create simple design doc to outline what the tutorial should look like and how users would walk through it
Implement tutorial based on this design doc

Required Skills
Python, AngularJS, Web Development, UX Design, JavaScript

Difficulty
Hard

Project 17: Make Answers Anonymous in the Statistics Tab

Context
Currently in our statistics tab, we show all answers to explorations so that creators have information on how their exploration performs. In this project, we would like to protect our learners from being identified. We'll accomplish this using k-anonymity. From Wikipedia: “A release of data is said to have the k-anonymity property if the information for each person contained in the release cannot be distinguished from at least k - 1 individuals whose information also appear in the release.”
We'd like the statistics tab to have this property to protect learners from being identified. Anonymity can give our learners confidence in playing our explorations, and would improve the overall privacy of Oppia.
As far as implementation goes, we should only show a particular answer in the stats tab when k unique learners have input that same answer. Additionally, we should only show such answers if there are at least j of them in total. The Github issue has more guidelines on how to go about the implementation.
Issue #6007

Deliverables
Write a design doc on the approach that will be taken to enforce this
Complete the implementation to enable k-anonymity

Required Skills
Angular JS, Python

Difficulty
Hard