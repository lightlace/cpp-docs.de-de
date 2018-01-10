---
title: Datenzugriff in Visual C++ | Microsoft Docs
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eaefb5f3ed8bd0c586e42527d47918dbb0dd5a57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="data-access-in-visual-c"></a>Datenzugriff in Visual C++

Praktisch alle Datenbankprodukte, SQL und NoSQL, bieten eine Schnittstelle für native C++-Anwendungen. Die Branchenstandardschnittstelle ist ODBC, die von allen wichtigen Produkten für die SQL-Datenbank und vielen NoSQL-Produkten unterstützt wird. Wenden Sie sich bei Nicht-Microsoft-Produkten für weitere Informationen an den Hersteller. Drittanbieter-Bibliotheken mit verschiedenen Lizenzbedingungen sind ebenfalls verfügbar.

Seit 2011 hat Microsoft ODBC als Standard für native Anwendungen zur Verbindung mit Microsoft SQL Server-Datenbanken sowohl lokal als auch in der Cloud ausgerichtet. Weitere Informationen finden Sie unter [Datenzugriffsprogrammierung \(MFC-ATL\)](data-access-programming-mfc-atl.md). Bei C++/CLI-Bibliotheken können die nativen ODBC-Treiber oder ADO.NET verwendet werden. Weitere Informationen finden Sie unter [Datenzugriff mit ADO.NET (C++-CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) und [Zugreifen auf Daten in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>In diesem Abschnitt
[Zugriff Datenprogrammierung (MFC/ATL)](data-access-programming-mfc-atl.md) beschreibt legacy datenzugriffsprogrammierung mit Visual C++, wobei die bevorzugte Methode ist die Verwendung einer der Klassenbibliotheken, z. B. die (ATL = Active Template Class Library) oder die Microsoft Foundation Class (MFC)-Bibliothek, die Arbeit mit Datenbank-APIs vereinfachen.

[Öffnen Sie die Database Connectivity (ODBC)](odbc/open-database-connectivity-odbc.md) der Microsoft Foundation Classes (MFC)-Bibliothek stellt Klassen für die Programmierung mit Open Database Connectivity (ODBC).

[OLE DB-Programmierung](oledb/ole-db-programming.md) eine größtenteils legacy-Schnittstelle weiterhin in einigen Szenarien erforderlich ist, insbesondere bei der Programmierung für Verbindungsserver.

## <a name="related-topics"></a>Verwandte Themen
[Herstellen einer Verbindung mit SQL-Datenbank, die mit C und C++](/azure/sql-database/sql-database-develop-cplusplus-simple) Verbinden mit Azure SQL-Datenbank von C- oder C++-Anwendungen.

[Microsoft Azure-Speicherclientbibliothek für C++](https://github.com/Azure/azure-storage-cpp)
[Azure-Speicher](/azure/storage/storage-introduction) ist eine Cloud-speicherlösung für moderne Anwendungen, Dauerhaftigkeit, Verfügbarkeit und Skalierbarkeit, um den Bedürfnissen ihrer Kunden. Stellen Sie eine Verbindung zu Azure Storage von C++ mithilfe der Azure Storage-Clientbibliothek für C++ her.

[ODBC Driver 13.1 for SQL Server - Windows freigegeben](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server) der aktuelle ODBC-Treiber stellt zuverlässigen Datenzugriff auf Microsoft SQL Server 2016 Microsoft Azure SQL-Datenbank für C/C++-Anwendungen basierte. Bietet Unterstützung für einschließlich grundsätzlichen, Azure Active Directory und AlwaysOn-Verfügbarkeitsgruppen. Auch für MacOS und Linux verfügbar.     
 
[SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client-programming) SQL Server Native Client ist eine eigenständige Data Access Anwendungsprogrammierschnittstelle (API), verwendet für OLE DB und ODBC, die SQL Server 2005 über SQL Server 2014 unterstützt. Neue Anwendungen sollten den ODBC-Treiber 13.1 für SQL Server verwenden.

[Microsoft Azure C- und C++ Developer Center](https://azure.microsoft.com/develop/cpp/) Azure erleichtert das Erstellen von C++-Anwendungen mit mehr Flexibilität, Skalierbarkeit und Zuverlässigkeit mithilfe von Tools, die Ihnen gefallen.    

[Gewusst wie: Verwenden von Blob-Speicher von C++](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs) Azure Blob-Speicher ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte-Blobs gespeichert. Blob Storage kann beliebige Typen von Text oder Binärdaten speichern, z.B. Dokumente, Mediendateien oder Installationsprogramme für Anwendungen. Blob Storage wird auch als Objektspeicher bezeichnet.

[ODBC Programmer's Reference](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference) dient der ODBC-Schnittstelle für die Verwendung mit der Programmiersprache C. Die Verwendung der ODBC-Schnittstelle umfasst drei Bereiche: SQL-Anweisungen, ODBC-Funktionsaufrufe und C-Programmierung.

## <a name="see-also"></a>Siehe auch
[Visual C++](../visual-cpp-in-visual-studio.md)
