load("@rules_proto//proto:defs.bzl", "proto_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library")
load("@io_bazel_rules_go//proto:def.bzl", "go_proto_library")

proto_library(
    name = "api_proto",
    srcs = ["echo.proto"],
    visibility = ["//visibility:public"],
    deps = ["@go_googleapis//google/api:annotations_proto"],
)

#gazelle:go_grpc_compilers @io_bazel_rules_go//proto:go_grpc,@grpc_ecosystem_grpc_gateway//protoc-gen-grpc-gateway:go_gen_grpc_gateway
go_proto_library(
    name = "api_go_proto",
    compilers = [
        "@io_bazel_rules_go//proto:go_grpc",
        "@grpc_ecosystem_grpc_gateway//protoc-gen-grpc-gateway:go_gen_grpc_gateway",
    ],
    importpath = "example.com/grpc/api",
    proto = ":api_proto",
    visibility = ["//visibility:public"],
    deps = ["@go_googleapis//google/api:annotations_go_proto"],
)

go_library(
    name = "go_default_library",
    embed = [":api_go_proto"],
    importpath = "example.com/grpc/api",
    visibility = ["//visibility:public"],
)
