---
title: ODBC und MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
ms.openlocfilehash: 9b7d04e2eb8bbb1adf96e05282861ef33e20434a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395871"
---
# <a name="odbc-and-mfc"></a>ODBC und MFC

> [!NOTE]
>  Um die MFC-Datenbankklassen verwenden zu können, müssen Sie den entsprechenden ODBC-Treiber für Ihre Datenquelle verfügen. Die neuesten Microsoft ODBC-Treiber für SQL Server ist [Microsoft ODBC Driver 13 für SQL Server](https://www.microsoft.com/download/details.aspx?id=50420). Die meisten Datenbankanbieter Geben Sie einen ODBC-Treiber für Windows.

Dieses Thema enthält die wichtigsten Konzepte von Klassen für die Microsoft Foundation Classes (MFC)-Bibliothek-ODBC-basierten Datenbank und bietet eine Übersicht über das Zusammenwirken der Klassen. Weitere Informationen zu ODBC und MFC finden Sie unter den folgenden Themen:

- [Aufbauen der Verbindung zu einer Datenquelle](connecting-to-a-data-source.md)

- [Auswählen und Verändern von Datensätzen](selecting-and-manipulating-records.md)

- [Anzeigen und Verändern von Daten in einem Formular](displaying-and-manipulating-data-in-a-form.md)

- [Arbeiten mit Dokumenten und Ansichten](working-with-documents-and-views.md)

- [Zugreifen auf ODBC und SQL](access-to-odbc-and-sql.md)

- [Weiterführende Themen zu MFC-ODBC-Klassen](further-reading-about-the-mfc-odbc-classes.md)

Die MFC-Datenbankklassen-ODBC-basierten dienen zum Zugriff auf eine Datenbank geben Sie für die ein ODBC-Treiber verfügbar ist. Da die Klassen ODBC verwenden, kann Ihre Anwendung Daten in vielen verschiedenen Datenformaten und verschiedene Konfigurationen von lokaler und Remote zugreifen. Sie müssen keinen speziellen Code zum Behandeln von anderen Datenbank-Managementsystemen (DBMS) zu schreiben. Solange Ihre Benutzer über einen entsprechenden ODBC-Treiber für die Daten, die sie zugreifen möchten verfügen, können sie das Programm verwenden, zum Bearbeiten von Daten in Tabellen, die dort gespeichert.

## <a name="see-also"></a>Siehe auch

[Open Database Connectivity (ODBC)](open-database-connectivity-odbc.md)