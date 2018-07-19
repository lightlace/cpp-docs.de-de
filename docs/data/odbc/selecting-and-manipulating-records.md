---
title: Auswählen und Verändern von Datensätzen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a4b76d0b4273e5afb32206336b4aabbfe9294eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090077"
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