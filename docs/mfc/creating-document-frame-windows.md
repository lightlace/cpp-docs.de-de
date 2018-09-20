---
title: Erstellen von Dokument-Frames Windows | Microsoft-Dokumentation
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
ms.openlocfilehash: 172076113a6bd7e223d99c238d0e05987cdcaae6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433691"
---
# <a name="creating-document-frame-windows"></a>Erstellen von Dokumentrahmenfenstern

[Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md) zeigt, wie die [CDocTemplate](../mfc/reference/cdoctemplate-class.md) Objekt orchestriert, erstellen das Rahmenfenster, Dokument und Ansicht, und verbinden sie alle. Drei [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Argumente für die `CDocTemplate` Konstruktor angegeben wird, das Rahmenfenster, Dokument und Ansichtsklassen, die die Dokumentvorlage dynamisch in Reaktion auf Benutzerbefehle wie z. B. den neuen Befehl in der Datei erstellt Menü oder den Befehl "Neues Fenster" ein MDI-Fensters im Menü ". Die Dokumentvorlage speichert diese Informationen für die spätere Verwendung auf, wenn es sich um ein Rahmenfenster für eine Ansicht und das Dokument erstellt.

Für die [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) Mechanismus, dem abgeleiteten ordnungsgemäße Rahmenfensterklassen müssen deklariert werden, mit der [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) Makro. Dies ist, da das Framework zum Erstellen von Dokument-Frame-Fensters mithilfe des Erstellungsmechanismus der dynamischen der Klasse muss `CObject`.

Wenn der Benutzer einen Befehl, der ein Dokument erstellt auswählt, wird die Dokumentvorlage, erstellen Sie das Document-Objekt, seine Ansicht und das Rahmenfenster, das die Ansicht angezeigt wird vom Framework aufgerufen. Wenn sie die Dokumentrahmenfenster erstellt haben, handelt es sich bei der Dokumentvorlage erstellt ein Objekt der entsprechenden Klasse – eine abgeleitete Klasse [CFrameWnd](../mfc/reference/cframewnd-class.md) für die einer SDI-Anwendung oder [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) für MDI-Formulars die Anwendung. Ruft das Framework klicken Sie dann auf das Rahmenfensterobjekt [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Member-Funktion zum Abrufen von Informationen aus den Ressourcen und zum Erstellen des Windows-Fensters. Das Framework fügt das Handle des Fensters an das Rahmenfenster Objekt. Anschließend wird die Sicht als untergeordnetes Fenster des Rahmenfensters Dokument erstellt.

Seien Sie vorsichtig bei der Entscheidung [beim Initialisieren](../mfc/when-to-initialize-cwnd-objects.md) Ihre `CWnd`-abgeleitetes Objekt.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Ableiten einer Klasse von CObject (die dynamische Erstellung-Mechanismus)](../mfc/deriving-a-class-from-cobject.md)

- [Dokument-/Ansicht-Erstellung (Vorlagen und Dokumentrahmenfenster-Erstellung)](../mfc/document-view-creation.md)

- [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

