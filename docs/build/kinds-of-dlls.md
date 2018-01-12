---
title: Arten von DLLs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47ce4a9264a59f88f22cd40bc3b6d6620c9702c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="kinds-of-dlls"></a>Arten von DLLs
Anhand der Informationen unter diesem Thema können Sie feststellen, welche Art von DLL erstellt werden sollte.  
  
##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a>Verschiedene Arten von DLLs verfügbar  
 Mit Visual C++ können Sie Win32-DLLs in C oder C++ erstellen, die nicht die MFC-Bibliothek (Microsoft Foundation Class Library) verwenden. Um ein MFC-fremdes DLL-Projekt zu erstellen, verwenden Sie den Win32-Anwendungs-Assistenten.  
  
 Die MFC-Bibliothek selbst ist über den MFC-DLL-Assistenten entweder in Static Link Libraries oder in einer Reihe von DLLs verfügbar. Wenn die DLL MFC verwendet, unterstützt Visual C++ drei verschiedene Szenarien für die DLL-Entwicklung:  
  
-   Erstellen einer reguläres MFC-DLL, die statisch mit MFC verknüpft wird  
  
-   Erstellen einer reguläres MFC-DLL, die dynamisch mit MFC verknüpft wird  
  
-   Erstellen einer MFC-Erweiterungs-DLL, die immer dynamisch mit MFC verknüpft wird  
  
### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [MFC-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC extension DLLs: Overview (MFC-Erweiterungs-DLLs: Übersicht)](../build/extension-dlls-overview.md)  
  
-   [Welche Art von DLL-Datei verwenden](#_core_which_kind_of_dll_to_use)  
  
##  <a name="_core_which_kind_of_dll_to_use"></a>Welche Art von DLL verwendet werden sollte  
 Wenn die DLL nicht MFC verwendet, erstellen Sie mit Visual C++ eine MFC-fremde Win32-DLL. Das (statische oder dynamische) Verknüpfen einer DLL mit MFC beansprucht erhebliche Festplattenspeicher- und Arbeitsspeicherkapazitäten. Sie sollten eine Verknüpfung mit MFC nur dann vorsehen, wenn MFC von der DLL auch tatsächlich verwendet wird.  
  
 Wenn die DLL MFC verwendet werden und von MFC oder MFC-Anwendungen verwendet werden wird, müssen Sie erstellen eine reguläre MFC-DLL, die dynamisch mit MFC verknüpft oder eine reguläre MFC-DLL, die statisch mit MFC verknüpft wird. In den meisten Fällen möchten Sie möglicherweise eine reguläre MFC-DLL zu verwenden, die dynamisch mit MFC verknüpft wird, da die Dateigröße der DLL wird wesentlich kleiner ist und die einsparungen im Arbeitsspeicher von der Verwendung der gemeinsam genutzten MFC-Version können sehr erheblich sein. Bei einer statischen Verknüpfung mit MFC wird die DLL größer, und es wird möglicherweise mehr Arbeitsspeicher benötigt, da eine eigene Kopie des MFC-Bibliothekscodes geladen wird.  
  
 Das Erstellen einer DLL, die dynamisch mit MFC verknüpft wird, verläuft schneller als das Erstellen einer DLL, die statisch mit MFC verknüpft wird, da MFC selbst in diesem Fall nicht verknüpft werden muss. Dies trifft insbesondere auf Debugbuilds zu, bei denen der Linker die Debuginformationen komprimieren muss. Durch das Verknüpfen mit einer DLL, die bereits Debuginformationen enthält, bleiben innerhalb der DLL weniger Debuginformationen zu komprimieren.  
  
 Ein Nachteil der dynamischen Verknüpfung mit MFC besteht darin, dass Sie die gemeinsam genutzten DLLs, nämlich Mfcx0.dll und Msvcrxx.dll (oder ähnliche Dateien), zusammen mit der DLL verteilen müssen. Die MFC-DLLs können frei verteilt werden, sie müssen jedoch noch im Setupprogramm installiert werden. Darüber hinaus müssen Sie Msvcrxx.dll mitliefern. Diese Datei enthält die C-Laufzeitbibliothek, die sowohl vom Programm als auch von den MFC-DLLs selbst verwendet wird.  
  
 Wenn Ihre DLL nur von ausführbaren MFC-Dateien verwendet werden, müssen Sie die Wahl zwischen dem Erstellen einer regulären MFC-DLL oder eine MFC-Erweiterungs-DLL. Wenn Ihre DLL wiederverwendbare von bestehenden MFC-Klassen abgeleitete Klassen implementiert oder MFC abgeleitete Objekte zwischen Anwendung und DLL übergeben werden müssen, müssen Sie eine MFC-Erweiterungs-DLL erstellen.  
  
 Wenn die DLL dynamisch mit MFC verknüpft wird, können die MFC-DLLs zusammen mit der DLL verteilt werden. Diese Architektur ist besonders geeignet, wenn die Klassenbibliothek von mehreren ausführbaren Dateien gemeinsam genutzt wird, um Festplattenspeicher zu sparen und die Arbeitsspeicherauslastung zu minimieren.  
  
 Vor Version 4.0 unterstützte Visual C++ nur zwei Arten von DLLs, die MFC verwendeten: USRDLLs und AFXDLLs. Reguläre, statisch mit MFC verknüpfte MFC-DLLs haben dieselben Merkmale wie die frühere USRDLL. MFC-Erweiterungs-DLLs haben dieselben Merkmale wie die früheren AFXDLLs.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [MFC-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC extension DLLs: Overview (MFC-Erweiterungs-DLLs: Übersicht)](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)