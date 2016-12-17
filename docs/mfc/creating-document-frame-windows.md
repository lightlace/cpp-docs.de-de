---
title: "Erstellen von Dokumentrahmenfenstern"
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
  - "Dokumentrahmenfenster, Erstellen"
  - "Dokumentvorlagen, und Dokumentrahmenfenster"
  - "Rahmenfenster [C++], Erstellen"
  - "MFC [C++], Rahmenfenster"
  - "run-time-Klasse, und Dokumentrahmenfenster-Erstellung"
  - "Laufzeit, Klasseninformation"
  - "Fenster [C++], Erstellen"
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen von Dokumentrahmenfenstern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Dokument\/Ansichts\-Erstellung](../mfc/document-view-creation.md) zeigt, wie das [CDocTemplate](../mfc/reference/cdoctemplate-class.md)\-Objekt das Erstellen des Rahmenfensters, Dokuments und der Ansicht und alle zusammen herstellen instrumentiert.  Drei [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)\-Argumente den Konstruktor `CDocTemplate` geben das Rahmenfenster, das Dokument und den Ansichtsklassen an, die die Normal\-Vorlage dynamisch auf Benutzerbefehle wie den neuen Befehl im Menü Datei oder den Befehl des neuen Fensters auf einem MDI\-Fenstermenü erstellt.  Die Normal\-Vorlage speichert diese Informationen zur späteren Verwendung, wenn sie ein Rahmenfenster für eine Ansicht und ein Dokument erstellt.  
  
 Damit der [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md) Mechanismus ordnungsgemäß, die abgeleitete Rahmenfensterklassen muss mit dem Makro [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) deklariert werden.  Dies ist, da das Framework Dokumentrahmenfenster mithilfe des dynamischen Konstruktionsmechanismus der Klasse `CObject` erstellen muss.  
  
 Wenn der Benutzer einen Befehl auswählt, der ein Dokument erstellt, fordert das Framework die Normal\-Vorlage auf, um das Dokumentobjekt, die Ansicht und das Rahmenfenster zu erstellen, das die Ansicht an.  Wenn das Dokumentrahmenfenster erstellt wird, erstellt die Normal\-Vorlage ein Objekt der entsprechenden Klasse \- eine Klasse, die von [CFrameWnd](../mfc/reference/cframewnd-class.md) für eine SDI\-Anwendung oder [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) für eine MDI\-Anwendung abgeleitet wird.  Das Framework ruft dann die [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) des Rahmenfenster Memberfunktion Objekts, um Erstellungsinformationen von Ressourcen abzurufen auf und das Windows\-Fenster zu erstellen.  Das Framework fügt das Fensterhandle zum Rahmenfensterobjekt an.  Dann erstellt es die Ansicht als untergeordnetes Fenster des Dokumentrahmenfensters.  
  
 Verwendungsvorsicht in entscheidendem [wann initialisiert](../mfc/when-to-initialize-cwnd-objects.md) Ihr `CWnd` abgeleitetes Objekt.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Eine Klasse von CObject \(kann dynamischer Erstellungsmechanismus ableiten\)](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Dokument\/Ansichts\-Erstellung \(Vorlagen und Rahmenfenstererstellung\)](../mfc/document-view-creation.md)  
  
-   [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)  
  
## Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)