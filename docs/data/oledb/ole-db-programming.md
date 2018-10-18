---
title: OLE DB-Programmierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 32f3fc1b6a990a746c3dc87740c63fbe898f79d5
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410628"
---
# <a name="ole-db-programming"></a>OLE DB-Programmierung

Microsoft OLE DB ist eine veraltete Technologie. für neue Anwendungen ist es die erforderlichen Datenzugriffs-API für die verknüpfte SQL Server. Alle anderen neuen Anwendungen sollten ODBC verwenden. Der aktuelle OLE DB-Anbieter für SQL Server ist SQLNCLI11. DLL. Der Anbieter ist in SQL Server 2016 weiterhin versenden. Diese Dokumentation ist für Entwickler konzipiert, die vorhandene Anwendungen beibehalten, die bereits OLE DB verwenden.
  
Die OLE DB-Vorlagen sind C++-Vorlagen, die die Arbeit mit der OLE DB-Hochleistungsdatenbanktechnologie vereinfachen, indem sie Klassen bereitstellen, die viele häufig verwendete OLE DB-Schnittstellen implementieren. Diese Vorlagenbibliothek ist in Verbraucher- und Anbietervorlagen unterteilt.  
  
Visual C++ verfügt auch über Assistentenunterstützung zum Erstellen von OLE DB-Startanwendungen.  
  
Darüber hinaus können Sie Attribute verwenden, um die OLE DB-Verbrauchervorlagen zu implementieren.  
  
|Themenbereich|Siehe|  
|-------------------------|---------|  
|Verwenden von OLE DB-Consumervorlagen (konzeptionelle Themen)|[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)|  
|Verwenden von OLE DB-Anbietervorlagen (konzeptionelle Themen)|[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)|  
|OLE DB-Vorlagenklassen und -Makros|[Referenz der OLE DB-Vorlagen](../../data/oledb/ole-db-templates.md) (Visual C++)|  
|OLE DB-Consumerattribute|[OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md)|  
|OLE DB-Schnittstellen|[OLE DB-Programmierreferenz](/previous-versions/windows/desktop/ms713643(v%3dvs.85)) (im Windows SDK)| 
|OLE DB-Vorlagenbeispiele|[Beispiele für OLE DB-Vorlagen](https://github.com/Microsoft/VCSamples)| 
|Übersicht über die Datenzugriffsprogrammierung (Visual C++)|[Datenzugriffsprogrammierung](../../data/data-access-programming-mfc-atl.md)|  
|Konzeptionelle ODBC-Themen|[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)|  

## <a name="see-also"></a>Siehe auch  

[Datenzugriff](../data-access-in-cpp.md)