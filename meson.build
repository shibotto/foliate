project('com.github.johnfactotum.Foliate',
        version: '1.2.1',
  meson_version: '>= 0.50.0',
)

i18n = import('i18n')


subdir('data')
subdir('src')
subdir('po')

meson.add_install_script('build-aux/meson/postinstall.py')
