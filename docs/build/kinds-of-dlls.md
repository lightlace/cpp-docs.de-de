---
title: "Arten von DLLs"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], MFC"
  - "DLLs [C++], Typen"
  - "MFC-DLLs [C++], Typen"
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Arten von DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Anhand der Informationen unter diesem Thema können Sie feststellen, welche Art von DLL erstellt werden sollte.  
  
##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> Verfügbare DLL\-Typen  
 Mit Visual C\+\+ können Sie Win32\-DLLs in C oder C\+\+ erstellen, die nicht die MFC\-Bibliothek \(Microsoft Foundation Class Library\) verwenden.  Um ein MFC\-fremdes DLL\-Projekt zu erstellen, verwenden Sie den Win32\-Anwendungs\-Assistenten.  
  
 Die MFC\-Bibliothek selbst ist über den MFC\-DLL\-Assistenten entweder in Static Link Libraries oder in einer Reihe von DLLs verfügbar.  Wenn die DLL MFC verwendet, unterstützt Visual C\+\+ drei verschiedene Szenarien für die DLL\-Entwicklung:  
  
-   Erstellen einer regulären DLL, die statisch mit MFC verknüpft wird  
  
-   Erstellen einer regulären DLL, die dynamisch mit MFC verknüpft wird  
  
-   Erstellen einer MFC\-Erweiterungs\-DLL, die immer dynamisch mit MFC verknüpft wird  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [MFC\-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Erweiterungs\-DLLs: Übersicht](../build/extension-dlls-overview.md)  
  
-   [Zu verwendender DLL\-Typ](#_core_which_kind_of_dll_to_use)  
  
##  <a name="_core_which_kind_of_dll_to_use"></a> Welche Art von DLL verwendet werden sollte  
 Wenn die DLL nicht MFC verwendet, erstellen Sie mit Visual C\+\+ eine MFC\-fremde Win32\-DLL.  Das \(statische oder dynamische\) Verknüpfen einer DLL mit MFC beansprucht erhebliche Festplattenspeicher\- und Arbeitsspeicherkapazitäten.  Sie sollten eine Verknüpfung mit MFC nur dann vorsehen, wenn MFC von der DLL auch tatsächlich verwendet wird.  
  
 Wenn die DLL MFC verwendet und selbst von MFC\-Anwendungen oder MFC\-fremden Anwendungen verwendet wird, müssen Sie eine dynamisch oder statisch mit MFC verknüpfte reguläre DLL erstellen.  In den meisten Fällen werden Sie wahrscheinlich eine dynamisch mit MFC verknüpfte reguläre DLL verwenden, da die DLL in diesem Fall viel kleiner ist und auch der Arbeitsspeicher bei einer gemeinsam genutzten MFC\-Version deutlich entlastet werden kann.  Bei einer statischen Verknüpfung mit MFC wird die DLL größer, und es wird möglicherweise mehr Arbeitsspeicher benötigt, da eine eigene Kopie des MFC\-Bibliothekscodes geladen wird.  
  
 Das Erstellen einer DLL, die dynamisch mit MFC verknüpft wird, verläuft schneller als das Erstellen einer DLL, die statisch mit MFC verknüpft wird, da MFC selbst in diesem Fall nicht verknüpft werden muss.  Dies trifft insbesondere auf Debugbuilds zu, bei denen der Linker die Debuginformationen komprimieren muss.  Durch das Verknüpfen mit einer DLL, die bereits Debuginformationen enthält, bleiben innerhalb der DLL weniger Debuginformationen zu komprimieren.  
  
 Ein Nachteil der dynamischen Verknüpfung mit MFC besteht darin, dass Sie die gemeinsam genutzten DLLs, nämlich Mfcx0.dll und Msvcrxx.dll \(oder ähnliche Dateien\), zusammen mit der DLL verteilen müssen.  Die MFC\-DLLs können frei verteilt werden, sie müssen jedoch noch im Setupprogramm installiert werden.  Darüber hinaus müssen Sie Msvcrxx.dll mitliefern. Diese Datei enthält die C\-Laufzeitbibliothek, die sowohl vom Programm als auch von den MFC\-DLLs selbst verwendet wird.  
  
 Wenn Ihre DLL nur von ausführbaren MFC\-Dateien verwendet wird, haben Sie die Wahl zwischen dem Erstellen einer regulären DLL oder einer Erweiterungs\-DLL.  Wenn die DLL wieder verwendbare, von bestehenden MFC\-Klassen abgeleitete Klassen implementiert, oder wenn Sie von MFC abgeleitete Objekte zwischen Anwendung und DLL übergeben, müssen Sie eine Erweiterungs\-DLL erstellen.  
  
 Wenn die DLL dynamisch mit MFC verknüpft wird, können die MFC\-DLLs zusammen mit der DLL verteilt werden.  Diese Architektur ist besonders geeignet, wenn die Klassenbibliothek von mehreren ausführbaren Dateien gemeinsam genutzt wird, um Festplattenspeicher zu sparen und die Arbeitsspeicherauslastung zu minimieren.  
  
 Vor Version 4.0 unterstützte Visual C\+\+ nur zwei Arten von DLLs, die MFC verwendeten: USRDLLs und AFXDLLs.  Reguläre, statisch mit MFC verknüpfte DLLs haben dieselben Merkmale wie die frühere USRDLL.  MFC\-Erweiterungs\-DLLs haben dieselben Merkmale wie die früheren AFXDLLs.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [MFC\-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Erweiterungs\-DLLs: Übersicht](../build/extension-dlls-overview.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)