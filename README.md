# Seal Security Patches

This is a centralized repository of standalone security patches that mitigate open-source libraries' vulnerabilities.
The patches help quickly deal with the security risk in cases where the operational risk of a full version update is too significant.

![Seal Security Hero](docs/assets/seal_hero.png)

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

## Coming Soon: Seal's Artifact Server

To further simplify security patching efforts, Seal Security is developing a SaaS artifact server that allows users to apply security patches seamlessly as part of their SDLC with simple integrations.

With a free tier, automatic detection and application of new patches, and extensive security measures, we can increase your security posture significantly with minimal investment on your end.

You can request early access by shooting an email to: [waitlist@seal.security](mailto:waitlist@seal.security).

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
@fastify/multipart|7.3.0|CVE-2023-25576
acorn|5.7.3|GHSA-6chw-6frg-f759
ansi-regex|3.0.0|CVE-2021-3807
async|2.6.3|CVE-2021-43138
async-es|2.6.3|CVE-2021-43138
axios|0.21.1|CVE-2021-3749
bson|1.0.9|CVE-2019-2391
bson|1.0.9|CVE-2020-7610
com.fasterxml.jackson.core:jackson-databind|2.13.1|CVE-2020-36518
com.fasterxml.jackson.core:jackson-databind|2.13.1|CVE-2022-42003
com.fasterxml.jackson.core:jackson-databind|2.13.1|CVE-2022-42004
com.nimbusds:nimbus-jose-jwt|9.23|CVE-2023-1370
cups-libs|1:2.3.3op2-16.el9|CVE-2023-32324
cups-libs|1:2.3.3op2-16.el9|CVE-2023-32360
cups-libs|1:2.3.3op2-16.el9|CVE-2023-34241
cups-libs|1:2.3.3op2-16.el9_2.1|CVE-2023-32324
cups-libs|1:2.3.3op2-16.el9_2.1|CVE-2023-34241
d3-color|2.0.0|GHSA-36jr-mh4h-2g58
ejs|2.7.4|CVE-2022-29078
ejs|2.7.4|SNYK-JS-EJS-1049328
fast-json-patch|2.2.1|CVE-2021-4279
fast-xml-parser|3.19.0|SNYK-JS-FASTXMLPARSER-3325616
glob-parent|3.1.0|CVE-2020-28469
global-modules-path|2.3.1|CVE-2022-21191
got|6.7.1|CVE-2022-33987
growl|1.9.2|CVE-2017-16042
handlebars|4.1.2|CVE-2019-20920
https-proxy-agent|1.0.0|CVE-2018-3739
ini|1.3.5|CVE-2020-7788
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
json5|0.5.1|CVE-2022-46175
json5|2.0.0|CVE-2022-46175
json5|2.0.1|CVE-2022-46175
json5|2.1.0|CVE-2022-46175
libtiff|4.0.3-35.el7|CVE-2022-3970
libtiff-devel|4.0.3-35.el7|CVE-2022-3970
libtiff-static|4.0.3-35.el7|CVE-2022-3970
libtiff-tools|4.0.3-35.el7|CVE-2022-3970
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
loader-utils|1.2.0|CVE-2022-37601
loader-utils|1.2.1|CVE-2022-37601
loader-utils|1.2.2|CVE-2022-37601
loader-utils|1.2.3|CVE-2022-37601
loader-utils|1.3.0|CVE-2022-37601
loader-utils|1.4.0|CVE-2022-37601
loader-utils|2.0.0|CVE-2022-37601
loader-utils|2.0.1|CVE-2022-37601
loader-utils|2.0.2|CVE-2022-37601
lodash|4.16.6|CVE-2018-16487
lodash|4.16.6|CVE-2018-3721
lodash|4.16.6|CVE-2019-1010266
lodash|4.16.6|CVE-2019-10744
lodash|4.16.6|CVE-2020-28500
lodash|4.16.6|CVE-2020-8203
lodash|4.16.6|CVE-2021-23337
lodash|4.17.11|CVE-2019-10744
lodash|4.17.11|CVE-2020-28500
lodash|4.17.11|CVE-2020-8203
lodash|4.17.11|CVE-2021-23337
lodash|4.17.15|CVE-2020-28500
lodash|4.17.15|CVE-2020-8203
lodash|4.17.15|CVE-2021-23337
lodash|4.17.5|CVE-2018-16487
lodash|4.17.5|CVE-2019-1010266
lodash|4.17.5|CVE-2019-10744
lodash|4.17.5|CVE-2020-28500
lodash|4.17.5|CVE-2020-8203
lodash|4.17.5|CVE-2021-23337
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
minimist|0.0.10|CVE-2020-7598
minimist|0.0.10|CVE-2021-44906
minimist|0.0.8|CVE-2020-7598
minimist|0.0.8|CVE-2021-44906
minimist|1.2.0|CVE-2020-7598
minimist|1.2.0|CVE-2021-44906
mongoose|5.3.3|CVE-2019-17426
mongoose|5.3.3|CVE-2022-2564
mongoose|5.3.3|CVE-2023-3696
net.minidev:json-smart|2.4.8|CVE-2023-1370
netmask|1.0.6|CVE-2021-28918
netmask|1.0.6|CVE-2021-29418
networkx|2.2|SNYK-PYTHON-NETWORKX-1062709
node-jose|1.1.4|CVE-2023-25653
node-jose|2.1.0|CVE-2023-25653
nth-check|1.0.2|CVE-2021-3803
org.scala-lang:scala-library|2.13.8|CVE-2022-36944
paramiko|1.16.0|CVE-2018-1000805
paramiko|1.16.0|CVE-2018-7750
protobufjs|6.11.3|CVE-2023-36665
pyjwt|1.7.1|CVE-2022-29217
pyyaml|5.1|CVE-2020-14343
pyyaml|5.1|CVE-2020-1747
requests|2.14.2|CVE-2018-18074
semver|7.3.2|CVE-2022-25883
semver|7.3.5|CVE-2022-25883
serialize-javascript|1.9.1|CVE-2019-16769
serialize-javascript|1.9.1|CVE-2020-7660
serialize-javascript|2.0.0|CVE-2019-16769
serialize-javascript|2.0.0|CVE-2020-7660
serialize-javascript|2.1.0|CVE-2019-16769
serialize-javascript|2.1.0|CVE-2020-7660
tough-cookie|2.5.0|CVE-2023-26136
trim|0.0.1|CVE-2020-7753
underscore|1.4.4|CVE-2021-23358
underscore|1.6.0|CVE-2021-23358
undici|4.16.0|CVE-2023-24807
vm2|3.9.11|CVE-2023-29017
vm2|3.9.12|CVE-2023-29017
vm2|3.9.13|CVE-2023-29017
vm2|3.9.14|CVE-2023-29017
webpack|5.74.0|CVE-2023-28154
webpack|5.75.0|CVE-2023-28154
xml2js|0.4.19|CVE-2023-0842
xml2js|0.4.23|CVE-2023-0842
yargs-parser|7.0.0|CVE-2020-7608
zstd|1.5.1-2.el9|CVE-2022-4899


</details>
