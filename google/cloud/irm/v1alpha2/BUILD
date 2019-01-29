load("//net/proto2/compiler/stubby/cc:cc_stubby_library.bzl", "cc_stubby_library")
load("//production/incident_response_management/util/mock_rpc_generator:mock_rpc.bzl", "mock_rpc")

package(default_visibility = ["//visibility:public"])

proto_library(
    name = "incidents_service",
    srcs = ["incidents_service.proto"],
    has_services = 1,
    cc_api_version = 2,
    deps = [
        ":incidents",
        "//google/api:annotations",
        "//google/api:auditing",
        "//google/api:policy",
        "//google/api:visibility",
        "//google/protobuf:empty",
        "//google/protobuf:field_mask",
        "//google/protobuf:timestamp",
        "//storage/datapol/annotations/proto:datapol_annotations",
    ],
)

mock_rpc(
    name = "mock_incidents_service",
    srcs = [":incidents_service"],
    service_names = ["google.cloud.irm.v1alpha2.IncidentService"],
    deps = [
        ":incidents",
        ":incidents_service",
        ":incidents_service_cc_stubby",
    ],
)

cc_stubby_library(
    name = "incidents_service_cc_stubby",
    srcs = [":incidents_service"],
    stubby_versions = ["1"],
    deps = [":incidents_service"],
)

proto_library(
    name = "incidents",
    srcs = ["incidents.proto"],
    cc_api_version = 2,
    deps = [
        "//google/api:annotations",
        "//google/api:auditing",
        "//google/api:monitored_resource",
        "//google/api:policy",
        "//google/api:visibility",
        "//google/monitoring/v3:monitoring",
        "//google/protobuf:empty",
        "//google/protobuf:timestamp",
        "//storage/datapol/annotations/proto:datapol_annotations",
    ],
)

java_proto_library(
    name = "incidents_service_java_proto",
    deps = [":incidents_service"],
)

java_proto_library(
    name = "incidents_java_proto",
    deps = [":incidents"],
)
