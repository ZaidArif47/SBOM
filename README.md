# CycloneDX & OWASP Dependency-Track Project Guide

This guide walks you through the steps I followed to generate a Software Bill of Materials (SBOM) and assess security risks in an intentionally insecure web application (OWASP Juice Shop). 

A Software Bill of Materials (SBOM) is a comprehensive inventory of every item that’s needed to build your application. It lists the components, libraries, modules, and other resources, along with the relevant version numbers and other useful metadata.

Follow these instructions to set up CycloneDX for SBOM creation and use OWASP Dependency-Track for vulnerability analysis.

---

## Part 1: CycloneDX Setup and Use

1. **Understand the Project Context**  
   I started with the OWASP Juice Shop project, an intentionally insecure web application, to generate its Bill of Materials (BOM).

2. **Select the Appropriate CycloneDX Tool**  
   Since Juice Shop uses the MEAN tech stack, I chose the `cyclonedx-npm` tool, which is specifically designed for creating CycloneDX SBOMs from npm projects.  
   More details can be found on the [cyclonedx-node-npm GitHub repository](https://github.com/CycloneDX/cyclonedx-node-npm).

3. **Generate the BOM**  
   Run the `cyclonedx-npm` command in your project directory to create the BOM for Juice Shop.

---

## Part 2: OWASP Dependency-Track Setup and Use

1. **Introduction to Dependency-Track**  
   OWASP Dependency-Track is a powerful Software Composition Analysis (SCA) platform that helps identify and mitigate risks in the software supply chain. It leverages the SBOM to uncover inherited vulnerabilities.

2. **Upload the BOM File**  
   - Navigate to the “Projects” section in the Dependency-Track interface.
   - Create a new project.
   - Upload the BOM file you generated with CycloneDX under the “BOM” tab.

   For more information, check out the [Dependency-Track GitHub repository](https://github.com/DependencyTrack/dependency-track).

---

## Part 3: SBOM Generation and Evaluation

1. **SBOM Generation in Dependency-Track**  
   After uploading your BOM, Dependency-Track automatically parses the file, identifies all components, and correlates any known vulnerabilities.

2. **Evaluate Security Risks**  
   - Review the identified vulnerabilities for each dependency.
   - Assess the risk level associated with each dependency.
   - Consider and implement appropriate mitigation strategies.

3. **Export the Vulnerability Report**  
   Dependency-Track provides an option to export a detailed vulnerability report. Use this report to further analyze and document the security posture of your project.

---

By following these steps, you can effectively generate an SBOM and leverage OWASP Dependency-Track to monitor and mitigate risks in your project. Happy securing!
