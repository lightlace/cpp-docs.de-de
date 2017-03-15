---
title: "OnIdle-Memberfunktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnIdle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp-Klasse, OnIdle-Methode"
  - "Leerlaufschleifen-Verarbeitung"
  - "Meldungsbehandlung, OnIdle-Methode"
  - "OnIdle-Methode"
  - "Verarbeitungsmeldungen"
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OnIdle-Memberfunktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn keine Windows\-Meldungen verarbeitet werden, ruft das Framework die [CWinApp](../mfc/reference/cwinapp-class.md)\-Memberfunktion [OnIdle](../Topic/CWinApp::OnIdle.md) auf \(beschrieben in der MFC\-Bibliotheksreferenz\).  
  
 `OnIdle` überschreiben, um " Hintergrundaufgaben auszuführen.  Die Standardversion aktualisiert den Zustand von Benutzeroberflächenobjekten wie Symbolleisten\-Schaltflächen und führt Bereinigung von temporären Objekten aus, die vom Framework im Verlauf ihrer Vorgänge erstellt werden.  Die folgende Abbildung veranschaulicht, wie die Meldungsschleife `OnIdle` aufruft, wenn keine Meldungen in der Warteschlange wird.  
  
 ![Nachrichtenschleifenprozess](../mfc/media/vc387c1.png "vc387C1")  
Nachrichtenschleife  
  
 Weitere Informationen darüber, wodurch Sie in die Leerlaufschleife ausführen können, finden Sie unter [Leerlaufschleifen\-Verarbeitung](../mfc/idle-loop-processing.md).  
  
## Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)