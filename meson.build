# Copyright (C) 2019 by Sukchan Lee <acetcom@gmail.com>

# This file is part of Open5GS.

# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.

project('libtins', 'c', 'cpp',
    version : '4.3',
    license : 'BSD-2-clause',
    meson_version : '>= 0.43.0',
    default_options : [
        'prefix=/usr',
    ],
)

libtins_version = meson.project_version()

cc = meson.get_compiler('c')
host_system = host_machine.system()

# Compiler flags
if cc.get_id() == 'gcc' or cc.get_id() == 'clang'
    possible_cc_flags = [
        '-Werror',

        '-Wno-deprecated-declarations',
    ]
else
    possible_cc_flags = []
endif

add_project_arguments(
    cc.get_supported_arguments(possible_cc_flags),
    language : 'c')

add_project_arguments(
    cc.get_supported_arguments(possible_cc_flags),
    language : 'cpp')

libtins_includes = include_directories('''
    include
'''.split())

subdir('include/tins')
subdir('src')
