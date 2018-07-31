---
title: 'Recordset: Sperren von Datensätzen (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 344f567ab014fc854dcb44eebadcd7346af8e851
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339983"
---
# <a name="recordset-locking-records-odbc"></a>Recordset: Sperren von Datensätzen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Die Art von Datensatz zu sperren](#_core_record.2d.locking_modes).  
  
-   [Gewusst wie: Sperren Sie Datensätze im Recordset während eines Updates](#_core_locking_records_in_your_recordset).  
  
 Wenn Sie ein Recordset verwenden, um einen Datensatz für die Datenquelle zu aktualisieren, kann die Anwendung den Datensatz sperren, damit kein anderer Benutzer den Datensatz gleichzeitig aktualisiert werden kann. Der Status eines Datensatzes von zwei Benutzern aktualisiert werden, zur gleichen Zeit ist nicht definiert, es sei denn, das System, dass zwei Benutzer einen Datensatz gleichzeitig aktualisieren können nicht garantieren kann.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie die massenzeilenabruf implementiert haben, einige der Informationen ist nicht relevant. Angenommen, Sie können nicht aufrufen, die `Edit` und `Update` Memberfunktionen. Weitere Informationen zu gesammelten Abrufens von Zeilen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_record.2d.locking_modes"></a> Datensatzsperrung Modi  
 Die Datenbankklassen stellen zwei [Datensatzsperre Modi](../../mfc/reference/crecordset-class.md#setlockingmode):  
  
-   Eingeschränktes Sperren (Standard)  
  
-   Pessimistische Sperrung  
  
 Aktualisieren eines Datensatzes erfolgt in drei Schritten:  
  
1.  Starten Sie den Vorgang, durch einen Aufruf der [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Member-Funktion.  
  
2.  Sie ändern die entsprechenden Felder des aktuellen Datensatzes.  
  
3.  Erhalten Sie den Vorgang, und normalerweise einen commit für das Update – durch Aufrufen der [aktualisieren](../../mfc/reference/crecordset-class.md#update) Member-Funktion.  
  
 Der Datensatz für die Datenquelle nur während der optimistischen Sperre gesperrt, die `Update` aufrufen. Die Anwendung bei Verwendung von Parallelität in einer mehrbenutzerumgebung verarbeiten sollte ein `Update` fehlerbedingung. Der Datensatz pessimistische Sperrung gesperrt werden, sobald Sie aufrufen `Edit` aufgehoben wird, es bis Aufruf `Update` (Fehler werden angezeigt, über die `CDBException` Mechanismus nicht durch den Wert "false" zurückgegeben, die von `Update`). Pessimistische Sperrung eine Leistungseinbuße für andere Benutzer hat, da der gleichzeitige Zugriff auf den gleichen Datensatz möglicherweise warten, bis zur Beendigung der Anwendung `Update` Prozess.  
  
##  <a name="_core_locking_records_in_your_recordset"></a> Sperren von Datensätzen im Recordset  
 Wenn Sie einem Recordset-Objekt ändern möchten [Sperrmodus](#_core_record.2d.locking_modes) von der standardmäßigen, müssen Sie den Modus ändern, vor dem Aufruf `Edit`.  
  
#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>So ändern Sie den aktuellen Sperrmodus für das recordset  
  
1.  Rufen Sie die [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) Memberfunktion, dabei wird entweder `CRecordset::pessimistic` oder `CRecordset::optimistic`.  
  
 Das neue Sperrverhalten bleibt wirksam, bis Sie es erneut ändern, oder das Recordset geschlossen wird.  
  
> [!NOTE]
>  Nur relativ wenige ODBC-Treiber unterstützen derzeit die pessimistische Sperrung.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)