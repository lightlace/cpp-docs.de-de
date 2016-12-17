---
title: "Transaktion: Auswirkungen von Transaktionen auf Aktualisierungen (ODBC)"
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
  - "CommitTrans-Methode"
  - "ODBC-Recordsets, Transaktionen"
  - "Rollback-Methode, ODBC-Transaktionen"
  - "Transaktionen, Ausführen eines Rollback"
  - "Transaktionen, Aktualisieren von Recordsets"
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Transaktion: Auswirkungen von Transaktionen auf Aktualisierungen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktualisierungen der [Datenquelle](../../data/odbc/data-source-odbc.md) werden während einer Transaktion mithilfe eines Bearbeitungspuffers verwaltet \(diese Methode wird auch außerhalb von Transaktionen eingesetzt\).  Die Felddatenmember eines Recordsets werden gemeinsam als Bearbeitungspuffer für den aktuellen Datensatz verwendet, den das Recordset während `AddNew` oder **Edit** temporär zwischenspeichert.  Während eines **Delete**\-Vorgangs wird der aktuelle Datensatz innerhalb einer Transaktion nicht gesichert.  Weitere Informationen über den Bearbeitungspuffer und darüber, wie bei Aktualisierungen der aktuelle Datensatz gespeichert wird, finden Sie unter [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, können Sie `AddNew`, **Edit** oder **Delete** nicht aufrufen.  Stattdessen müssen Sie eigene Funktionen schreiben, die Aktualisierungen der Datenquelle durchführen.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Während einer Transaktion können die Operationen `AddNew`, **Edit** und **Delete** entweder bestätigt oder zurückgesetzt werden.  **CommitTrans** und **Rollback** können bewirken, dass der aktuelle Datensatz nicht in den Bearbeitungspuffer wiederhergestellt wird.  Um sicherzustellen, dass der aktuelle Datensatz fehlerfrei wiederhergestellt wird, müssen Sie genau verstehen, wie die **CommitTrans**\-Memberfunktion und **Rollback**\-Memberfunktion von `CDatabase` mit den Aktualisierungsfunktionen von `CRecordset` zusammenwirken.  
  
##  <a name="_core_how_committrans_affects_updates"></a> Auswirkungen von CommitTrans auf Aktualisierungen  
 Die folgende Tabelle erläutert, wie sich **CommitTrans** auf Transaktionen auswirkt.  
  
### Auswirkungen von CommitTrans auf Aktualisierungen  
  
|Vorgang|Status der Datenquelle|  
|-------------|----------------------------|  
|`AddNew` und **Update**, anschließend **CommitTrans**|Ein neuer Datensatz wird zur Datenquelle hinzugefügt.|  
|`AddNew` \(ohne **Update**\), anschließend **CommitTrans**|Der neue Datensatz geht verloren.  Der Datensatz wird nicht zur Datenquelle hinzugefügt.|  
|**Edit** und **Update**, anschließend **CommitTrans**|Die Änderungen werden in der Datenquelle durchgeführt.|  
|**Edit** \(ohne **Update**\), anschließend **CommitTrans**|Die Änderungen am Datensatz gehen verloren.  Der Datensatz bleibt in der Datenquelle unverändert.|  
|**Delete**, anschließend **CommitTrans**|Die Datensätze werden aus der Datenquelle gelöscht.|  
  
##  <a name="_core_how_rollback_affects_updates"></a> Auswirkungen von Rollback auf Transaktionen  
 Die folgende Tabelle erläutert, wie sich **Rollback** auf Transaktionen auswirkt.  
  
### Auswirkungen von Rollback auf Transaktionen  
  
|Vorgang|Status des aktuellen Datensatzes|Außerdem müssen Sie|Status der Datenquelle|  
|-------------|--------------------------------------|-------------------------|----------------------------|  
|`AddNew` und **Update**, anschließend **Rollback**|Der Inhalt des aktuellen Datensatzes wird temporär gespeichert, um für einen neuen Datensatz Platz zu schaffen.  Der neue Datensatz wird in den Bearbeitungspuffer eingefügt.  Nach dem Aufruf von **Update** wird der aktuelle Datensatz im Bearbeitungspuffer wiederhergestellt.||Die mit **Update** durchgeführte Ergänzung der Datenquelle wird rückgängig gemacht.|  
|`AddNew` \(ohne **Update**\), anschließend **Rollback**|Der Inhalt des aktuellen Datensatzes wird temporär gespeichert, um für einen neuen Datensatz Platz zu schaffen.  Der Bearbeitungspuffer enthält den neuen Datensatz.|`AddNew` erneut aufrufen, um im Bearbeitungspuffer einen leeren, neuen Datensatz wiederherzustellen.  Oder **Move**\(0\) aufrufen, um die alten Werte im Bearbeitungspuffer wiederherzustellen.|Da **Update** nicht aufgerufen wurde, wurden keine Änderungen an der Datenquelle vorgenommen.|  
|**Edit** und **Update**, anschließend **Rollback**|Eine unveränderte Version des aktuellen Datensatzes wird temporär gespeichert.  Der Inhalt des Bearbeitungspuffers wird verändert.  Nach dem Aufruf von **Update** bleibt die unveränderte Version des Datensatzes weiterhin temporär gespeichert.|*Dynaset*: sich vom aktuellen Datensatz wegbewegen, anschließend zurückbewegen, um die unveränderte Version des Datensatzes im Bearbeitungspuffer wiederherzustellen.<br /><br /> *Snapshot*: Requery aufrufen, um das Recordset aus der Datenquelle zu aktualisieren.|Die mit **Update** durchgeführten Änderungen an der Datenquelle werden rückgängig gemacht.|  
|**Edit** \(ohne **Update**\), anschließend **Rollback**|Eine unveränderte Version des aktuellen Datensatzes wird temporär gespeichert.  Der Inhalt des Bearbeitungspuffers wird verändert.|**Edit** erneut aufrufen, um die unveränderte Version des Datensatzes im Bearbeitungspuffer wiederherzustellen.|Da **Update** nicht aufgerufen wurde, wurden keine Änderungen an der Datenquelle vorgenommen.|  
|**Delete**, anschließend **Rollback**|Der Inhalt des aktuellen Datensatzes wird gelöscht.|**Requery** aufrufen, um den Inhalt des aktuellen Datensatzes aus der Datenquelle zu wiederherzustellen.|Das Löschen von Daten aus der Datenquelle wird rückgängig gemacht.|  
  
## Siehe auch  
 [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [Transaktion: Ausführen einer Transaktion in einem Recordset \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)