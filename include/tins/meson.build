# Copyright (C) 2019-2024 by Sukchan Lee <acetcom@gmail.com>

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
#

libtins_conf = configuration_data()

# GCC built-in swap
if cc.links('''#include <stdint.h>

               int main() {
                   uint16_t u16 = __builtin_bswap16(0x9812U);
                   uint32_t u32 = __builtin_bswap32(0x9812ad81U);
                   uint64_t u64 = __builtin_bswap64(0x9812ad81f61a890dU);
                   return (u16 > 0 && u32 > 0 && u64 > 0) ? 0 : 1;
               }''', name : 'gcc built-in swap call')
    libtins_conf.set('TINS_HAVE_GCC_BUILTIN_SWAP', 1)
endif

# Version of the source code
version_arr = libtins_version.split('.')
libtins_conf.set('TINS_VERSION_MAJOR', version_arr[0].to_int())
libtins_conf.set('TINS_VERSION_MINOR', version_arr[1].to_int())
if version_arr.length() > 2
  libtins_conf.set('TINS_VERSION_PATCH', version_arr[2].to_int())
else
  libtins_conf.set('TINS_VERSION_PATCH', '0')
endif

configure_file(output : 'config.h',
               configuration : libtins_conf)
