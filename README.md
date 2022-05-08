[![EO principles respected here](https://www.elegantobjects.org/badge.svg)](https://www.elegantobjects.org)
[![DevOps By Rultor.com](http://www.rultor.com/b/yegor256/xsline)](http://www.rultor.com/p/yegor256/xsline)
[![We recommend IntelliJ IDEA](https://www.elegantobjects.org/intellij-idea.svg)](https://www.jetbrains.com/idea/)

[![mvn](https://github.com/yegor256/xsline/actions/workflows/mvn.yml/badge.svg)](https://github.com/yegor256/xsline/actions/workflows/mvn.yml)
[![PDD status](http://www.0pdd.com/svg?name=yegor256/xsline)](http://www.0pdd.com/p?name=yegor256/xsline)
[![Maintainability](https://api.codeclimate.com/v1/badges/742bde48ea6fabdba1ce/maintainability)](https://codeclimate.com/github/yegor256/xsline/maintainability)
[![Maven Central](https://img.shields.io/maven-central/v/com.yegor256/xsline.svg)](https://maven-badges.herokuapp.com/maven-central/com.yegor256/xsline)

[![codecov](https://codecov.io/gh/yegor256/xsline/branch/master/graph/badge.svg)](https://codecov.io/gh/yegor256/xsline)
[![Hits-of-Code](https://hitsofcode.com/github/yegor256/xsline)](https://hitsofcode.com/view/github/yegor256/xsline)
![Lines of code](https://img.shields.io/tokei/lines/github/yegor256/xsline)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/yegor256/xsline/blob/master/LICENSE.txt)

It's a chain of XSL transformations in Java.

You add this to your `pom.xml`:

```xml
<dependency>
  <groupId>com.yegor256</groupId>
  <artifactId>xsline</artifactId>
</dependency>
```

Use it like this:

```java
import com.jcabi.xml.XML;
import com.jcabi.xml.XMLDocument;
import com.jcabi.xml.XSLDocument;
import com.yegor256.xsline.Shift;
import com.yegor256.xsline.StXSL;
import com.yegor256.xsline.TrDefault;
import com.yegor256.xsline.Train;
import com.yegor256.xsline.Xsline;
import java.io.File;

Train<Shift> train = new TrDefault()
  .with(new StXSL(new XSLDocument(new File("first.xsl"))))
  .with(new StXSL(new XSLDocument(new File("second.xsl"))));
XML input = new XMLDocument("<hello/>");
XML output = new Xsline(train).pass(input);
```

This will transform your `input` XML document through two XSL stylesheets.

## How to Contribute

Fork repository, make changes, send us a [pull request](https://www.yegor256.com/2014/04/15/github-guidelines.html).
We will review your changes and apply them to the `master` branch shortly,
provided they don't violate our quality standards. To avoid frustration,
before sending us your pull request please run full Maven build:

```bash
$ mvn clean install -Pqulice
```

You will need Maven 3.3+ and Java 8+.
