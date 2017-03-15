---
title: "Framework (MFC) | Microsoft Docs"
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
  - "APIs [C++], Kapselung durch MFC Win32"
  - "Anwendungsframework [C++], Informationen über MFC-Anwendungsframework"
  - "gekapselte Win32 API"
  - "Kapselung [C++]"
  - "Kapselung [C++], Win32 API"
  - "MFC [C++], Anwendungsframework"
  - "Win32 [C++], API-Kapselung durch MFC"
  - "Windows-API [C++], Kapselung durch MFC"
  - "Wrapperklassen, erklärt"
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Framework (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

die Arbeit mit dem Bibliotheksframework Microsoft Foundation Class \(MFC\) basiert größtenteils auf einigen wenigen Klassen und einigen Visual C\+\+\-Tools.  Einige Klassen kapseln einen großen Teil der Win32\-Anwendungsprogrammierschnittstelle \(API\).  Andere Klassen kapseln Anwendungskonzepte wie Dokumente, Ansichten und die Anwendung selbst.  Noch kapseln andere OLE\-Funktionen und ODBC\- und DAO\-Datenzugriffsfunktionalität.  
  
 Beispielsweise Win32\- wird Konzept des Fensters von MFC\-Klasse `CWnd` gekapselt.  Das heißt, kapselt eine C\+\+\-Datei Klasse namens `CWnd`, oder "binden" das `HWND` ein Handle ein, das Windows\-Fenster darstellt.  Entsprechend kapselt Klasse `CDialog` Win32\-Dialogfelder.  
  
 Kapselung bedeutet, dass die C\+\+\-Klasse `CWnd` beispielsweise eine Membervariable vom Typ `HWND` enthält und die Memberfunktionen der Klasse Aufrufe auf Win32 funktioniert kapseln, die `HWND` als Parameter akzeptieren.  Die Memberfunktionen haben in der Regel den Namen, den die Win32\-Funktion sie kapseln.  
  
## In diesem Abschnitt  
 [SDI und MDI](../mfc/sdi-and-mdi.md)  
  
 [Dokumente, Ansichten und Framework](../mfc/documents-views-and-the-framework.md)  
  
 [Ressourcen\-Editoren und Assistenten](../mfc/wizards-and-the-resource-editors.md)  
  
## In den Abschnitten verknüpften  
 [Erstellen auf dem Framework](../mfc/building-on-the-framework.md)  
  
 [Wie das Framework den Code aufruft](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: Die Application\-Klasse](../mfc/cwinapp-the-application-class.md)  
  
 [Dokumentvorlagen und der Ansichts\-Erstellungs\-Prozess Dokument\/](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
 [Fensterobjekte](../mfc/window-objects.md)  
  
## Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)