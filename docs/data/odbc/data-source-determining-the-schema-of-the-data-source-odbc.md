---
title: 'Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC) | Microsoft Docs'
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
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fc425cf767db6939223288ebe74dcbc7fd4cf5b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Zum Einrichten der Datenmember in Ihrem `CRecordset` -Objekte, müssen Sie wissen, das Schema der Datenquelle, dem Sie eine Verbindung herstellen. Bestimmen des Schemas einer Datenquelle umfasst das Abrufen einer Liste der Tabellen in der Datenquelle, die eine Liste der Spalten in jeder Tabelle, den Datentyp jeder Spalte und das Vorhandensein von Indizes.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Datenquelle: Verwalten von Verbindungen (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)