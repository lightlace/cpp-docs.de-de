---
title: Datenquelle (ODBC) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e4276c997069e69d6e84dd4426af4b82c2a839b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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