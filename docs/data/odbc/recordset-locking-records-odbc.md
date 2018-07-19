---
title: 'Recordset: Sperren von Datensätzen (ODBC) | Microsoft Docs'
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
ms.openlocfilehash: 1fcef3233e4c2035cc481128d81723dad03fb18b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092136"
---
# <a name="recordset-locking-records-odbc"></a>Recordset: Sperren von Datensätzen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Die Arten von Datensatz zu sperren](#_core_record.2d.locking_modes).  
  
-   [Das Sperren von Datensätzen im Recordset während eines Updates](#_core_locking_records_in_your_recordset).  
  
 Wenn Sie ein Recordset verwenden, um einen Datensatz in der Datenquelle zu aktualisieren, kann die Anwendung den Datensatz sperren, sodass kein anderer Benutzer den Datensatz zur gleichen Zeit aktualisiert werden kann. Der Status eines Datensatzes, der von zwei Benutzern gleichzeitig aktualisiert ist nicht definiert, es sei denn, das System garantieren kann, dass einen Datensatz von zwei Benutzern gleichzeitig aktualisiert werden können.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, einige der Informationen ist nicht relevant. Angenommen, Sie können nicht aufgerufen werden der **bearbeiten** und **Update** Memberfunktionen. Weitere Informationen über das gesammelte finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_record.2d.locking_modes"></a> Datensatz Sperrverhalten  
 Die Datenbankklassen bieten zwei [Datensatz Sperrverhalten](../../mfc/reference/crecordset-class.md#setlockingmode):  
  
-   Eingeschränktes Sperren (Standard)  
  
-   vollständige Sperren  
  
 Aktualisieren eines Datensatzes erfolgt in drei Schritten:  
  
1.  Starten Sie den Vorgang durch einen Aufruf der [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Memberfunktion.  
  
2.  Sie ändern die entsprechenden Feldern des aktuellen Datensatzes.  
  
3.  Sie den Vorgang beenden, und normalerweise einen commit für das Update – durch Aufrufen der [aktualisieren](../../mfc/reference/crecordset-class.md#update) Memberfunktion.  
  
 Eingeschränktes Sperren sperrt den Datensatz in der Datenquelle nur während der **Update** aufrufen. Bei Verwendung von Parallelität in einer mehrbenutzerumgebung, sollte die Anwendung verarbeiten einer **Update** fehlerbedingung. Eingeschränkte Sperren wird den Datensatz als Sie rufen **bearbeiten** und ist nicht freigegeben werden, bis Sie Aufruf **Update** (Fehler werden angezeigt, über die `CDBException` Mechanismus nicht in einem Abstand von **"False"** zurückgegebenes **Update**). Vollständige Sperren eine Leistungseinbuße für andere Benutzer hat, da es sich bei gleichzeitigen Zugriff auf den gleichen Datensatz möglicherweise warten, bis zur Fertigstellung Ihrer Anwendung **Update** Prozess.  
  
##  <a name="_core_locking_records_in_your_recordset"></a> Sperren von Datensätzen im Recordset  
 Wenn Sie einem Recordset-Objekt ändern möchten [Sperrverhalten](#_core_record.2d.locking_modes) von der Standardeinstellung müssen Sie den Modus ändern, vor dem Aufruf **bearbeiten**.  
  
#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>So ändern Sie das aktuelle Sperrverhalten für das recordset  
  
1.  Rufen Sie die [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) -Memberfunktion, entweder **pessimistic** oder **CRecordset:: optimistic**.  
  
 Das neue Sperrverhalten bleibt wirksam, bis Sie ihn erneut ändern oder das Recordset geschlossen wird.  
  
> [!NOTE]
>  Nur relativ wenige ODBC-Treiber unterstützen zurzeit pessimistische Sperren.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)