# Seal Security Patches

**Announcement: Seal Security's public artifact server enters open-beta! Join the beta here: [https://app.sealsecurity.io](https://app.sealsecurity.io/?ref=seal-community). For feedback or feature request you can shoot an email to [info@seal.security](mailto:info@seal.security)**

This is a centralized repository of standalone security patches that mitigate open-source libraries' vulnerabilities.
The patches help quickly deal with the security risk in cases where the operational risk of a full version update is too significant.

Developers everywhere constantly face scenarios where patching a security issue by performing a full version update is too time-consuming and/or impractical. Such as:

- Breaking changes or deprecated features in the newer library version
- Vulnerable transitive dependency
- Vulnerable unmaintained library
- Legacy codebase
- Mission-critical application
- Vulnerable third-party Container/VM images
- LLM-produced code (due to training cut-off)

Whatever the scenario, unpatched vulnerabilities should be dealt with. At Seal Security, we help users achieve that while accounting for the operational risk with the help of the standalone security patch approach. 

To verify that a patch has no side effects and mitigates the security risk, the original library's test suite is executed, and additional tests are backported/created and included in the patch file.

⭐ **To follow new patch releases, please leave a star.** ⭐

## How to Use the Repository

**tl;dr** - git apply the relevant patches in the vulnerable library folder, rebuild, and replace the vulnerable library in your application.

<details>
<summary>npm example</summary>

How to patch `CVE-2022-46175` in the `json5` library version `0.5.1`:

1. **Find the patch you need**: The patches are arranged by ecosystem, namespace (if applicable), package name, and finally, package version. In our example, navigate to `npm->json5->0.5.1`. Each directory contains at least one SP (security patch) sub-directory. We will add additional SPs when new vulnerabilities are discovered and patched or if there's an issue with an existing SP.
2. **Pull the original version**: Get the source code for the version that needs fixing. In our example: https://github.com/json5/json5/tree/v0.5.1
3. **Download the patch(es)**: Move the patch files to the sources folder.
4. **Apply the patch(es)**: Apply all the patches within an SP directory in their order. If there are multiple SPs, apply all the patches in SP1, then SP2, etc. (edited)

    ```bash
    git apply 0001-CVE-2022-46175.patch
    ```

5. **Build the package**: Instructions to build the package are ecosystem-specific and sometimes library-specific. Follow the relevant project documentation for this step. In our example:
    ```bash
    npm pack
    ```
6.  **Replace the vulnerable library**: Instructions to replace the vulnerable package are ecosystem-specific. In our example:
    ```bash
    npm install <path_to_package_tgz>
    ```
</details>

## How to Contribute

We're excited to hear success stories, discuss possible integrations, receive requests for new patches, and review new security patches. Please open issues, pull requests, or contact us at: [contribute@seal.security](mailto:contribute@seal.security).

**IMPORTANT: DO NOT OPEN PUBLIC ISSUES FOR SECURITY FIXES BYPASS. PLEASE REFER TO THE SECURITY POLICY.**

## Seal's Artifact Server

Seal Security is hosting a public artifact server that allows users to apply security patches seamlessly as part of their SDLC with simple integrations.

The artifact server and the patches are free to use, with some integrations and features only being available to paying customers.

You can access the artifact server here: [https://app.sealsecurity.io](https://app.sealsecurity.io/?ref=seal-community).

## About Seal Security

![Seal Security Logo](docs/assets/logo.png)

Seal Security is an early-stage cybersecurity startup committed to simplifying vulnerability remediation for developers and application security practitioners. For more details, visit our [website](https://seal.security).

## Legal Considerations

The patches are published under an MIT license (refer to the LICENSE file). However, please keep in mind that you still need the code of the underlying library and must comply with its license.

## Patch List

<details>
<summary>Show</summary>

Library | Version | Vulnerability
--|--|--
@babel/traverse|7.17.3|CVE-2023-45133
@babel/traverse|7.18.8|CVE-2023-45133
@babel/traverse|7.21.5|CVE-2023-45133
@babel/traverse|7.22.4|CVE-2023-45133
@babel/traverse|7.9.0|CVE-2023-45133
@fastify/multipart|7.3.0|CVE-2023-25576
@okta/oidc-middleware|4.5.1|CVE-2022-3145
ImageMagick|6.9.10.68-6.el7_9|CVE-2022-44267
ImageMagick-devel|6.9.10.68-6.el7_9|CVE-2022-44267
Snappier|1.1.0|CVE-2023-28638
acorn|5.7.3|GHSA-6chw-6frg-f759
ansi-regex|3.0.0|CVE-2021-3807
ansi-regex|4.1.0|CVE-2021-3807
ansi-regex|5.0.0|CVE-2021-3807
async|2.6.3|CVE-2021-43138
async-es|2.6.3|CVE-2021-43138
axios|0.21.1|CVE-2021-3749
axios|0.21.4|CVE-2023-45857
axios|0.26.1|CVE-2023-45857
axios|0.27.2|CVE-2023-45857
axios|1.3.6|CVE-2023-45857
axios|1.4.0|CVE-2023-45857
axios|1.5.0|CVE-2023-45857
axios|1.5.1|CVE-2023-45857
bson|1.0.9|CVE-2019-2391
bson|1.0.9|CVE-2020-7610
c-ares|1.10.0-3.el7|CVE-2022-4904
com.fasterxml.jackson.core:jackson-databind|2.13.1|CVE-2020-36518
com.fasterxml.jackson.core:jackson-databind|2.13.1|CVE-2022-42003
com.fasterxml.jackson.core:jackson-databind|2.13.1|CVE-2022-42004
com.fasterxml.jackson.core:jackson-databind|2.13.2.2|CVE-2022-42003
com.fasterxml.jackson.core:jackson-databind|2.13.2.2|CVE-2022-42004
com.nimbusds:nimbus-jose-jwt|9.23|CVE-2023-1370
cryptography|39.0.1|CVE-2023-2975
cryptography|39.0.1|CVE-2023-3446
cryptography|39.0.1|CVE-2023-3817
cryptography|39.0.1|CVE-2023-4807
cryptography|39.0.1|CVE-2023-49083
cryptography|39.0.1|CVE-2023-50782
cryptography|39.0.1|CVE-2023-5363
cryptography|39.0.1|CVE-2023-5678
cryptography|39.0.1|CVE-2023-6129
cryptography|39.0.1|CVE-2023-6237
cryptography|39.0.1|CVE-2024-0727
cryptography|39.0.1|CVE-2024-26130
cryptography|41.0.2|CVE-2023-2975
cryptography|41.0.2|CVE-2023-3446
cryptography|41.0.2|CVE-2023-3817
cryptography|41.0.2|CVE-2023-4807
cryptography|41.0.2|CVE-2023-49083
cryptography|41.0.2|CVE-2023-50782
cryptography|41.0.2|CVE-2023-5363
cryptography|41.0.2|CVE-2023-5678
cryptography|41.0.2|CVE-2023-6129
cryptography|41.0.2|CVE-2023-6237
cryptography|41.0.2|CVE-2024-0727
cryptography|41.0.2|CVE-2024-26130
cryptography|41.0.3|CVE-2023-4807
cryptography|41.0.3|CVE-2023-49083
cryptography|41.0.3|CVE-2023-50782
cryptography|41.0.3|CVE-2023-5363
cryptography|41.0.3|CVE-2023-5678
cryptography|41.0.3|CVE-2023-6129
cryptography|41.0.3|CVE-2023-6237
cryptography|41.0.3|CVE-2024-0727
cryptography|41.0.3|CVE-2024-26130
cryptography|41.0.4|CVE-2023-49083
cryptography|41.0.4|CVE-2023-50782
cryptography|41.0.4|CVE-2023-5363
cryptography|41.0.4|CVE-2023-5678
cryptography|41.0.4|CVE-2023-6129
cryptography|41.0.4|CVE-2023-6237
cryptography|41.0.4|CVE-2024-0727
cryptography|41.0.4|CVE-2024-26130
cryptography|41.0.5|CVE-2023-49083
cryptography|41.0.5|CVE-2023-50782
cryptography|41.0.5|CVE-2023-5678
cryptography|41.0.5|CVE-2023-6129
cryptography|41.0.5|CVE-2023-6237
cryptography|41.0.5|CVE-2024-0727
cryptography|41.0.5|CVE-2024-26130
cryptography|41.0.7|CVE-2023-50782
cryptography|41.0.7|CVE-2023-5678
cryptography|41.0.7|CVE-2023-6129
cryptography|41.0.7|CVE-2023-6237
cryptography|41.0.7|CVE-2024-0727
cryptography|41.0.7|CVE-2024-26130
cups-libs|1:2.2.6-51.el8_8.2|CVE-2023-32324
cups-libs|1:2.2.6-51.el8_8.2|CVE-2023-34241
cups-libs|1:2.2.6-51.el8_8.2|CVE-2023-4504
cups-libs|1:2.3.3op2-16.el9|CVE-2023-32324
cups-libs|1:2.3.3op2-16.el9|CVE-2023-32360
cups-libs|1:2.3.3op2-16.el9|CVE-2023-34241
cups-libs|1:2.3.3op2-16.el9_2.1|CVE-2023-32324
cups-libs|1:2.3.3op2-16.el9_2.1|CVE-2023-34241
d3-color|1.4.0|GHSA-36jr-mh4h-2g58
d3-color|1.4.1|GHSA-36jr-mh4h-2g58
d3-color|2.0.0|GHSA-36jr-mh4h-2g58
decode-uri-component|0.2.0|CVE-2022-38900
deep-extend|0.4.2|CVE-2018-3750
django|3.2.18|CVE-2023-31047
django|3.2.18|CVE-2023-36053
dmidecode|1:3.2-5.el7|CVE-2023-30630
dottie|2.0.2|CVE-2023-26132
ejs|2.7.4|CVE-2022-29078
ejs|2.7.4|SNYK-JS-EJS-1049328
ejs|3.1.6|CVE-2022-29078
fast-json-patch|2.2.1|CVE-2021-4279
fast-xml-parser|3.19.0|CVE-2023-26920
follow-redirects|1.15.2|CVE-2023-26159
follow-redirects|1.15.3|CVE-2023-26159
getobject|0.1.0|CVE-2020-28282
github.com/Masterminds/goutils|1.1.0|CVE-2021-4238
glob-parent|3.1.0|CVE-2020-28469
global-modules-path|2.3.1|CVE-2022-21191
got|6.7.1|CVE-2022-33987
got|9.6.0|CVE-2022-33987
growl|1.9.2|CVE-2017-16042
grub2|1:2.02-0.87.el7.centos.6|CVE-2022-2601
grub2|1:2.02-0.87.el7.centos.6|CVE-2022-3775
grub2-common|1:2.02-0.87.el7.centos.6|CVE-2022-2601
grub2-common|1:2.02-0.87.el7.centos.6|CVE-2022-3775
grub2-pc|1:2.02-0.87.el7.centos.6|CVE-2022-2601
grub2-pc|1:2.02-0.87.el7.centos.6|CVE-2022-3775
grub2-pc-modules|1:2.02-0.87.el7.centos.6|CVE-2022-2601
grub2-pc-modules|1:2.02-0.87.el7.centos.6|CVE-2022-3775
grub2-tools|1:2.02-0.87.el7.centos.6|CVE-2022-2601
grub2-tools|1:2.02-0.87.el7.centos.6|CVE-2022-3775
grub2-tools-extra|1:2.02-0.87.el7.centos.6|CVE-2022-2601
grub2-tools-extra|1:2.02-0.87.el7.centos.6|CVE-2022-3775
grub2-tools-minimal|1:2.02-0.87.el7.centos.6|CVE-2022-2601
grub2-tools-minimal|1:2.02-0.87.el7.centos.6|CVE-2022-3775
handlebars|4.1.2|CVE-2019-20920
hoek|2.16.3|CVE-2018-3728
hoek|2.16.3|CVE-2020-36604
http-cache-semantics|4.1.0|CVE-2022-25881
https-proxy-agent|1.0.0|CVE-2018-3739
ini|1.3.5|CVE-2020-7788
ip|1.1.5|CVE-2023-42282
ip|1.1.6|CVE-2023-42282
ip|1.1.7|CVE-2023-42282
ip|1.1.8|CVE-2023-42282
ip|2.0.0|CVE-2023-42282
jinja2|2.8|CVE-2016-10745
joblib|0.14.1|CVE-2022-21797
js-yaml|3.10.0|SNYK-JS-JSYAML-174129
js-yaml|3.11.0|SNYK-JS-JSYAML-174129
js-yaml|3.12.0|SNYK-JS-JSYAML-174129
js-yaml|3.12.1|SNYK-JS-JSYAML-174129
js-yaml|3.12.2|SNYK-JS-JSYAML-174129
js-yaml|3.13.0|SNYK-JS-JSYAML-174129
js-yaml|3.7.0|SNYK-JS-JSYAML-174129
js-yaml|3.8.0|SNYK-JS-JSYAML-174129
js-yaml|3.8.1|SNYK-JS-JSYAML-174129
js-yaml|3.8.2|SNYK-JS-JSYAML-174129
js-yaml|3.8.3|SNYK-JS-JSYAML-174129
js-yaml|3.8.4|SNYK-JS-JSYAML-174129
js-yaml|3.9.0|SNYK-JS-JSYAML-174129
js-yaml|3.9.1|SNYK-JS-JSYAML-174129
json-schema|0.2.3|CVE-2021-3918
json5|0.5.1|CVE-2022-46175
json5|1.0.1|CVE-2022-46175
json5|2.0.0|CVE-2022-46175
json5|2.0.1|CVE-2022-46175
json5|2.1.0|CVE-2022-46175
json5|2.1.1|CVE-2022-46175
json5|2.1.2|CVE-2022-46175
json5|2.1.3|CVE-2022-46175
json5|2.2.0|CVE-2022-46175
json5|2.2.1|CVE-2022-46175
langchain|0.0.279|CVE-2024-28088
langchain|0.0.281|CVE-2024-28088
langchain|0.0.287|CVE-2024-28088
langchain|0.0.288|CVE-2024-28088
langchain|0.0.289|CVE-2024-28088
langchain|0.0.290|CVE-2024-28088
langchain|0.0.297|CVE-2024-28088
langchain|0.0.298|CVE-2024-28088
langchain|0.0.299|CVE-2024-28088
langchain|0.0.300|CVE-2024-28088
langchain|0.0.301|CVE-2024-28088
langchain|0.0.302|CVE-2024-28088
langchain|0.0.303|CVE-2024-28088
langchain-core|0.1.23|CVE-2024-28088
libXpm|3.5.12-1.el7|CVE-2022-44617
libXpm|3.5.12-1.el7|CVE-2022-46285
libXpm|3.5.12-2.el7_9|CVE-2022-44617
libXpm|3.5.12-2.el7_9|CVE-2022-46285
libseccomp|2.3.1-4.el7|CVE-2019-9893
libtiff|4.0.3-35.el7|CVE-2022-3970
libtiff-devel|4.0.3-35.el7|CVE-2022-3970
libtiff-static|4.0.3-35.el7|CVE-2022-3970
libtiff-tools|4.0.3-35.el7|CVE-2022-3970
libxml2|2.9.1-6.el7_9.6|CVE-2022-40303
libxml2|2.9.1-6.el7_9.6|CVE-2022-40304
libxml2-devel|2.9.1-6.el7_9.6|CVE-2022-40303
libxml2-devel|2.9.1-6.el7_9.6|CVE-2022-40304
libxml2-python|2.9.1-6.el7_9.6|CVE-2022-40303
libxml2-python|2.9.1-6.el7_9.6|CVE-2022-40304
libzstd|1.5.1-2.el9|CVE-2022-4899
libzstd-devel|1.5.1-2.el9|CVE-2022-4899
libzstd-static|1.5.1-2.el9|CVE-2022-4899
loader-utils|0.2.10|CVE-2022-37601
loader-utils|0.2.11|CVE-2022-37601
loader-utils|0.2.12|CVE-2022-37601
loader-utils|0.2.13|CVE-2022-37601
loader-utils|0.2.14|CVE-2022-37601
loader-utils|0.2.15|CVE-2022-37601
loader-utils|0.2.16|CVE-2022-37601
loader-utils|0.2.17|CVE-2022-37601
loader-utils|0.2.7|CVE-2022-37601
loader-utils|0.2.8|CVE-2022-37601
loader-utils|0.2.9|CVE-2022-37601
loader-utils|1.0.0|CVE-2022-37601
loader-utils|1.0.1|CVE-2022-37601
loader-utils|1.0.2|CVE-2022-37601
loader-utils|1.0.3|CVE-2022-37601
loader-utils|1.0.4|CVE-2022-37601
loader-utils|1.2.0|CVE-2022-37599
loader-utils|1.2.0|CVE-2022-37601
loader-utils|1.2.0|CVE-2022-37603
loader-utils|1.2.1|CVE-2022-37601
loader-utils|1.2.2|CVE-2022-37601
loader-utils|1.2.3|CVE-2022-37599
loader-utils|1.2.3|CVE-2022-37601
loader-utils|1.2.3|CVE-2022-37603
loader-utils|1.3.0|CVE-2022-37601
loader-utils|1.4.0|CVE-2022-37599
loader-utils|1.4.0|CVE-2022-37601
loader-utils|1.4.0|CVE-2022-37603
loader-utils|2.0.0|CVE-2022-37599
loader-utils|2.0.0|CVE-2022-37601
loader-utils|2.0.0|CVE-2022-37603
loader-utils|2.0.1|CVE-2022-37601
loader-utils|2.0.2|CVE-2022-37599
loader-utils|2.0.2|CVE-2022-37601
loader-utils|2.0.2|CVE-2022-37603
loader-utils|3.2.0|CVE-2022-37599
loader-utils|3.2.0|CVE-2022-37603
lodash|4.16.6|CVE-2018-16487
lodash|4.16.6|CVE-2018-3721
lodash|4.16.6|CVE-2019-1010266
lodash|4.16.6|CVE-2019-10744
lodash|4.16.6|CVE-2020-28500
lodash|4.16.6|CVE-2020-8203
lodash|4.16.6|CVE-2021-23337
lodash|4.16.6|SNYK-JS-LODASH-608086
lodash|4.17.11|CVE-2019-10744
lodash|4.17.11|CVE-2020-28500
lodash|4.17.11|CVE-2020-8203
lodash|4.17.11|CVE-2021-23337
lodash|4.17.11|SNYK-JS-LODASH-608086
lodash|4.17.15|CVE-2020-28500
lodash|4.17.15|CVE-2020-8203
lodash|4.17.15|CVE-2021-23337
lodash|4.17.15|SNYK-JS-LODASH-608086
lodash|4.17.5|CVE-2018-16487
lodash|4.17.5|CVE-2019-1010266
lodash|4.17.5|CVE-2019-10744
lodash|4.17.5|CVE-2020-28500
lodash|4.17.5|CVE-2020-8203
lodash|4.17.5|CVE-2021-23337
lodash|4.17.5|SNYK-JS-LODASH-608086
lodash.template|2.4.1|CVE-2021-23337
lodash.template|3.6.2|CVE-2021-23337
lodash.template|4.5.0|CVE-2021-23337
luxon|1.24.0|CVE-2023-22467
luxon|1.24.1|CVE-2023-22467
luxon|1.25.0|CVE-2023-22467
luxon|1.26.0|CVE-2023-22467
luxon|1.27.0|CVE-2023-22467
luxon|1.28.0|CVE-2023-22467
luxon|2.0.1|CVE-2023-22467
luxon|2.0.2|CVE-2023-22467
luxon|2.1.0|CVE-2023-22467
luxon|2.1.1|CVE-2023-22467
luxon|2.2.0|CVE-2023-22467
luxon|2.3.0|CVE-2023-22467
luxon|2.3.1|CVE-2023-22467
luxon|2.3.2|CVE-2023-22467
luxon|2.4.0|CVE-2023-22467
luxon|2.5.0|CVE-2023-22467
luxon|2.5.1|CVE-2023-22467
luxon|3.0.4|CVE-2023-22467
luxon|3.1.0|CVE-2023-22467
luxon|3.1.1|CVE-2023-22467
luxon|3.2.0|CVE-2023-22467
mem|1.1.0|GHSA-4xcv-9jjx-gfj3
merge|1.2.1|CVE-2020-28499
merge|1.2.1|SNYK-JS-MERGE-1040469
minimatch|3.0.4|CVE-2022-3517
minimist|0.0.10|CVE-2020-7598
minimist|0.0.10|CVE-2021-44906
minimist|0.0.8|CVE-2020-7598
minimist|0.0.8|CVE-2021-44906
minimist|1.2.0|CVE-2020-7598
minimist|1.2.0|CVE-2021-44906
minimist|1.2.5|CVE-2021-44906
moment|2.29.3|CVE-2022-31129
mongoose|5.3.3|CVE-2019-17426
mongoose|5.3.3|CVE-2022-2564
mongoose|5.3.3|CVE-2023-3696
ncurses|5.9-14.20130511.el7_4|CVE-2023-29491
ncurses-base|5.9-14.20130511.el7_4|CVE-2023-29491
ncurses-libs|5.9-14.20130511.el7_4|CVE-2023-29491
net.minidev:json-smart|2.4.8|CVE-2023-1370
netmask|1.0.6|CVE-2021-28918
netmask|1.0.6|CVE-2021-29418
networkx|2.2|SNYK-PYTHON-NETWORKX-1062709
node-jose|1.1.4|CVE-2023-25653
node-jose|2.1.0|CVE-2023-25653
nth-check|1.0.2|CVE-2021-3803
openssl|1:1.0.2k-25.el7_9|CVE-2023-0464
openssl-libs|1:1.0.2k-25.el7_9|CVE-2023-0464
org.scala-lang:scala-library|2.13.8|CVE-2022-36944
org.springframework.security:spring-security-config|5.6.1|CVE-2023-34034
org.springframework:spring-beans|5.3.15|CVE-2022-22965
org.springframework:spring-beans|5.3.15|CVE-2022-22970
paramiko|1.16.0|CVE-2018-1000805
paramiko|1.16.0|CVE-2018-7750
paramiko|2.2.1|CVE-2018-1000805
paramiko|2.2.1|CVE-2018-7750
paramiko|2.2.1|CVE-2022-24302
pixman|0.34.0-1.el7|CVE-2022-44638
poppler|0.26.5-43.el7.1|CVE-2022-38784
postcss|7.0.39|CVE-2023-44270
postcss|8.4.20|CVE-2023-44270
postcss|8.4.30|CVE-2023-44270
protobufjs|6.10.2|CVE-2022-25878
protobufjs|6.10.2|CVE-2023-36665
protobufjs|6.11.2|CVE-2022-25878
protobufjs|6.11.2|CVE-2023-36665
protobufjs|6.11.3|CVE-2023-36665
pyjwt|1.7.1|CVE-2022-29217
pyjwt|2.3.0|CVE-2022-29217
python|2.7.5-92.el7_9|CVE-2022-45061
python-libs|2.7.5-92.el7_9|CVE-2022-45061
python-multipart|0.0.5|CVE-2024-24762
python-multipart|0.0.5|GHSA-2jv5-9r88-3w3p
python-multipart|0.0.5|GHSA-93gm-qmq6-w238
python-multipart|0.0.6|CVE-2024-24762
python-multipart|0.0.6|GHSA-2jv5-9r88-3w3p
python-multipart|0.0.6|GHSA-93gm-qmq6-w238
pyyaml|5.1|CVE-2020-14343
pyyaml|5.1|CVE-2020-1747
qs|6.5.2|CVE-2022-24999
qs|6.7.0|CVE-2022-24999
requests|2.14.2|CVE-2018-18074
requests|2.25.1|CVE-2023-32681
requests|2.26.0|CVE-2023-32681
requests|2.27.1|CVE-2023-32681
requests|2.28.0|CVE-2023-32681
requests|2.30.0|CVE-2023-32681
screen|4.1.0-0.27.20120314git3c2946.el7_9|CVE-2015-6806
screen|4.1.0-0.27.20120314git3c2946.el7_9|CVE-2023-24626
scss-tokenizer|0.2.3|CVE-2022-25758
scss-tokenizer|0.3.0|CVE-2022-25758
semver|4.3.6|CVE-2022-25883
semver|5.4.1|CVE-2022-25883
semver|5.7.1|CVE-2022-25883
semver|6.3.0|CVE-2022-25883
semver|7.0.0|CVE-2022-25883
semver|7.1.0|CVE-2022-25883
semver|7.1.1|CVE-2022-25883
semver|7.1.2|CVE-2022-25883
semver|7.1.3|CVE-2022-25883
semver|7.2.0|CVE-2022-25883
semver|7.2.1|CVE-2022-25883
semver|7.2.2|CVE-2022-25883
semver|7.2.3|CVE-2022-25883
semver|7.3.0|CVE-2022-25883
semver|7.3.1|CVE-2022-25883
semver|7.3.2|CVE-2022-25883
semver|7.3.3|CVE-2022-25883
semver|7.3.4|CVE-2022-25883
semver|7.3.5|CVE-2022-25883
semver|7.3.7|CVE-2022-25883
semver|7.3.8|CVE-2022-25883
serialize-javascript|1.9.1|CVE-2019-16769
serialize-javascript|1.9.1|CVE-2020-7660
serialize-javascript|2.0.0|CVE-2019-16769
serialize-javascript|2.0.0|CVE-2020-7660
serialize-javascript|2.1.0|CVE-2019-16769
serialize-javascript|2.1.0|CVE-2020-7660
set-getter|0.1.0|CVE-2021-25949
set-value|0.4.3|CVE-2019-10747
set-value|0.4.3|CVE-2021-23440
set-value|2.0.0|CVE-2019-10747
set-value|2.0.0|CVE-2021-23440
setuptools|58.1.0|CVE-2022-40897
setuptools|65.5.0|CVE-2022-40897
snappier|1.1.0|CVE-2023-28638
sqlite|3.7.17-8.el7_7.1|CVE-2019-5827
sqlparse|0.4.3|CVE-2023-30608
sysstat|10.1.5-19.el7|CVE-2022-39377
tar|2:1.26-35.el7|CVE-2022-48303
tar|4.4.13|CVE-2021-32803
tar|4.4.13|CVE-2021-32804
tar|4.4.13|CVE-2021-37701
tar|4.4.13|CVE-2021-37712
tar|4.4.13|CVE-2021-37713
tough-cookie|2.5.0|CVE-2023-26136
tough-cookie|4.0.0|CVE-2023-26136
tough-cookie|4.1.2|CVE-2023-26136
trim|0.0.1|CVE-2020-7753
twisted|22.1.0|CVE-2023-46137
twisted|22.10.0|CVE-2023-46137
ua-parser-js|0.7.31|CVE-2022-25927
underscore|1.4.4|CVE-2021-23358
underscore|1.6.0|CVE-2021-23358
undici|4.16.0|CVE-2023-24807
urllib3|1.25.11|CVE-2023-43804
urllib3|1.25.11|CVE-2023-45803
urllib3|1.26.16|CVE-2023-43804
urllib3|1.26.16|CVE-2023-45803
urllib3|1.26.17|CVE-2023-45803
urllib3|1.26.5|CVE-2023-43804
urllib3|1.26.5|CVE-2023-45803
urllib3|2.0.4|CVE-2023-43804
urllib3|2.0.4|CVE-2023-45803
urllib3|2.0.6|CVE-2023-45803
vite|4.4.11|CVE-2023-49293
vite|4.4.11|CVE-2024-23331
vm2|3.9.11|CVE-2023-29017
vm2|3.9.12|CVE-2023-29017
vm2|3.9.13|CVE-2023-29017
vm2|3.9.14|CVE-2023-29017
webpack|5.74.0|CVE-2023-28154
webpack|5.75.0|CVE-2023-28154
webpack-dev-middleware|5.3.3|CVE-2024-29180
word-wrap|1.2.3|CVE-2023-26115
xml2js|0.4.19|CVE-2023-0842
xml2js|0.4.23|CVE-2023-0842
y18n|4.0.0|CVE-2020-7774
yargs-parser|7.0.0|CVE-2020-7608
zstd|1.5.1-2.el9|CVE-2022-4899


</details>
