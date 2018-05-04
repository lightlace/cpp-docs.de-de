---
title: Zum Auffinden einer DLL von Windows verwendeter Suchpfad | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- searching [C++], DLLs
- DLLs [C++], Windows search path
- Windows [C++], DLL search path
- known DLL searches [C++]
- locating DLLs
- finding DLLs
- search paths [C++]
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 166b5fccf6dd231029f79fede837909a49e7fc4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="search-path-used-by-windows-to-locate-a-dll"></a>Von Windows verwendeter Suchpfad zum Auffinden einer DLL
Sowohl bei der impliziten als auch bei der expliziten Verknüpfung, sucht Windows zuerst nach "bekannten DLLs", z. B. Kernel32.dll und User32.dll. Danach werden die DLLs von Windows in der folgenden Reihenfolge gesucht:  
  
1.  Das Verzeichnis, in dem sich das ausführbare Modul des aktuellen Prozesses befindet.  
  
2.  Das aktuelle Verzeichnis.  
  
3.  Das Systemverzeichnis von Windows. Die **GetSystemDirectory** Funktion ruft den Pfad dieses Verzeichnisses ab.  
  
4.  Das Windows-Verzeichnis. Die **GetWindowsDirectory** Funktion ruft den Pfad dieses Verzeichnisses ab.  
  
5.  Die in der PATH-Umgebungsvariablen aufgeführten Verzeichnisse.  
  
    > [!NOTE]
    >  Die LIBPATH-Umgebungsvariable wird nicht verwendet.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Gewusst wie: implizit mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Gewusst wie: die explizite Verknüpfung mit einer DLL](../build/linking-an-executable-to-a-dll.md#linking-explicitly)  
  
-   [Welche Verknüpfungsmethode ermitteln](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)