---
title: Modulzustände einer regulären MFC DLL dynamisch mit MFC verknüpfte | Microsoft-Dokumentation
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
ms.openlocfilehash: d458c445930896fb04cb339c7191f649be542faf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717027"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>Modulzustände einer regulären MFC DLL dynamisch mit MFC verknüpften

Die Möglichkeit, eine reguläre MFC-DLL dynamisch mit MFC-DLL zu verknüpfen, können einige Konfigurationen, die sehr kompliziert sind. Beispielsweise können eine reguläre MFC-DLL und die ausführbare Datei, die sie verwendet beide dynamisch die MFC-DLL und alle MFC-Erweiterungs-DLLs verknüpfen.

Diese Konfiguration stellt ein Problem in Bezug auf die globalen MFC-Daten, z. B. der Zeiger auf die aktuelle `CWinApp` Objekt und Handlezuordnungen.

Vor MFC, Version 4.0 diese globalen Daten in der MFC-DLL selbst befand und wurde von allen Modulen im Prozess freigegeben. Da jeder Prozess eine Win32-DLL eine eigene Kopie der DLL Daten abruft, bereitgestellt dieses Schema eine einfache Möglichkeit zum Nachverfolgen von pro-Prozess Daten an. Darüber hinaus, da das AFXDLL-Modell, das davon ausgeht, wäre, würde nur eine `CWinApp` Objekt und nur einen Satz von Handlezuordnungen im Prozess, diese Elemente in der MFC-DLL selbst nachverfolgt werden.

Aber mit der Möglichkeit, eine reguläre MFC-DLL dynamisch mit MFC-DLL zu verknüpfen, ist es jetzt möglich, dass zwei oder mehr `CWinApp` Objekte in einem Prozess – und auch mindestens zwei Sätze von Handlezuordnungen. Wie mitverfolgen MFC, welche sie verwenden sollten?

Die Lösung besteht darin, jedes Modul (Anwendung oder regulären MFC-DLL) Geben Sie eine eigene Kopie dieser globalen Zustandsinformationen. Daher einen Aufruf von **AfxGetApp** in der regulären MFC-DLL gibt einen Zeiger auf die `CWinApp` Objekt in der DLL, die nicht zu derjenigen in der ausführbaren Datei. Dieser modulspezifischen Kopie der globalen MFC-Daten wird als Modulstatus bezeichnet und ist in [MFC technischer Hinweis 58](../mfc/tn058-mfc-module-state-implementation.md).

Die Fensterprozedur der MFC-allgemeine wechselt automatisch in den richtigen Zustand, sodass Sie nicht in jeder Meldungshandler, der in der regulären MFC DLL implementiert kümmern müssen. Aber wenn die ausführbare Datei in der regulären MFC-DLL aufgerufen wird, müssen Sie explizit den aktuellen Modulstatus, die für die DLL festlegen. Verwenden Sie hierzu die **AFX_MANAGE_STATE** Makro in jeder Funktion, die aus der DLL exportiert. Dies erfolgt durch die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen hinzufügen:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

- [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls-overview.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)