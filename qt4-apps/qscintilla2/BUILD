export PATH=$QTDIR/bin:$PATH  &&
export CXXFLAGS+=" -I../Qt4Qt5" &&
export LDFLAGS+=" -L../Qt4Qt5" &&

source /etc/profile.d/qt4.rc &&

pushd Qt4Qt5 > /dev/null
  qmake qscintilla.pro &&
  default_make  &&
popd > /dev/null &&

pushd designer-Qt4Qt5 > /dev/null &&
  qmake designer.pro INCLUDEPATH+=../Qt4Qt5 QMAKE_LIBDIR+=../Qt4Qt5 &&
  default_make &&
popd > /dev/null &&

# install the Python bindings
pushd Python > /dev/null &&
  python ./configure.py -n ../Qt4Qt5/ -o ../Qt4Qt5/ -c --qmake /usr/bin/qmake &&
  default_make &&
popd > /dev/null
