About calchep-feedstock
=======================

Feedstock license: [BSD-3-Clause](https://github.com/conda-forge/calchep-feedstock/blob/main/LICENSE.txt)

Home: https://theory.sinp.msu.ru/~pukhov/calchep.html

Package license: GPL-3.0-or-later

Summary: Calculation of Feynman diagrams and integration over multi-particle phase space

Documentation: https://theory.sinp.msu.ru/~pukhov/calchep.html

CalcHEP is a package for automatic calculations of elementary particle decay
and collision properties in the lowest order of perturbation theory
(the tree approximation).
The main idea prescribed into the CalcHEP is to make available passing on
from the Lagrangian to the final distributions effectively with a high
level of automation.

Two variants are provided:

* `calchep` builds in "blind" (non-interactive) mode, with no X11
  dependency. The symbolic engine, numerical integration, batch operation,
  and matrix-element generation all work; only the interactive graphical
  menu is unavailable.
* `calchep-gui` adds the X11-enabled interactive `calchep-gui` front-end
  (it depends on `calchep` for the shared data and libraries).

CalcHEP is a run-in-place package installed under `$CONDA_PREFIX/share/calchep`;
activation exports the `CALCHEP` environment variable. Generating a new process
compiles C code on demand at run time, so the package depends on a C compiler
(`gcc` on Linux, `clang` on macOS) and works out of the box. (A Fortran compiler
is only needed for models that use user-defined Fortran functions; standard
process generation is C only.)

Current build status
====================


<table><tr>
    <td>GitHub Actions</td>
    <td>
      <a href="https://github.com/conda-forge/calchep-feedstock/actions/workflows/conda-build.yml">
        <img src="https://github.com/conda-forge/calchep-feedstock/actions/workflows/conda-build.yml/badge.svg?event=push&branch=main">
      </a>
    </td>
  </tr>
    
  <tr>
    <td>Azure</td>
    <td>
      <details>
        <summary>
          <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=28768&branchName=main">
            <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/calchep-feedstock?branchName=main">
          </a>
        </summary>
        <table>
          <thead><tr><th>Variant</th><th>Status</th></tr></thead>
          <tbody><tr>
              <td>osx_64</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=28768&branchName=main">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/calchep-feedstock?branchName=main&jobName=osx&configuration=osx%20osx_64_" alt="variant">
                </a>
              </td>
            </tr>
          </tbody>
        </table>
      </details>
    </td>
  </tr>
</table>

Current release info
====================

| Name | Downloads | Version | Platforms |
| --- | --- | --- | --- |
| [![Conda Recipe](https://img.shields.io/badge/recipe-calchep-green.svg)](https://anaconda.org/conda-forge/calchep) | [![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/calchep.svg)](https://anaconda.org/conda-forge/calchep) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/calchep.svg)](https://anaconda.org/conda-forge/calchep) | [![Conda Platforms](https://img.shields.io/conda/pn/conda-forge/calchep.svg)](https://anaconda.org/conda-forge/calchep) |
| [![Conda Recipe](https://img.shields.io/badge/recipe-calchep--gui-green.svg)](https://anaconda.org/conda-forge/calchep-gui) | [![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/calchep-gui.svg)](https://anaconda.org/conda-forge/calchep-gui) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/calchep-gui.svg)](https://anaconda.org/conda-forge/calchep-gui) | [![Conda Platforms](https://img.shields.io/conda/pn/conda-forge/calchep-gui.svg)](https://anaconda.org/conda-forge/calchep-gui) |

Installing calchep
==================

Installing `calchep` from the `conda-forge` channel can be achieved by adding `conda-forge` to your channels with:

```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

Once the `conda-forge` channel has been enabled, `calchep, calchep-gui` can be installed with `conda`:

```
conda install calchep calchep-gui
```

or with `mamba`:

```
mamba install calchep calchep-gui
```

It is possible to list all of the versions of `calchep` available on your platform with `conda`:

```
conda search calchep --channel conda-forge
```

or with `mamba`:

```
mamba search calchep --channel conda-forge
```

Alternatively, `mamba repoquery` may provide more information:

```
# Search all versions available on your platform:
mamba repoquery search calchep --channel conda-forge

# List packages depending on `calchep`:
mamba repoquery whoneeds calchep --channel conda-forge

# List dependencies of `calchep`:
mamba repoquery depends calchep --channel conda-forge
```


About conda-forge
=================

[![Powered by
NumFOCUS](https://img.shields.io/badge/powered%20by-NumFOCUS-orange.svg?style=flat&colorA=E1523D&colorB=007D8A)](https://numfocus.org)

conda-forge is a community-led conda channel of installable packages.
In order to provide high-quality builds, the process has been automated into the
conda-forge GitHub organization. The conda-forge organization contains one repository
for each of the installable packages. Such a repository is known as a *feedstock*.

A feedstock is made up of a conda recipe (the instructions on what and how to build
the package) and the necessary configurations for automatic building using freely
available continuous integration services. Thanks to the awesome service provided by
[Azure](https://azure.microsoft.com/en-us/services/devops/), [GitHub](https://github.com/),
[CircleCI](https://circleci.com/), [AppVeyor](https://www.appveyor.com/),
[Drone](https://cloud.drone.io/welcome), and [TravisCI](https://travis-ci.com/)
it is possible to build and upload installable packages to the
[conda-forge](https://anaconda.org/conda-forge) [anaconda.org](https://anaconda.org/)
channel for Linux, Windows and OSX respectively.

To manage the continuous integration and simplify feedstock maintenance,
[conda-smithy](https://github.com/conda-forge/conda-smithy) has been developed.
Using the ``conda-forge.yml`` within this repository, it is possible to re-render all of
this feedstock's supporting files (e.g. the CI configuration files) with ``conda smithy rerender``.

For more information, please check the [conda-forge documentation](https://conda-forge.org/docs/).

Terminology
===========

**feedstock** - the conda recipe (raw material), supporting scripts and CI configuration.

**conda-smithy** - the tool which helps orchestrate the feedstock.
                   Its primary use is in the construction of the CI ``.yml`` files
                   and simplify the management of *many* feedstocks.

**conda-forge** - the place where the feedstock and smithy live and work to
                  produce the finished article (built conda distributions)


Updating calchep-feedstock
==========================

If you would like to improve the calchep recipe or build a new
package version, please fork this repository and submit a PR. Upon submission,
your changes will be run on the appropriate platforms to give the reviewer an
opportunity to confirm that the changes result in a successful build. Once
merged, the recipe will be re-built and uploaded automatically to the
`conda-forge` channel, whereupon the built conda packages will be available for
everybody to install and use from the `conda-forge` channel.
Note that all branches in the conda-forge/calchep-feedstock are
immediately built and any created packages are uploaded, so PRs should be based
on branches in forks, and branches in the main repository should only be used to
build distinct package versions.

In order to produce a uniquely identifiable distribution:
 * If the version of a package **is not** being increased, please add or increase
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string).
 * If the version of a package **is** being increased, please remember to return
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string)
   back to 0.

Feedstock Maintainers
=====================

* [@matthewfeickert](https://github.com/matthewfeickert/)

