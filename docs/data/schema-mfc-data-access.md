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
ms.openlocfilehash: cc333ee987ed0c6cba6cb11730d8f940e49d525d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039032"
---
# <a name="schema--mfc-data-access"></a>Schema (MFC-Datenzugriff)

Ein Datenbankschema beschreibt die aktuelle Struktur der Tabellen und Datenbankansichten in der Datenbank. Vom Assistenten generierter Code geht im Allgemeinen davon aus, dass das Schema für die Tabelle bzw. Tabellen, auf die ein Recordset zugreift, sich nicht ändert, die Datenbankklassen können jedoch einige Schemaänderungen verarbeiten, wie das Hinzufügen, Neuanordnen oder Löschen ungebundener Spalten. Wenn eine Tabelle geändert wird, müssen Sie das Recordset für die Tabelle manuell aktualisieren und die Anwendung anschließend neu kompilieren.

Sie können den vom Assistenten generierten Code auch ergänzen, um die Bearbeitung einer Datenbank zu ermöglichen, deren Schema zum Zeitpunkt der Kompilierung nicht vollständig bekannt ist. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

## <a name="see-also"></a>Siehe auch

[Datenzugriffsprogrammierung (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Recordset (ODBC)](../data/odbc/recordset-odbc.md)