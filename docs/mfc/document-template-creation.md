---
title: Dokumentieren Sie die Vorlagenerstellung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b1a9067929e96c6d3fd851168af079e7e825dcb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443631"
---
# <a name="document-template-creation"></a>Erstellen von Dokumentvorlagen

Beim Erstellen eines neuen Dokuments als Reaktion auf eine **neu** oder **öffnen** Befehl die **Datei** Menü erstellt die Dokumentvorlage auch ein neues Rahmenfensterobjekt über das Anzeigen der Dokument.

Dokumentvorlage Konstruktor gibt an, welche Arten von Dokumente, Fenster und Ansichten, die die Vorlage erstellen kann. Dies wird durch die Argumente bestimmt, die Sie an der Dokumentvorlage Konstruktor übergeben. Der folgende Code veranschaulicht die Erstellung einer [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) eine beispielanwendung:

[!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]

Der Zeiger auf ein neues `CMultiDocTemplate` Objekt dient als Argument an [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Argumente für die `CMultiDocTemplate` Konstruktor enthalten, die Ressourcen-ID, die des Dokumenttyps Menüs und Zugriffstasten zugeordnet, und drei verwendet, der die [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) Makro. `RUNTIME_CLASS` Gibt die [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) -Objekt für die C++-Klasse, die mit dem Namen als Argument. Die drei `CRuntimeClass` an den Dokument-Template-Konstruktor übergebene Objekte geben Sie die Informationen, die zum Erstellen neuer Objekte den angegebenen Klassen während des Erstellungsprozesses des Dokuments erforderlich sind. Das Beispiel veranschaulicht die Erstellung einer Dokumentvorlage, die erstellt `CScribDoc` Objekte mit `CScribView` Objekte angefügt werden. Die Ansichten von untergeordneten MDI-standard Rahmenfenster eingebunden.

## <a name="see-also"></a>Siehe auch

[Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)<br/>
[Beziehungen zwischen MFC-Objekten](../mfc/relationships-among-mfc-objects.md)<br/>
[Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

