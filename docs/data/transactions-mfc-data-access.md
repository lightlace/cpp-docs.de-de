---
title: Transaktionen (MFC-Datenzugriff)
ms.date: 11/04/2016
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
ms.openlocfilehash: e3dc5b9319a8745ddb446ae7dbe895bfcd446c37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152656"
---
# <a name="transactions--mfc-data-access"></a>Transaktionen (MFC-Datenzugriff)

Das Konzept der Transaktionen wurde entwickelt, um Fälle zu behandeln, in denen der resultierende Status der Datenbank vom Gesamterfolg einer Reihe von Operationen abhängt. Dieses könnte vorkommen, da aufeinander folgende Operationen die Ergebnisse von vorangegangenen Operationen ändern können. Wenn eine der Operationen fehlschlägt, kann der resultierende Status in solchen Fällen unbestimmt sein.

Um dieses Problem zu lösen, gruppieren die Transaktionen eine Reihe von Operationen so, dass die Integrität des Endergebnisses sichergestellt werden kann. Alle Operationen müssen erfolgreich sein, und anschließend muss ein Commit ausgeführt werden (Schreiben in die Datenbank), oder die ganze Transaktion schägt fehl. Der Abbruch einer Transaktion wird als Rollback bezeichnet. Rollbacks ermöglichen die Wiederherstellung von Änderungen, und die Datenbank wird in den Zustand versetzt, der vor der Transaktion vorhanden war.

Wenn Sie beispielsweise bei einer automatisierten Banküberweisung Geld von Konto A auf Konto B übertragen, muss sowohl die Abbuchung von Konto A als auch die Einzahlung auf Konto B erfolgreich sein, damit die Überweisung fehlerfrei erfolgt, oder die ganze Transaktion schlägt fehl.

Eine Transaktion muss über ACID-Eigenschaften verfügen, die für Folgendes stehen:

- **Unteilbarkeit** eine Transaktion ist eine unteilbare Arbeitseinheit und wird genau einmal ausgeführt; alle die Arbeit erfolgt oder nichts davon ist.

- **Konsistenz** eine Transaktion behält die Konsistenz der Daten, die ein konsistenten Zustand der Daten in einen anderen konsistenten Zustand der Daten transformiert. Durch eine Transaktion gebundene Daten müssen semantisch erhalten bleiben.

- **Isolation** eine Transaktion ist eine Isolationseinheit, und jede einzelne erfolgt separat und unabhängig von gleichzeitigen Transaktionen. Eine Transaktion sollte nie die Zwischenschritte einer anderen Transaktion sehen.

- **Dauerhaftigkeit** eine Transaktion ist eine Wiederherstellungseinheit. Wenn eine Transaktion erfolgreich ausgeführt wird, werden die entsprechenden Aktualisierungen beibehalten, auch wenn das System abstürzt oder heruntergefahren wird. Schlägt eine Transaktion fehl, verbleibt das System in dem Zustand, der vor der Ausführung eines Commit für die Transaktion vorhanden war.

Sie können Transaktionen unterstützt, in der OLE DB (finden Sie unter [unterstützen von Transaktionen in OLE DB](../data/oledb/supporting-transactions-in-ole-db.md)) oder ODBC (finden Sie unter [Transaktion (ODBC)](../data/odbc/transaction-odbc.md)).

Eine verteilte Transaktion ist eine Transaktion, die verteilte Daten aktualisiert. Dabei handelt es sich also um Daten, die sich auf mehreren vernetzten Computersystemen befinden. Wenn Sie Transaktionen über ein verteiltes System unterstützen möchten, sollten Sie ADO.NET anstelle der OLE DB-transaktionsunterstützung verwenden.

## <a name="see-also"></a>Siehe auch

[Datenzugriffsprogrammierung (MFC/ATL)](../data/data-access-programming-mfc-atl.md)