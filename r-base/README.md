
# Enter Help

Your are here right now. You can get here by simply running:

```
docker run inwt/[<image>]
```

# Main-function in package or folder

Expects either a package with an exported function 'main', or a script in the
working directory called 'main.R'. A package is always favored. If neither is
found the help is displayed.

```
docker run -v $(pwd):/app/ inwt/[<image>] [main|]
```

# R CMD CHECK

Run `R CMD check` on a package by:

```
docker run -v $(pwd):/app/ inwt/[<image>] check
```

This command assumes that the package root is your current working directory.
You can also do

```
docker run -v <path-to-package>:/app/ inwt/[<image>] check
```

# TEST

Runs tests in a package:

```
docker run -v $(pwd):/app/ inwt/[<image>] test
```

# Notes on Docker-Commands

Options:

- v: stands for volume: '`-v <host-dir>:<container-dir>:ro`' means we make available
  `<host-dir>` as read only directory to the container. Inside the container you
  find the contents at `<container-dir>`. In the usage examples above we mount
  $(pwd) (current working directory) to /app/ (working directory inside the
  container).
- to be continued...

# Notes on Docker-Files

- To be continued

# Contribute

You can edit this help at https://github.com/INWTlab/r-docker. So do not
complain, improve it instead. Compile this file using:

```
Rscript -e 'knitr::pandoc("README.md", format = "plain")'
```
