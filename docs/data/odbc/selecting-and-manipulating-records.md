---
title: Auswählen und Verändern von Datensätzen | Microsoft-Dokumentation
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
ms.openlocfilehash: 3220fe505bc4f4478fa663eab41f99f01d0f15d7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072094"
---
# <a name="selecting-and-manipulating-records"></a>Auswählen und Verändern von Datensätzen

Normalerweise bei der Auswahl Datensätze aus einer Datenquelle, die mittels einer SQL- **wählen** -Anweisung, erhalten Sie ein Resultset, die eine Gruppe von Datensätzen aus einer Tabelle oder einer Abfrage ist. Mit den Datenbankklassen verwenden Sie ein Recordset-Objekt auswählen und den Zugriff auf das Resultset an. Dies ist ein Objekt einer anwendungsspezifischen-Klasse, die Sie aus der Klasse abgeleitet sind [CRecordset](../../mfc/reference/crecordset-class.md). Wenn Sie eine Recordset-Klasse definieren, geben Sie an der Datenquelle zuordnen, in der Tabelle zu verwenden und die Spalten der Tabelle. MFC-Anwendung-Assistenten oder **Klasse hinzufügen** (siehe [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) erstellt eine Klasse mit einer Verbindung mit einer bestimmten Datenquelle. Schreiben Sie die Assistenten die [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) Memberfunktion der Klasse `CRecordset` den Namen der Tabelle zurückgegeben. Weitere Informationen zur Verwendung von der Assistenten zum Erstellen von Recordset-Klassen finden Sie unter [Datenbankunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md) und [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
Mit einem [CRecordset](../../mfc/reference/crecordset-class.md) Objekt zur Laufzeit können Sie:  
  
- Überprüfen Sie die Datenfelder des aktuellen Datensatzes an.  
  
- Filtern Sie oder sortieren Sie das Recordset.  
  
- Passen Sie die Standardeinstellungen SQL **wählen** Anweisung.  
  
- Scrollen Sie durch die ausgewählten Datensätze an.  
  
- Hinzufügen, aktualisieren oder Löschen von Datensätzen (Wenn sowohl der Datenquelle und das Recordset aktualisierbar sind).  
  
- Überprüfen Sie, ob das Recordset erneutes Abfragen ermöglicht, und aktualisieren Sie den Inhalt des Recordsets.  
  
Wenn Sie fertig sind, mithilfe des Recordset-Objekts, schließen und es zerstören. Weitere Informationen über Recordsets finden Sie unter [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  

[ODBC und MFC](../../data/odbc/odbc-and-mfc.md)