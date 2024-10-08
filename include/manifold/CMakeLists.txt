# Copyright 2024 The Manifold Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

set(MANIFOLD_PUBLIC_HDRS
  common.h
  iters.h
  manifold.h
  optional_assert.h
  parallel.h
  polygon.h
  vec_view.h
  )

set(MANIFOLD_C_BINDING_HDRS
  manifoldc.h
  types.h
  )
list(APPEND MANIFOLD_PUBLIC_HDRS ${MANIFOLD_C_BINDING_HDRS})

if (MANIFOLD_CROSS_SECTION)
  list(APPEND MANIFOLD_PUBLIC_HDRS cross_section.h)
endif()

if (MANIFOLD_EXPORT)
  list(APPEND MANIFOLD_PUBLIC_HDRS meshIO.h)
endif()

install(FILES ${MANIFOLD_PUBLIC_HDRS}
  DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/manifold
  )


# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
