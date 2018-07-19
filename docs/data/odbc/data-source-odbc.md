---
title: Datenquelle (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 842a8bf3faadcf96b4f44441e45dc94d5679f9f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087873"
---
# <a name="data-source-odbc"></a>Datenquelle (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In Datenbankterminologie ausgedrückt setzt sich eine Datenquelle aus einem bestimmten Satz von Daten zusammen, den Informationen, die für den Zugriff auf die Daten notwendig sind, und der Position der Datenquelle, die in Form eines Datenquellennamens beschrieben werden kann. Zur Bearbeitung der Klasse [CDatabase](../../mfc/reference/cdatabase-class.md), muss die Datenquelle, die Sie über Open Database Connectivity (ODBC)-Administrator konfiguriert haben. Beispiele für Datenquellen sind eine remote-Datenbank auf Microsoft SQL Server ausgeführt wird, über ein Netzwerk oder eine Microsoft Access-Datei in einem lokalen Verzeichnis. Sie können von der Anwendung aus auf jede Datenquelle zugreifen, für die Sie einen ODBC-Treiber besitzen.  
  
 In der Anwendung können eine oder mehrere Datenquellen gleichzeitig aktiv sein. Dabei wird jede von einem `CDatabase`-Objekt repräsentiert. Es können auch gleichzeitig mehrere Verbindungen zu einer Datenquelle bestehen. Sie können eine Verbindung zu Remote- oder zu lokalen Datenquellen aufbauen, je nachdem, welche Treiber installiert wurden und welche Funktionen diese ODBC-Treiber unterstützen. Weitere Informationen zu Datenquellen und ODBC-Administrator finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [ODBC-Administrator](../../data/odbc/odbc-administrator.md).  
  
 Die folgenden Themen enthalten weitere Informationen zu Datenquellen:  
  
-   [Datenquelle: Verwalten von Verbindungen (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)