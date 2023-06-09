load("@rules_python//python:defs.bzl", "py_binary", "py_library", "py_test")

package(default_visibility = ["//visibility:public"])

licenses(["notice"])

py_library(
    name = "analysis",
    srcs = ["__init__.py"],
)

py_library(
    name = "compute_dp_sgd_privacy_lib",
    srcs = ["compute_dp_sgd_privacy_lib.py"],
    srcs_version = "PY3",
    deps = [":rdp_accountant"],
)

py_binary(
    name = "compute_dp_sgd_privacy",
    srcs = ["compute_dp_sgd_privacy.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [":compute_dp_sgd_privacy_lib"],
)

py_test(
    name = "compute_dp_sgd_privacy_test",
    size = "small",
    srcs = ["compute_dp_sgd_privacy_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [":compute_dp_sgd_privacy_lib"],
)

py_binary(
    name = "compute_noise_from_budget",
    srcs = ["compute_noise_from_budget.py"],
    deps = [":compute_noise_from_budget_lib"],
)

py_library(
    name = "compute_noise_from_budget_lib",
    srcs = ["compute_noise_from_budget_lib.py"],
    deps = [":rdp_accountant"],
)

py_test(
    name = "compute_noise_from_budget_test",
    srcs = ["compute_noise_from_budget_test.py"],
    deps = [":compute_noise_from_budget_lib"],
)

py_library(
    name = "dp_event",
    srcs = ["dp_event.py"],
    srcs_version = "PY3",
)

py_library(
    name = "dp_event_builder",
    srcs = ["dp_event_builder.py"],
    srcs_version = "PY3",
    deps = [":dp_event"],
)

py_test(
    name = "dp_event_builder_test",
    srcs = ["dp_event_builder_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":dp_event",
        ":dp_event_builder",
    ],
)

py_library(
    name = "gdp_accountant",
    srcs = ["gdp_accountant.py"],
)

py_library(
    name = "privacy_accountant",
    srcs = ["privacy_accountant.py"],
    srcs_version = "PY3",
    deps = [
        ":dp_event",
        ":dp_event_builder",
    ],
)

py_library(
    name = "privacy_accountant_test",
    srcs = ["privacy_accountant_test.py"],
    srcs_version = "PY3",
    deps = [
        ":dp_event",
        ":privacy_accountant",
    ],
)

py_library(
    name = "rdp_accountant",
    srcs = ["rdp_accountant.py"],
    srcs_version = "PY3",
    visibility = ["//visibility:public"],
)

py_test(
    name = "rdp_accountant_test",
    size = "small",
    srcs = ["rdp_accountant_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [":rdp_accountant"],
)

py_library(
    name = "rdp_privacy_accountant",
    srcs = ["rdp_privacy_accountant.py"],
    srcs_version = "PY3",
    deps = [
        ":dp_event",
        ":privacy_accountant",
    ],
)

py_test(
    name = "rdp_privacy_accountant_test",
    size = "small",
    srcs = ["rdp_privacy_accountant_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":dp_event",
        ":privacy_accountant",
        ":privacy_accountant_test",
        ":rdp_privacy_accountant",
    ],
)

py_library(
    name = "tensor_buffer",
    srcs = ["tensor_buffer.py"],
    srcs_version = "PY3",
)

py_test(
    name = "tensor_buffer_eager_test",
    size = "small",
    srcs = ["tensor_buffer_eager_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [":tensor_buffer"],
)

py_test(
    name = "tensor_buffer_graph_test",
    size = "small",
    srcs = ["tensor_buffer_graph_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [":tensor_buffer"],
)

py_library(
    name = "tree_aggregation_accountant",
    srcs = ["tree_aggregation_accountant.py"],
    srcs_version = "PY3",
)

py_test(
    name = "tree_aggregation_accountant_test",
    srcs = ["tree_aggregation_accountant_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":rdp_accountant",
        ":tree_aggregation_accountant",
    ],
)
