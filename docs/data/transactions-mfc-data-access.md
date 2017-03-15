---
title: "Transaktionen (MFC-Datenzugriff) | Microsoft Docs"
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
  - "Datenbanken [C++], Transaktionen"
  - "Transaktionen [C++]"
  - "Transaktionen [C++], Unterstützung für"
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Transaktionen (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Konzept der Transaktionen wurde entwickelt, um Fälle zu behandeln, in denen der resultierende Status der Datenbank vom Gesamterfolg einer Reihe von Operationen abhängt.  Dieses könnte vorkommen, da aufeinander folgende Operationen die Ergebnisse von vorangegangenen Operationen ändern können.  Wenn eine der Operationen fehlschlägt, kann der resultierende Status in solchen Fällen unbestimmt sein.  
  
 Um dieses Problem zu lösen, gruppieren die Transaktionen eine Reihe von Operationen so, dass die Integrität des Endergebnisses sichergestellt werden kann.  Alle Operationen müssen erfolgreich sein, und anschließend muss ein Commit ausgeführt werden \(Schreiben in die Datenbank\), oder die ganze Transaktion schägt fehl.  Der Abbruch einer Transaktion wird als Rollback bezeichnet.  Rollbacks ermöglichen die Wiederherstellung von Änderungen, und die Datenbank wird in den Zustand versetzt, der vor der Transaktion vorhanden war.  
  
 Wenn Sie beispielsweise bei einer automatisierten Banküberweisung Geld von Konto A auf Konto B übertragen, muss sowohl die Abbuchung von Konto A als auch die Einzahlung auf Konto B erfolgreich sein, damit die Überweisung fehlerfrei erfolgt, oder die ganze Transaktion schlägt fehl.  
  
 Eine Transaktion muss über ACID\-Eigenschaften verfügen, die für Folgendes stehen:  
  
-   **Unteilbarkeit** Eine Transaktion ist eine unteilbare Arbeitseinheit und wird genau einmal ausgeführt; entweder wird der Vorgang vollständig ausgeführt, oder nichts davon wird erledigt.  
  
-   **Konsistenz** Eine Transaktion behält die Konsistenz der Daten bei, wobei ein konsistenter Zustand der Daten in einen anderen konsistenten Zustand der Daten transformiert wird.  Durch eine Transaktion gebundene Daten müssen semantisch erhalten bleiben.  
  
-   **Isolation** Eine Transaktion ist eine Isolationseinheit, und jede einzelne erfolgt separat und unabhängig von gleichzeitigen Transaktionen.  Eine Transaktion sollte nie die Zwischenschritte einer anderen Transaktion sehen.  
  
-   **Dauerhaftigkeit** Eine Transaktion ist eine Wiederherstellungseinheit.  Wenn eine Transaktion erfolgreich ausgeführt wird, werden die entsprechenden Aktualisierungen beibehalten, auch wenn das System abstürzt oder heruntergefahren wird.  Schlägt eine Transaktion fehl, verbleibt das System in dem Zustand, der vor der Ausführung eines Commit für die Transaktion vorhanden war.  
  
 Sie können Transaktionen in OLE DB \(siehe [Unterstützen von Transaktionen in OLE DB](../data/oledb/supporting-transactions-in-ole-db.md)\) oder ODBC \(siehe [Transaktion \(ODBC\)](../data/odbc/transaction-odbc.md)\) unterstützen.  
  
 Eine verteilte Transaktion ist eine Transaktion, die verteilte Daten aktualisiert. Dabei handelt es sich also um Daten, die sich auf mehreren vernetzten Computersystemen befinden.  Wenn Sie Transaktionen über ein verteiltes System unterstützen möchten, sollten Sie das Microsoft.NET Framework anstelle der OLE DB\-Transaktionsunterstützung verwenden.  
  
## Siehe auch  
 [Datenzugriffsprogrammierung \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)