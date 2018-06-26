---
title: Dokumentieren Sie die Vorlagenerstellung | Microsoft Docs
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
ms.openlocfilehash: 3695d2795fa324051b76cf012aae7e1b1f275fa1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928021"
---
# <a name="document-template-creation"></a>Erstellen von Dokumentvorlagen
Beim Erstellen eines neuen Dokuments als Antwort auf eine **neu** oder **öffnen** Befehl die **Datei** im Menü erstellt die Dokumentvorlage auch ein neues Rahmenfenster, zeigen Sie an der die Dokument.  
  
 Dokumentvorlagen-Konstruktor gibt an, welche Arten von Dokumenten, Fenster und Ansichten von die Vorlage erstellt werden. Dies wird von den Argumenten bestimmt, die Sie an den Dokumentvorlagen-Konstruktor übergeben. Das folgende Codebeispiel veranschaulicht die Erstellung einer [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) eine beispielanwendung:  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 Der Zeiger auf ein neues `CMultiDocTemplate` Objekt dient als Argument an [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Argumente für die `CMultiDocTemplate` Konstruktor enthalten, die Ressourcen-ID, die des Dokumenttyps Menüs und Zugriffstasten zugeordnet, und drei verwendet, der die [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) Makro. `RUNTIME_CLASS` Gibt die [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Objekt für die C++-Klasse, die mit dem Namen als Argument. Die drei `CRuntimeClass` an den Dokumentvorlagen-Konstruktor übergebene Objekte angeben, die zum Erstellen von neuer Objekten von den angegebenen Klassen während des Erstellungsprozesses Dokument erforderlichen Informationen. Das Beispiel zeigt die Erstellung einer Dokument Vorlage, die erstellt `CScribDoc` Objekte mit `CScribView` Objekte angefügt. Die Ansichten werden von untergeordneten MDI-standard Rahmenfenster eingerahmt.  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)   
 [Beziehungen zwischen MFC-Objekte](../mfc/relationships-among-mfc-objects.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

