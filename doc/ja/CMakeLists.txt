# Copyright (c) 2003-2009 FlashCode <flashcode@flashtux.org>
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.
#

# quickstart
ADD_CUSTOM_COMMAND(
  OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/weechat_quickstart.ja.html
  COMMAND ${ASCIIDOC_EXECUTABLE} ARGS -a toc -a toc_title='目次' -a date=`date "+%F"` -a revision="${VERSION}" -n -o ${CMAKE_CURRENT_BINARY_DIR}/weechat_quickstart.ja.html ${CMAKE_CURRENT_SOURCE_DIR}/weechat_quickstart.ja.txt
  DEPENDS
  ${CMAKE_CURRENT_SOURCE_DIR}/weechat_quickstart.ja.txt
  COMMENT "Building weechat_quickstart.ja.html"
)
ADD_CUSTOM_TARGET(doc-quickstart-ja ALL DEPENDS ${CMAKE_CURRENT_BINARY_DIR}/weechat_quickstart.ja.html)
INSTALL(FILES ${CMAKE_CURRENT_BINARY_DIR}/weechat_quickstart.ja.html DESTINATION ${SHAREDIR}/doc/${PROJECT_NAME})