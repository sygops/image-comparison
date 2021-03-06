![logo-trans](https://user-images.githubusercontent.com/16310793/42029324-df117c42-7ad7-11e8-8d3e-9c6cd8822d6c.png)
[ ![Bintray](https://api.bintray.com/packages/romankh3/image-comparison/image-comparison/images/download.svg) ](https://bintray.com/romankh3/image-comparison/image-comparison/_latestVersion)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/e4fd1c61d0f147358f8c5df212256491)](https://app.codacy.com/app/romankh3/image-comparison?utm_source=github.com&utm_medium=referral&utm_content=romankh3/image-comparison&utm_campaign=Badge_Grade_Dashboard)
[![Build Status](https://travis-ci.org/romankh3/image-comparison.svg?branch=master)](https://travis-ci.org/romankh3/image-comparison) [![Coverage Status](https://coveralls.io/repos/github/romankh3/image-comparison/badge.svg?branch=master)](https://coveralls.io/github/romankh3/image-comparison?branch=master) [![BCH compliance](https://bettercodehub.com/edge/badge/romankh3/image-comparison?branch=master)](https://bettercodehub.com/) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/romankh3/image-comparison/pulls)

*   [About](#about)
*   [Requirements](#requirements)
*   [Building](#building)
*   [Relesase Notes](#relesase-notes)
*   [Usage](#usage)
    *   [Using the command-line](#using-the-command-line)
    *   [Using as a Java library](#using-as-a-java-library)
*   [Demo](#demo)
*   [License](#license)
*   [Contributing](#contributing)
*   [Code of Conduct](#code-of-conduct)
*   [Other Projects](#also-if-youre-interesting---see-my-other-repositories)

## About
The program in Java that compares any 2 images and shows the differences visually by drawing rectangles. The Usages of the `image-comparison` can be found here [Usage Image Comparison](https://github.com/romankh3/usage-image-comparison)

## Requirements
*   Implementation is using only standard core language and platform features, no 3rd party libraries and plagiarized code is permitted.
*   Pixels (with the same coordinates in two images) can be visually similar, but have different values of RGB. 2 pixels are considered to be "different" if they differ more than 10% from each other.
*   The output of the comparison is a copy of one of the images. The differences are outlined with red rectangles as shown below.
*   No third party libraries or borrowed code are in usage.

## Building
To clone and build this project, run the following commands:
 
```bash
git clone https://github.com/romankh3/image-comparison
cd image-comparison
./gradlew check jar
```

This will compile, run the tests, and create a runnable jar at `${projectDir}/build/libs`.

## Release Notes

### 2.2.0
*   Added ability to customize rectangle line width.
*   Moved the main method from Image Comparison to own class.
*   Made non-static threshold field.
*   Added Code of Conduct and Contributing pages.
*   Added Point model.

### 2.1.0
*   Added publishing to JCenter

### 2.0.2
*   fixed bug #11(finally!!)
*   fixed bug #43

### 2.0.1 
*   fixed bug #21

### 2.0
*   use as a library 

### 1.0
*The program in Java that compares any 2 images and shows the differences visually by drawing rectangles.*
*   Implementation is using only standard core language and platform features, no 3rd party libraries and plagiarized code is permitted.
*   Pixels (with the same coordinates in two images) can be visually similar, but have
different values of RGB. We are only consider 2 pixels to be "different" if the
difference between them is more than 10%.
*   The output of the comparison is a copy of one of the images image with
differences outlined with red rectangles as shown below.
*   No third party libraries and borrowed code are not using.

## Usage

### Using the command-line

This library can be used as a command-line utility to compare two images.

After building with `./gradlew jar`, you will find the runnable jar at `${projectDir}/build/libs`.

To compare two images in files `a.png` and `b.png`, for example, run:

```bash
java -jar image-comparison.jar a.png b.png
```

To save the result image in a third file, say `comparison.png`, just give that file as a third argument:

```bash
java -jar image-comparison.jar a.png b.png comparison.png
```

To show more usage details, run:

```bash
java -jar image-comparison.jar -h
```

### Using as a Java library

#### Dependency
##### Maven
```xml
<dependency>
    <groupId>com.github.romankh3</groupId>
    <artifactId>image-comparison</artifactId>
    <version>2.2.0</version>
</dependency>
```
##### Gradle
```groovy
compile 'com.github.romankh3:image-comparison:2.2.0'
```


#### To compare two images programmatically
```java
class Example {
    public static void main( String[] args ) {
        // load the images to be compared
        BufferedImage bufferedImage1 = ImageComparisonTools.readImageFromResources("image1.png");
        BufferedImage bufferedImage2 = ImageComparisonTools.readImageFromResources("image2.png");
        
        // where to save the result (leave null if you want to see the result in the UI)
        File result = new File( "result.png" );
        
        // compare them
        BufferedImage drawnDifferences = new ImageComparison( image1, image2, result ).compareImages();
    }
}
```

## Demo

Run the `./run.sh` script to run the demo.

You will get the result of comparing two images.
The images, which are using:

### Image 1

![image1](https://user-images.githubusercontent.com/16310793/28955567-52edeabe-78f0-11e7-8bb2-d435c8df23ff.png)

### Image 2

![image2](https://user-images.githubusercontent.com/16310793/28955566-52ead892-78f0-11e7-993c-847350da0bf8.png)

### Result

![result](https://user-images.githubusercontent.com/16310793/28955568-52f23e02-78f0-11e7-92c5-07602b6a0887.png)

## Contributing
Please, follow [Contributing](CONTRIBUTING.md) page.

## Code of Conduct
Please, follow [Code of Conduct](CODE_OF_CONDUCT.md) page.

## License
This project is unlicense - see the [LICENSE](LICENSE) file for details

### Thanks [@dee-y](https://github.com/dee-y) for designing this logo

### Also if you're interesting - see my other repositories
*   [Raspberry home ecosystem](https://github.com/romankh3/raspberrypi-home-ecosystem) - home ecosystem based on raspberry pi.
*   [Movie Tracking](https://github.com/romankh3/movietracking) Simple API for tracking movies with favorite actors for the specific time.
*   [Tic Tac Toe NxM](https://github.com/romankh3/tictactoe)- Own implementation. For any rectangle and any winner line count. 
