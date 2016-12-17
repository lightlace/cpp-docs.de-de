---
title: "Transaktion (ODBC)"
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
  - "Datenbanken [C++], Transaktionen"
  - "ODBC [C++], Transaktionen"
  - "ODBC-Recordsets [C++], Transaktionen"
  - "ODBC-Recordsets [C++], Aktualisieren"
  - "Recordsets [C++], Transaktionen"
  - "Recordsets [C++], Aktualisieren"
  - "Transaktionen [C++], MFC-ODBC-Klassen"
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Transaktion (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Eine Transaktion ist eine Methode, um eine Reihe von Aktualisierungen an einer [Datenquelle](../../data/odbc/data-source-odbc.md) zu gruppieren oder in einem Batch zusammenzufassen, sodass für alle gleichzeitig ein Commit ausgeführt werden kann oder kein Commit erfolgt, falls ein Rollback für die Transaktion ausgeführt wird.  Falls Sie keine Transaktion verwenden, werden Änderungen an der Datenquelle automatisch durchgeführt, nicht erst nach einer Bestätigung.  
  
> [!NOTE]
>  Nicht alle ODBC\-Datenbanktreiber unterstützen Transaktionen.  Rufen Sie die `CanTransact`\-Memberfunktion eines [CDatabase](../../mfc/reference/cdatabase-class.md)\-Objekts oder [CRecordset](../../mfc/reference/crecordset-class.md)\-Objekts auf, um zu bestimmen, ob der Treiber Transaktionen für eine bestimmte Datenbank unterstützt.  Beachten Sie, dass `CanTransact` Sie nicht informiert, ob die Datenquelle eine vollständige Transaktionsunterstützung bietet.  Sie müssen nach **CommitTrans** und **Rollback** zusätzlich `CDatabase::GetCursorCommitBehavior` und `CDatabase::GetCursorRollbackBehavior` aufrufen, um die Auswirkung der Transaktion auf das geöffnete `CRecordset`\-Objekt zu überprüfen.  
  
 Aufrufe der `AddNew`\-Memberfunktion und **Edit**\-Memberfunktion eines `CRecordset`\-Objekts wirken sich sofort auf die Datenquelle aus, sobald Sie **Update** aufrufen.  **Delete**\-Aufrufe wirken sich ebenfalls sofort aus.  Wenn Sie im Gegensatz dazu eine Transaktion verwenden, die aus mehreren Aufrufen von `AddNew`, **Edit**, **Update** und **Delete** besteht, werden diese Operationen erst dann ausgeführt, wenn Sie explizit **CommitTrans** aufrufen.  Indem Sie eine Transaktion einrichten, können Sie eine Reihe solcher Aufrufe ausführen und sich trotzdem die Möglichkeit vorbehalten, diese zurückzusetzen.  Falls eine wichtige Ressource nicht verfügbar ist oder eine andere Bedingung verhindert, dass die vollständige Transaktion abgeschlossen werden kann, können Sie die Transaktion zurücksetzen, statt sie zu bestätigen.  In diesem Fall wirkt sich keine der in der Transaktion ausgeführten Änderungen auf die Datenquelle aus.  
  
> [!NOTE]
>  Zurzeit unterstützt die `CRecordset`\-Klasse keine Aktualisierungen der Datenquelle, wenn Sie das gesammelte Abrufen von Zeilen implementiert haben.  Dies bedeutet, dass Sie `AddNew`, **Edit**, **Delete** oder **Update** nicht aufrufen können.  Sie können jedoch eigene Funktionen erstellen, um Aktualisierungen durchzuführen und die Funktionen in Transaktionen aufzurufen.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Neben dem Recordset wirken sich Transaktionen auch auf SQL\-Anweisungen aus, die Sie direkt ausführen, sofern Sie eine mit einem `CDatabase`\-Objekt verknüpfte ODBC\-**HDBC** oder ein auf dieser **HDBC** basiertes ODBC\-**HSTMT** verwenden.  
  
 Transaktionen sind besonders nützlich, wenn mehrere Datensätze gleichzeitig zu aktualisieren sind.  In diesem Fall sollten Sie halbfertige Transaktionen vermeiden, wie sie z. B. auftreten, wenn eine Ausnahme vor Durchführung der letzten Aktualisierung ausgelöst wird.  Die Gruppierung solcher Aktualisierungen zu einer Transaktion gibt Ihnen die Möglichkeit, die Änderungen rückgängig zu machen \(zurückzusetzen\) und die Datensätze in den Zustand zu versetzen, in dem sie sich vor Beginn der Transaktion befanden.  Wenn eine Bank z. B. Geld von Konto A auf Konto B transferiert, müssen sowohl das Abheben von Konto A als auch die Einzahlung auf Konto B erfolgreich durchgeführt werden, damit die Überweisung fehlerfrei erfolgt. Andernfalls schlägt die gesamte Transaktion fehl.  
  
 In den Datenbankklassen führen Sie Transaktionen über `CDatabase`\-Objekte aus.  Ein `CDatabase`\-Objekt repräsentiert eine Verbindung zu einer Datenquelle. Eine oder mehrere mit diesem `CDatabase`\-Objekt verknüpfte Recordsets bearbeiten Datenbanktabellen mithilfe von Recordset\-Memberfunktionen.  
  
> [!NOTE]
>  Es wird nur eine Transaktionsebene unterstützt.  Sie können Transaktionen nicht schachteln. Eine Transaktion kann auch nicht mehrere Datenbankobjekte umfassen.  
  
 Die folgenden Themen enthalten weitere Informationen über die Ausführung von Transaktionen:  
  
-   [Transaktion: Ausführen einer Transaktion in einem Recordset \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [Transaktion: Auswirkungen von Transaktionen auf Aktualisierungen \(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)