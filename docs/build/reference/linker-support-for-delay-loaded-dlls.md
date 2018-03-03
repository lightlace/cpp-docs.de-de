---
title: "Linkerunterstützung für verzögertes Laden von DLLs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83e75df963889730e4514c38d0551af241a788fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Linkerunterstützung für verzögertes Laden von DLLs
Der Visual C++-Linker unterstützt jetzt das verzögerte Laden von DLLs. Dies entlastet Sie das Windows SDK-Funktionen verwenden, müssen **LoadLibrary** und **GetProcAddress** implementieren verzögertes Laden von DLLs.  
  
 Vor Visual C++ 6.0 war die einzige Möglichkeit zum Laden einer DLL zur Laufzeit mit **LoadLibrary** und **GetProcAddress**; das Betriebssystem lädt die DLL Wenn die ausführbare Datei oder DLL mit dem es geladen wurde.  
  
 Beginnen mit dem Visual C++ 6.0 beim statisch mit einer DLL verknüpfen, enthält der Linker Optionen verzögert das Laden der DLL, bis die Anwendung in dieser DLL eine Funktion aufruft.  
  
 Eine Anwendung kann verzögert werden. Laden Sie eine DLL mit der [/DELAYLOAD (Laden von Import Verzögerung)](../../build/reference/delayload-delay-load-import.md) (Linkeroption) mit einer Hilfsfunktion (standardmäßige Implementierung von Visual C++ bereitgestellten). Die Hilfsfunktion lädt die DLL zur Laufzeit durch Aufrufen von **LoadLibrary** und **GetProcAddress** für Sie.  
  
 Verzögertes Laden einer DLL, wenn sollten Sie Folgendes berücksichtigen:  
  
-   Das Programm kann nicht auf eine Funktion in der DLL aufrufen.  
  
-   Eine Funktion in der DLL kann nicht bis spät im Ausführung des Programms aufgerufen wird.  
  
 Das verzögerte Laden einer DLL kann angegeben werden, während der Erstellung entweder ein. EXE-Datei oder. DLL-Projekt. EIN. DLL-Projekt, das das Laden von DLLs für eine oder mehrere verzögert sollten nicht selbst einen verzögert geladene Einstiegspunkt in Dllmain aufrufen.  
  
 Die folgenden Themen beschreiben das verzögerte Laden von DLLs:  
  
-   [Festlegen von DLLs für verzögertes Laden](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [Explizites Entladen einer verzögert geladenen DLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [Laden aller Importe für eine verzögert geladene DLL](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [Binden von Importen](../../build/reference/binding-imports.md)  
  
-   [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)  
  
-   [Sichern von verzögert geladenen Importen](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [Beschränkungen für das verzögerte Laden von DLLs](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [Die Hilfsfunktion](understanding-the-helper-function.md)  
  
-   [Entwickeln eigener Hilfsfunktionen](../../build/reference/developing-your-own-helper-function.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../../build/dlls-in-visual-cpp.md)   
 [Verknüpfen](../../build/reference/linking.md)