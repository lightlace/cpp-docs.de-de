---
title: "In Apps f&#252;r die universelle Windows-Plattform nicht unterst&#252;tzte CRT-Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# In Apps f&#252;r die universelle Windows-Plattform nicht unterst&#252;tzte CRT-Funktionen
Viele CRT\-Funktionen \(C\-Laufzeit\) sind nicht verfügbar, wenn Sie Apps für die universelle Windows\-Plattform erstellen. In einigen Fällen sind Problemumgehungen verfügbar, Sie können z. B. [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\- oder Win32\-APIs verwenden. In anderen Fällen wurden die CRT\-Funktionen jedoch möglicherweise gesperrt, da die ihnen entsprechenden Features oder die unterstützenden APIs nicht auf Apps für die universelle Windows\-Plattform \(UWP\) angewendet werden können.  
  
 In der folgenden Tabelle sind die CRT\-Funktionen, die beim Erstellen von Apps für die universelle Windows\-Plattform nicht verfügbar sind, sowie mögliche Problemumgehungen aufgeführt.  
  
## Nicht unterstützte CRT\-Funktionen  
  
||||  
|-|-|-|  
|\_beep \_sleep \_seterrormode|Diese Funktionen waren in früheren Versionen der CRT veraltet. Darüber hinaus sind die entsprechenden Win32\-APIs für Apps für die universelle Windows\-Plattform nicht verfügbar.|Keine Problemumgehung.|  
|chdir \_chdrive getcwd|Diese Funktionen sind veraltet oder nicht threadsicher.|Verwenden Sie „\_chdir“, „\_getcwd“ und verwandte Funktionen.|  
|\_cgets \_cgets\_s \_cgetws \_cgetws\_s \_cprintf \_cprintf\_l \_cprintf\_p \_cprintf\_p\_l \_cprintf\_s \_cprintf\_s\_l \_cputs \_cputws \_cscanf \_cscanf\_l \_cscanf\_s \_cscanf\_s\_l \_cwait \_cwprintf \_cwprintf\_l \_cwprintf\_p \_cwprintf\_p\_l \_cwprintf\_s \_cwprintf\_s\_l \_cwscanf \_cwscanf\_l \_cwscanf\_s \_cwscanf\_s\_l \_vcprintf \_vcprintf\_l \_vcprintf\_p \_vcprintf\_p\_l \_vcprintf\_s \_vcprintf\_s\_l \_vcwprintf \_vcwprintf\_l \_vcwprintf\_p \_vcwprintf\_p\_l \_vcwprintf\_s \_vcwprintf\_s\_l \_getch \_getch\_nolock \_getche \_getche\_nolock \_getwch \_getwch\_nolock \_getwche \_getwche\_nolock \_putch \_putch\_nolock \_putwch \_putwch\_nolock \_ungetch \_ungetch\_nolock \_ungetwch \_ungetwch\_nolock \_kbhit kbhit putch cgets cprintf cputs cscanf cwait getch getche ungetch|Diese Funktionen werden zum direkten Lesen von der sowie zum direkten Schreiben in die Konsole verwendet. Apps für die universelle Windows\-Plattform sind nur für die grafische Benutzeroberfläche \(GUI\) vorgesehen und unterstützen die Konsole nicht.|Keine Problemumgehung.|  
|getpid|Diese Funktion ist veraltet.|Verwenden Sie „\_getpid“ oder die Win32\-API `GetCurrentProcessId()`.|  
|\_getdiskfree|Nicht verfügbar.|Verwenden Sie die Win32\-API `GetDiskFreeSpaceExW()`.|  
|\_getdrive \_getdrives|Die entsprechende API ist für Apps für die universelle Windows\-Plattform nicht verfügbar.|Keine Problemumgehung.|  
|\_inp \_inpd \_inpw \_outp \_outpd \_outpw inp inpd inpw outp outpd outpw|Port\-E\/A wird in Apps für die universelle Windows\-Plattform nicht unterstützt.|Keine Problemumgehung.|  
|\_ismbcalnum \_ismbcalnum\_l \_ismbcalpha \_ismbcalpha\_l \_ismbcdigit \_ismbcdigit\_l \_ismbcgraph \_ismbcgraph\_l \_ismbchira \_ismbchira\_l \_ismbckata \_ismbckata\_l \_ismbcl0 \_ismbcl0\_l \_ismbcl1 \_ismbcl1\_l \_ismbcl2 \_ismbcl2\_l \_ismbclegal \_ismbclegal\_l \_ismbclower \_ismbclower\_l \_ismbcprint \_ismbcprint\_l \_ismbcpunct \_ismbcpunct\_l \_ismbcspace \_ismbcspace\_l \_ismbcsymbol \_ismbcsymbol\_l \_ismbcupper \_ismbcupper\_l \_mbbtombc \_mbbtombc\_l \_mbbtype \_mbbtype\_l \_mbccpy \_mbccpy\_l \_mbccpy\_s \_mbccpy\_s\_l \_mbcjistojms \_mbcjistojms\_l \_mbcjmstojis \_mbcjmstojis\_l \_mbclen \_mbclen\_l \_mbctohira \_mbctohira\_l \_mbctokata \_mbctokata\_l \_mbctolower \_mbctolower\_l \_mbctombb \_mbctombb\_l \_mbctoupper \_mbctoupper\_l \_mbsbtype \_mbsbtype\_l \_mbscat \_mbscat\_l \_mbscat\_s \_mbscat\_s\_l \_mbschr \_mbschr\_l \_mbscmp \_mbscmp\_l \_mbscoll \_mbscoll\_l \_mbscpy \_mbscpy\_l \_mbscpy\_s \_mbscpy\_s\_l \_mbscspn \_mbscspn\_l \_mbsdec \_mbsdec\_l \_mbsicmp \_mbsicmp\_l \_mbsicoll \_mbsicoll\_l \_mbsinc \_mbsinc\_l \_mbslen \_mbslen\_l \_mbslwr \_mbslwr\_l \_mbslwr\_s \_mbslwr\_s\_l \_mbsnbcat \_mbsnbcat\_l \_mbsnbcat\_s \_mbsnbcat\_s\_l \_mbsnbcmp \_mbsnbcmp\_l \_mbsnbcnt \_mbsnbcnt\_l \_mbsnbcoll \_mbsnbcoll\_l \_mbsnbcpy \_mbsnbcpy\_l \_mbsnbcpy\_s \_mbsnbcpy\_s\_l \_mbsnbicmp \_mbsnbicmp\_l \_mbsnbicoll \_mbsnbicoll\_l \_mbsnbset \_mbsnbset\_l \_mbsnbset\_s \_mbsnbset\_s\_l \_mbsncat \_mbsncat\_l \_mbsncat\_s \_mbsncat\_s\_l \_mbsnccnt \_mbsnccnt\_l \_mbsncmp \_mbsncmp\_l \_mbsncoll \_mbsncoll\_l \_mbsncpy \_mbsncpy\_l \_mbsncpy\_s \_mbsncpy\_s\_l \_mbsnextc \_mbsnextc\_l \_mbsnicmp \_mbsnicmp\_l \_mbsnicoll \_mbsnicoll\_l \_mbsninc \_mbsninc\_l \_mbsnlen \_mbsnlen\_l \_mbsnset \_mbsnset\_l \_mbsnset\_s \_mbsnset\_s\_l \_mbspbrk \_mbspbrk\_l \_mbsrchr \_mbsrchr\_l \_mbsrev \_mbsrev\_l \_mbsset \_mbsset\_l \_mbsset\_s \_mbsset\_s\_l \_mbsspn \_mbsspn\_l \_mbsspnp \_mbsspnp\_l \_mbsstr \_mbsstr\_l \_mbstok \_mbstok\_l \_mbstok\_s \_mbstok\_s\_l \_mbsupr \_mbsupr\_l \_mbsupr\_s \_mbsupr\_s\_l is\_wctype|Multibyte\-Zeichenfolgen werden in Apps für die universelle Windows\-Plattform nicht unterstützt.|Verwenden Sie stattdessen Unicode\-Zeichenfolgen.|  
|\_pclose \_pipe \_popen \_wpopen|Die Pipe\-Funktionalität ist in Apps für die universelle Windows\-Plattform nicht verfügbar.|Keine Problemumgehung.|  
|\_resetstkoflw|Unterstützende Win32\-APIs sind für Apps für die universelle Windows\-Plattform nicht verfügbar.|Keine Problemumgehung.|  
|\_getsystime \_setsystime|Dies waren veraltete APIs in früheren CRT\-Versionen. Darüber hinaus kann ein Benutzer die Systemzeit in einer App für die universelle Windows\-Plattform aufgrund fehlender Berechtigungen nicht festlegen.|Um nur die Systemzeit zu erhalten, verwenden Sie die Win32\-API `GetSystemTime`. Die Systemzeit kann nicht festgelegt werden.|  
|\_environ \_putenv \_putenv\_s \_searchenv \_searchenv\_s \_dupenv\_s \_wputenv \_wputenv\_s \_wsearchenv getenv getenv\_s putenv \_wdupenv\_s \_wenviron \_wgetenv \_wgetenv\_s \_wsearchenv\_s tzset|Umgebungsvariablen sind für Apps für die universelle Windows\-Plattform nicht verfügbar.|Keine Problemumgehung. Verwenden Sie „\_tzset“ zum Festlegen der Zeitzone.|  
|\_loaddll \_getdllprocaddr \_unloaddll|Dies waren veraltete Funktionen in früheren CRT\-Versionen. Darüber hinaus können Benutzer DLL\-Dateien nur in demselben Anwendungspaket laden.|Verwenden Sie die Win32\-APIs `LoadPackagedLibrary`, `GetProcAddress` und `FreeLibrary` zum Laden und Verwenden verpackter DLL\-Dateien.|  
|\_wexecl \_wexecle \_wexeclp \_wexeclpe \_wexecv \_wexecve \_wexecvp \_wexecvpe \_execl \_execle \_execlp \_execlpe \_execv \_execve \_execvp \_execvpe \_spawnl \_spawnle \_spawnlp \_spawnlpe \_spawnv \_spawnve \_spawnvp \_spawnvpe \_wspawnl \_wspawnle \_wspawnlp \_wspawnlpe \_wspawnv \_wspawnve \_wspawnvp \_wspawnvpe \_wsystem execl execle execlp execlpe execv execve execvp execvpe spawnl spawnle spawnlp spawnlpe spawnv spawnve spawnvp spawnvpe system|Die Funktionalität ist in Apps für die universelle Windows\-Plattform nicht verfügbar. Eine App für die universelle Windows\-Plattform kann keine andere App für die universelle Windows\-Plattform oder eine Desktop\-App aufrufen.|Keine Problemumgehung.|  
|\_heapwalk \_heapadd \_heapchk \_heapset \_heapused|Diese Funktionen werden in der Regel bei der Arbeit mit dem Heap verwendet. Entsprechende Win32\-APIs werden in Apps für die universelle Windows\-Plattform jedoch nicht unterstützt. Zudem können Apps keine privaten Heaps mehr erstellen oder verwenden.|Keine Problemumgehung. Allerdings ist `_heapwalk` nur zu Debugzwecken in der DEBUG CRT verfügbar. Diese können nicht in Apps für die universelle Windows\-Plattform verwendet werden, die in den Windows Store hochgeladen werden.|  
  
 Die folgenden Funktionen sind in der CRT für Apps für die universelle Windows\-Plattform verfügbar, sollten aber nur verwendet werden, wenn die entsprechenden Win32\- oder [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-APIs nicht verwendet werden können, z. B. beim Portieren umfangreicher Codebasen.  
  
|||  
|-|-|  
|Einzelbyte\-Zeichenfolgenfunktionen, z. B. `strcat`, `strcpy`, `strlwr` usw.|Verwenden Sie für Ihre Apps für die universelle Windows\-Plattform ausschließlich Unicode, da alle Win32\- und [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-APIs, die verfügbar gemacht werden, nur Unicode\-Zeichensätze verwenden. Einzelbyte\-Funktionen wurden für die Portierung umfangreicher Codebasen beibehalten, sollten aber ansonsten vermieden werden, und es sollten stattdessen nach Möglichkeit die entsprechenden Breitzeichen\-Funktionen verwendet werden.|  
|Stream\-E\/A\- und Datei\-E\/A\-Funktionen auf niedriger Ebene, z. B. `fopen`, `open` usw.|Diese Funktionen sind synchron, was für Apps für die universelle Windows\-Plattform nicht empfohlen wird. Verwenden Sie in Ihren Apps für die universelle Windows\-Plattform asynchrone APIs, um Dateien zu öffnen, aus Dateien zu lesen und in Dateien zu schreiben, damit das Sperren des UI\-Threads verhindert wird. Beispiele für derartige APIs finden Sie in der `Windows::Storage::FileIO`\-Klasse.|  
  
## Windows 8.x Store\-Apps und Windows Phone 8.x\-Apps  
 Zusätzlich zu den zuvor erwähnten APIs sind die folgenden APIs in Windows 8.x Store\-Apps und Windows Phone 8.x\-Apps nicht verfügbar.  
  
||||  
|-|-|-|  
|\_beginthread \_beginthreadex \_endthread \_endthreadex|Threading\-Win32\-APIs sind in Windows 8.x Store\-Apps nicht verfügbar.|Verwenden Sie stattdessen `Windows Runtime Windows::System::Threading::ThreadPool` oder `concurrency::task`.|  
|\_chdir \_wchdir \_getcwd \_getdcwd \_wgetcwd \_wgetdcwd|Das Konzept des Arbeitsverzeichnisses gilt nicht für Windows 8.x Store\-Apps.|Verwenden Sie stattdessen vollständige Pfade.|  
|\_getpid|Diese Funktion war in früheren Versionen der CRT veraltet.|Verwenden Sie die Win32\-API `GetCurrentProcessId()`.|  
|\_isleadbyte\_l \_ismbbalnum, \_ismbbalnum\_l, \_ismbbalpha, \_ismbbalpha \_ismbbalpha\_l \_ismbbgraph \_ismbbgraph\_l \_ismbbkalnum \_ismbbkalnum\_l \_ismbbkana \_ismbbkana\_l \_ismbbkprint \_ismbbkprint\_l \_ismbbkpunct \_ismbbkpunct\_l \_ismbblead \_ismbblead\_l \_ismbbprint \_ismbbprint\_l \_ismbbpunct \_ismbbpunct\_l \_ismbbtrail \_ismbbtrail\_l \_ismbslead \_ismbslead\_l \_ismbstrail \_ismbstrail\_l \_mbsdup isleadbyte|Multibyte\-Zeichenfolgen werden in Windows 8.x Store\-Apps nicht unterstützt.|Verwenden Sie stattdessen Unicode\-Zeichenfolgen.|  
|\_tzset|Umgebungsvariablen sind für Windows 8.x Store\-Apps nicht verfügbar.|Keine Problemumgehung.|  
|\_get\_heap\_handle, \_heapmin|Entsprechende Win32\-APIs werden in Windows 8.x Store\-Apps nicht unterstützt. Zudem können Apps keine privaten Heaps mehr erstellen.|Keine Problemumgehung. Allerdings ist `_get_heap_handle` nur zu Debugzwecken in der DEBUG CRT verfügbar.|