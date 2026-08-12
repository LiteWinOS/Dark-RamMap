# Dark RAMMap

![NET](https://img.shields.io/badge/.NET-10.0-512BD4?logo=dotnet)
![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-0078D4?logo=windows)
![License](https://img.shields.io/badge/License-MIT-green.svg)

**Dark RAMMap** is a lightweight, dark-themed Windows physical memory utility inspired by Sysinternals RAMMap. Built using C# and native NT kernel APIs (`ntdll.dll`), it provides a real-time, low-level breakdown of system RAM allocation across process working sets, standby lists, modified pages, and kernel pools—wrapped in a modern dark interface.

---
Fast to retrieve info but not accuracy , close enough tho 
---

## Key Features

* **Native NT Kernel Inspection:** Queries system Page Frame Numbers (PFNs) directly via `NtQuerySystemInformation` (`SystemMemoryListInformation`) for accurate memory distribution metrics.
* **Sysinternals-Style Use Counts Matrix:** Categorizes physical memory into Active, Standby, Modified, and Zeroed states across Driver Locked, Process Private, Paged/Nonpaged Pools, System PTEs, Metafiles, and more.
* **Standby & Working Set Purging:** Safely empties the Standby List (`MemoryPurgeStandbyList`) and Working Sets (`MemoryEmptyWorkingSets`) on demand with automatic `SeProfileSingleProcessPrivilege` token adjustment.
* **Extended Subsystem Counters Tab:** Provides a secondary matrix mapping raw and formatted Windows performance counters (`% Committed Bytes`, `Cache Bytes`, `Commit Limit`, `Available Bytes`).
* **Dynamic Palette & Map:** Features a real-time, color-coded usage bar and vertical row legend matching classic RAMMap category colors.

---

## Screenshots & UI Layout

| Tab | Description |
| :--- | :--- |
| **Use Counts** | Primary RAMMap matrix showing physical memory allocation in KB across usage categories and page states. |
| **Extended Counters** | Low-level subsystem performance counters providing detailed system-wide memory metrics. |

---

## Requirements

* **Operating System:** Windows 10 / Windows 11 (x64)
* **SDK / Runtime:** .NET 10.0 SDK (or Windows Desktop Runtime)
* **Execution Privileges:** Administrator rights (required to acquire `SeProfileSingleProcessPrivilege` and execute `NtSetSystemInformation` memory purges).

---

## Building from Source

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/DarkRAMMap.git](https://github.com/your-username/DarkRAMMap.git)
   cd DarkRAMMap
