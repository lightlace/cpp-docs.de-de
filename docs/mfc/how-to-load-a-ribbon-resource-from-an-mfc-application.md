---
title: "Gewusst wie: Laden einer Men&#252;bandressource aus einer MFC-Anwendung | Microsoft Docs"
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
  - "Menübandressource, Laden"
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Gewusst wie: Laden einer Men&#252;bandressource aus einer MFC-Anwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um die Menübandressource in der Anwendung zu verwenden, ändern Sie die Anwendung die Menübandressource laden.  
  
### So eine Menübandressource laden  
  
1.  Deklarieren Sie das `Ribbon Control`\-Objekt in der `CMainFrame`\-Klasse.  
  
    ```  
    CMFCRibbonBar m_wndRibbonBar;   
    ```  
  
2.  In `CMainFrame::OnCreate` Erstellen und initialisieren Sie das Menüband\-Steuerelement.  
  
    ```  
    if (!m_wndRibbonBar.Create (this))  
    {  
        return -1;  
    }  
  
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
    {  
        return -1;  
    }  
    ```  
  
## Siehe auch  
 [Menüband\-Designer \(MFC\)](../mfc/ribbon-designer-mfc.md)