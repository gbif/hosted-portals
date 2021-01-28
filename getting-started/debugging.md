# Debugging

> Debuggin the process of identifying and removing errors from computer hardware or software.

Every now and then you will make a change and it won't show on the website. Or worse the site might even be broken. Then you need to debug the issue. For the most part it will probably be a mistake in your YAML. Remember that YAML cares about spaces in the beginning of lines.

## Check the build server
A good start is to go to the build server and [locate your project](https://builds.gbif.org/view/Hosted%20Portals/) and select it. Once you have done that the sidebar will show you the build history. A red dot next to the latest build indicates that it failed. If you select the build attempt and go to `console output` then you will most likely see an error in the logs. It will often say something like 
```
(/srv/jekyll/_data/navigation.yml): did not find expected '-' indicator while parsing a block collection at line 3 column 1 (Psych::SyntaxError)
```
In this case it tells us what file the error is in and that there is a syntax error in the YAML.
![Jenkins console output](../assets/images/jenkins.png "Jenkins console output")


## Look at the latest changes
If you look at the commit history of your project (e.g. `https://github.com/gbif/hp-legume/commits/master`), you can see what have changed and also what commit broke the build. Commits (changes) that build successfully will have a little green tick, and failed builds will have a red cross.  You can then select the commit that caused the failure and see what was changed.

## The project builds fine, but the site isn't as I expected
These errors are more tricky to find, but again it can be a good idea to look at your latest changes in the commit history. So far we have seen these issues:
* Invalid file name. If you are expecting a webpage, then your file should probably end with with `.md`.
* You forgot the [front matter](https://jekyllrb.com/docs/front-matter/) - the area between `---`

## Ask for help
If you cannot figure out what is the cause of the error, then ask. The mailing list is a good place to do so.
