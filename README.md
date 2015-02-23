What is Godot?
==============

Do you like waiting? Godot is for passionate thumb-twiddlers of the quantified-self-era. A Gradle plugin to help you keep track of how much time you spend waiting for builds to finish.

### Isn't that like the `--profile` option in Gradle?

`--profile` only summarizes the timing of one build, whereas Godot keeps track of
how your build duration changes over time.

How to use this
---------------

Add the following to your project's root buildscript:

```Groovy
buildScript {
  repositories {
    jcenter()
    maven {
      url "https://oss.sonatype.org/content/repositories/snapshots"
    }
  }
  dependencies {
    // ... other buildscript dependencies, e.g. the Android Gradle plugin
    classpath 'de.hannesstruss:godot:0.1-SNAPSHOT'
  }
}

apply plugin: 'de.hannesstruss.godot'
```

When the plugin is applied, it'll keep information about how long each of your
builds took. Continue working for a couple of days, then run

    ./gradlew generateGodotReport

and Godot will generate a [nice report][4] with some charts.

You may or may not want to add `godot.log` to your VCS ignores (e.g.
`.gitignore`), although as of now it is recommended. If you know a good location
to put this file in, [let me know!][5]


Credits
-------

Godot is created by [Hannes Struß][1] with help from [d3.js][2] and [dimple][3].


License
-------

    Copyright 2015 Hannes Struß

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.



 [1]: https://twitter.com/hannesstruss
 [2]: http://d3js.org/
 [3]: http://dimplejs.org/
 [4]: http://hannesstruss.github.io/godot/report.html
 [5]: http://forums.gradle.org/gradle/topics/is-it-bad-practice-for-a-plugin-to-write-to-gradle-user-home