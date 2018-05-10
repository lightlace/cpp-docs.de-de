---
title: Beziehung zu der Programmiersprache C-API | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d06c4adfa5493929a24c233fa923451c7bf0f95
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="relationship-to-the-c-language-api"></a>Beziehung zum C-Sprachen-API
Die einzigen Merkmals, durch die die Microsoft Foundation Class (MFC)-Bibliothek abgesehen von anderen Klassenbibliotheken für Windows festgelegt ist die Zuordnung sehr nahe an die Windows-API, die in der Programmiersprache C geschrieben. Darüber hinaus können Sie in der Regel Aufrufe an die Klassenbibliothek frei mit direkten Aufrufen der Windows-API kombinieren. Ein direkter Zugriff gewährt impliziert, allerdings, dass der Klassen vollständiger Ersatz für diese API sind. Entwickler müssen immer noch gelegentlich, direkte Aufrufe an einige Windows-Funktionen, wie z. B. [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) und [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), z. B. Eine Windows-Funktion wird durch eine Klassenmemberfunktion umschlossen, nur, wenn ein auf diese Weise löschen Vorteil.  
  
 Da Sie gelegentlich systemeigene Windows-Funktionsaufrufe vornehmen müssen, sollten Sie in der Programmiersprache C-Windows-API-Dokumentation zugreifen. Diese Dokumentation ist im Lieferumfang von Microsoft Visual C++.  
  
> [!NOTE]
>  Einen Überblick darüber, wie das MFC-Bibliothek-Framework ausgeführt wird, finden Sie unter [mithilfe der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Prinzipien für den Klassenentwurf](../mfc/general-class-design-philosophy.md)
