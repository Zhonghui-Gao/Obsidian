# A platform for secure static binary instrumentation
> [!info] Bibliography
> [1]  M. Zhang, R. Qiao, N. Hasabnis, and R. Sekar, “A platform for secure static binary instrumentation,” in _Proceedings of the 10th ACM SIGPLAN/SIGOPS international conference on Virtual execution environments_, in VEE ’14. New York, NY, USA: Association for Computing Machinery, Mar. 2014, pp. 129–140. doi: [10.1145/2576195.2576208](https://doi.org/10.1145/2576195.2576208).

## Information

| Key          |                                   Value                                   |
| :----------- | :-----------------------------------------------------------------------: |
| Date         |                                      2014-03  |
| Author       |                         Mingwei Zhang, Rui Qiao, Niranjan Hasabnis, R. Sekar                          |
| Contributors |                                                           |
| Tags         |                           #/unread, #binary-instrumentation, #binary-translation, #control-flow-integrity, #cots-binary-hardening, #security-policy-enforcement, #software-security, #zotero                           |
| Journal      |                            #              |
| DOI          |                            [10.1145/2576195.2576208](https://doi.org/10.1145/2576195.2576208)                             |
| Extra        |                                              |
| Type         |                            conferencePaper                           |
| Publisher    |                               Association for Computing Machinery                               |
| Others       |              |
| Zotero Link  |                             [全文](zotero://select/library/items/2YBZYBPP)                             |

## Abstract
> [!abstract]
> Program instrumentation techniques form the basis of many recent software security defenses, including defenses against common exploits and security policy enforcement. As compared to source-code instrumentation, binary instrumentation is easier to use and more broadly applicable due to the ready availability of binary code. Two key features needed for security instrumentations are (a) it should be applied to all application code, including code contained in various system and application libraries, and (b) it should be non-bypassable. So far, dynamic binary instrumentation (DBI) techniques have provided these features, whereas static binary instrumentation (SBI) techniques have lacked them. These features, combined with ease of use, have made DBI the de facto choice for security instrumentations. However, DBI techniques can incur high overheads in several common usage scenarios, such as application startups, system-calls, and many real-world applications. We therefore develop a new platform for secure static binary instrumentation (PSI) that overcomes these drawbacks of DBI techniques, while retaining the security, robustness and ease-of-use features. We illustrate the versatility of PSI by developing several instrumentation applications: basic block counting, shadow stack defense against control-flow hijack and return-oriented programming attacks, and system call and library policy enforcement. While being competitive with the best DBI tools on CPU-intensive SPEC 2006 benchmark, PSI provides an order of magnitude reduction in overheads on a collection of real-world applications.

## Annotations
> [!warning]
> ANYTHING OUT OF %begin%...%end% BLOCK WILL BE CLEARED WHEN UPDATE

%% begin annotations %%

***Imported on 2023-12-07 10:49***
***
> [!Image]
> ![](assets/A%20platform%20for%20secure%20static%20binary%20instrumentation/image-1-x35-y278.png)  [(p.1)](zotero://open-pdf/library/items/2YBZYBPP?page=1&annotation=KR5BAC87)

它介绍了一个名为"安全静态二进制仪器化平台"的研究，该平台提供了对二进制代码进行静态分析和修改的功能，并可安全地保护软件系统免受恶意攻击。该平台的设计理念是在不影响系统正常运行的前提下，对二进制代码进行修改、插桩和监视。论文的目标是提供一种可靠的、自动化的方法，同时对系统性能的影响较小，以提高软件系统的安全性

***
%% end annotations %%

## Zotero-Notes




## Notes
%% begin Obsidian-Notes %%



%% end Obsidian-Notes %%
> [!danger]
> NEVER MODIFY ANYTHING BELOW

%% Import Date: 2023-12-07T10:50:55.792+08:00 %%
