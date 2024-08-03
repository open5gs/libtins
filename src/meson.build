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

tins_sources = files('''
    address_range.cpp
    arp.cpp
    bootp.cpp
    crypto.cpp
    detail/address_helpers.cpp
    detail/icmp_extension_helpers.cpp
    detail/pdu_helpers.cpp
    detail/sequence_number_helpers.cpp
    dhcp.cpp
    dhcpv6.cpp
    dns.cpp
    dot1q.cpp
    dot3.cpp
    eapol.cpp
    ethernetII.cpp
    handshake_capturer.cpp
    hw_address.cpp
    icmp.cpp
    icmp_extension.cpp
    icmpv6.cpp
    ip_address.cpp
    ip.cpp
    ip_reassembler.cpp
    ipsec.cpp
    ipv6_address.cpp
    ipv6.cpp
    llc.cpp
    loopback.cpp
    memory_helpers.cpp
    mpls.cpp
    network_interface.cpp
    packet_sender.cpp
    pdu.cpp
    pdu_iterator.cpp
    pdu_option.cpp
    pppoe.cpp
    radiotap.cpp
    rawpdu.cpp
    rsn_information.cpp
    sll.cpp
    snap.cpp
    stp.cpp
    tcp.cpp
    tcp_ip/ack_tracker.cpp
    tcp_ip/data_tracker.cpp
    tcp_ip/flow.cpp
    tcp_ip/stream.cpp
    tcp_ip/stream_follower.cpp
    tcp_ip/stream_identifier.cpp
    timestamp.cpp
    udp.cpp
    utils/checksum_utils.cpp
    utils/frequency_utils.cpp
    utils/pdu_utils.cpp
    utils/radiotap_parser.cpp
    utils/radiotap_writer.cpp
    utils/resolve_utils.cpp
    utils/routing_utils.cpp
    vxlan.cpp
'''.split())

libtins = library('tins',
    sources : tins_sources,
    version : libtins_version,
    include_directories : libtins_includes,
    install : true)

libtins_dep = declare_dependency(
    link_with : libtins,
    include_directories : libtins_includes)
