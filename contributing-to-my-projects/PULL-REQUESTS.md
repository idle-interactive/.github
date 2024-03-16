* Confirm your idea will be committed if the code is viable by the maintainer by contacting the maintainer in CONTRIBUTORS.md

* Please refer to our .pre-commit-config.yaml file to know what should be run before you submit a pull request to the main repository.
    * While we will likely have some checks on our end as well, keep in mind, that this is intended to save us both time and delays from async communication.
    * https://pre-commit.com/ is the project that you need to install to run the file.

* Note in the request
    * Note anything dependencies being added, such as composer libraries or other stuff
    * Note any changes to the install / deployment process

* Git branches
    * Use ONE branch for the issue or feedback id you plan to resolve
    * If it's not an existing issue or feedback id, please open one after your idea is tentatively approved in theory with final approval based on it being a good implementation/passing code review/ passing qa.

* Git commit
    * The FIRST line should be the title/topic text of the issue/feedback you are resolving
    * ONE pull request per issue or feedback id you plan to resolve
    * ONE commit per issue or feedback id you plan to resolve in the git log
    * Include the issue or feedback id you are handling with the request
    * If it is a security issue, ping the maintainer on discord to get it QA’d/reviewed ASAP to avoid it dangling for too long
    * Any config values being added sould have blocks for LOCAL, DEV, and PROD
        * Make sure your actual config file is not added to the repo.
        * Instead, you should update the config.sample file with examples.
    * If you have not commmited previously, please add yourself to the CONTRIBUTORS.md file with your psuedonym and/or real name that you wish to be credited as.
        * Right now the plan is to use the CONTRIBUTORS.md files in these projects to automatically build a list of people who contribute.
        * You may add links to your projects, blogs, etc. in the CONTRIBUTORS.md file.
        * The CONTRIBUTORS.md file under your section cannot be longer than 3 bullet points of up to 300 visible characters per point.            
        * Note that you agree to CONTRIBUTOR-AGREEMENT.md if you have not previously done so.
            * A link to this will probably get added to the CONTRIBUTORS.md file if you haven't done so already
            * "I, <psuedonym or real name>, agree as of <date> to the CONTRIBUTOR-AGREEMENT.md file in this repository as of this commit as well as future variations if I continue to submit pull requests after a change to the agreement or related licensing files such as COMMUNITY-LICENSE.md or STABLE-LICENSE.md."

* Automated changelog generation
    * We take the first line of git log as the human readable commit
    * We take the author line of the git log as the contributor responsible (based on the name/psuedonym used) and drop the e-mail data. That said, automation, if you are worried about bugs revealing the git log e-mail, just use the github one or an anonymous one.
    * We take the issue/feedback link + any other links in the gitlog as the body of the changelog
        * In other words, its <topic> + bullet points with any links referenced in the log
        * Only certain whitelisted domains (feedbase, github, project sites) will be used
    * This will probably also cover the release changelogs but may have manual cleanup when there is time
    