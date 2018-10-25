---
title: 'Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b5ba9789226e54c9607e85caaa5e8af3f157f02d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052637"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Zum Einrichten der Datenmember in Ihrem `CRecordset` -Objekte, müssen Sie wissen, das Schema der Datenquelle, dem Sie eine Verbindung herstellen. Bestimmen des Schemas für die Datenquelle umfasst das Abrufen einer Liste der Tabellen in der Datenquelle, die eine Liste der Spalten in jeder Tabelle, die den Datentyp jeder Spalte und das Vorhandensein von Indizes.

## <a name="see-also"></a>Siehe auch

[Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Datenquelle: Verwalten von Verbindungen (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)