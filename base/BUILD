# Copyright 2019 The Chromium Authors. All rights reserved.
# Use of this source code is governed by a BSD-style license that can be
# found in the LICENSE file.
load("//build_config:build_config.bzl", "build_config")
load("@rules_cc//cc:defs.bzl", "cc_library")

cc_library(
    name = "base",
    srcs = [
        "debug/crash_logging.cc",
        "strings/string_piece.cc",
        "strings/string_util.cc",
        "strings/string_util_constants.cc",
        "strings/utf_string_conversion_utils.cc",
        "strings/utf_string_conversions.cc",
    ] + select({
        "//build_config:windows_x86_64": ["strings/string_util_win.cc"],
        "//conditions:default": [],
    }),
    hdrs = [
        "compiler_specific.h",
        "containers/checked_iterators.h",
        "containers/contains.h",
        "containers/contiguous_iterator.h",
        "containers/span.h",
        "containers/util.h",
        "cxx17_backports.h",
        "cxx20_to_address.h",
        "debug/crash_logging.h",
        "debug/leak_annotations.h",
        "functional/identity.h",
        "functional/invoke.h",
        "functional/not_fn.h",
        "memory/raw_ptr.h",
        "no_destructor.h",
        "ranges/algorithm.h",
        "ranges/functional.h",
        "ranges/ranges.h",
        "stl_util.h",
        "template_util.h",
        "strings/char_traits.h",
        "strings/string_piece_forward.h",
        "strings/string_piece.h",
        "strings/string_util.h",
        "strings/string_util_internal.h",
        "strings/string_number_conversions.h",
        "strings/utf_string_conversions.h",
        "strings/utf_string_conversion_utils.h",
    ] + build_config.strings_hdrs,
    copts = build_config.default_copts,
    textual_hdrs = [
        "win/win_handle_types_list.inc",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "//base/third_party/icu",
        "//build:build_config",
        "//build:buildflag",
        "//polyfills",
        "@com_google_absl//absl/types:optional",
    ],
)
