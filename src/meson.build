pkgdatadir = join_paths(get_option('datadir'), meson.project_name())
gnome = import('gnome')

src_res = gnome.compile_resources('com.github.johnfactotum.Foliate.src',
  'com.github.johnfactotum.Foliate.src.gresource.xml',
  gresource_bundle: true,
  install: true,
  install_dir: pkgdatadir,
)

bin_conf = configuration_data()
bin_conf.set('GJS', find_program('gjs').path())
bin_conf.set('PACKAGE_VERSION', meson.project_version())
bin_conf.set('PACKAGE_NAME', meson.project_name())
bin_conf.set('prefix', get_option('prefix'))
bin_conf.set('libdir', join_paths(get_option('prefix'), get_option('libdir')))
bin_conf.set('datadir', join_paths(get_option('prefix'), get_option('datadir')))

configure_file(
  input: 'com.github.johnfactotum.Foliate.in',
  output: 'com.github.johnfactotum.Foliate',
  configuration: bin_conf,
  install: true,
  install_dir: get_option('bindir')
)

run_target('run',
  command: join_paths(meson.build_root(), 'src', 'com.github.johnfactotum.Foliate'),
  depends: [
    src_res,
  ]
)

install_subdir('assets',
  install_dir: pkgdatadir
)
