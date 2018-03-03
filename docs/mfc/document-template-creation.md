---
title: Dokumentieren Sie die Vorlagenerstellung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04950601a74b1ed3e44b236e1d07dcdff997eca6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="document-template-creation"></a>Erstellen von Dokumentvorlagen
Beim Erstellen eines neuen Dokuments als Antwort auf eine `New` oder **öffnen** Befehl die **Datei** im Menü die Dokumentvorlage auch über die zum Anzeigen des Dokuments ein neues Rahmenfenster erstellt.  
  
 Dokumentvorlagen-Konstruktor gibt an, welche Arten von Dokumenten, Fenster und Ansichten von die Vorlage erstellt werden. Dies wird von den Argumenten bestimmt, die Sie an den Dokumentvorlagen-Konstruktor übergeben. Das folgende Codebeispiel veranschaulicht die Erstellung einer [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) eine beispielanwendung:  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 Der Zeiger auf ein neues `CMultiDocTemplate` Objekt dient als Argument an [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Argumente für die `CMultiDocTemplate` Konstruktor enthalten, die Ressourcen-ID, die des Dokumenttyps Menüs und Zugriffstasten zugeordnet, und drei verwendet, der die [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) Makro. `RUNTIME_CLASS`Gibt die [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Objekt für die C++-Klasse, die mit dem Namen als Argument. Die drei `CRuntimeClass` an den Dokumentvorlagen-Konstruktor übergebene Objekte angeben, die zum Erstellen von neuer Objekten von den angegebenen Klassen während des Erstellungsprozesses Dokument erforderlichen Informationen. Das Beispiel zeigt die Erstellung einer Dokument Vorlage, die erstellt `CScribDoc` Objekte mit `CScribView` Objekte angefügt. Die Ansichten werden von untergeordneten MDI-standard Rahmenfenster eingerahmt.  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)   
 [Beziehungen zwischen MFC-Objekte](../mfc/relationships-among-mfc-objects.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

