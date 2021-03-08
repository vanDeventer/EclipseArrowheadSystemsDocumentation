# EclipseArrowheadSystemsDocumentation
Documentation of Systems used within the Eclipse Arrowhead framework is based on the framework's [documentation model](https://arrowhead.eu/eclipse-arrowhead/this-is-it/documentation-model/).
This documentation allows other persons to understand what the systems do and how they interface to each other.

The issues (that I have personally) with this model is that there are no hyperlinks connecting these documents (so after the first one, I am too lazy to bother checking the other documents), and that it is not clear what is the latest version and how it differs from the previous one (i.e., version control).

But going to markdown and git hub

The example used to develop this documentation is based on the reviewed documentation of the mandatory core systems (v 4.3).
It can be found on the ownCloud with path Arrowhead_Tools > WP3 Arrowhead Framework > Task 3.1 > Work > Roadmap > 4.3_preparation > Documentation_review and specifically the [Services registry](https://atmospheres.research.ltu.se/owncloud/index.php/apps/files/?dir=/Arrowhead_Tools/WP3%20Arrowhead%20Framework/Task%203.1/Work/Roadmap/4.3_preparation/Documentation_review/Arrowhead%20Service%20Registry%20Documentation_JD&fileid=1941349)

The issues (that I have personally) with this model is that there are no hyperlinks connecting these documents (so after the first one, I am too lazy to bother checking the other documents), and that it is not clear what is the latest version and how it differs from the previous one (i.e., version control).

But going to markdown and GitHub, we can see another extreme with monolithic documentation such as found for the core systems:
[Contents](https://github.com/arrowhead-f/core-java-spring#table-of-contents)
- [Authorization](https://github.com/arrowhead-f/core-java-spring#authorization)
- [Service Registry](https://github.com/arrowhead-f/core-java-spring#service-registry)
- [Orchestrator](https://github.com/arrowhead-f/core-java-spring#orchestrator)
- [Certificate Authority](https://github.com/arrowhead-f/core-java-spring#certificate-authority)
- [Gate Keeper](https://github.com/arrowhead-f/core-java-spring#gatekeeper)
- [Event Handler](https://github.com/arrowhead-f/core-java-spring#event-handler)
- [Certificates](https://github.com/arrowhead-f/core-java-spring#certificates)



## Arrowhead Framework systems
- [ROS](/ROS)
- [OPC-UA](/OPCUA)
- [Z-Wave](/ZWave)

## Contributing to this repository
To contribute to this repository, you will have to fork it and in the *develop* branch make suggestions for changes via a pull request.

Prior to any work, please, make sure that you have the latest version of the documentation on your computer by pulling (or fetch & merge) from the source repository e.g.

```
git pull upstream origin develop
```
where *upstream* refers to (done only once):
```
git remote add upstream git@github.com:vanDeventer/EclipseArrowheadSystemsDocumentation.git
```
To verify your remote repositories, you can type
```
git remote -v
```