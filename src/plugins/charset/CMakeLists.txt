#
# Copyright (C) 2003-2014 Sébastien Helleu <flashcode@flashtux.org>
#
# This file is part of WeeChat, the extensible chat client.
#
# WeeChat is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3 of the License, or
# (at your option) any later version.
#
# WeeChat is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with WeeChat.  If not, see <http://www.gnu.org/licenses/>.
#

ADD_LIBRARY(charset MODULE charset.c)
SET_TARGET_PROPERTIES(charset PROPERTIES PREFIX "")

IF(ICONV_FOUND)
  INCLUDE_DIRECTORIES(${ICONV_INCLUDE_PATH})
  IF(ICONV_LIBRARY)
    TARGET_LINK_LIBRARIES(charset ${ICONV_LIBRARY})
  ELSE(ICONV_LIBRARY)
    TARGET_LINK_LIBRARIES(charset)
  ENDIF(ICONV_LIBRARY)
ENDIF(ICONV_FOUND)

INSTALL(TARGETS charset LIBRARY DESTINATION ${LIBDIR}/plugins)
