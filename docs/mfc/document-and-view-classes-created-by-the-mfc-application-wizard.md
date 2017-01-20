---
title: "Mithilfe des MFC-Anwendungs-Assistenten erstellte Dokument- und Ansichtsklassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsassistenten [C++], erstellte Dokument/Ansichtsklassen"
  - "Dokumentklassen"
  - "Dokumentklassen, Erstellt mit Anwendungs-Assistenten"
  - "Ansichtsklassen, Erstellt mit Anwendungs-Assistenten"
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Mithilfe des MFC-Anwendungs-Assistenten erstellte Dokument- und Ansichtsklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der MFC\-Anwendungs\-Assistent bietet einen Vorsprung auf der Programmentwicklung, indem er skelettartiges Dokument und Ansichtsklassen für Sie erstellt.  Sie können dann die [Zuordnungsbefehle und Meldungen zu diesen Klassen](../mfc/reference/mapping-messages-to-functions.md) und den Visual C\+\+\-Quellcode\-Editor verwenden, um deren Memberfunktionen zu schreiben.  
  
 Die Dokumentklasse, die vom MFC\-Anwendungs\-Assistenten erstellt wird, wird von der Klasse [CDocument](../mfc/reference/cdocument-class.md) abgeleitet.  Die Ansichtsklasse wird von [CView](../mfc/reference/cview-class.md) abgeleitet.  Die Namen, den der Anwendungs\-Assistent diese Klassen und Dateien vorhanden sind, die sie enthalten, basieren auf den Projektnamen, den Sie im Anwendungs\-Assistenten\-Dialogfeld stellen.  im Anwendungs\-Assistenten können Sie die generierte Klassenseite verwenden, um den Standardnamen zu ändern.  
  
 Einige Anwendungen erfordern möglicherweise mehrere Dokumentklasse, Ansichtsklasse oder Rahmenfensterklasse.  Weitere Informationen finden Sie unter [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)