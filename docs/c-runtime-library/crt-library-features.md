---
title: "CRT-Bibliotheksfunktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSVCR71.dll"
  - "Bibliotheken [C++], Multithreaded"
  - "Bibliotheksdateien, Laufzeit"
  - "LIBCMT.lib"
  - "LIBCP.lib"
  - "LIBCPMT.lib"
  - "Laufzeitbibliotheken, C"
  - "CRT, Releaseversionen"
  - "MSVCP71.dll"
  - "LIBC.lib"
  - "Bibliotheken [C++]"
  - "Bibliotheken [C++], Laufzeit"
  - "Linken [C++], Bibliotheken"
ms.assetid: a889fd39-807d-48f2-807f-81492612463f
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# CRT-Bibliotheksfunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden die verschiedenen LIB\-Dateien erläutert, die die C\-Laufzeitbibliotheken sowie ihre zugeordneten Compileroptionen und Präprozessordirektiven bilden.  
  
## C\-Laufzeitbibliotheken \(CRT\)  
 Die CRT \(C Run\-time Library, C\-Laufzeitbibliothek\) ist Bestandteil der C\+\+\-Standardbibliothek, die die ISO C99\-Standardbibliothek umfasst. Die Visual C\+\+\-Bibliotheken, die die CRT implementieren, unterstützen die Entwicklung von systemeigenem Code und Mischungen aus systemeigenem und verwaltetem Code sowie reinen verwalteten Code für die .NET\-Entwicklung. Alle Versionen der CRT unterstützen Multithreaded\-Entwicklung. Die meisten Bibliotheken unterstützen sowohl statisches Linken \(Binden\), um die Bibliothek direkt in Ihren Code einzubinden, oder dynamisches Linken, damit in Ihrem Code allgemeine DLL\-Dateien verwendet werden können.  
  
 In Visual Studio 2015 wurde die CRT in neue Binärdateien umgestaltet. Die UCRT \(Universal CRT\) enthält die Funktionen und globalen Elemente, die durch die Standard\-C99 CRT\-Bibliothek exportiert werden. Die UCRT ist nun eine Windows\-Komponente und wird als Bestandteil von Windows 10 bereitgestellt. Die statische Bibliothek, die DLL\-Importbibliothek und die Headerdateien für die UCRT sind jetzt im Windows 10 SDK zu finden. Wenn Sie Visual C\+\+ installieren, installiert Visual Studio\-Setup die Teilmenge des Windows 10 SDKs, die erforderlich ist, um die UCRT verwenden zu können. Sie können die UCRT unter jeder Version von Windows verwenden, die von Visual Studio 2015 unterstützt wird. Sie können die URCT über vcredist für unterstützte Versionen von Windows neu verteilen, die nicht Windows 10 sind. Weitere Informationen finden Sie unter [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
 In der folgenden Tabelle sind die Bibliotheken aufgelistet, die die UCRT implementieren.  
  
|Bibliothek|Zugehörige DLL|Eigenschaften|Option|Präprozessordirektiven|  
|----------------|--------------------|-------------------|------------|----------------------------|  
|libucrt.lib|Keine|Bindet die UCRT statisch in Ihren Code ein.|**\/MT**|\_MT|  
|libucrtd.lib|Keine|Die Debugversion der UCRT für statisches Linken. Nicht neu verteilbar.|**\/MTd**|\_DEBUG, \_MT|  
|ucrt.lib|ucrtbase.dll|DLL\-Importbibliothek für die UCRT.|**\/MD**|\_MT, \_DLL|  
|ucrtd.lib|ucrtbased.dll|DLL\-Importbibliothek für die Debugversion der UCRT. Nicht neu verteilbar.|**\/MDd**|\_DEBUG, \_MT, \_DLL|  
  
 Die vcruntime\-Bibliothek enthält Visual C\+\+\-CRT\-implementierungsspezifischen Code, beispielsweise Ausnahmebehandlungs\- und Debugunterstützung, Laufzeitprüfungen und Typinformationen, Implementierungsdetails und bestimmte erweiterte Bibliotheksfunktionen. Diese Bibliothek ist speziell entsprechend der Version des verwendeten Compilers.  
  
 In der folgenden Tabelle sind die Bibliotheken aufgelistet, die die vcruntime\-Bibliothek implementieren.  
  
|Bibliothek|Zugehörige DLL|Eigenschaften|Option|Präprozessordirektiven|  
|----------------|--------------------|-------------------|------------|----------------------------|  
|libvcruntime.lib|Keine|Wird statisch in Ihren Code eingebunden.|**\/MT**|\_MT|  
|libvcruntimed.lib|Keine|Die Debugversion für statisches Linken. Nicht neu verteilbar.|**\/MTd**|\_MT, \_DEBUG|  
|vcruntime.lib|vcruntime\<Version\>.dll|DLL\-Importbibliothek für die vcruntime.|**\/MD**|\_MT, \_DLL|  
|vcruntimed.lib|vcruntime\<Version\>d.dll|DLL\-Importbibliothek für die Debug\-vcruntime. Nicht neu verteilbar.|**\/MDd**|\_DEBUG, \_MT, \_DLL|  
  
 Der Code, von dem die CRT initialisiert wird, befindet sich in einer von mehreren Bibliotheken, je nachdem, ob die CRT\-Bibliothek statisch oder dynamisch gebunden wird oder als systemeigener, verwalteter oder gemischter Code vorliegt. Dieser Code verwaltet den CRT\-Start, die interne threadbezogene Dateninitialisierung und die Beendigung. Der Code ist speziell entsprechend der Version des verwendeten Compilers. Diese Bibliothek wird immer statisch gebunden, auch wenn eine dynamisch gebundene UCRT verwendet wird.  
  
 In der folgenden Tabelle sind die Bibliotheken aufgelistet, die die CRT\-Initialisierung und \-Beendigung implementieren.  
  
|Bibliothek|Eigenschaften|Option|Präprozessordirektiven|  
|----------------|-------------------|------------|----------------------------|  
|libcmt.lib|Bindet den systemeigenen CRT\-Startcode statisch in Ihren Code ein.|**\/MT**|\_MT|  
|libcmtd.lib|Bindet die Debugversion des systemeigenen CRT\-Startcode statisch ein. Nicht neu verteilbar.|**\/MTd**|\_DEBUG, \_MT|  
|msvcrt.lib|Statische Bibliothek für den systemeigenen CRT\-Startcode zur Verwendung mit DLL UCRT und vcruntime.|**\/MD**|\_MT, \_DLL|  
|msvcrtd.lib|Statische Bibliothek für die Debugversion des systemeigenen CRT\-Startcodes zur Verwendung mit DLL UCRT und vcruntime. Nicht neu verteilbar.|**\/MDd**|\_DEBUG, \_MT, \_DLL|  
|msvcmrt.lib|Statische Bibliothek für den gemischten systemeigenen und verwalteten CRT\-Startcode zur Verwendung mit DLL UCRT und vcruntime.|**\/clr**||  
|msvcmrtd.lib|Statische Bibliothek für die Debugversion des gemischten systemeigenen und verwalteten CRT\-Startcodes zur Verwendung mit DLL UCRT und vcruntime. Nicht neu verteilbar.|**\/clr**||  
|msvcurt.lib|Statische Bibliothek für die ausschließlich verwaltete CRT.|**\/clr:pure**||  
|msvcurtd.lib|Statische Bibliothek für die Debugversion der ausschließlich verwalteten CRT. Nicht neu verteilbar.|**\/clr:pure**||  
  
 Wenn Sie Ihr Programm über die Befehlszeile ohne eine Compileroption linken \(binden\), die die C\-Laufzeitbibliothek angibt, verwendet der Linker die statisch gebundenen CRT\-Bibliotheken: „libcmt.lib“, „libvcruntime.lib“ und „libucrt.lib“.  
  
 Die Verwendung der statisch verknüpften CRT bedeutet, dass alle von der C\-Laufzeitbibliothek gespeicherten Zustandsinformationen für diese CRT\-Instanz lokal sind. Wenn Sie bei einer statisch gebundenen CRT [strtok, \_strtok\_l, wcstok, \_wcstok\_l, \_mbstok, \_mbstok\_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) verwenden, ist die Position des `strtok`\-Parsers nicht mit dem `strtok`\-Zustand verbunden, der im Code des gleichen Prozesses \(jedoch in einer anderen DLL oder einem EXE\) verwendet wird, der mit einer anderen Instanz der statischen CRT verknüpft ist. Im Gegensatz dazu teilen dynamisch verknüpfte CRT den Zustand für sämtlichen Code innerhalb eines Prozesses, der dynamisch mit der CRT verknüpft ist. Bei den neuen sichereren Versionen dieser Funktionen wie `strtok_s` tritt dieses Problem nicht auf.  
  
 Da eine durch das Verknüpfen mit einer statischen CRT erstellten DLL ihren eigenen CRT\-Zustand besitzt, wird in einer DLL das statische Verknüpfen mit einer CRT nicht empfohlen, es sei denn, dass die daraus resultierenden Konsequenzen verstanden werden und erwünscht sind. Wenn Sie z. B. [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md) in einer ausführbaren Datei aufrufen, die die DLL lädt, die mit ihrer eigenen statischen CRT verknüpft ist, werden alle vom Code in der DLL generierten Hardwareausnahmen vom Konvertierungsprogramm nicht erfasst, wohingegen die vom Code in der Hauptausführungsdatei generierten Hardwareausnahmen erfasst werden.  
  
 Wenn Sie den **\/clr**\-Compilerschalter verwenden, wird der Code mit der statischen Bibliothek msvcmrt.lib verknüpft. Die statische Bibliothek stellt einen Proxy zwischen dem verwalteten Code und der systemeigenen CRT bereit. Die statisch verknüpfte CRT \(Option **\/MT** oder Option **\/MTd**\) können Sie nicht mit **\/clr** verwenden. Verwenden Sie stattdessen die dynamisch verknüpften Bibliotheken \(**\/MD** oder **\/MDd**\).  
  
 Wenn Sie den **\/clr:pure**\-Compilerschalter verwenden, wird der Code mit der statischen Bibliothek msvcurt.lib verknüpft. Wie bei **\/clr** können Sie keine Verknüpfung mit der statisch verknüpften Bibliothek erstellen.  
  
 Weitere Informationen zum Verwenden der CRT mit **\/clr** finden Sie unter [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md). Informationen zu **\/clr:pure** finden Sie unter [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Um eine Debugversion der Anwendung zu erstellen, muss das [\_DEBUG](../c-runtime-library/debug.md)\-Flag definiert sein und die Anwendung muss mit einer Debugversion von einer dieser Bibliotheken verknüpft sein. Weitere Informationen zur Verwendung der Debugversionen der Bibliotheksdateien finden Sie unter [CRT\-Debugverfahren](../Topic/CRT%20Debugging%20Techniques.md).  
  
 Diese Version der CRT ist nicht vollständig mit dem Standard C99 konform. Insbesondere der \<tgmath.h\>\-Header und die CX\_LIMITED\_RANGE\/FP\_CONTRACT\-Pragmamakros werden nicht unterstützt. Für bestimmte Elemente, etwa die Bedeutung von Parameterbezeichnern in Standard\-E\/A\-Funktionen, werden standardmäßig frühere Interpretationen verwendet. Sie können die \/Zc\-Compileroptionen für Konformität verwenden und Linkeroptionen angeben, um einige Aspekte der Bibliothekskonformität zu steuern.  
  
## C\+\+\-Standardbibliothek  
  
|C\+\+\-Standardbibliothek|Eigenschaften|Option|Präprozessordirektiven|  
|-------------------------------|-------------------|------------|----------------------------|  
|LIBCPMT.LIB|Multithreaded, statischer Link|**\/MT**|\_MT|  
|MSVCPRT.LIB|Multithreaded, dynamischer Link \(Importbibliothek für MSVCP\<Version\>.dll\)|**\/MD**|\_MT, \_DLL|  
|LIBCPMTD.LIB|Multithreaded, statischer Link|**\/MTd**|\_DEBUG, \_MT|  
|MSVCPRTD.LIB|Multithreaded, dynamischer Link \(Importbibliothek für MSVCP\<Version\>D.DLL\)|**\/MDd**|\_DEBUG, \_MT, \_DLL|  
  
 Wenn Sie eine Releaseversion des Projekts erstellen, wird abhängig von der ausgewählten Compileroption \(Multithreaded, DLL, \/clr\) eine der grundlegenden C\-Laufzeitbibliotheken \(LIBCMT.LIB, MSVCMRT.LIB, MSVCRT.LIB\) standardmäßig verknüpft. Wenn Sie eine der [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md) in Ihren Code einfügen, wird von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] eine C\+\+\-Standardbibliothek automatisch zur Kompilierzeit eingebunden. Zum Beispiel:  
  
```  
#include <ios>   
```  
  
## Welche Probleme gibt es, wenn in einer Anwendung mehrere CRT\-Version verwendet werden?  
 Wenn Sie über mehr als einer DLL oder EXE\-Dateien verfügen, dann verfügen Sie möglicherweise auch über mehr als eine CRT, unabhängig davon, ob Sie verschiedene Versionen von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] verwenden. Das statische Verknüpfen der CRT mit mehreren DLLs kann das gleiche Problem darstellen. Entwickler, bei denen dieses Problem mit statischen CRTs auftritt, sollen mit **\/MD** kompilieren, um die CRT\-DLL zu verwenden. Wenn Ihre DLLs CRT\-Ressourcen über die DLL\-Grenze hinaus übergeben, treten möglicherweise Probleme mit nicht übereinstimmenden CRTs auf, und Sie müssen Ihr Projekt mit Visual C\+\+ neu kompilieren.  
  
 Wenn das Programm mehr als eine CRT\-Version verwendet, muss beim Übergeben bestimmter CRT\-Objekte \(wie z. B. Dateihandles, Gebietsschemas und Umgebungsvariablen\) über DLL\-Grenzen hinweg sorgfältig vorgegangen werden. Weitere Informationen zu diesen Problemen und den jeweiligen Lösungsmöglichkeiten finden Sie unter [Potenzielle Fehler bei der Übergabe von CRT\-Objekten über DLL\-Grenzen](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).  
  
## Siehe auch  
 [C\-Laufzeitbibliotheksverweis](../c-runtime-library/c-run-time-library-reference.md)