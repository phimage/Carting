<p align="center">
<img src=".github/Logo.png" width="480" max-width="90%" alt="Carting" />
</p>

<p align="center">
	<a href="https://travis-ci.org/artemnovichkov/Carting">
        <img src="https://travis-ci.org/artemnovichkov/Carting.svg?branch=master" />
    <img src="https://img.shields.io/badge/homebrew-compatible-brightgreen.svg?style=flat" alt="Make" />
  <a href="https://swift.org/package-manager">
    <img src="https://img.shields.io/badge/spm-compatible-brightgreen.svg?style=flat" alt="Swift Package Manager" />
  </a>
  <a href="https://github.com/JohnSundell/Marathon">
    <img src="https://img.shields.io/badge/marathon-compatible-brightgreen.svg?style=flat" alt="Swift Package Manager" />
  </a>
</p>

Do you use [Carthage](https://github.com/Carthage/Carthage)? Are you feel tired of adding special script and the paths to frameworks (point 4, 5 and 6 in [Getting Started guide](https://github.com/Carthage/Carthage#getting-started)) manually? Me too. Carting does it for you. It scans Carthage folder and linked frameworks, gets framework names and updates the script.

<p align="center">
<img src=".github/carting.png" max-width="90%" alt="Carting usage" />
</p>

## Using

Run `carting update` in project folder. That's all.

By default Carting searches a script named `Carthage`, but you can set a name of your script via command line arguments:

```
$ carting update -s MyBestScript
```

If there is no script with the name, Carting will add a new one.

**🚨Note**: be sure to have no uncommitted changes in project file to prevent project parsing errors 😱.
<img src="error.png" alt="Project parsing error" />

Run `carting help` to see available commands:

```bash
Usage: carting [command] [options]
  update:
      Adds a new script with input/output file paths or updates the script named `Carthage`.
  -s, --script:
      Updates input/output file paths for the script with passed name.
  -p, --path:
      The project directory path.
  list:
      Prints Carthage frameworks list with linking description.
  help:
      Prints this message.
```

## Installing

### Homebrew (recommended):

```bash
$ brew install artemnovichkov/projects/carting
```

### Make:

```bash
$ git clone https://github.com/artemnovichkov/carting.git
$ cd Carting
$ make
```

### Swift Package Manager:

```swift
let package = Package(
    dependencies: [
        .Package(url: "https://github.com/artemnovichkov/carting", majorVersion: 1)
    ]
)
```
### Marathon

- Install [Marathon](https://github.com/johnsundell/marathon#installing).
- Add Carting to Marathon using `$ marathon add git@github.com:artemnovichkov/carting.git`. Alternatively, add `git@github.com:artemnovichkov/carting.git` to your `Marathonfile`.
- Write your script, then run it using `$ marathon run <path-to-your-script>`.

## Todo
 - [x] Add option for adding new script
 - [x] Add support of multiple targets
 - [x] Add check of linked frameworks
 - [x] Unify errors
 - [ ] Add support of tvOS and watchOS platforms
 - [ ] Check correct work with workspaces
 - [ ] Write tests

## Author

Artem Novichkov, novichkoff93@gmail.com

## License

Carting is available under the MIT license. See the LICENSE file for more info.

