---
title: "Gewusst wie: Umwandeln eines vorhandenen MFC-Men&#252;bands in eine Men&#252;bandressource | Microsoft Docs"
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
  - "MFC-Menüband, Umwandeln in eine Menübandressource"
  - "Menübandressource, Umwandeln von einem MFC-Menüband"
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Gewusst wie: Umwandeln eines vorhandenen MFC-Men&#252;bands in eine Men&#252;bandressource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Menübandressourcen sind einfacher als manuell codierte Menübänder visuell darzustellen, ändern und verwalten.  In diesem Thema wird beschrieben, wie diese manuell codiertes Menüband in einem MFC\-Projekt in eine Menübandressource konvertiert.  
  
 Sie müssen ein vorhandenes MFC\-Projekt haben, das Code verfügt, der die MFC\-Menübandklassen beispielsweise [CMFCRibbonBar\-Klasse](../mfc/reference/cmfcribbonbar-class.md) verwendet.  
  
### So ein MFC\-Menüband zu einer Menübandressource konvertieren  
  
1.  In Visual Studio in einem vorhandenen MFC\-Projekt, die Quelldatei, in der das CMFCRibbonBar\-Objekt initialisiert wird.  In der Regel ist die Datei mainfrm.cpp.  Fügen Sie den folgenden Code nach den Initialisierungscode für das Menüband hinzu.  
  
    ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");  
    ```  
  
     Speichern und schließen Sie die Datei.  
  
2.  Erstellen und Ausführen die MFC\-Anwendung, und anschließend im Editor, die Datei RibbonOutput.txt aus und kopieren Sie den Inhalt.  
  
3.  In Visual Studio im Menü **Projekt**, klicken Sie auf **Ressource hinzufügen**.  Wählen Sie im Dialogfeld **Ressource hinzufügen** die Option **Menüband** aus, und klicken Sie dann auf **Neu**.  
  
     Visual Studio erstellt eine Menübandressource und öffnet sie in der Entwurfsansicht.  Das Menübandressourcen\-ID lautet IDR\_RIBBON1 und wird in **Ressourcenansicht** angezeigt.  Das Menüband wird in der ribbon1.mfcribbon\-ms XML\-Datei definiert.  
  
4.  In Visual Studio deaktivieren geöffnete ribbon1.mfcribbon\-ms, Inhalte und anschließend den Inhalt von RibbonOutput.txt ein, die Sie zuvor kopierten.  Speichern und schließen Sie ribbon1.mfcribbon\-ms.  
  
5.  Wiederum Öffnen Sie die Quelldatei, in der das CMFCRibbonBar\-Objekt initialisiert wird \(in der Regel, mainfrm.cpp\) und kommentieren Sie sie der vorhandene Menübandcode.  Fügen Sie den folgenden Code nach dem Code hinzu, dass Sie den kommentierten.  
  
    ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);  
    ```  
  
6.  Erstellen Sie das Projekt und führen Sie das Programm aus.  
  
## Siehe auch  
 [Menüband\-Designer \(MFC\)](../mfc/ribbon-designer-mfc.md)