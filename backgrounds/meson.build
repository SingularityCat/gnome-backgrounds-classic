dataconf = configuration_data()
dataconf.set('BACKGROUNDDIR', backgrounddir)
dataconf.set('datadir', datadir)

adwaita_timed = configure_file(
  input: 'adwaita-pi-timed.xml.in',
  output: 'adwaita-pi-timed.xml',
  configuration: dataconf
)

backgrounds = [
  'adwaita-pi-day.jpg',
  'adwaita-pi-lock.jpg',
  'adwaita-pi-morning.jpg',
  'adwaita-pi-night.jpg',
  'Aqua.jpg',
  'Spaceflare.jpg',
  'Spaceflare-nova.jpg',
  'Spaceflare-supernova.jpg',
  'Stripes34.jpg',
  'Stripes.jpg',
  'Terraform-blue.jpg',
  'Terraform-orange.jpg',
  'UnderLit.jpg',
  'Wood-classic.jpg'
]

install_data([adwaita_timed] + backgrounds, install_dir: backgrounddir)

foreach metadata : ['gnome-backgrounds-classic.xml']
  i18n.merge_file(metadata,
    input: configure_file(
      input: metadata + '.in.in',
      output: metadata + '.in',
      configuration: dataconf
    ),
    output: metadata,
    po_dir: '../po',
    data_dirs: '..',
    install: true,
    install_dir: metadatadir
  )
endforeach
