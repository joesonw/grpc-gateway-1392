package(default_visibility = ["//visibility:public"])

load("@bazel_gazelle//:def.bzl", "gazelle")

gazelle(
    prefix = "github.com/dstreamcloud/quiz",
    name = "gazelle",
    command = "fix",
    args = [
        "-build_file_name",
        "BUILD,BUILD.bazel",
    ],
)
