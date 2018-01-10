---
title: Schema (MFC-Datenzugriff) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 76a38525f7fdf451d40f555d76d3557cbc155936
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="schema--mfc-data-access"></a>Schema (MFC-Datenzugriff)
Ein Datenbankschema beschreibt die aktuelle Struktur der Tabellen und Datenbankansichten in der Datenbank. Vom Assistenten generierter Code geht im Allgemeinen davon aus, dass das Schema für die Tabelle bzw. Tabellen, auf die ein Recordset zugreift, sich nicht ändert, die Datenbankklassen können jedoch einige Schemaänderungen verarbeiten, wie das Hinzufügen, Neuanordnen oder Löschen ungebundener Spalten. Wenn eine Tabelle geändert wird, müssen Sie das Recordset für die Tabelle manuell aktualisieren und die Anwendung anschließend neu kompilieren.  
  
 Sie können den vom Assistenten generierten Code auch ergänzen, um die Bearbeitung einer Datenbank zu ermöglichen, deren Schema zum Zeitpunkt der Kompilierung nicht vollständig bekannt ist. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Spalten (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenzugriffsprogrammierung (MFC/ATL)](../data/data-access-programming-mfc-atl.md)   
 [SQL](../data/odbc/sql.md)   
 [Recordset (ODBC)](../data/odbc/recordset-odbc.md)