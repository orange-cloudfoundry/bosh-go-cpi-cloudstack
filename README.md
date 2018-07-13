<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [BOSH Release for bosh-go-cpi-cloudstack](#bosh-release-for-bosh-go-cpi-cloudstack)
- [CI/CD](#cd-ci)

<!-- markdown-toc end -->



# BOSH Release for bosh-go-cpi-cloudstack

Work in progress : do not use yet


# CI/CD

To create and publish a new version of the release, create and push a branch named ```release-[0-9]+\.[0-9]+\.[0-9]+``` where X.X.X will be the new version
of the release.


For each commit in the branch, the pipeline will :
- upload blobs to public S3 using creds found in pipeline protected variables
- create a final release with a build increment, eg: ```bosh-go-cpi-cloudstack-15.0.0-4.yml```
- push updated index and release yaml in repository
- tag repository with current branch X.X.X version
- upload bosh-release tarball to artifactory (creds from pipeline protected variables)


