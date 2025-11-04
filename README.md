# Ubuntainium
An idea forged from the frustration of outdated repos and the people who created Obtainium for Android

**Obtainium for Ubuntu** — Update GitHub apps *outside* of `apt`.

No PPAs. No stale repos. No 8-year-old packages.

# THE IDEA
The idea came by mistake and sheer ignorance on my part. I was debugging a lengthy bash script I had written to automate some server installs. It was 2 or 3am, I was tired but on a roll (we've all been there). Well, at some point I quit searching Ubuntu's official repositories, unable to find up-to-date versions of packages needed for my project. When I was finished I had a bunch of packages sourced directly from the developers' sites or their official gitlab/github repos. When I went to validate my work for errors with my AI homie (Sup Bro), he informed me that I had goofed (I tried to add them as apt repos). Although I did some damn good research, and found all the right packages with versions needed directly from the source, these were not true repositories in a linux OS sense and would never work the way we need them to work in a deployed setting (automatic updates, package management). I knew better but, no shame in my game. I exclusively use [Graphene OS](https://github.com/GrapheneOS) for cell phones. If it doesn't have [Graphene](https://github.com/GrapheneOS) on it I don't use it. I do not like google, or apple, samsung, any of them. This means I use [F-Droid](https://github.com/f-droid) and source my packages directly. One of the downsides of directly sourcing APKs is that you don't get updates like you would with an app store. However, there is the Android app [Obtainium](https://github.com/ImranR98/Obtainium) which is made to fill that gap and they do it very well. [Check out their project](https://github.com/ImranR98/Obtainium). I wondered if there was a project that did that for linux. Apparently I wasn't alone. There were a lot of people who were aware of Obtainium and wanted that for their linux machines. So here we are! 

**Project Goals**
Stay as close to native tooling as we can. Implement trong validation using file hashing. I want it to "feel" right. If you are used to using apt to install packages then this should feel the same. Create a modern GUI at some point. Snap is trash. I want to do something I feel should have been done a long time ago. debian packaging built in. It's 2025 and we're downloading and fiddling with tools off a website build in 1998 to create deb files. No more reading lengthy install instructions, have this do it for you, install it, and give you automatic updates on major releases. Since it will be building the deb packages when we intall them I want to give users an opion to anonymously submit these debian pakcages to the appropriate repos. I haven't decided but I might create a repository that this automatically submits to.  Version rollback via a local cache. If an update broke the network stack, a few clicks and you can get it back. I know personally, official repositories have screwed me a bunch of times. You know for a fact that your dependencies are good but because this is all coummunity led, repos are huge, people aren't able to update packages, sometimes in many years. Once you've gone down the dependency rabbit hole because you ran apt update* and it wrecked everything, you'll never forget. 

*This was the command that kick started the project* 
curl -fsSL get.ubuntainium.sh | bash
ubuntainium add github-project user/github-project deb "github-project_*amd64\\.deb" \
  "sudo dpkg -i {{file}} || sudo apt install -f -y"
ubuntainium



sudo apt upgrade            → updates Ubuntu
ubuntainium update          → updates (ALL) WindTerm, Notesnook, myfavgit-project, etc.
ubuntainium update <package>→ updates One package
ubuntainium --offline       → updates from local cache (ISO)
ubuntainium add git-proj    → auto-tracks latest .deb
ubuntainium remove          → (runs sudo apt purge)
ubuntainium back            → roll back to previous version.
ubuntainium list            → shows all tracked apps
