load("//tools:cpplint.bzl", "cpplint")
load("//tools:apollo_package.bzl", "apollo_cc_test", "apollo_package", "apollo_plugin")

package(default_visibility = ["//visibility:public"])

filegroup(
    name = "runtime_files",
    srcs = glob([
        "conf/**",
    ]),
)

apollo_plugin(
    name = "liblane_follow_path.so",
    srcs = ["lane_follow_path.cc"],
    hdrs = ["lane_follow_path.h"],
    copts = ["-DMODULE_NAME=\\\"planning\\\""],
    description = ":plugins.xml",
    deps = [
        "//modules/common_msgs/planning_msgs:planning_cc_proto",
        "//modules/map:apollo_map",
        "//modules/planning/planning_interface_base:apollo_planning_planning_interface_base",
        "//modules/planning/tasks/lane_follow_path/proto:lane_follow_path_cc_proto",
    ],
)

apollo_package()

cpplint()
