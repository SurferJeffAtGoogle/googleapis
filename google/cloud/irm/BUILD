load("//google/api/build_defs:producer.bzl", "api_service", "api_validation_test", "api_publish", "api_discovery", "api_doc", "api_cli")

api_service(
    name = "irm",
    configs = ["irm.yaml"],
    configs_override = [
        "prod-cloud.yaml",
        "authentication.yaml",
    ],
    documentation_deps = glob(["doc/*.md"]),
    gen_apiary_config = False,
    visibility = [
        "//java/com/google/cloud/stackdriver:internal",
        "//production/incident_response_management:internal",
    ],
    deps = [
        "//google/cloud/irm/v1alpha2:incidents",
        "//google/cloud/irm/v1alpha2:incidents_service",
    ],
)

api_validation_test(
    name = "irm",
    include_inception_validation = True,
    warning_as_error = True,
)

api_publish(
    name = "irm-public-proto",
    srcs = [
        "//google/cloud/irm/v1alpha2:incidents",
        "//google/cloud/irm/v1alpha2:incidents_service",
    ],
    api_service = "irm",
    api_version_filter = "v1alpha2",
    visibility_labels = ["INCIDENTS_TRUSTED_TESTER"],
)

api_discovery(
    name = "irm",
    schema = "GOOGLE_REST",
    version = "v1alpha2",
    visibility = ["//cloud/console/web/signals/common/api:__pkg__"],
    visibility_labels = ["INCIDENTS_TRUSTED_TESTER"],
)

api_service(
    name = "irm-internal",
    configs = ["irm.yaml"],
    configs_override = ["prod-internal.yaml"],
    gen_apiary_config = False,
    visibility = [
        "//java/com/google/cloud/stackdriver:internal",
        "//production/incident_response_management:internal",
    ],
    deps = [
        "//google/cloud/irm/v1alpha2:incidents",
        "//google/cloud/irm/v1alpha2:incidents_service",
    ],
)

api_service(
    name = "staging-irm-cloud",
    configs = ["irm.yaml"],
    configs_override = [
        "staging-cloud.yaml",
        "authentication.yaml",
    ],
    gen_apiary_config = False,
    visibility = [
        "//java/com/google/cloud/stackdriver:internal",
        "//production/incident_response_management:internal",
    ],
    deps = [
        "//google/cloud/irm/v1alpha2:incidents",
        "//google/cloud/irm/v1alpha2:incidents_service",
    ],
)

api_validation_test(
    name = "staging-irm-cloud",
    include_inception_validation = True,
    warning_as_error = True,
)

api_discovery(
    name = "staging-irm-cloud",
    schema = "GOOGLE_REST",
    version = "v1alpha2",
    visibility = ["//cloud/console/web/signals/common/api:__pkg__"],
    visibility_labels = ["INCIDENTS_TRUSTED_TESTER"],
)

api_service(
    name = "staging-irm-internal",
    configs = ["irm.yaml"],
    configs_override = ["staging-internal.yaml"],
    gen_apiary_config = False,
    visibility = [
        "//java/com/google/cloud/stackdriver:internal",
        "//production/incident_response_management:internal",
    ],
    deps = [
        "//google/cloud/irm/v1alpha2:incidents",
        "//google/cloud/irm/v1alpha2:incidents_service",
    ],
)

api_validation_test(
    name = "staging-irm-internal",
    include_inception_validation = True,
    warning_as_error = True,
)

api_service(
    name = "dev-irm-cloud",
    configs = ["irm.yaml"],
    configs_override = [
        "dev-cloud.yaml",
        "authentication.yaml",
    ],
    gen_apiary_config = False,
    visibility = [
        "//java/com/google/cloud/stackdriver:internal",
        "//production/incident_response_management:internal",
    ],
    deps = [
        "//google/cloud/irm/v1alpha2:incidents",
        "//google/cloud/irm/v1alpha2:incidents_service",
    ],
)

api_validation_test(
    name = "dev-irm-cloud",
    warning_as_error = True,
)

api_discovery(
    name = "dev-irm-cloud",
    schema = "GOOGLE_REST",
    version = "v1alpha2",
    visibility = ["//cloud/console/web/signals/common/api:__pkg__"],
    visibility_labels = ["INCIDENTS_TRUSTED_TESTER"],
)

api_service(
    name = "dev-irm-internal",
    configs = ["irm.yaml"],
    configs_override = ["dev-internal.yaml"],
    gen_apiary_config = False,
    visibility = [
        "//java/com/google/cloud/stackdriver:internal",
        "//production/incident_response_management:internal",
    ],
    deps = [
        "//google/cloud/irm/v1alpha2:incidents",
        "//google/cloud/irm/v1alpha2:incidents_service",
    ],
)

api_validation_test(
    name = "dev-irm-internal",
    warning_as_error = True,
)

### Rules for generating API reference docs
#
# Rules API Preview, using production service
#
#   To build this API:
#   % cd <BUILD directory>
#   % blaze build :cli-alpha-irm-api-preview
#   % apido cli-alpha-irm-api-preview \
#     --devsite_piper_content_root=googledata/devsite/site-cloud devsite update

api_doc(
    name = "irm",
    api_category = "CLOUD_API",
    project_root_path = "incident-response/alpha-irm-api-preview",
    relative_reference_doc_path = "api",
    tool_flags = [
        # Cloud Platform > ... > Stackdriver > IRM
        "--buganizerId=508707",
        "--enableApiExplorer='True'",
        "--documentTypes='RPC,REST'",
        "--expandFieldSegInHttpRequest='False'",
    ],
)

api_cli(
    name = "cli-alpha-irm-api-preview",
    api_service = "irm",
)
