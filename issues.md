\# Issues Identified and Fixed



| Tool | Issue Identified | Fix Applied |

|---|---|---|

| Pylint | Missing module and function docstrings | Added docstrings to the module and functions |

| Pylint | Function names were not in snake\_case | Renamed functions such as `calculateEMI` to `calculate\_emi` |

| Pylint | Mutable default argument `\[]` was used | Removed the mutable default argument |

| Pylint | Unused import and variables were present | Removed the unused import and variable |

| Pylint | File operations were not using `with` | Changed file operations to use `with open(...)` |

| Pylint | Unnecessary `else` and complex conditions | Simplified the conditional statements |

| Pylint | Use of `global` statement | Kept it because the existing application structure uses the global application dictionary |

| Bandit | `random.randint()` was used for generating application IDs | Replaced it with the `secrets` module |

| Bandit | Hardcoded bureau password was present | Removed the hardcoded password and used the `BUREAU\_TOKEN` environment variable |

| Bandit | FTP was used for uploading reports | Replaced FTP with HTTPS using `urllib.request` |

| Bandit | `marshal.loads()` was used | Removed the unsafe deserialization code |

| Bandit | `subprocess` was used for applicant notification | Removed the process call and changed it to a simple notification message |

| Flake8 | Unused `math` import | Removed the unused import |

| Flake8 | Lines were longer than the allowed limit | Reformatted long lines |

| Flake8 | Incorrect number of blank lines | Added the required blank lines |

| Flake8 | f-string without placeholders | Replaced it with a normal string |

| Flake8 | Missing final newline / formatting issues | Corrected the file formatting |



\## Final Results



\- \*\*Pylint:\*\* 9.89/10

\- \*\*Bandit:\*\* No issues identified

\- \*\*Flake8:\*\* No issues identified

