---
title: Modulzustände einer regulären MFC-DLL dynamisch mit MFC verknüpfte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d15f533473ebe90d6d105ddeb57dcdcddd90e87b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>Modulzustände einer regulären MFC-DLL dynamisch mit MFC verknüpften
Die Möglichkeit, eine reguläre MFC-DLL dynamisch mit MFC-DLL verknüpfen ermöglicht, dass einige Konfigurationen, die sehr kompliziert sind. Beispielsweise können eine reguläre MFC-DLL und die ausführbare Datei, die verwendet werden beide dynamisch mit MFC-DLL und alle MFC-Erweiterungs-DLLs verknüpfen.  
  
 Diese Konfiguration stellt ein Problem im Hinblick auf die globalen MFC-Daten, z. B. den Zeiger auf den aktuellen `CWinApp` Objekt und Handlezuordnungen.  
  
 Vor MFC, Version 4.0 diese globalen Daten in der MFC-DLL selbst befand und wurde von allen Modulen im Prozess gemeinsam verwendet. Da jeder Prozess eine Win32-DLL auf eine eigene Kopie der DLL Daten abruft, bereitgestellten dieses Schema eine einfache Möglichkeit zum Nachverfolgen von Daten pro Prozess. Darüber hinaus da AFXDLL-Modell davon ausgegangen, dass es nur eine wäre `CWinApp` Objekt und nur ein Satz von Handlezuordnungen im Prozess, diese Elemente in der MFC-DLL selbst nachverfolgt werden.  
  
 Aber mit der Fähigkeit, eine reguläre MFC-DLL dynamisch mit MFC-DLL zu verknüpfen, ist es jetzt möglich, dass zwei oder mehr `CWinApp` Objekte in einem Prozess – und auch mindestens zwei Sätze von Handlezuordnungen. Wie MFC nachverfolgen, welche von verwendet werden sollte?  
  
 Die Lösung besteht darin, jedes Modul (Anwendung oder reguläre MFC-DLL) Geben Sie eine eigene Kopie dieser globalen Zustandsinformationen. Daher einen Aufruf von **AfxGetApp** in reguläre MFC-DLL gibt einen Zeiger auf die `CWinApp` Objekt in der DLL, die nicht dem GUID in die ausführbare Datei. Dieser pro Modul Kopie der globalen MFC-Daten wird als eine Modulstatus bezeichnet und ist in der beschriebenen [MFC technischer Hinweis 58](../mfc/tn058-mfc-module-state-implementation.md).  
  
 Die Fensterprozedur der MFC-common wechselt automatisch in die richtige Modulstatus, damit Sie nicht in jeder in der regulären MFC-DLL implementiert Meldungshandler kümmern müssen. Aber wenn Ihre ausführbare Datei in der regulären MFC-DLL aufgerufen wird, müssen Sie zum expliziten Festlegen von den aktuellen Zustand des Moduls auf das Objekt für die DLL. Verwenden Sie hierzu die **AFX_MANAGE_STATE** Makro in jeder Funktion aus der DLL exportierten. Dies erfolgt durch die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen hinzufügen:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)