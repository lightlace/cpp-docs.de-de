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
ms.openlocfilehash: 5417918ee3cf966183e1910fdbc12bd7b8cc046e
ms.sourcegitcommit: 984fb4814a2dd9bcea5ec88c9528707f17a7cffa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2018
ms.locfileid: "51949491"
---
# <a name="data-access-programming-mfcatl"></a>Datenzugriffsprogrammierung (MFC/ATL)

Über die Jahre hinweg hat Visual C++ mehrere Möglichkeiten zum Arbeiten mit Datenbanken bereitgestellt. 2011 kündigte Microsoft an, dass das Ausrichten auf ODBC als bevorzugte Technologie für den Zugriff auf SQL Server-Produkte über nativen Code angewendet wird. ODBC ist ein Branchenstandard, durch dessen Verwendung Sie die maximale Portabilität Ihres Codes über mehrere Plattformen und Datenquellen erreichen. Die meisten SQL-Datenbankprodukte und viele NoSQL-Produkte unterstützen ODBC. Sie können ODBC direkt verwenden, indem Sie die ODBC-APIs auf niedriger Ebene aufrufen, oder Sie können die MFC-ODBC-Wrapperklassen oder eine C++-Wrapperbibliothek eines Drittanbieters verwenden.

OLE DB ist eine leistungsstarke API auf niedriger Ebene, die auf der COM-Spezifikation basiert und nur unter Windows unterstützt wird. Verwenden Sie OLE DB, wenn Ihr Programm auf [Verbindungsserver](/sql/relational-databases/linked-servers/linked-servers-database-engine) zugreift. ATL stellt OLE DB-Vorlagen bereit, die das Erstellen von benutzerdefinierten OLE DB-Anbietern und -Consumern vereinfachen. Die neueste Version von OLE DB wird mit SQL Native Client 11 bereitgestellt.

## <a name="porting-data-applications"></a>Portieren von datenanwendungen

Wenn Ihre ältere Anwendung OLE DB oder die ADO-Schnittstelle auf höherer Ebene verwendet, um eine Verbindung mit SQL Server herzustellen, und Sie nicht auf Verbindungsserver zugreifen, sollten Sie eine Migration zu ODBC in naher Zukunft in Betracht ziehen. Wenn Sie keine plattformübergreifende Portabilität oder keine der neuesten SQL Server-Funktionen benötigen, können Sie wahrscheinlich den Microsoft OLE DB-Anbieter für ODBC (MSDASQL) verwenden.  MSDASQL ermöglicht Anwendungen, die auf OLE DB und ADO (das OLE DB intern verwendet) erstellt wurden, den Zugriff auf Datenquellen über einen ODBC-Treiber. Wie bei jeder kann MSDASQL datenbankleistung auswirken. Sie sollten testen, um zu bestimmen, ob die Auswirkungen für Ihre Anwendung von großer Bedeutung ist. MSDASQL ist im Lieferumfang des Windows-Betriebssystems enthalten, und Windows Server 2008 sowie Windows Vista SP1 sind die ersten Windows-Releases, in denen eine 64-Bit-Version der Technologie enthalten ist.

Die SQL Native Client-Komponente (SNAC), die OLE DB- und ODBC-Treiber in eine einzelne DLL packt, wird in ODBC-Anwendungen nicht mehr unterstützt. Die SQL Server 2012-Version von SNAC (SQLNCLI11.DLL) wird mit SQL Server 2016 geliefert, da andere SQL Server-Komponenten davon abhängig sind. Allerdings sollten neue C++-Anwendungen, die über ODBC eine Verbindung mit SQL Server oder Azure SQL-Datenbank herstellen, [den neuesten ODBC-Treiber](/sql/connect/odbc/download-odbc-driver-for-sql-server) verwenden. Weitere Informationen finden Sie unter [SQL Server Native Client Programming (SQL Server Native Client-Programmierung)](/sql/relational-databases/native-client/sql-server-native-client-programming)

Wenn Sie C++/CLI verwenden, können Sie weiterhin wie gewohnt ADO.NET verwenden. Weitere Informationen finden Sie unter [Datenzugriff mit ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) und [Zugreifen auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).

- Zusätzlich zu den ODBC-Wrapperklassen stellt MFC auch Datenzugriffsobjekte (DAO)-Wrapperklassen für die Verbindung mit Access-Datenbanken bereit.  DAO ist jedoch veraltet. Jeglicher Code, der auf CDaoDatabase oder CDaoRecordset basiert, sollte upgegradet werden.

Weitere Informationen zur Geschichte von Datenzugriffstechnologien unter Windows finden Sie unter [Microsoft Data Access Components (Wikipedia) (Microsoft-Datenzugriffskomponenten)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>Siehe auch

[Datenzugriff](data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
