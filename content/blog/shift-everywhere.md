
+++
title = "Shift Left? Shift Everywhere!"
description = "What direction do we go after we’ve shifted left? How about everywhere else!"
author = "MaTTeo DeCaPa"
date = "2023-03-18"
tags = ["appSec", "security"]
categories = ["web2"]
[[images]]
  src = "img/appsec/everywhere.png"
  alt = "Shift Everywhere"
+++

# Shift Left? Shift Everywhere!
The notion of shifting left has been a best practice by application security practitioners, devOps engineers, and application security tool vendors for a long time.  Shift Left is a term used to reflect the practice of identifying weaknesses and vulnerabilities as quickly as possible, while minimizing development friction. The advantage to identifying issues early on, results in better security, agility, and cost efficiencies.

## Left Until You Cannot
Shift Left is accomplished by utilizing secure code analysis tools, trained secure developers, and automation to provide feedback at the speed of DevOps. Moving farther left is intended to provide results without the need to exit source code, wait on check-in, or automated scanning. It is accomplished by utilizing Integration Development Environment (IDE) extensions to identify and highlight the line where the flaw is found. Some plugins have a capability to analyze code while it is being written. Now that is as far left as one can go!

## Everywhere Else
What is meant by “shifting everywhere”? In a [previous post](../opensource-security-tools-across-the-devops-lifecycle), I provided a brief list of decent open source application security tools. I categorized them by where they fit within the Secure Development Lifecycle (SDL). Just as a screwdriver and a hammer serve different purposes in the construction of a house, security tools have different uses within the SDL. Implementing security tools across all SDL phases is like placing security everywhere. Hence, “Shift Everywhere”!

{{< rawhtml >}}
  <center><img src="../img/infinity.png" alt="infinity diagram" /></center>
{{< /rawhtml >}}

## Security Pipelines
How do we do this? Security pipelines combined with automation. Shifting everywhere has several implications, and there is no single solution that suits all organizations.

“Whoa, whoa, whoa”, I imagine more than a few readers thinking, “If it isn’t in my Continuous Integration, Continuous Deployment (CI/CD) pipeline then it isn’t DevSecOps”. In order to shift everywhere, more security tools will be introduced across the lifecycle as maturity increases. As a result, CI/CD velocity could be impacted and add unwanted friction. Security pipelines need to extend beyond code check-in and deployment. It is a noble intention to try to run everything inline within a single pipeline, but reality may get in the way.  

Long scan times can leave a developer wondering if the check-in passes a policy or breaks a build.  QA security tests, [DAST](https://github.com/DeCaPa/appsec-acronyms#D), and other automated tests take time. A security pipeline running asynchronously might be a better fit. 

The security pipeline will extend across all SDL phases.  It is more than CI where code devdevelopment and static scans take place. How you architect is up to you team's and company's particular requirements.


# In summary
A holistic and balanced approach to Application Security inclusive of all phases of the SDL is the cornerstone of Shift Everywhere. In the age of Agile and continuous release methodologies, secure practices are injected into each iterative phase based on the organization’s or the product’s strategic risk acceptance & avoidance criteria.

Shifting left is a great approach for application security and product teams. Once there, shifting everywhere else is the next step on the path towards greater application security maturity. Development teams continuously add new features to product releases with each iteration. It makes sense to do similar iterations while shifting everywhere as well. In no time, a fully secured software product will be realized.

A future article will introduce the concept of a security product, to expand upon the premise of Shift Everywhere.