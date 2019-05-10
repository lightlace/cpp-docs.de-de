---
title: Datenzugriffsprogrammierung (MFC / ATL)
ms.date: 11/16/2018
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
ms.openlocfilehash: e71e16bef29239e0c6a391b2d5e2129042cd52fa
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221846"
---
# <a name="data-access-programming-mfcatl"></a>Datenzugriffsprogrammierung (MFC/ATL)

Über die Jahre hinweg hat Visual C++ mehrere Möglichkeiten zum Arbeiten mit Datenbanken bereitgestellt. 2011 kündigte Microsoft an, dass es in Open Database Connectivity (ODBC) als bevorzugte Technologie für den Zugriff auf SQL Server-Produkte von nativem Code eine Ausrichtung auf. ODBC ist ein Branchenstandard, durch dessen Verwendung Sie die maximale Portabilität Ihres Codes über mehrere Plattformen und Datenquellen erreichen. Die meisten SQL-Datenbankprodukte und viele NoSQL-Produkte unterstützen ODBC. Sie können ODBC direkt verwenden, indem Sie die ODBC-APIs auf niedriger Ebene aufrufen, oder Sie können die MFC-ODBC-Wrapperklassen oder eine C++-Wrapperbibliothek eines Drittanbieters verwenden.

OLE DB ist eine leistungsstarke API auf niedriger Ebene, die auf der COM-Spezifikation basiert und nur unter Windows unterstützt wird. Verwenden Sie OLE DB, wenn Ihr Programm auf [Verbindungsserver](/sql/relational-databases/linked-servers/linked-servers-database-engine) zugreift. ATL stellt OLE DB-Vorlagen bereit, die das Erstellen von benutzerdefinierten OLE DB-Anbietern und -Consumern vereinfachen. Der neueste Anbieter für Microsoft SQL Server finden Sie in der Dokumentation für die [OLE DB-Treiber für SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server).

## <a name="porting-data-applications"></a>Portieren von datenanwendungen

Wenn Ihre ältere Anwendung OLE DB oder die ADO-Schnittstelle auf höherer Ebene für die Verbindung mit SQL Server verwendet, sollten Sie erwägen, auf die neueste Migration [OLE DB-Treiber für SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server) um die neuesten SQL Server-Features nutzen. Eine weitere Alternative, wenn Sie keine plattformübergreifende Portabilität oder der neuesten SQL Server-Funktionen benötigen möglicherweise Microsoft OLE DB-Anbieter für ODBC (MSDASQL) können Sie.  MSDASQL ermöglicht Anwendungen, die auf OLE DB und ADO (das OLE DB intern verwendet) erstellt wurden, den Zugriff auf Datenquellen über einen ODBC-Treiber. Wie bei jeder Übersetzungsebene kann sich MSDASQL auf die Datenbankleistung auswirken. Sie sollten testen, ob die Auswirkungen für Ihre Anwendung von Bedeutung sind. MSDASQL ist im Lieferumfang des Windows-Betriebssystems enthalten, und Windows Server 2008 sowie Windows Vista SP1 sind die ersten Windows-Releases, in denen eine 64-Bit-Version der Technologie enthalten ist.

Wenn Ihre C++ Anwendung eine Verbindung herstellt, in SQL Server oder Azure SQL-Datenbank über ODBC, muss bei Verwendung [den neuesten ODBC-Treiber](/sql/connect/odbc/download-odbc-driver-for-sql-server).

Wenn Sie C++/CLI verwenden, können Sie weiterhin wie gewohnt ADO.NET verwenden. Weitere Informationen finden Sie unter [Datenzugriff mit ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) und [Zugreifen auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).

- Neben den ODBC-Wrapperklassen stellt MFC auch Wrapperklassen für Datenzugriffsobjekte (Data Access Object, DAO) zum Herstellen einer Verbindung mit Access-Datenbanken bereit.  DAO ist jedoch veraltet. Jeglicher Code, der auf CDaoDatabase oder CDaoRecordset basiert, sollte upgegradet werden.

Weitere Informationen zur Geschichte von Datenzugriffstechnologien unter Windows finden Sie unter [Microsoft Data Access Components (Wikipedia) (Microsoft-Datenzugriffskomponenten)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>Siehe auch

[Datenzugriff](data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
