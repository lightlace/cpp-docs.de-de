---
title: Linkerunterstützung für verzögertes Laden von DLLs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aea4ca6d5391f71f27d59d0192fcf1f832dd6702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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