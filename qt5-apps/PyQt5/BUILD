OPTS+=" --no-timestamp \
        --assume-shared \
        --confirm-license \
        --qmake=/usr/lib/qt5/bin/qmake" &&

if module_installed qscintilla2; then
  OPTS+=" --qsci-api"
fi &&

python configure.py -w $OPTS -j${MAKES} &&
find -name 'Makefile' | xargs sed -i 's|-Wl,-rpath,/usr/lib||g;s|-Wl,-rpath,.* ||g' &&
default_make &&

# Now the Python-3 stuff
if in_depends $MODULE Python-3; then
  python3 configure.py -w $OPTS -j${MAKES} &&
  find -name 'Makefile' | xargs sed -i 's|-Wl,-rpath,/usr/lib||g;s|-Wl,-rpath,.* ||g' &&
  default_make
fi
