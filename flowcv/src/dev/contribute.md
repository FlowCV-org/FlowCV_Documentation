# Becoming A Contributor

A few guidelines to be aware if you would like to become a contributor.

In general we are trying to follow the [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html) except in the case of third-party libraries that may not be using the same coding style in which case you should adopt their code style if changes are needed.

The rule for what should be an "Internal" node versus a "Plugin" is based on a few factors:

### Internal

---
* Functionality based purely on OpenCV built-in functions
* No third party libraries (other than OpenCV or the few included within the FlowCV SDK)

### External

---
* Uses third-party libraries or other external code
* Requires platform independent functionality
* Has functionality that would benefit greatly from easy updatability (in other words easy to swap out plugin for updates instead of re-building entire application)

Another note on plugins is that if the plugin requires additional external dependencies to build then consider whether it will be better to make the plugin its own separate plugin project like for example when supporting specific hardware like the RealSense 3D camera plugin.

Once you're ready to start contributing go ahead and fork the repo.

check the currently open issues for bugs or feature request you are interested in working on.

create a branch for your work.

when ready make a pull request to the master branch.

make sure your pull request pass all of the CI tests, fix any issues as needed.

check for reviewer comments and provide feedback or changes based on reviewers comments

and that's pretty much it.

I appreciate any help you can provide and look forward to your contributions!

Feel free to email if you have any questions: richard@flowcv.org
