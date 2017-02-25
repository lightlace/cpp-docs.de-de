---
title: "Erstellen von Dokumentvorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konstruktoren [C++], Dokumentvorlage"
  - "Dokumentvorlagen"
  - "Dokumentvorlagen, Erstellen"
  - "MFC, Dokumentvorlagen"
  - "Vorlagen, Dokumentvorlagen"
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Erstellen von Dokumentvorlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein neues Dokument in Reaktion auf einen `New` Befehl **Datei** oder **Öffnen** im Menü erstellt, stellt der Normal\-Vorlage auch ein neues Rahmenfenster erstellt, durch das das Dokument anzeigen.  
  
 Der Dokumentvorlagenkonstruktor gibt an, was von Dokumenten, Fenster eingibt und Ansichten die Vorlage in der Lage sind zu erstellen.  Dies wird in der Argumente bestimmt, die Sie zum Dokumentvorlagenkonstruktor übergeben.  Der folgende Code veranschaulicht Erstellung von [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) für eine Beispielanwendung:  
  
 [!CODE [NVC_MFCDocView#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#7)]  
  
 Der Zeiger auf ein neues `CMultiDocTemplate`\-Objekt wird als Argument an [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md).  Argumente an `CMultiDocTemplate`\-Konstruktor umfassen die Ressourcen\-ID, die mit den Menüs und den Zugriffstasten Dokumenttyps zugeordnet sind, und drei Verwendungen des [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)\-Makro.  `RUNTIME_CLASS` gibt das Objekt für die [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) C\+\+\-Klasse zurück, die als Argument benannt wird.  Die drei `CRuntimeClass`\-Objekte haben z Dokumentvorlagenkonstruktorzubehör die Informationen, die erforderlich waren, um neue Objekte der angegebenen Klasse während der Dokumenterstellung erstellen, verarbeiten.  Das Beispiel veranschaulicht Erstellung der Normal\-Vorlage an, die `CScribDoc`\-Objekte mit angefügten `CScribView`\-Objekten erstellt.  Die Ansichten werden durch Standarduntergeordnete mdi\-rahmenfenster Formen.  
  
## Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokument\/Ansicht](../mfc/document-view-creation.md)   
 [Beziehungen zwischen MFC\-Objekten](../mfc/relationships-among-mfc-objects.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)