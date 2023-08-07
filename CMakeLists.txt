cmake_minimum_required(VERSION 3.0.0)
project(googleurl VERSION 0.1.0)

set (CMAKE_CXX_STANDARD 17)

# set(ABSL_PROPAGATE_CXX_STD ON)

# add_subdirectory(third_party/abseil-cpp)

set(SRCS 
  base/debug/crash_logging.cc
  base/strings/string_piece.cc
  base/strings/string_util.cc
  base/strings/string_util_constants.cc
  base/strings/utf_string_conversion_utils.cc
  base/strings/utf_string_conversions.cc

  url/gurl.cc
  url/third_party/mozilla/url_parse.cc
  url/url_canon.cc
  url/url_canon_etc.cc
  url/url_canon_filesystemurl.cc
  url/url_canon_fileurl.cc
  url/url_canon_host.cc
  url/url_canon_internal.cc
  url/url_canon_internal.h
  url/url_canon_internal_file.h
  url/url_canon_ip.cc
  url/url_canon_mailtourl.cc
  url/url_canon_path.cc
  url/url_canon_pathurl.cc
  url/url_canon_query.cc
  url/url_canon_relative.cc
  url/url_canon_stdstring.cc
  url/url_canon_stdurl.cc
  url/url_constants.cc
  url/url_parse_file.cc
  url/url_parse_internal.h
  url/url_util.cc
  url/url_util_internal.h

  url/url_idna_ascii_only.cc

)

set(HEADERS
  base/compiler_specific.h
  base/containers/checked_iterators.h
  base/containers/contains.h
  base/containers/contiguous_iterator.h
  base/containers/span.h
  base/containers/util.h
  base/cxx17_backports.h
  base/cxx20_to_address.h
  base/debug/crash_logging.h
  base/debug/leak_annotations.h
  base/functional/identity.h
  base/functional/invoke.h
  base/functional/not_fn.h
  base/memory/raw_ptr.h
  base/no_destructor.h
  base/ranges/algorithm.h
  base/ranges/functional.h
  base/ranges/ranges.h
  base/stl_util.h
  base/template_util.h
  base/strings/char_traits.h
  base/strings/string_piece_forward.h
  base/strings/string_piece.h
  base/strings/string_util.h
  base/strings/string_util_internal.h
  base/strings/string_number_conversions.h
  base/strings/utf_string_conversions.h
  base/strings/utf_string_conversion_utils.h
)

add_library(${PROJECT_NAME} ${HEADERS} ${SRCS})

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

