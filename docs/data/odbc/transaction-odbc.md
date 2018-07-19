---
title: Transaktion (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3acd47746d3a920b679fb5509c34e5978ad43eed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094025"
---
# <a name="transaction-odbc"></a>Transaktion (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Eine Transaktion ist eine Möglichkeit, eine Gruppe oder ein batch, eine Reihe von Updates für eine [Datenquelle](../../data/odbc/data-source-odbc.md) , damit alle gleichzeitig ein Commit ausgeführt werden oder keine ein Commit ausgeführt, sind Wenn Sie ein Rollback der Transaktion auszuführen. Wenn Sie eine Transaktion nicht verwenden, sind Änderungen an der Datenquelle automatisch anstatt bei Bedarf Commit ein Commit ausgeführt.  
  
> [!NOTE]
>  Nicht alle ODBC-Datenbanktreiber unterstützen Transaktionen. Rufen Sie die `CanTransact` Memberfunktion von Ihrem [CDatabase](../../mfc/reference/cdatabase-class.md) oder [CRecordset](../../mfc/reference/crecordset-class.md) bestimmt, ob der Treiber für eine bestimmte Datenbank Transaktionen unterstützt. Beachten Sie, dass `CanTransact` können Sie nicht ermitteln, ob die Datenquelle volle transaktionsunterstützung bereitstellt. Sie müssen auch aufrufen, `CDatabase::GetCursorCommitBehavior` und `CDatabase::GetCursorRollbackBehavior` nach **CommitTrans** und **Rollback** , überprüfen Sie die Auswirkungen der Transaktion auf der Open `CRecordset` Objekt.  
  
 Aufrufe von der `AddNew` und **bearbeiten** Memberfunktionen von einem `CRecordset` Objekt auswirken, die die Datenquelle sofort beim Aufruf **Update**. **Löschen Sie** Aufrufe auch sofort wirksam. Im Gegensatz dazu können Sie eine Transaktion besteht aus mehreren Aufrufen an `AddNew`, **bearbeiten**, **Update**, und **löschen**, die ausgeführt werden, doch kein Commit ausgeführt, bis Rufen Sie **CommitTrans** explizit. Durch die Einrichtung einer Transaktions, können Sie eine Reihe von solche Aufrufe ausführen, und behalten Sie die Möglichkeit, die sie für einen Rollback auszuführen. Wenn eine wichtige Ressource nicht verfügbar ist, oder eine andere Bedingung verhindert, dass die gesamte Transaktion abgeschlossen werden, können Sie die Transaktion ein Commit anstelle von zurücksetzen. In diesem Fall keine der Änderungen, die für die Transaktion gehören wirken sich auf die Datenquelle.  
  
> [!NOTE]
>  Derzeit-Klasse `CRecordset` unterstützt keine Updates für die Datenquelle aus, wenn Sie massenzeilenabruf implementiert haben. Dies bedeutet, Sie können keine Aufrufe an `AddNew`, **bearbeiten**, **löschen**, oder **Update**. Allerdings können Sie Sie eigene Funktionen schreiben Updates ausführen, und rufen Sie anschließend diese Funktionen innerhalb einer bestimmten Transaktion. Weitere Informationen über das gesammelte finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Neben Auswirkungen auf das Recordset, Transaktionen Auswirkungen auf den SQL-Anweisungen, die Sie direkt ausgeführt, solange Sie die ODBC verwenden **HDBC** zugeordneten Ihrer `CDatabase` Objekt oder eine ODBC- **Befehls beschäftigt** basierend auf **HDBC**.  
  
 Transaktionen sind besonders nützlich, wenn Sie mehrere Datensätze verfügen, die gleichzeitig aktualisiert werden müssen. In diesem Fall möchten Sie vermeiden eine Transaktion Halb fertig gestelltes, z. B. vorkommen, wenn eine Ausnahme ausgelöst wurde, bevor die letzte Aktualisierung vorgenommen wurde. Solche Updates zu einer Transaktion gruppiert ermöglichen die Wiederherstellung (Rollback) von Änderungen und gibt die Datensätze in den Zustand versetzt. Z. B. wenn eine Bank Geld von Konto A auf Konto B übertragen, sowohl die Abbuchung von als auch die Einzahlung auf B erfolgreich sein, damit die Überweisung fehlerfrei erfolgt oder muss die gesamte Transaktion ein Fehler auftreten.  
  
 In den Datenbankklassen führen Sie Transaktionen über `CDatabase` Objekte. Ein `CDatabase` Objekt stellt eine Verbindung mit einer Datenquelle dar und eine oder mehrere Recordsets zugeordnet sind, `CDatabase` Objekt arbeiten mit Tabellen der Datenbank über Memberfunktionen Recordset.  
  
> [!NOTE]
>  Es wird nur eine Ebene von Transaktionen unterstützt. Transaktionen können nicht geschachtelt, noch kann eine Transaktion umfassen mehrere Datenbankobjekte.  
  
 Die folgenden Themen enthalten weitere Informationen, wie Transaktionen ausgeführt werden:  
  
-   [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [Transaktion: Wie Transaktionen sich auf Aktualisierungen auswirken (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)