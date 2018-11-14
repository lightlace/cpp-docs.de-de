---
title: OLE DB-Programmierung
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
ms.openlocfilehash: 59bee1c204d2f101d8175ff42c78ca4bbdcaeb4c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523142"
---
# <a name="ole-db-programming"></a>OLE DB-Programmierung

Microsoft OLE DB ist eine veraltete Technologie. für neue Anwendungen ist es die erforderlichen Datenzugriffs-API für die verknüpfte SQL Server. Alle anderen neuen Anwendungen sollten ODBC verwenden. Der aktuelle OLE DB-Anbieter für SQL Server ist SQLNCLI11. DLL. Der Anbieter ist in SQL Server 2016 weiterhin versenden. Diese Dokumentation ist für Entwickler konzipiert, die vorhandene Anwendungen beibehalten, die bereits OLE DB verwenden.

Die OLE DB-Vorlagen sind C++-Vorlagen, die die Arbeit mit der OLE DB-Hochleistungsdatenbanktechnologie vereinfachen, indem sie Klassen bereitstellen, die viele häufig verwendete OLE DB-Schnittstellen implementieren. Diese Vorlagenbibliothek ist in Verbraucher- und Anbietervorlagen unterteilt.

Visual C++ verfügt auch über Assistentenunterstützung zum Erstellen von OLE DB-Startanwendungen.

Attribute können Sie auch um den OLE DB-verbrauchervorlagen zu implementieren.

|Themenbereich|Siehe|
|-------------------------|---------|
|Verwenden von OLE DB-Consumervorlagen (konzeptionelle Themen)|[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)|
|Verwenden von OLE DB-Anbietervorlagen (konzeptionelle Themen)|[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)|
|OLE DB-Vorlagenklassen und -Makros|[Referenz der OLE DB-Vorlagen](../../data/oledb/ole-db-templates.md) (Visual C++)|
|OLE DB-Consumerattribute|[OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md)|
|OLE DB-Schnittstellen|[OLE DB-Programmierreferenz](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming(v%3dvs.85)) (im Windows SDK)|
|OLE DB-Vorlagenbeispiele|[Beispiele für OLE DB-Vorlagen](https://github.com/Microsoft/VCSamples)|
|Übersicht über die Datenzugriffsprogrammierung (Visual C++)|[Datenzugriffsprogrammierung](../../data/data-access-programming-mfc-atl.md)|
|Konzeptionelle ODBC-Themen|[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)|

## <a name="see-also"></a>Siehe auch

[Datenzugriff](../data-access-in-cpp.md)