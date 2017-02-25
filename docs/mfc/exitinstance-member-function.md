---
title: "ExitInstance-Memberfunktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp::ExitInstance"
  - "CWinApp.ExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp-Klasse, ExitInstance"
  - "ExitInstance-Methode"
  - "Programme [C++], Terminieren"
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ExitInstance-Memberfunktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die [ExitInstance](../Topic/CWinApp::ExitInstance.md)\-Memberfunktion der [CWinApp](../mfc/reference/cwinapp-class.md) wird, wenn eine Kopie der Anwendung beendet wird, normalerweise aufgrund des Benutzers aufgerufen, der die Anwendung beendet.  
  
 Überschreiben Sie `ExitInstance`, wenn Sie besondere Bereinigung Verarbeitung erfordern, z Freigeben von Graphics Device Interface \(GDI\)\- Ressourcen oder Freigeben des Speichers, der während der Programmausführung verwendet wird.  Bereinigung von Standardelementen wie Dokumenten und Ansichten wird jedoch vom Framework, mit anderen Funktionen schreibbaren für die Variante des speziellen Bereinigungsbesonderen zu diesen Objekten bereitgestellt.  
  
## Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)