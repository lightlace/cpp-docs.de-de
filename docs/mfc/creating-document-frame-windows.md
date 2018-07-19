---
title: Erstellen von Dokumentrahmenfenstern | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4b27154197e4e8347e73936f319aeb416a153d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342942"
---
# <a name="creating-document-frame-windows"></a>Erstellen von Dokumentrahmenfenstern
[Dokument-/Ansichtarchitektur Erstellung](../mfc/document-view-creation.md) wird gezeigt, wie die [CDocTemplate](../mfc/reference/cdoctemplate-class.md) Objekt orchestriert, das Rahmenfenster, Dokument und Ansicht erstellen und sie alle miteinander zu verbinden. Drei [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Argumente für die `CDocTemplate` Konstruktor angeben, das Rahmenfenster, Dokument und Ansichtsklassen, die die Dokumentvorlage dynamisch in Reaktion auf Benutzerbefehle wie z. B. den neuen Befehl für die Datei erstellt Menüs oder Befehls neues Fenster eine MDI-Fensters im Menü auf. Die Dokumentvorlage speichert diese Informationen für die spätere Verwendung an, bei der Erstellung eines Rahmenfensters für eine Sicht und das Dokument.  
  
 Für die [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) Mechanismus ordnungsgemäß Ihrer abgeleiteten funktioniert Rahmenfensterklassen müssen deklariert werden, mit der [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) Makro. Dies ist, da das Framework Dokument Rahmenfenster mithilfe des Erstellungsmechanismus der dynamischen der Klasse erstellen muss `CObject`.  
  
 Wenn der Benutzer einen Befehl auswählt, der ein Dokument erstellt wird, wird die Dokumentvorlage zum Erstellen der Document-Objekt, seine Ansicht und das Rahmenfenster, in denen die Ansicht angezeigt wird vom Framework aufgerufen. Bei der Erstellung der Dokumentrahmenfenster Dokumentvorlage wird ein Objekt der entsprechenden Klasse erstellt – eine abgeleitete Klasse [CFrameWnd](../mfc/reference/cframewnd-class.md) für SDI-Anwendung oder [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) für MDI-Formulars die Anwendung. Das Framework ruft dann das Rahmenfensterobjekt [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Member-Funktion zum Abrufen von Informationen über Erstellungsdatum von Ressourcen und das Windows-Fenster zu erstellen. Das Framework fügt das Fensterhandle an das Rahmenfenster Objekt. Dann wird die Sicht als untergeordnetes Fenster des Rahmenfensters Dokument erstellt.  
  
 Gehen Sie vorsichtig vor, bei der Entscheidung [initialisiert werden, wenn](../mfc/when-to-initialize-cwnd-objects.md) Ihrer `CWnd`-abgeleitetes Objekt.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Ableiten einer Klasse von CObject (die dynamische Erstellung-Mechanismus)](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Dokument-/Ansichtarchitektur Erstellung (Vorlagen und Dokumentrahmenfenster-Erstellung)](../mfc/document-view-creation.md)  
  
-   [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

