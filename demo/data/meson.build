desktop_file = i18n.merge_file(
  input: 'org.gnome.Adwaita1.Demo.desktop.in',
  output: 'org.gnome.Adwaita1.Demo.desktop',
  type: 'desktop',
  po_dir: '../../po',
  install: true,
  install_dir: datadir / 'applications'
)

desktop_utils = find_program('desktop-file-validate', required: false)
if desktop_utils.found()
  test('Validate desktop file', desktop_utils,
    args: [desktop_file],
    suite: ['demo'],
  )
endif

today = 'unknown'
python3 = find_program('python3', 'python', required: false)
if python3.found()
  r = run_command(python3, '-c',
    'import datetime, os; e = os.environ.get("SOURCE_DATE_EPOCH"); print((datetime.datetime.fromtimestamp(int(e), tz=datetime.timezone.utc) if e else datetime.datetime.now(tz=datetime.timezone.utc)).strftime("%Y-%m-%d"))',
    check: false)
  if r.returncode() == 0
    today = r.stdout().strip()
  endif
endif

appdata_config = configuration_data()
appdata_config.set('BUILD_VERSION', meson.project_version())
appdata_config.set('BUILD_DATE', today)

appstream_file = i18n.merge_file(
  input: configure_file(
    input: 'org.gnome.Adwaita1.Demo.metainfo.xml.in.in',
    output: 'org.gnome.Adwaita1.Demo.metainfo.xml.in',
    configuration: appdata_config
  ),
  output: 'org.gnome.Adwaita1.Demo.metainfo.xml',
  po_dir: '../../po',
  install: true,
  install_dir: datadir / 'metainfo'
)

appstreamcli = find_program('appstreamcli', required: false)
if appstreamcli.found()
  test('Validate appstream file', appstreamcli,
    args: ['validate', '--no-net', '--explain', appstream_file],
    suite: ['demo'],
  )
endif

install_data(
  'org.gnome.Adwaita1.Demo.svg',
  install_dir: datadir / 'icons' / 'hicolor' / 'scalable' / 'apps'
)

install_data(
  'org.gnome.Adwaita1.Demo-symbolic.svg',
  install_dir: datadir / 'icons' / 'hicolor' / 'symbolic' / 'apps'
)
