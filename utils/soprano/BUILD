
  patch_it $SOURCE2 1 &&
  patch_it $SOURCE3 1 &&

  OPTS+=" -DRAPTOR_INCLUDE_DIR=/usr/include/raptor2" &&

  if in_depends $MODULE sun-jdk; then
    . /etc/profile.d/sun-jdk.rc
  else
    if in_depends $MODULE sun-jre; then
      . /etc/profile.d/sun-jre.rc
    fi
  fi  &&

  # build qt4 version
  . /etc/profile.d/qt4.rc  &&
  OPTS+=" -DQT5_BUILD=0" &&
  default_cmake_build &&

  # cleanup to build qt5
  devoke_installwatch &&
  mv $SOURCE_DIRECTORY/$MODULE-oosb $SOURCE_DIRECTORY/$MODULE.qt4-oosb

  . /etc/profile.d/qt5.rc &&
  OPTS+=" -DQT5_BUILD=1" &&
  default_cmake_build
