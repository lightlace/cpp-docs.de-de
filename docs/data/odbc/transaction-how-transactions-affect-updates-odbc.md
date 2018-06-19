---
title: 'Transaktion: Aktualisierungen (ODBC) Auswirkungen von Transaktionen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 549f8495ca3a088ec4314cd26318d19f9a5a3176
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098003"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>Transaktion: Auswirkungen von Transaktionen auf Aktualisierungen (ODBC)
Updates für die [Datenquelle](../../data/odbc/data-source-odbc.md) verwaltet werden, während Transaktionen durch die Verwendung von Bearbeitungspuffer (die gleiche Methode außerhalb von Transaktionen verwendet). Die Felddatenmembern eines Recordset-Objekts dienen zusammen als Bearbeitungspuffer, die den aktuellen Datensatz das Recordset enthält bei vorübergehend sichert eine `AddNew` oder **bearbeiten**. Während einer **löschen** Vorgang, der aktuelle Datensatz nicht innerhalb einer Transaktion gesichert wird. Weitere Informationen zu den Bearbeitungspuffer und dazu, wie Updates für den aktuellen Datensatz speichern, finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie können nicht `AddNew`, **bearbeiten**, oder **löschen**. Sie müssen stattdessen Ihre eigenen Funktionen zum Durchführen von Updates mit der Datenquelle schreiben. Weitere Informationen über das gesammelte finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Während einer Transaktion `AddNew`, **bearbeiten**, und **löschen** Vorgänge übernommen oder zurückgesetzt werden können. Die Auswirkungen der **CommitTrans** und **Rollback** kann dazu führen, dass den aktuellen Datensatz im Bearbeitungspuffer nicht wiederhergestellt werden. Um sicherzustellen, dass der aktuelle Datensatz ordnungsgemäß wiederhergestellt wird, ist es wichtig zu verstehen, wie die **CommitTrans** und **Rollback** Memberfunktionen der `CDatabase` können Sie mit den Funktionen der Aktualisierung der `CRecordset`.  
  
##  <a name="_core_how_committrans_affects_updates"></a> Wie wirkt sich auf CommitTrans Updates  
 Die folgende Tabelle erläutert die Auswirkungen der **CommitTrans** Transaktionen.  
  
### <a name="how-committrans-affects-updates"></a>Wie wirkt sich auf CommitTrans Updates  
  
|Vorgang|Status der Datenquelle|  
|---------------|---------------------------|  
|`AddNew` und **Update**, und klicken Sie dann **CommitTrans**|Neuen Eintrag Datenquelle hinzugefügt werden.|  
|`AddNew` (ohne **Update**), und klicken Sie dann **CommitTrans**|Neuen Eintrag geht verloren. Datensatz nicht zur Datenquelle hinzugefügt.|  
|**Bearbeiten Sie** und **Update**, und klicken Sie dann **CommitTrans**|Änderungen an Datenquelle übergeben.|  
|**Bearbeiten Sie** (ohne **Update**), und klicken Sie dann **CommitTrans**|Änderungen an den Datensatz verloren. Datensatz bleibt in der Datenquelle unverändert.|  
|**Löschen Sie** dann **CommitTrans**|Datensätze, die aus der Datenquelle gelöscht werden.|  
  
##  <a name="_core_how_rollback_affects_updates"></a> Wie wirkt sich auf Rollback Transaktionen  
 Die folgende Tabelle erläutert die Auswirkungen der **Rollback** Transaktionen.  
  
### <a name="how-rollback-affects-transactions"></a>Wie wirkt sich auf Rollback Transaktionen  
  
|Vorgang|Status des aktuellen Datensatzes|Sie müssen auch|Status der Datenquelle|  
|---------------|------------------------------|-------------------|---------------------------|  
|`AddNew` und **Update**, klicken Sie dann **Rollback**|Inhalt des aktuellen Datensatzes ist temporär gespeichert, um Platz für den neuen Datensatz zu schaffen. Neuen Eintrag wird in Bearbeitungspuffer eingegeben. Nach dem **Update** aufgerufen wird, wird der aktuelle Datensatz im Bearbeitungspuffer wiederhergestellt wird.||Zusätzlich zu der Datenquelle vorgenommen werden, indem **Update** wird umgekehrt.|  
|`AddNew` (ohne **Update**), klicken Sie dann **Rollback**|Inhalt des aktuellen Datensatzes ist temporär gespeichert, um Platz für den neuen Datensatz zu schaffen. Bearbeiten Sie Puffer enthält den neuen Datensatz.|Rufen Sie `AddNew` erneut aus, um einen leeren, neuen Datensatz Bearbeitungspuffer wiederherzustellen. Oder rufen Sie **verschieben**(0), um die alten Werte im Bearbeitungspuffer wiederherzustellen.|Da **Update** wurde nicht aufgerufen, es wurden keine Änderungen an der Datenquelle vorgenommen wurden.|  
|**Bearbeiten Sie** und **Update**, klicken Sie dann **Rollback**|Eine unveränderte Version des aktuellen Datensatzes ist temporär gespeichert. Änderungen werden auf den Inhalt des Bearbeitungspuffers vorgenommen. Nach dem **Update** aufgerufen wird, die unveränderte Version des Datensatzes weiterhin temporär gespeichert.|*Dynaset*: Führen Sie einen Bildlauf aus dem aktuellen Datensatz, und klicken Sie dann zurück an die unveränderte Version des Datensatzes im Bearbeitungspuffer wiederherzustellen.<br /><br /> *Momentaufnahme*: Rufen Sie **Requery** das Recordset aus der Datenquelle zu aktualisieren.|Änderungen an der Datenquelle vorgenommen werden, indem **Update** rückgängig gemacht werden.|  
|**Bearbeiten Sie** (ohne **Update**), klicken Sie dann **Rollback**|Eine unveränderte Version des aktuellen Datensatzes ist temporär gespeichert. Änderungen werden auf den Inhalt des Bearbeitungspuffers vorgenommen.|Rufen Sie **bearbeiten** erneut aus, um die unveränderte Version des Datensatzes im Bearbeitungspuffer wiederherzustellen.|Da **Update** wurde nicht aufgerufen, es wurden keine Änderungen an der Datenquelle vorgenommen wurden.|  
|**Löschen Sie** dann **Rollback**|Inhalt des aktuellen Datensatzes wird gelöscht.|Rufen Sie **Requery** den Inhalt des aktuellen Datensatzes aus der Datenquelle wiederhergestellt.|Löschen von Daten aus der Datenquelle wird umgekehrt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)