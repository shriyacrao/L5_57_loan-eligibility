\# Issues Identified and Fixed



| \*\*Issue\*\* | \*\*Type\*\* | \*\*Line(s)\*\* | \*\*Description\*\* | \*\*Fix Approach\*\* |

| --------- | -------- | ----------- | --------------- | ---------------- |

| FTP module import | Security - High | 3 | The `ftplib` module was imported, which uses the insecure FTP protocol. | Removed FTP and replaced the upload mechanism with HTTPS. |

| FTP usage | Security - High | 68 | The program used FTP to upload reports, which is considered insecure. | Replaced FTP with HTTPS using `urllib.request`. |

| Unsafe deserialization | Security - Medium | 64 | `marshal.loads()` was used to deserialize data, which can be dangerous with untrusted input. | Removed the `marshal` deserialization and changed application loading to JSON. |

| Hardcoded password | Security - Low | 67 | A bureau password was directly written in the source code. | Removed the hardcoded password and used the `BUREAU\_TOKEN` environment variable. |

| Insecure random number generation | Security - Low | 51 | `random.randint()` was used to generate the application ID. | Replaced it with the `secrets` module. |

| Subprocess execution | Security - Low | 74 | `subprocess.run()` was used to launch a mail command. | Removed the subprocess call and changed the function to record a notification message. |

| Partial executable path | Security - Low | 74 | A process was started using a partial executable path. | Removed the process execution completely. |

| Missing docstrings | Code Quality | Multiple | The module and several functions did not have docstrings explaining their purpose. | Added module and function docstrings. |

| Function naming convention | Code Quality | 14, 20, 33, 40, 50, 53, 61, 67, 73, 76, 81 | Several function names did not follow the recommended snake\_case naming convention. | Renamed functions such as `calculateEMI` to `calculate\_emi`. |

| Mutable default argument | Code Quality | 20 | A mutable list `\[]` was used as a default function argument. | Removed the mutable default argument. |

| Unused import | Code Quality | 2 | The `math` module was imported but was never used. | Removed the unused import. |

| Unused variable | Code Quality | 36 | The variable `month` was assigned but was not used. | Removed the unnecessary variable. |

| File handling without context manager | Code Quality | 56, 63, 70 | Files were opened without consistently using a context manager. | Changed file operations to use `with open(...)`. |

| Unused argument | Code Quality | 33 | The `annual\_rate` argument was not used in the function. | Removed its warning by explicitly handling the unused argument. |

| Unnecessary conditional branches | Code Quality | 28, 82 | Some `else` and `elif` branches were unnecessary after returning from the previous condition. | Simplified the conditional statements. |

| Long lines | Style | 20, 55, 70, 78, 95, 96, 100 | Several lines exceeded the allowed line length. | Reformatted the long lines. |

| Incorrect blank-line formatting | Style | Multiple | Required blank lines between functions were missing. | Added the required blank lines. |

| f-string without placeholders | Style | 104 | An f-string was used without any interpolated variables. | Replaced it with a normal string. |

| Missing final newline | Style | End of file | The file did not end with the required newline. | Added the final newline. |

