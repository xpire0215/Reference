## If there is a libpackage.pc in /opt/package/lib/pkgconfig, add it to PKG_CONFIG_PATH
>> export PKG_CONFIG_PATH=/opt/package/lib/pkgconfig

### Test is it success
>> pkg-config --libs package

