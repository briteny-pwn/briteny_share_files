The IDA Pro 8.3 Portable Edition is developed by Hmily, 微笑一刀, and 云在天 based on the leaked IDA Pro 8.3 Windows version. To install the portable edition, simply extract and run "IDA_Pro_8.3_绿化工具." This edition mainly includes three functionalities: 1、Blocking unnecessary internet connections; 2、Default support for Chinese GBK string recognition; 3、Support for Portable Python.


Modification Details:
1. Based on the differential information provided by UniSoft [EXETOOLS], we restored the content of IDA files modified in the leaked version and applied a crack patch for Floating authorization functionality (the leaked version only included Hex-Rays Decompiler plugins for x86 and x64; we didn’t package plugins for other platforms, which may cause compatibility issues. These can be resolved using github.com/x0rloser/ida_dll_shim if necessary).
2. Patched the LAN authorization count check (no data sending or receiving over LAN) and IDB blacklist restrictions, with STORE_USER_INFO turned off by default.
3. To reduce the load on Hex-Rays SA servers, we disabled automatic and manual upgrade requests that usually occur weekly (upgrade verification typically uploads user MAC address, IP, KEY, etc.), as well as the IDA BugReport and database upload functionalities.
4. To further reduce server load, the IDA Lumina feature is disabled by default, including automatic Lumina analysis (Lumina functionality typically uploads user hostname, IDB path, binary file path, binary MD5, IP, KEY, email, etc.). Due to the complexity of setting up a new Lumina private server, it is not detailed here. If needed, set up via IDA-Options-Lumina-Servers, and refer to available resources. Be aware of privacy risks when using a private server.
5. Added StrongCC v0.3, patching, and findcrypt plugins to enhance Chinese string recognition, facilitate code modification and decompilation, and identify encryption algorithms and constants in code.
6. Included necessary Visual C++ runtime libraries.
7. Created a Portable of Python 3.11.7 (IDA 8.3 doesn't fully support version 3.12, requiring IDA code modifications, so we used version 3.11 for the sake of stability and precaution)
8. Portable tools by 云在天 include:
       a. Use of portable Python 3.11.7;
       b. Setting .idb and .i64 database file associations;
       c. Creating IDA desktop shortcuts;
       d. Setting IDA context menus;
       e. Customizing IDA license user name (based on KEYGEN code by CZC[EXETOOLS]);
       f. Support for uninstalling and clearing registry entries set by the portable edition IDA;
       g. GPT-generated beautiful icons and detail check reminders.


Note:
1. Avoid Chinese characters or symbols in the extraction path, as IDA's QT LoadLibrary does not correctly encode Chinese paths. We attempted a file patch, but it required extensive code changes. Hijacking methods are not elegant and may cause issues with other languages, so we've avoided special handling.
2. When installing plugins using the Portable Python, enter the python311 directory and use the "-m" parameter to specify running pip as an import module. For example:
       a. python.exe -m pip list
       b. python.exe -m pip install [package name or path]
3. To switch to a different Python version, use the idapyswitch.exe program in the root directory (custom Python requires manual installation of plugin libraries; current portable edition no longer supports Win7, but 3.9.3 can be installed if needed).
4. Since IDA 7.7, changes in acquiring and processing Chinese system encoding have led to the default use of UTF-8 encoding (instead of gb2312 in version 7.6), causing many Chinese program strings to be unrecognized. To address this, 微笑一刀 updated StrongCC v3, which adjusts IDA's default encoding based on system language, using CP936 for Chinese systems by default, reducing manual encoding changes. This can be toggled via the configuration file (/cfg/StrongCC.cfg, CPACP = true or false). If your system is Chinese but program strings aren't in GBK, or you're unsure of the string language and encoding, follow these steps:
       a. In IDA, select Options - General - Strings, set “Default 8-bit” to UTF-8 (or corresponding encoding).
       b. Choose Options - General - Analysis - “Reanalyze program” for IDA to reanalyze the program.
       c. If strings were analyzed before, right-click in the Strings window and select Rebuild for IDA to reconstruct strings.
5.The IDA83_SDK_TOOLS.7z in the root directory contains IDA 8.3 SDK files, which can be deleted if not needed without affecting usage.

Thanks to UniSoft[EXETOOLS] for sharing information that allowed us to restore original files. Special thanks to Hex-Rays SA for providing such a great tool. We strongly encourage users to support the official version for continued software improvement and updates. Without permission from the software author, the above content should not be used for commercial purposes or copyright infringement. Users bear all consequences of using this tool; the provider is not responsible. This content is for learning and research purposes only.


LCG
https://www.52pojie.cn