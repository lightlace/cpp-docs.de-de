---
title: 'Recordset: Ausführen einer Verknüpfung (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0be740a57f5c455b971dd23575401c666bf0723c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093310"
---
# <a name="recordset-performing-a-join-odbc"></a>Recordset: Ausführen einer Verknüpfung (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
## <a name="what-a-join-is"></a>Was ist ein Join  
 Die Join-Operation eine häufige Aufgabe für die Datenzugriffs-können Sie die Arbeit mit Daten aus mehreren Tabellen mit einem einzigen Recordset-Objekt. Verknüpfen von zwei oder mehr Tabellen führt zu einem Recordset, die Spalten aus jeder Tabelle darf, jedoch als eine einzelne Tabelle für Ihre Anwendung angezeigt wird. In einigen Fällen verwendet der Join alle Spalten aus allen Tabellen, aber in einigen Fällen die SQL **wählen** -Klausel in einen Join verwendet nur einige Spalten aus jeder Tabelle. Die Datenbankklassen unterstützen nur-Lese Joins, aber keine aktualisierbaren Joins.  
  
 Um die Datensätze mit Spalten aus verknüpften Tabellen auswählen, benötigen Sie die folgenden Elemente:  
  
-   Eine Liste ' Tabelle ', die die Namen aller zu verknüpfenden Tabellen enthält.  
  
-   Eine Liste der Spalte mit den Namen aller beteiligten Spalten. Spalten mit demselben Namen aber aus unterschiedlichen Tabellen werden durch den Tabellennamen qualifiziert.  
  
-   Ein Filter (SQL **, in denen** Klausel), die angibt, dass der Spalten, auf denen die Tabellen verknüpft sind. Dieser Filter nimmt die Form "Table1.KeyCol = Table2.KeyCol" und den Join führt.  
  
 Sie können mehr als zwei Tabellen auf die gleiche Weise beitreten, indem die Spaltenpaare mehrere Paare von Spalten durch das SQL-Schlüsselwort verknüpften **AND**.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)