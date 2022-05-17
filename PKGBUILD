#!/bin/bash

# Based on the original packaging by Achmad Fathoni<fathoni.id(at)gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/orgs/Archiv8/python-trio-websocket/iscussions>
# Contributor: Ross Clark <https://github.com/orgs/Archiv8/python-trio-websocket/discussions>

_langname="python"
_relname="trio-websocket"

pkgname="${_langname}-${_relname}"

pkgver=0.9.2
pkgrel=1
pkgdesc="A WebSocket library for Trio"
arch=(
    "any"
    )
url="https://pypi.org/project/${_relname}"
license=(
    "MIT"
    )
makedepends=(
    # Arch Linux Official Repositories
    "python-build"
    "python-installer"
    "python-wheel"
    "python-setuptools"
    )
depends=(
    # Arch Linux Official Repositories
    "python" 
    "python-async_generator" 
    "python-trio"
    "python-wsproto"
    )
source=(
    "https://files.pythonhosted.org/packages/source/${_relname::1}/$_relname/$_relname-$pkgver.tar.gz"
    )
sha256sums=(
    "a3d34de8fac26023eee701ed1e7bf4da9a8326b61a62934ec9e53b64970fd8fe"
    )

build() {
  cd ${srcdir}/${_relname}-${pkgver}

  python -m build --wheel --no-isolation
}

package() {
  cd ${srcdir}/${_relname}-${pkgver}

  python -m installer --destdir="$pkgdir" dist/*.whl
}
