# better_system_search
Personal utility to avoid the nuances of customizing indexing settings on windows systems, to evaluate bloated systems quickly to find relevant files based off of a provided keyword. Only really useful on lower-end systems, or systems with a lot of bloat. 

<details> <summary><strong>Q: What does this script do?</strong></summary>
A: This Python script provides an alternative way to search for files across local directories. Windows search can often be slow on bloated systems, without extensive customization on older machines. When the soal goal is finding files by one relevant parameter, this script can improve speeds by over 80%. Presently, it only support file name- as for what I often need it for, I only need file name. (Finding and altering all relevant files when assiting individuals in fixing broken js configuration files.)

</details> <details> <summary><strong>Q: Why not just enable indexing on Windows?</strong></summary>
A: Windows Search indexing can...
1. Aggressively slow down performance on large or external drives<br/>
2. Requires administrative privileges to configure comprehensively
3. Fails to index network paths or uncommon file formats reliably
4. Can return outdated results due to stale indices
 
This script bypasses those issues by directly scanning the file system in real time, with no dependency on OS-level indexing. Its lightweight, quick to run and allows quick filtering to file paths. 
Additionally, you're not always using YOUR OWN system. Making perm-changes on a client's system is bad. When all you need is simple indexing, this is the better option.
</details>
⚙️ Configuration & Usage
<details> <summary><strong>Q: How do I customize what files to search?</strong></summary>
A: Presently right now there is only filtering by file name, and directory. There are plans to add;
1. CLI arguments (e.g., --ext .log --min-size 100KB)
2. A JSON config file (e.g., search_config.json)
3. Environment variables, if integrating into larger systems

..but presently, I am working on other ventures. Feel free to submit other suggestions!

</details> <details> <summary><strong>Q: Can it search network drives or mounted volumes?</strong></summary>
A: Yes. As long as the OS can access the mounted location via a path (e.g., Z:\, /mnt/shared), the script can traverse it without needing any additional setup.

</details> <details> <summary><strong>Q: How does it compare to `os.walk()`?</strong></summary>
A: It is built on top of os.walk() or pathlib to ensure fast directory traversal, with additional filtering and formatting logic layered in. This makes it faster and more configurable than basic walk scripts, especially on systems with large file counts.

</details>
⚠️ Performance & Limitations
<details> <summary><strong>Q: How does it handle massive folders with millions of files? Or just scanning from my entire root?</strong></summary>
A: Unfortunately, this method definitely becomes weaker on HIGHER-performance systems. If you have a very good PC, and you're able to have indexing active with no concerns- then technically Windows Search will outperform this script very easily. This script is more intended for lower-end PCs.

</details> <details> <summary><strong>Q: Does it index or cache file data?</strong></summary>
A: No — this script performs real-time scanning for maximum accuracy. This is not intended to be a long-term solution, so it avoids the complexity and overhead of maintaining a persistent index.

</details>
