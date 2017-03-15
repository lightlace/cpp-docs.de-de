---
title: "TN047: Abschw&#228;chen der Anforderungen f&#252;r eine Datenbanktransaktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN047"
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN047: Abschw&#228;chen der Anforderungen f&#252;r eine Datenbanktransaktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Technologie\-Hinweis, der die Transaktionsanforderungen die MFC\-ODBC\-Datenbankklassen erläuterte, ist jetzt veraltet.  Vor MFC 4.2 benötigen die Datenbankklassen, dass Cursor in Recordsets nach einer **CommitTrans** oder **Zurücksetzung** beibehalten Vorgang werden.  Wenn der ODBC\-Treiber und DBMS diese Sicherheitsebene nicht der Cursor\-Beibehaltung unterstützte, dann aktiviert die Datenbankklassen nicht Transaktionen.  
  
 Ab MFC 4.2, verfügen die Datenbankklassen sich die Einschränkung der verbindlichen Verwendung von Cursor\-Beibehaltung gelockert.  Transaktionen sind aktiviert, wenn der Treiber sie unterstützt.  Sie müssen jedoch den Effekt eines **CommitTrans** oder **Zurücksetzung** Vorgangs auf geöffneten Recordsets jetzt überprüfen.  Siehe die Memberfunktionen [CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md) und [CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md).  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)