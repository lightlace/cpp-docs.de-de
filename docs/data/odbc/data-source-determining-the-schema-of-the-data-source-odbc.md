---
title: 'Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
ms.openlocfilehash: ed6500c5718cf90b39600b12659a3090fe9532ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580757"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Zum Einrichten der Datenmember in Ihrem `CRecordset` -Objekte, müssen Sie wissen, das Schema der Datenquelle, dem Sie eine Verbindung herstellen. Bestimmen des Schemas für die Datenquelle umfasst das Abrufen einer Liste der Tabellen in der Datenquelle, die eine Liste der Spalten in jeder Tabelle, die den Datentyp jeder Spalte und das Vorhandensein von Indizes.

## <a name="see-also"></a>Siehe auch

[Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Datenquelle: Verwalten von Verbindungen (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)