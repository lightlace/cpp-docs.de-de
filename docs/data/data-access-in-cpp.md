---
title: Datenzugriff in Visual C++
ms.date: 03/28/2017
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
ms.openlocfilehash: e9222f16ef6356c2d89401690bda7e6d27f8aba6
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708033"
---
# <a name="data-access-in-visual-c"></a>Datenzugriff in Visual C++

Praktisch alle Datenbankprodukte, SQL und NoSQL, bieten eine Schnittstelle für native C++-Anwendungen. Die Branchenstandardschnittstelle ist ODBC, die von allen wichtigen Produkten für die SQL-Datenbank und vielen NoSQL-Produkten unterstützt wird. Wenden Sie sich bei Nicht-Microsoft-Produkten für weitere Informationen an den Hersteller. Drittanbieter-Bibliotheken mit verschiedenen Lizenzbedingungen sind ebenfalls verfügbar.

Seit 2011 hat Microsoft ODBC als Standard für native Anwendungen zur Verbindung mit Microsoft SQL Server-Datenbanken sowohl lokal als auch in der Cloud ausgerichtet. Weitere Informationen finden Sie unter [Datenzugriffsprogrammierung \(MFC-ATL\)](data-access-programming-mfc-atl.md). Bei C++/CLI-Bibliotheken können die nativen ODBC-Treiber oder ADO.NET verwendet werden. Weitere Informationen finden Sie unter [Datenzugriff mit ADO.NET (C++-CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) und [Zugreifen auf Daten in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>In diesem Abschnitt

[Datenzugriffsprogrammierung (MFC/ATL)](data-access-programming-mfc-atl.md)<br/>
Beschreibt die Legacy-Datenzugriffsprogrammierung mit Visual C++, wobei die bevorzugte Zugriffsart in der Verwendung einer der Klassenbibliotheken, z. B. ATL (Active Template Class Library) oder MFC (Microsoft Foundation Class), besteht, die die Arbeit mit den Datenbank-APIs vereinfachen.

[Open Database Connectivity (ODBC)](odbc/open-database-connectivity-odbc.md)<br/>
Die MFC-Bibliothek (Microsoft Foundation Classes) stellt Klassen für die Programmierung mit ODBC (Open Database Connectivity) zur Verfügung.

[OLE DB-Programmierung](oledb/ole-db-programming.md)<br/>
Eine größtenteils veraltete Schnittstelle, die in einigen Szenarios immer noch erforderlich ist, insbesondere bei der Programmierung für Verbindungsserver.

## <a name="related-topics"></a>Verwandte Themen

[Herstellen einer Verbindung mit SQL-Datenbank mit C und C++](/azure/sql-database/sql-database-develop-cplusplus-simple)<br/>
Herstellen einer Verbindung mit Azure SQL-Datenbank aus C- oder C++-Anwendungen

[Microsoft Azure Storage-Clientbibliothek für C++](https://github.com/Azure/azure-storage-cpp)<br/>
[Azure Storage](/azure/storage/storage-introduction) ist eine Cloudspeicherlösung für moderne Anwendungen, die auf Stabilität, Verfügbarkeit und Skalierbarkeit für die Bedürfnisse ihrer Kunden beruhen. Stellen Sie eine Verbindung zu Azure Storage von C++ mithilfe der Azure Storage-Clientbibliothek für C++ her.

[ODBC-Treiber für SQL Server](/sql/connect/odbc/microsoft-odbc-driver-for-sql-server)<br/>
Der aktuelle ODBC-Treiber bietet zuverlässigen Datenzugriff auf Microsoft SQL Server und Microsoft Azure SQL-Datenbank für Anwendungen auf C/C++-Basis. Er bietet Unterstützung für Funktionen, z.B. Always Encrypted, Azure Active Directory und Always On-Verfügbarkeitsgruppen. Auch für MacOS und Linux verfügbar.

[Microsoft OLE DB-Treiber für SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server)<br/>
Der neueste OLE DB-Treiber ist eine eigenständige Anwendungsprogrammierschnittstelle (API) für Datenzugriffe, die Microsoft SQL Server und Microsoft Azure SQL-Datenbank unterstützt.

[Microsoft Azure C und C++ Developer Center](https://azure.microsoft.com/develop/cpp/)<br/>
Azure vereinfacht die C++-Anwendungsentwicklung mit mehr Flexibilität, Skalierbarkeit und Zuverlässigkeit mithilfe von Tools, die Sie lieben werden.

[Verwenden des Blob-Speichers mit C++](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)<br/>
Azure Blob Storage ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte/Blobs speichert. Blob Storage kann beliebige Typen von Text oder Binärdaten speichern, z.B. Dokumente, Mediendateien oder Installationsprogramme für Anwendungen. Blob Storage wird auch als Objektspeicher bezeichnet.

[ODBC-Programmierreferenz](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)<br/>
Die ODBC-Schnittstelle dient zur Verwendung mit der Programmiersprache C. Ein Verwenden der ODBC-Schnittstelle betrifft drei Bereiche: SQL-Anweisungen, ODBC-Funktionsaufrufe und C-Programmierung.

## <a name="see-also"></a>Siehe auch

[C++ in Visual Studio](../overview/visual-cpp-in-visual-studio.md)
