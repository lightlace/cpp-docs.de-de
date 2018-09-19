---
title: Transaktion (ODBC) | Microsoft-Dokumentation
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
ms.openlocfilehash: f142b4602ad1a9605987bc71e477e977902dccac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090268"
---
# <a name="transaction-odbc"></a>Transaktion (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
Eine Transaktion ist eine Möglichkeit, eine Gruppe oder ein batch, einer Reihe von Updates für eine [Datenquelle](../../data/odbc/data-source-odbc.md) , damit alle gleichzeitig ein Commit ausgeführt werden oder keine ein Commit ausgeführt, sind Wenn Sie ein Rollback der Transaktion auszuführen. Wenn Sie eine Transaktion nicht verwenden, sind Änderungen an der Datenquelle automatisch, anstatt nach Bedarf Commit ein Commit ausgeführt.  
  
> [!NOTE]
>  Nicht alle ODBC-Datenbanktreiber unterstützt Transaktionen. Rufen Sie die `CanTransact` Memberfunktion Ihre [CDatabase](../../mfc/reference/cdatabase-class.md) oder [CRecordset](../../mfc/reference/crecordset-class.md) bestimmt, ob der Treiber die Transaktionen für eine bestimmte Datenbank unterstützt. Beachten Sie, dass `CanTransact` enthält keine Informationen darüber, ob die Datenquelle vollständig Transaktion unterstützt. Sie müssen auch aufrufen, `CDatabase::GetCursorCommitBehavior` und `CDatabase::GetCursorRollbackBehavior` nach `CommitTrans` und `Rollback` , überprüfen Sie die Auswirkungen der Transaktion auf das geöffnete `CRecordset` Objekt.  
  
Aufrufe von der `AddNew` und `Edit` Memberfunktionen von einem `CRecordset` Objekt auswirken, die die Datenquelle sofort beim Aufruf `Update`. `Delete` Aufrufe werden auch sofort wirksam. Im Gegensatz dazu können Sie eine Transaktion besteht aus mehreren Aufrufen an `AddNew`, `Edit`, `Update`, und `Delete`, die ausgeführt werden, jedoch kein Commit ausgeführt, bis zum Aufruf von `CommitTrans` explizit. Durch die Einrichtung einer Transaktions, können Sie eine Reihe von solche Aufrufe ausführen, und behalten Sie die Möglichkeit, diese zurückzusetzen. Wenn eine wichtige Ressource nicht verfügbar ist, oder eine andere Bedingung verhindert, dass die gesamte Transaktion abgeschlossen wird, können Sie die Transaktion durch ein Commit zurücksetzen. In diesem Fall keine der Änderungen, die für die Transaktion gehören wirken sich auf die Datenquelle.  
  
> [!NOTE]
>  Derzeit Klasse `CRecordset` Aktualisierungen der Datenquelle nicht unterstützt, wenn Sie die massenzeilenabruf implementiert haben. Dies bedeutet, es können keine Aufrufe `AddNew`, `Edit`, `Delete`, oder `Update`. Allerdings können Sie Sie schreiben eigene Funktionen auf, um Updates ausführen, und klicken Sie dann rufen diese Funktionen innerhalb einer bestimmten Transaktion. Weitere Informationen zu gesammelten Abrufens von Zeilen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Neben der Auswirkungen auf das Recordset, Transaktionen Auswirkungen auf den SQL-Anweisungen, die Sie direkt ausführen, solange Sie die ODBC verwenden **HDBC** zugeordneten Ihrer `CDatabase` Objekt oder eine ODBC- **Befehls beschäftigt** basierend auf **HDBC**.  
  
Transaktionen sind besonders nützlich, wenn Sie mehrere Einträge verfügen, die gleichzeitig aktualisiert werden müssen. In diesem Fall möchten Sie vermeiden eine halb abgeschlossenen Transaktion, z. B. auftreten, wenn eine Ausnahme ausgelöst wurde, bevor das letzte Update durchgeführt wurde. Solche Updates in einer Transaktion gruppieren ermöglichen die Wiederherstellung (Rollback) von den Änderungen und die Datensätze in den Zustand vor zurückgegeben. Z. B. wenn eine Bank Geld von Konto A auf Konto B übertragen, sowohl die Abbuchung von A und der Einzahlung b erfolgreich sein, damit die Überweisung fehlerfrei erfolgt oder die gesamte Transaktion muss fehl.  
  
In der Datenbank, führen Sie Transaktionen über `CDatabase` Objekte. Ein `CDatabase` -Objekt stellt eine Verbindung mit einer Datenquelle und eine oder mehrere Recordsets zugeordnet sind, `CDatabase` Objekt, die für die Tabellen der Datenbank über das Recordset-Member-Funktionen verwendet werden.  
  
> [!NOTE]
>  Es wird nur eine Ebene von Transaktionen unterstützt. Transaktionen können nicht geschachtelt, noch kann eine Transaktion umfassen mehrere Datenbankobjekte.  
  
Die folgenden Themen Weitere Informationen zur Ausführung von Transaktionen:  
  
- [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
- [Transaktion: Wie Transaktionen sich auf Aktualisierungen auswirken (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## <a name="see-also"></a>Siehe auch  

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)