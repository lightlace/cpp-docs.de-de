---
title: "Recordset: Hinzufügen von Datensätzen in einer Sammeloperation (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 251d2fa4b7c28c1458fdc5643c9b17c53ba1b0ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Recordset: Hinzufügen von Datensätzen in einer Sammeloperation (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Die MFC-Bibliothek [CRecordset](../../mfc/reference/crecordset-class.md) -Klasse verfügt über eine neue Optimierung, die Effizienz verbessert, wenn Sie neue Datensätze in einem Massenvorgang in eine Tabelle hinzufügen.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Eine neue Option für die **Wert** Parameter an die [CRecordset](../../mfc/reference/crecordset-class.md#open) Memberfunktion, **OptimizeBulkAdd**, verbessert die Leistung beim Hinzufügen mehrerer Datensätze fortlaufend ohne Aufruf **Requery** oder **schließen**. Nur die Felder, die vor dem ersten dirty sind **Update** Aufruf werden als modifizierte für nachfolgende `AddNew` / **Update** aufrufen.  
  
 Wenn Sie die Datenbankklassen verwenden, nutzen die **:: SQLSetPos** ODBC-API-Funktion zum Hinzufügen, bearbeiten und Löschen von Datensätzen, diese Optimierung ist nicht erforderlich.  
  
 Wenn die ODBC-Cursorbibliothek geladen ist oder der ODBC-Treiber unterstützt keine hinzufügen, bearbeiten und löschen Sie über **:: SQLSetPos**, diese Optimierung sollten Bulk verbessern Leistung hinzufügen. Um diese Optimierung zu aktivieren, setzen die **OpenEx** Parameter in der **öffnen** für das Recordset, der dem folgenden aufrufen:  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)