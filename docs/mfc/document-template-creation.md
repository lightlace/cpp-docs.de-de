---
title: Erstellen von Dokumentvorlagen
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
ms.openlocfilehash: 85ff6ad47b37d85c812608dbee918f0543730eae
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271677"
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
