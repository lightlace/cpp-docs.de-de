---
title: Die Hilfsfunktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54ed331022c29ecc47d61bbcccbfac82000cb235
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-the-helper-function"></a>Die Hilfsfunktion
Die Hilfsfunktion für das verzögerte Laden Linker unterstützt wird, was tatsächlich die DLL zur Laufzeit geladen wird. Sie können die Hilfsfunktion, um das Verhalten anpassen, indem Sie eine eigene Funktion schreiben, und verknüpfen es mit Ihrer Anwendung anstelle der angegebenen Hilfsfunktion in "delayimp.lib" ändern. Eine Hilfsfunktion ist für alle verzögert geladene DLLs.  
  
 Sie können eine eigene Version der Hilfsfunktion bereitstellen, wenn spezifischen Verarbeitung basierend auf den Namen der DLL oder importiert werden sollen.  
  
 Die Hilfsfunktion führt die folgenden Aktionen aus:  
  
-   Überprüft die gespeicherte Handle für die Bibliothek aus, um festzustellen, ob sie bereits geladen wurde  
  
-   Aufrufe **LoadLibrary** zum Laden der DLL versuchen  
  
-   Aufrufe **GetProcAddress** versucht, die Adresse der Prozedur abrufen  
  
-   Gibt die Verzögerung importieren Thunk, um der neu geladenen Einstiegspunkt aufzurufen.  
  
 Die Hilfsfunktion kann Benachrichtigungshook im Programm nach jedem der folgenden Aktionen Rückruf:  
  
-   Wenn die Hilfsfunktion gestartet wird  
  
-   Unmittelbar vor dem **LoadLibrary** in die Hilfsfunktion aufgerufen wird  
  
-   Unmittelbar vor dem **GetProcAddress** in die Hilfsfunktion aufgerufen wird  
  
-   Wenn der Aufruf von **LoadLibrary** Fehler in der Hilfsfunktion  
  
-   Wenn der Aufruf von **GetProcAddress** Fehler in der Hilfsfunktion  
  
-   Nach dem Hilfsprogramm Funktion erfolgt Verarbeitung  
  
 Jede dieser Punkte verknüpfen kann einen Wert, der normalen Verarbeitung der Hilfsfunktion auf eine Weise mit Ausnahme der Rückkehr zum Verzögerung Import Thunk dahingehend geändert, wird zurückgegeben.  
  
 Der Standard-Hilfscode verwendbaren in Delayhlp.cpp und Delayimp.h (im Vc\include) und ist in "delayimp.lib" (in Vc\lib) kompiliert. Sie müssen diese Bibliothek in den Kompilierungen eingeschlossen, es sei denn, Sie eine eigene Hilfsfunktion schreiben.  
  
 Die folgenden Themen beschreiben die Hilfsfunktion:  
  
-   [Änderungen an der Hilfsfunktion für das verzögerte Laden von DLLs seit Visual C++ 6.0](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [Aufrufkonventionen, Parameter und Rückgabetyp](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [Struktur- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md)  
  
-   [Berechnen der erforderlichen Werte](../../build/reference/calculating-necessary-values.md)  
  
-   [Entladen einer verzögert geladenen DLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)