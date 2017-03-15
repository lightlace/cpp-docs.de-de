---
title: "Recordset: Hinzuf&#252;gen von Datens&#228;tzen in einer Sammeloperation (ODBC) | Microsoft Docs"
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
  - "Sammeldatensätze zu Recordsets hinzufügen"
  - "ODBC-Recordsets, Hinzufügen von Datensätzen"
  - "Recordsets, Hinzufügen von Datensätzen"
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Recordset: Hinzuf&#252;gen von Datens&#228;tzen in einer Sammeloperation (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Die [CRecordset](../../mfc/reference/crecordset-class.md)\-Klasse von MFC verfügt über eine neue Optimierung, die die Effizienz beim gesammelten Hinzufügen neuer Datensätze zu einer Tabelle verbessert.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Eine neue Option für den **dwOptions**\-Parameter der [CRecordset::Open](../Topic/CRecordset::Open.md)\-Memberfunktion **optimizeBulkAdd** verbessert die Leistung, wenn Sie mehrere Datensätze ohne Aufruf von **Requery** oder **Close** hintereinander hinzufügen.  Nur die Felder, die vor dem ersten **Update**\-Aufruf als geändert gekennzeichnet waren, werden auch in den nachfolgenden `AddNew`\/**Update**\-Aufrufen als geändert gekennzeichnet.  
  
 Falls Sie die Datenbankklassen in der Form verwenden, dass Sie zum Hinzufügen, Bearbeiten und Löschen von Datensätzen die ODBC\-API\-Funktion **::SQLSetPos** aufrufen, ist diese Optimierung nicht erforderlich.  
  
 Wenn die ODBC\-Cursorbibliothek geladen ist oder der ODBC\-Treiber das Hinzufügen, Bearbeiten und Löschen mit ::**SQLSetPos** nicht unterstützt, kann diese Optimierung die Geschwindigkeit beim gesammelten Hinzufügen erhöhen.  Um diese Optimierung zu aktivieren, stellen Sie beim Aufruf der **Open**\-Memberfunktion des Recordsets den **dwOptions**\-Parameter auf den folgenden Wert ein:  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Recordset: Sperren von Datensätzen \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)