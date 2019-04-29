---
title: 'Recordset: Ausführen einer Verknüpfung (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
ms.openlocfilehash: 9e589f00ec0512794d14accc6bb33c0e7adbd378
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397727"
---
# <a name="recordset-performing-a-join-odbc"></a>Recordset: Ausführen einer Verknüpfung (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

## <a name="what-a-join-is"></a>Was ist ein Join

Der Verknüpfungsvorgang, der eine häufige Aufgabe für die Datenzugriffs-ermöglicht Ihnen die Arbeit mit Daten aus mehr als eine Tabelle mit einem einzigen Recordset-Objekt. Verknüpfen von zwei oder mehr Tabellen führt zu einem Recordset, die Spalten aus jeder Tabelle darf, sondern wird als eine einzelne Tabelle zu Ihrer Anwendung angezeigt. Manchmal verwendet die Verknüpfung für alle Spalten aus allen Tabellen, aber manchmal SQL **wählen** -Klausel in einer Verknüpfung verwendet nur einige der Spalten aus jeder Tabelle. Die Datenbankklassen unterstützen nur-Lese Joins, aber keine aktualisierbaren Joins.

Um Datensätze mit Spalten aus verknüpften Tabellen auswählen zu können, benötigen Sie Folgendes:

- Eine Tabellenliste mit den Namen aller Tabellen verknüpft wird.

- Eine Liste der Spalten, die die Namen aller beteiligten Spalten enthält. Spalten, die mit dem gleichen Namen, aber aus unterschiedlichen Tabellen werden durch den Tabellennamen gekennzeichnet.

- Ein Filter (SQL **, in denen** Klausel), der gibt an, die Spalten, die auf dem die Tabellen verknüpft sind. Dieser Filter nimmt die Form "Table1.KeyCol Table2.KeyCol =" und den Join führt.

Sie können mehr als zwei Tabellen auf die gleiche Weise beitreten, indem die Spaltenpaare mehrere Paare von Spalten mithilfe der SQL-Schlüsselwort **und**.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)