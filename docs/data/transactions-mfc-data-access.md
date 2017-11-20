---
title: Transaktionen (MFC-Datenzugriff) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 655c8e2cc900aa369055e5f1b9975e02c1a8ac88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="transactions--mfc-data-access"></a>Transaktionen (MFC-Datenzugriff)
Das Konzept der Transaktionen wurde entwickelt, um Fälle zu behandeln, in denen der resultierende Status der Datenbank vom Gesamterfolg einer Reihe von Operationen abhängt. Dieses könnte vorkommen, da aufeinander folgende Operationen die Ergebnisse von vorangegangenen Operationen ändern können. Wenn eine der Operationen fehlschlägt, kann der resultierende Status in solchen Fällen unbestimmt sein.  
  
 Um dieses Problem zu lösen, gruppieren die Transaktionen eine Reihe von Operationen so, dass die Integrität des Endergebnisses sichergestellt werden kann. Alle Operationen müssen erfolgreich sein, und anschließend muss ein Commit ausgeführt werden (Schreiben in die Datenbank), oder die ganze Transaktion schägt fehl. Der Abbruch einer Transaktion wird als Rollback bezeichnet. Rollbacks ermöglichen die Wiederherstellung von Änderungen, und die Datenbank wird in den Zustand versetzt, der vor der Transaktion vorhanden war.  
  
 Wenn Sie beispielsweise bei einer automatisierten Banküberweisung Geld von Konto A auf Konto B übertragen, muss sowohl die Abbuchung von Konto A als auch die Einzahlung auf Konto B erfolgreich sein, damit die Überweisung fehlerfrei erfolgt, oder die ganze Transaktion schlägt fehl.  
  
 Eine Transaktion muss über ACID-Eigenschaften verfügen, die für Folgendes stehen:  
  
-   **Unteilbarkeit** eine Transaktion ist eine unteilbare Arbeitseinheit und wird genau einmal ausgeführt; erledigt wird oder nichts davon ist.  
  
-   **Konsistenz** eine Transaktion behält die Konsistenz der Daten, die ein konsistenten Zustand der Daten in einen anderen konsistenten Zustand der Daten transformiert. Durch eine Transaktion gebundene Daten müssen semantisch erhalten bleiben.  
  
-   **Isolation** eine Transaktion ist eine Isolationseinheit, und jede einzelne erfolgt separat und unabhängig von gleichzeitigen Transaktionen. Eine Transaktion sollte nie die Zwischenschritte einer anderen Transaktion sehen.  
  
-   **Dauerhaftigkeit** eine Transaktion ist eine Wiederherstellungseinheit. Wenn eine Transaktion erfolgreich ausgeführt wird, werden die entsprechenden Aktualisierungen beibehalten, auch wenn das System abstürzt oder heruntergefahren wird. Schlägt eine Transaktion fehl, verbleibt das System in dem Zustand, der vor der Ausführung eines Commit für die Transaktion vorhanden war.  
  
 Sie können Transaktionen in OLE DB-Unterstützung (finden Sie unter [unterstützen von Transaktionen in OLE DB-](../data/oledb/supporting-transactions-in-ole-db.md)) oder ODBC (finden Sie unter [Transaktion (ODBC)](../data/odbc/transaction-odbc.md)).  
  
 Eine verteilte Transaktion ist eine Transaktion, die verteilte Daten aktualisiert. Dabei handelt es sich also um Daten, die sich auf mehreren vernetzten Computersystemen befinden. Wenn Sie Transaktionen über ein verteiltes System unterstützen möchten, sollten Sie ADO.NET anstelle der OLE DB-transaktionsunterstützung verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenzugriffsprogrammierung (MFC/ATL)](../data/data-access-programming-mfc-atl.md)