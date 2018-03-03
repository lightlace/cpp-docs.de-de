---
title: "Auswählen und Verändern von Datensätzen | Microsoft Docs"
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
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dec5e0094405cf9d038e53959da97ba079736505
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="selecting-and-manipulating-records"></a>Auswählen und Verändern von Datensätzen
Normalerweise bei Auswahl Datensätze aus einer Datenquelle mit einer SQL **wählen** -Anweisung, erhalten Sie ein Resultset, das eine Gruppe von Datensätzen aus einer Tabelle oder einer Abfrage ist. Mit den Datenbankklassen verwenden Sie ein Recordset-Objekt auswählen und das Resultset zuzugreifen. Dies ist ein Objekt einer anwendungsspezifischen-Klasse, die Sie von der Klasse ableiten [CRecordset](../../mfc/reference/crecordset-class.md). Wenn Sie eine Recordset-Klasse definieren, geben Sie an der Datenquelle zum Zuordnen der Tabelle und die Spalten der Tabelle. MFC-Anwendung-Assistenten oder **Klasse hinzufügen** (wie in beschrieben [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) erstellt eine Klasse mit einer Verbindung mit einer bestimmten Datenquelle. Schreiben Sie die Assistenten der [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) Memberfunktion der Klasse `CRecordset` zum Zurückgeben des Namens der Tabelle. Weitere Informationen zum Verwenden der Assistenten zum Erstellen von Recordset-Klassen finden Sie unter [Datenbankunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md) und [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Mit einem [CRecordset](../../mfc/reference/crecordset-class.md) -Objekt zur Laufzeit können Sie:  
  
-   Überprüfen Sie die Datenfelder des aktuellen Datensatzes.  
  
-   Filtern Sie oder sortieren Sie das Recordset.  
  
-   Anpassen des Standard-SQL **wählen** Anweisung.  
  
-   Führen Sie einen Bildlauf durch die ausgewählten Datensätze.  
  
-   Hinzufügen, aktualisieren oder Löschen von Datensätzen (wenn die Datenquelle und das Recordset aktualisierbar sind).  
  
-   Testen Sie, ob das Recordset erneutes Abfragen zulässt, und aktualisieren Sie den Inhalt des Recordsets.  
  
 Wenn Sie fertig sind, verwenden das Recordset-Objekt, Sie schließen und zerstören. Weitere Informationen über Recordsets finden Sie unter [Recordset (ODBC)](../../data/odbc/recordset-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)