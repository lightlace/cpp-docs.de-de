---
title: "M&#246;gliche &#196;nderungen am Standardcode (MFC-Datenzugriff) | Microsoft Docs"
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
  - "Datensatzansichten [C++], Anpassen des Standardcodes"
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# M&#246;gliche &#196;nderungen am Standardcode (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der [MFC\-Anwendungs\-Assistent](../mfc/reference/database-support-mfc-application-wizard.md) schreibt eine Recordset\-Klasse, mit der sämtliche Datensätze einer einzelnen Tabelle ausgewählt werden.  Dieses Verhalten können Sie häufig auf eine oder mehrere der folgenden Arten ändern:  
  
-   Legen Sie einen Filter oder eine Sortierreihenfolge für das Recordset fest.  Führen Sie dies in `OnInitialUpdate` nach der Erstellung des Recordset\-Objekts durch, jedoch bevor seine Memberfunktion **Öffnen** aufgerufen wird.  Weitere Informationen finden Sie unter [Recordset: Filtern von Datensätzen \(ODBC\)](../data/odbc/recordset-filtering-records-odbc.md) und [Recordset: Sortieren von Datensätzen \(ODBC\)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Parametrisieren Sie das Recordset.  Geben Sie den tatsächlichen Laufzeit\-Parameterwert nach dem Filter an.  Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
-   Übergeben Sie eine benutzerdefinierte SQL\-Zeichenfolge an die Memberfunktion [Öffnen](../Topic/CRecordset::Open.md).  Eine Erläuterung der Ergebnisse, die Sie mit dieser Technik erzielen können, finden Sie unter [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
## Siehe auch  
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)