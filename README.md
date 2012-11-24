Jenkins Build Flow Plugin
=========================

This Jenkins plugin allows managing jobs orchestration using a dedicated DSL, extracting the flow logic from jobs.

## Sample Build Flow Content ##

    parallel (
      {
        guard {
            build("job1A")
        } rescue {
            build("job1B")
        }
      },
      {
        retry 3, {
            build("job2")
        }
      }
    )

See the documentation and release notes at [Build Flow Plugin](https://wiki.jenkins-ci.org/display/JENKINS/Build+Flow+Plugin) on the Jenkins Wiki for more information.

Other informations:
* Bug Tracker : [Jenkins Build Flow Component](https://issues.jenkins-ci.org/browse/JENKINS/component/16533)


