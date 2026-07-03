# Feature flags — canvas-repo-hnnu2hd_

No feature-flag call sites detected. We scan for LaunchDarkly (`ldclient.variation` / typed variants), split.io (`get_treatment`), unleash (`is_enabled`), Optimizely (`is_feature_enabled`), Flagsmith (`has_feature`), plain internal `is_enabled('key')` calls, `settings.FEATURE_*` attribute reads, and env-var-gated flags whose names start with `ENABLE_` / `DISABLE_` / `FEATURE_` / `FF_`.
