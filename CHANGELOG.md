# Change Log

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/) and this
project adheres to [Semantic Versioning](http://semver.org/).

<a name="unreleased"></a>
## [Unreleased]


- Added flag `create_eks` to conditionally create resources (by @syst0m / @tbeijen)
- Support for AWS EKS Managed Node Groups. (by @wmorgan6796)
- Added a if check on `aws-auth` configmap when `map_roles` is empty (by @shanmugakarna)
- **Breaking:** Configure the aws-auth configmap using the terraform kubernetes providers. See Important notes below for upgrade notes (by @sdehaes)
- Removed no longer used variable `write_aws_auth_config` (by @tbeijen)
- Exit with error code when `aws-auth` configmap is unable to be updated (by @knittingdev)
- Fix deprecated interpolation-only expression (by @angelabad)
- Updated required version of AWS Provider to >= v2.38.0 for Managed Node Groups (by @wmorgan6796)
- Updated minimum version of Terraform to avoid a bug (by @dpiddockcmp)
- Fix cluster_oidc_issuer_url output from list to string (by @chewvader)
- Fix idempotency issues for node groups with no remote_access configuration (by @jeffmhastings)
- Support for AWS EKS Fargate Profiles. (by @kamirendawkins)
<a name="v11.0.0"></a>
## [v11.0.0] - 2020-03-31
FEATURES:
- Add instance tag specifications to Launch Template ([#822](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/822))
- Add support for additional volumes in launch templates and launch configurations ([#800](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/800))
- Add interpreter option to `wait_for_cluster_cmd` ([#795](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/795))

ENHANCEMENTS:
- Use `aws_partition` to build IAM policy ARNs ([#820](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/820))
- Generate `aws-auth` configmap's roles from Object. No more string concat. ([#790](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/790))
- Add timeout to default wait_for_cluster_cmd ([#791](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/791))
- automate changelog management ([#786](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/786))

BUG FIXES:
- Fix destroy failure when talking to EKS endpoint on private network ([#815](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/815))
- add ip address when manage_aws_auth is true and public_access is false ([#745](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/745))
- Add node_group direct dependency on eks_cluster ([#796](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/796))
- Do not recreate cluster when no SG given ([#798](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/798))
- Create `false` and avoid waiting forever for a non-existent cluster to respond ([#789](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/789))
- fix git-chglog template to format changelog `Type` nicely ([#803](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/803))
- fix git-chglog configuration ([#802](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/802))

CI:
- Restrict sementic PR to validate PR title only ([#804](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/804))

TESTS:
- remove unused kitchen test related stuff ([#787](https://github.com/terraform-aws-modules/terraform-aws-eks/issues/787))


[Unreleased]: https://github.com/terraform-aws-modules/terraform-aws-eks/compare/v11.0.0...HEAD
[v11.0.0]: https://github.com/terraform-aws-modules/terraform-aws-eks/compare/v10.0.0...v11.0.0
