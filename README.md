<!-- note marker start -->
**NOTE**: This repo contains only the documentation for the private BoltsOps Pro repo code.
Original file: https://github.com/boltopspro/amazon-linux-extras/blob/master/README.md
The docs are publish so they are available for interested customers.
For access to the source code, you must be a paying BoltOps Pro subscriber.
If are interested, you can contact us at contact@boltops.com or https://www.boltops.com

<!-- note marker end -->

# Configset: amazon-linux-extras

![CodeBuild](https://codebuild.us-west-2.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiNDJHVHdCTEh1dnBwME0yYmszOXh6OExTOGpVTzY0cGI1aG1oVVk4V1RwS0ljZDRoMFVBWUswMjNETXJ4b3IreTJhV1BZUnl1TEVUajFNeXlMbjF5WEtRPSIsIml2UGFyYW1ldGVyU3BlYyI6IjV4ZTJjMWMyakZuK3JlOTQiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=master)

[![BoltOps Badge](https://img.boltops.com/boltops/badges/boltops-badge.png)](https://www.boltops.com)

This configset installs and enables the amazon-linux-extras repo.

## What are lono configsets?

Lono configsets allow CloudFormation [cfn-init](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-init.html) [configsets](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-init.html) that are typically embedded in the template to be reusable.  More info: [Lono Configsets docs](https://lono.cloud/docs/configsets/).

## Usage

Use `configset` to enable the configset for the blueprint.  Example:

configs/demo/configsets/base.rb:

```ruby
configset("amazon-linux-extras", resource: "Instance")
```

This adds the configset to the `resource` with the logical id `Instance` in your CloudFormation template.  The configset is added to the [Resources[].Metadata.AWS::CloudFormation::Init](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-init.html) attribute of the `Instance` resource.

Here's an example adding to a `LaunchConfig` resource:

```ruby
configset("amazon-linux-extras", resource: "LaunchConfig")
```

Here's an example adding to a `LaunchTemplate` resource:

```ruby
configset("amazon-linux-extras", resource: "LaunchTemplate")
```
