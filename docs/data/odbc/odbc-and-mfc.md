---
title: ODBC und MFC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f4e90281b3202303fa95e44684f8250259d0d653
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-and-mfc"></a>ODBC und MFC
> [!NOTE]
>  Um den MFC-Datenbankklassen verwenden zu können, müssen Sie den entsprechenden ODBC-Treiber für die Datenquelle verfügen. Die neueste Microsoft ODBC Driver für SQL Server ist [Microsoft ODBC Driver 13 für SQL Server](https://www.microsoft.com/en-us/download/details.aspx?id=50420). Die meisten Datenbankhersteller Geben Sie einen ODBC-Treiber für Windows. 
  
 Dieses Thema enthält die wichtigsten Konzepte der ODBC-basierten Datenbankklassen von der Microsoft Foundation Classes (MFC)-Bibliothek und bietet einen Überblick darüber, wie die Klassen zusammenarbeiten. Weitere Informationen zu ODBC und MFC finden Sie unter den folgenden Themen:  
  
-   [Aufbauen der Verbindung zu einer Datenquelle](connecting-to-a-data-source.md)  
  
-   [Auswählen und Verändern von Datensätzen](selecting-and-manipulating-records.md)  
  
-   [Anzeigen und Verändern von Daten in einem Formular](displaying-and-manipulating-data-in-a-form.md)  
  
-   [Arbeiten mit Dokumenten und Ansichten](working-with-documents-and-views.md)  
  
-   [Zugreifen auf ODBC und SQL](access-to-odbc-and-sql.md)  
  
-   [Weiterführende Themen zu MFC-ODBC-Klassen](further-reading-about-the-mfc-odbc-classes.md)  
  
 Der ODBC-basierten MFC-Datenbankklassen dienen zum Zugriff auf eine Datenbank bereitstellen, für die ein ODBC-Treiber verfügbar ist. Da die Klassen ODBC verwenden, kann Ihre Anwendung Daten in vielen verschiedenen Datenformaten und andere lokale/Remote-Konfigurationen zugreifen. Sie müssen keinen speziellen Code zum Behandeln der anderen Datenbank-Managementsystemen (DBMS) zu schreiben. Als Ihre Benutzer einen entsprechenden ODBC-Treiber für die Daten, die sie zugreifen möchten verfügen, können sie Ihr Programm verwenden, zum Bearbeiten von Daten in Tabellen, die dort gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [Open Database Connectivity (ODBC)](open-database-connectivity-odbc.md)