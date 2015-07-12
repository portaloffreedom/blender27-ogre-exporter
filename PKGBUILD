# Contributor : giacomogiorgianni@gmail.com

pkgname=blender26-ogre-exporter
_name=blender2ogre
pkgver=0.6.0
pkgrel=1
pkgdesc="Blender-integrated exporter for exporting OGRE meshes"
arch=('i686' 'x86_64')
url="http://www.ogre3d.org/wiki/index.php/OGRE_Meshes_Exporter"
depends=('python' 'blender')
license=('GPL')
install=blender-ogre-exporter.install
_raw_repo='https://bitbucket.org/sinbad/ogre/raw/'
_commit='3cbd67467fab3fef44d1b32bc42ccf4fb1ccfdd0'
_folder='/Tools/Blender2.6Export/ogre_mesh_exporter/'
source=(
	"blender27.patch"
	"${_raw_repo}${_commit}${_folder}__init__.py"
	"${_raw_repo}${_commit}${_folder}global_properties.py"
	"${_raw_repo}${_commit}${_folder}log_manager.py"
        "${_raw_repo}${_commit}${_folder}main_exporter_panel.py"
        "${_raw_repo}${_commit}${_folder}material_properties.py"
        "${_raw_repo}${_commit}${_folder}mesh_exporter.py"
        "${_raw_repo}${_commit}${_folder}mesh_impl.py"
        "${_raw_repo}${_commit}${_folder}mesh_panel.py"
        "${_raw_repo}${_commit}${_folder}mesh_properties.py")


md5sums=(
	 'f21376a600b7cc71974e4491c8b3a943'
         'c40c9bfb27390072b300d73ff79a29bb'
         '90d1fa9cb43986bfc0a613f559d6a288'
         'd5983b7f711f3c39ced6f06301e7f17c'
         'a27b8613dcfd56075d77a1af2033e2f0'
         'aca54a259df690150dc10cf40ac41fb3'
         'f558c505918f137c9a86f397772f414a'
         '0cc3a248bbc28c9cc3b669f533e98823'
         'e92d34ca92da6d62f6004bc60de7bacd'
         'b2b8226b8dd8bffd0a4123345243fa4b')

_installdir='/usr/share/blender/2.75/scripts/addons/ogre_mesh_exporter/'

build() {

  #copy the file so we can apply the patch
  sed -i -e '/^not in this file__ASasðaßðæðkdfmfasf/ s@$@$@' main_exporter_panel.py
  
  patch -Np1 -i blender27.patch
}

package() {
  DESTDIR="${pkgdir}/${_installdir}"
  mkdir -p ${DESTDIR}

  install -m644 -Dt "${DESTDIR}" __init__.py
  install -m644 -Dt "${DESTDIR}" global_properties.py
  install -m644 -Dt "${DESTDIR}" log_manager.py
  install -m644 -Dt "${DESTDIR}" main_exporter_panel.py
  install -m644 -Dt "${DESTDIR}" material_properties.py
  install -m644 -Dt "${DESTDIR}" mesh_exporter.py
  install -m644 -Dt "${DESTDIR}" mesh_impl.py
  install -m644 -Dt "${DESTDIR}" mesh_panel.py
  install -m644 -Dt "${DESTDIR}" mesh_properties.py
}

