# Gradle plugin for building Elasticsearch plugins

This is a copy of the `buildSrc` folder in the original Elasticsearch sources, cloned here so we can make some changes to it and track it's progress separately of Elasticsearch's huge codebase.

## Purpose

```groovy
// TODO
```

## Usage

Create a new Elasticsearch plugin project, or convert an existing one to gradle, and in your build.gradle file put the following:

```groovy
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'io.plugind.builders.elasticsearch:gradle-plugin:0.4.0'
    }
}
apply plugin: 'elasticsearch.esplugin'

group = '....'
version = '0.1.0-es' + elasticsearch
description = """foo bar"""

esplugin {
    name 'my-es-plugin'
    version rootProject.version
    description 'foo bar'
    classname 'fully.qualified.MainPluginClass'
}
```

## Building

```bash
gradle clean build
```

## License and Copyrights

```
This software is licensed under the Apache License, version 2 ("ALv2"), quoted below.

Copyright 2009-2016 Elasticsearch <https://www.elastic.co>

Licensed under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License. You may obtain a copy of
the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations under
the License.
```
