---
title: Schema (MFC-Datenzugriff)
ms.date: 11/04/2016
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
ms.openlocfilehash: 2dcfb5d22cf84fed7313686c943fbbd7c7ce1c84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512488"
---
# <a name="schema--mfc-data-access"></a>Schema (MFC-Datenzugriff)

Ein Datenbankschema beschreibt die aktuelle Struktur der Tabellen und Datenbankansichten in der Datenbank. Vom Assistenten generierter Code geht im Allgemeinen davon aus, dass das Schema für die Tabelle bzw. Tabellen, auf die ein Recordset zugreift, sich nicht ändert, die Datenbankklassen können jedoch einige Schemaänderungen verarbeiten, wie das Hinzufügen, Neuanordnen oder Löschen ungebundener Spalten. Wenn eine Tabelle geändert wird, müssen Sie das Recordset für die Tabelle manuell aktualisieren und die Anwendung anschließend neu kompilieren.

Sie können den vom Assistenten generierten Code auch ergänzen, um die Bearbeitung einer Datenbank zu ermöglichen, deren Schema zum Zeitpunkt der Kompilierung nicht vollständig bekannt ist. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Spalten (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

## <a name="see-also"></a>Siehe auch

[Datenzugriffsprogrammierung (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Recordset (ODBC)](../data/odbc/recordset-odbc.md)