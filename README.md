Retrieves a Cloudify environment's data using name/labels or both, into a file and/or an output.

# Environment Variables

This Action uses the Cloudify Profile environment variables described in the official
Cloudify documentation (see [More Information](#more-information) below).

# Inputs

(Certain commonly-used inputs are documented in our official website; see [More Information](#more-information) below)

# Outputs

| Name | Description
|------|------------
| `environment-data` | The environment's data, as described in the official Cloudify documentation (see below)

If `outputs-file` is specified, then the environment's data is also written into that file.

*Note* the result will be an array of environments and it could have more than one entry if environments have the same name/labels

# Example

```yaml
jobs:
  test_job:
    steps:
      - name: Get Environment Data using name and labels
        uses: cloudify-cosmo/environment-data-using-labels-action@v1.3
        with:
          environment-name: "my-environment"
          labels: some_label:label_value,yet_another_label:some_value
          outputs-file: env-data.json
```

# More Information

Refer to [Cloudify CI/CD Integration](https://docs.cloudify.co/latest/working_with/integration/) for additional information about
Cloudify's integration with CI/CD tools.
