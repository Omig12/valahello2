# Project name and programming language
project('com.github.omig12.valahello2', 'vala', 'c')

# Create a new executable, list the file we want to compile, list the dependencies we need, and install
# executable(
#     meson.project_name(),
#     'src/Application.vala',
#     dependencies: [
#         dependency('gtk+-3.0')
#     ],
#     install: true
# )

# Install our .desktop file so that the Application Menu will see it
# install_data(
#     join_paths('data', meson.project_name() + '.desktop'),
#     install_dir: join_paths(get_option('datadir'), 'applications')
# )

# Install out .appdata.xml file so the AppCentr will see it
# install_data(
#         join_paths('data', meson.project_name() + '.appdata.xml'),
#         install_dir: join_paths(get_option('datadir'), 'metainfo')
# )

# Include translations module
il8n = import('i18n')

# Set our global translation domain
add_global_arguments('-DGETTEXT_PACKAGE="@0@"'.format (meson.project_name()),language: 'c')

#Translate and install our .desktop file
il8n.merge_file(
    input: join_paths('data', meson.project_name() + '.desktop.in'),
    output: meson.project_name() + '.desktop',
    po_dir: join_paths(meson.source_root(), 'po'),
    type: 'desktop',
    install: true,
    install_dir: join_paths(get_option('datadir'), 'applications')
)

# Translate and install out .appdata file
il8n.merge_file(
    input: join_paths('data', meson.project_name() + '.appdata.xml.in'),
    output: meson.project_name() + '.appdata.xml',
    po_dir: join_paths(meson.source_root(), 'po'),
    install: true,
    install_dir: join_paths(get_option('datadir'), 'metainfo')
)

subdir('po')
