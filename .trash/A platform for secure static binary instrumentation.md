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


%% end annotations %%

## Zotero-Notes




## Notes
%% begin Obsidian-Notes %%



%% end Obsidian-Notes %%
> [!danger]
> NEVER MODIFY ANYTHING BELOW

%% Import Date: 2023-12-07T10:42:44.698+08:00 %%
