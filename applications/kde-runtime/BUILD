
  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

  if in_depends $MODULE qca2; then
    OPTS+=" -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2 -DQCA2_INCLUDE_DIR=/usr/include/Qca-qt4/QtCrypto/QtCrypto"
  fi &&

  if in_depends $MODULE samba ; then 
    OPTS+=" -DSAMBA_INCLUDE_DIR=/usr/include/samba-4.0"
  fi &&

  OPTS+=" -DBUILD_kglobalaccel=0  -DBUILD_kuiserver=0 -DBUILD_khelpcenter=0 -DBUILD_doc=0 -DWITH_QNtrack=0 -DWITH_NepomukCore=0 " &&

  default_cmake_build &&

 # This used to be installed by kdelibs4 but will be over written by 
 # kdebase4-runtime causing a conflict. So lets just move it here from 
 # kdelibs4 and be done with it.

  install -m0755 $SCRIPT_DIRECTORY/kde4 /usr/bin/
