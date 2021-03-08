# EclipseArrowheadSystemsDocumentation
Documentation of Systems used within the Eclipse Arrowhead framework is based on the framework's [documentation model](https://arrowhead.eu/eclipse-arrowhead/this-is-it/documentation-model/).
This documentation allows other persons to understand what the systems do and how they interface to each other.

The example used to develop this documentation is based on the reviewed documentation of the mandatory core systems (v 4.3).
It can be found on the ownCloud with path Arrowhead_Tools > WP3 Arrowhead Framework > Task 3.1 > Work > Roadmap > 4.3_preparation > Documentation_review and specifically the [Services registry](https://atmospheres.research.ltu.se/owncloud/index.php/apps/files/?dir=/Arrowhead_Tools/WP3%20Arrowhead%20Framework/Task%203.1/Work/Roadmap/4.3_preparation/Documentation_review/Arrowhead%20Service%20Registry%20Documentation_JD&fileid=1941349)

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