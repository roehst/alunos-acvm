# Notes on MSR 2020

## The call for papers

There are three categories accepted:

### Research papers
> Full research papers are expected to describe new methodologies and/or provide novel research results, and should be evaluated scientifically. While a high degree of technical rigor is expected for long papers, short research papers should discuss controversial issues in the field, or describe interesting or thought-provoking ideas that are not yet fully developed

### Practice experience
> papers that report on both positive and negative experiences of applying software analytics strategies in an industry/open source organization context. Adapting existing algorithms or proposing new algorithms or approaches for practical use are considered a plus

### Reusable tool
> MSR actively promotes and recognizes the creation and use of tools that are designed and built not only for a specific research project, but for the MSR community as a whole. Those tools enable other researchers to jumpstart their own research efforts, and also enable reproducibility of earlier work.

## The papers
1. A Large-Scale Comparative Evaluation of IR-Based Tools for Bug Localization

Bug localization using information retrieval techniques. This specific paper improves upon earlier studies by using a larger dataset and languages other than Java (C++, Python).

2. A Machine Learning Approach for Vulnerability Curation

Curation of various data items (JIRA tickets, GitHub Issues, etc) to classify whether they are vulnerability-related or not. This datasets are important for security research.

So far 1 and 2 work on datasets extracted from version control systems or project-management systems.

3. A Soft Alignment Model for Bug Deduplication

Deduplicating bugs is important for research and also for curating bug tracking systems and doing triage on new bug reports.

Again we see the theme of characterizing parts of software or other artifacts as being buggy or not. More generally this addresses the problem of labeling artifacts from software development.

4. A Study of Potential Code Borrowing and License Violations in Java Projects on GitHub

How to locate code clones? This is very interesting, the problem of program equivalence is very hard.

This was conducted by JetBrains. Interesting.

5. A Study on the Accuracy of OCR Engines for Source Code Transcription from Programming Screencasts

6. A Tale of Docker Build Failures: A Preliminary Study

A study on 800k docker builds from 3k projets. They analise the frequency of broken builds and how long it takes to fix them. This is cool because Docker is so prevalent today and a failure in the Docker build indicates a failed deployment very clearly.

7. AIMMX: Artificial Intelligence Model Metadata Extractor

Extracts metadata from the AI papers and model zoos. Interesting for ML reprodutibility.

8. An Empirical Study of Method Chaining in Java

> While some promote method chaining as a good practice for improving code readability, others refer to it as a bad practice that worsens code quality. In this paper, we first investigate whether method chaining is a programming style accepted by real-world programmers.

Nice, this is closer to our purposes - repositories being mined for things that are statically defined. It looks at the trend in a particular language pattern/construct. So nice!

9. An Empirical Study on Regular Expression Bugs

Regular expressions are very brittle and this paper investigates bugs in regular expressions and how long it takes to fix a Regex bug.

10. Automatically Granted Permissions in Android apps

Back to the theme of security research. Specifically on mobile, so it should be interesting to Alexandre. 3M app releases.

So datasets are getting larger... it seems so. Do they?

11.  Behind the Intents: An In-depth Empirical Study on Software Refactoring in Modern Code Review

This paper characterizes code refactorings based on a small dataset (1,8k code changes). 

This might have some interest for us. It raises an important option in research. Should we use knowledge (code parsers/analysers) or just work with unstructured text and labeled data?

They use a tool called [[RefMiner]]. It is Java specific.

*Brazilian study* from PUC Rio mainly

12. Beyond the Code: Mining Self-Admitted Technical Debt in Issue Tracker Systems

> Self-admitted technical debt (SATD) is a particular case of Technical Debt (TD) where developers explicitly acknowledge their sub-optimal implementation decisions.

Ooh it would be great to have this at Loft. This is of special interest for Alexandre.

> Our findings suggest that there is space for designing novel tools to support technical debt management, particularly tools that encourage developers to create and label issues containing TD concerns.

Brazilian study, UFMG.

13. Boa Views: Easy Modularization and Sharing of MSR Analyses Technical Papers

Boa is a tool for 
> Mining Ultra-Large-Scale Software Repositories

It is a DSL for analysing software repository data... Weird...  but cool.

Seems very sophisticated and featured.

14. Can We Use SE-specific Sentiment Analysis Tools in a Cross-Platform Setting?

Might be interesting for someone - not me.

15. Capture the Feature Flag: Detecting Feature Flags in Open-Source Technical Papers

Cool! 

16. Challenges in Chatbot Development: A Study of Stack Overflow Posts\

17. Characterizing and Identifying Composite Refactorings: Concepts, Heuristics and Patterns

Again by PUC-Rio, again the theme of classifying commits and pull requests and detecting refactoring patterns. 

There is an interesting bit on an "algebra" of software refactoring - how single step refactorings combine to larger refactorings or smells.

This might be useful for analysing commits - smells might prevent rapid integration. This can really focus my research - it is an [[Hypothesis]].

18. Detecting Video Game-Specific Bad Smells in Unity Projects

Similar to 17.

19. Detecting and Characterizing Bots that Commit Code

Detecting bots is interesting for building very large datasets from GitHub data.

Example that a well design small piece of research ca be relevant.

19. Developer-Driven Code Smell Prioritization

> Code smells are symptoms of poor implementation choices applied during software evolution. While previous research has devoted effort in the definition of automated solutions to detect them, still little is known on how to support developers when prioritizing them.

Basically on detecting code sells and classifying them according to severity. 

It is interesting because they e-mail developers after they submit a patch.

20. Did You Remember To Test Your Tokens?

Security again.

21. Embedding Java Classes with code2vec: Improvements from Variable Obfuscation

Code2vec... hummm... this might be REALLY interesting for me. Shit me not.

#hot

22. Empirical Study of Restarted and Flaky Builds on Travis CI

More analysis of builds... cool.

23. Ethical Mining – A Case Study on MSR Mining Challenges

24. Forking Without Clicking: on How to Identify Software Repository Forks

This might be really #useful because the [[Pull-based development model]] is very connected to [[Distributed software development]] which is highly dependent on [[Forks]].

This brings a #question: what is more common: forks or plain PRs?

25. From Innovations to Prospects: What Is Hidden Behind Cryptocurrencies?

They look for similarities in code in various cryptocurrencies. 

The theme of labeling source code is very recurrent!

26. Improved Automatic Summarization of Subroutines via Attention to File Context

Cool. Automatic summarization is automatic documentation. Moving from heuristics to ML. This is a cool theme. Maybe this is a big underlyling force in MSR.

27. Investigating Severity Thresholds for Test Smells

Again, very similar to 19.

28. Need for tweet. How open-source developers use Twitter to talk about their GitHub work

29. On the Prevalence, Impact, and Evolution of SQL code smells in Data-Intensive Systems

Nice, I like the idea of mining SQL queries. There is so much SQL in any company. And SQL is always written by non-developers and it sucks.

30. On the Relationship between User Churn and Software Issues

Very very very cool. Does bad code induce user churn?

> Through our empirical study, we observe that (i) the intention to change software is tightly associated to the issues that are present in these software; (ii) we can use deep learning models to predict the rate of potential churn that will occur for a software; (iii) the longer the issue takes to be fixed, the higher the chances of users’ churn; and (iv) issues within more general software modules are more likely to be associated with users’ churn. 

31. PUMiner: Mining Security Posts from Developer Question and Answer Websites with PU Learning

Security & labeling artifacts (Stack overflow posts in this case)

32. Painting Flowers: Reasons for Using Single-State State Machines in Model-Driven Engineering

33. Polyglot and Distributed Software Repository Mining with CROSSFLOW

Useful but unexciting - how to distribute mining in order to deal with rate limiting.

34. RTPTorrent: An Open-source Dataset for Evaluating Regression Test Prioritization Technical Papers

35. SoftMon: A Tool to Compare Similar Open-source Software from a Performance Perspective

36. The Impact of a Major Security Event on an Open Source Project: The Case of OpenSSL

37. The Scent of Deep Learning Code: An Empirical Study

> In this paper, we conduct an empirical study using 118 open-source software systems from GitHub where we contrast between deep learning-based and traditional systems in terms of their code quality.

Could be useful at work. 

Might contain useful features!

38. The State of the ML-universe: 10 Years of Artificial Intelligence & Machine Learning Software Development on GitHub

Also might be useful at work.

39. Traceability Support for Multi-Lingual Software Projects

40. Using Large-Scale Anomaly Detection on Code to Improve Kotlin Compiler

Finds unusual compiler generated code (anomalies) and tries to suggest improvements to the compiler.

41. Using Others' Tests to Avoid Breaking Updates

So interesting - running test suites in dependencies to avoid breaking updates.

Like a veeeery large scale integration test.

42. Visualization of Methods Changeability Based on VCS Data

Visualizinng chages in code can lead to insights in my own research.

43. What constitutes Software? An Empirical, Descriptive Study of Artifacts

> The term software is ubiquitous, however, it does not seem as if we as a community have a clear understanding of what software actually is. Imprecise definitions of software do not help other professions, in particular those acquiring and sourcing software from third-parties, when deciding what precisely are potential deliverables. 

I will happily use this paper to define software.

44. What is the Vocabulary of Flaky Tests?

Useful.

## Data showcase

1. 20-MAD - 20 years of issues and commits of Mozilla and Apache Development

Long-term datasets on Mozilla & Apache projects (issues, commits, reviews), including sentiment analysis.

2. A C/C++ Code Vulnerability Dataset with Code Changes and CVE Summaries

Security is not of intererst.

3. A Complete Set of Related Git Repositories Identified via Community Detection Approaches Based on Shared Commits

A dataset for community detection. Might be useful for Diego since he is interested in committers, reviewers and collaborators.

4. A Dataset and an Approach for Identity Resolution of 38 Million Author IDs extracted from 2B Git Commits

Is this a real issue during analysis? Idk. Might be useful for Diego.

5. A Dataset for GitHub Repository Deduplication

Has analysis of cliques in repository graphs.

6. A Dataset of Dockerfiles

Complex docker files might be closely related to complicated builds and complex projects.

7. A Dataset of Enterprise-Driven Open Source Software

Very useful for me. [[Enterprise-driven projects]] might be different from other open-source projects. This might be a very interesting subject to me. This can lead to a #research-question 

8. A Mixed Graph-Relational Dataset of Socio-technical Interactions in Open Source System

Possibly interesting to Diego.

9. A New Dataset for Pull Request Acceptance

Of direct interest to me.

10. AndroZooOpen: Collecting Large-scale Open Source Android Apps for the Research Community

Of interest to Iocci. He is working with mobile.

11. Dataset of Video Game Development Problems

Not anyone's domain.

12. Employing Contribution and Quality Metrics for Quantifying the Software Development Process

Of direct interest to me and Diego.

13.  GitterCom: A Dataset of Open Source Developer Communications in Gitter

Might be a useful control for Diego.

14. Hall-of-Apps: The Top Android Apps Metadata Archive

Iocci.

15. How Often Do Single-Statement Bugs Occur? The ManySStuBs4J Dataset

Hum... interesting research question.

16. JTeC: A Large Collection of Java Test Classes for Test Code Analysis and Processing

A dataset of test code. Might point to refactoring and tech debt. and thus be useful do Iocci.

17. LogChunks: A Data Set for Build Log Analysis

Cool but I don't know if this is useful for us.

18. Software-related Slack Chats with Disentangled Conversations

Same as 13.

19. TestRoutes: A Manually Curated Method Level Dataset for Test-to-Code Traceability

Maybe useful for Iocci.

## Mining Challenges

1. Cheating Death: A Statistical Survival Analysis of Publicly Available Python Projects

> We apply survival analysis methods to a dataset of publicly-available software projects in order to examine the attributes that might lead to their inactivity over time. We ran a Kaplan-Meier analysis and fit a Cox Proportional-Hazards model to a subset of Software Heritage Graph Dataset, consisting of 3052 popular Python projects hosted on GitLab/GitHub, Debian, and PyPI, over a period of 165 months. We show that projects with repositories on multiple hosting services, a timeline of publishing major releases, and a good network of developers, remain healthy over time and should be worthy of the effort put in by developers and contributors.

Exactly me.