package(default_visibility = ["//tensorboard:internal"])

load("@io_bazel_rules_webtesting//web:py.bzl", "py_web_test_suite")

licenses(["notice"])

py_web_test_suite(
    name = "core_test",
    srcs = ["core_test.py"],
    browsers = ["//tensorboard/functionaltests/browsers:chromium"],
    data = [
        "//tensorboard",
    ],
    # TODO(@jart): Make this fast and not flaky.
    flaky = True,
    srcs_version = "PY2AND3",
    tags = ["manual", "webtest"],
    deps = [
        "//tensorboard/plugins/audio:audio_demo",
        "//tensorboard/plugins/scalar:scalars_demo",
        "@io_bazel_rules_webtesting//testing/web",
    ],
)

py_library(
    name = "wct_test_driver",
    srcs = ["wct_test_driver.py"],
    srcs_version = "PY2AND3",
    deps = ["@io_bazel_rules_webtesting//testing/web"],
    testonly = True,
)
