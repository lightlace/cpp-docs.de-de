---
title: "Ausw&#228;hlen und Ver&#228;ndern von Datens&#228;tzen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC-Recordsets, Auswählen von Datensätzen"
  - "Datensatzauswahl, MFC-ODBC-Klassen"
  - "Datensätze, Auswählen"
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Ausw&#228;hlen und Ver&#228;ndern von Datens&#228;tzen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie normalerweise mit einer SQL\-**SELECT**\-Anweisung Datensätze aus einer Datenquelle auswählen, erhalten Sie ein Resultset, d. h. eine Gruppe von Datensätzen aus einer Tabelle oder einer Abfrage.  Mit den Datenbankklassen wählen Sie mithilfe eines Recordset\-Objekts das Resultset aus und greifen darauf zu.  Dies ist ein Objekt einer anwendungsspezifischen Klasse, das Sie von der [CRecordset](../../mfc/reference/crecordset-class.md)\-Klasse ableiten.  Wenn Sie eine Recordset\-Klasse definieren, geben Sie die damit zu verknüpfende Datenquelle, die zu verwendende Tabelle und die Spalten der Tabelle an.  Der MFC\-Anwendungs\-Assistent oder **Klasse hinzufügen** \(wie beschrieben unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\) erstellt eine Klasse mit einer Verbindung zu einer bestimmten Datenquelle.  Die Assistenten schreiben die [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md)\-Memberfunktion der `CRecordset`\-Klasse, sodass diese den Tabellennamen zurückgibt.  Weitere Informationen zum Erstellen von Recordset\-Klassen mithilfe der Assistenten finden Sie unter [Datenbankunterstützung, MFC\-Anwendungs\-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md) und [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Mit einem [CRecordset](../../mfc/reference/crecordset-class.md)\-Objekt können Sie zur Laufzeit:  
  
-   die Datenfelder des aktuellen Datensatzes untersuchen;  
  
-   das Recordset filtern oder sortieren;  
  
-   die Standard\-SQL\-**SELECT**\-Anweisung anpassen;  
  
-   zwischen den ausgewählten Datensätzen wechseln;  
  
-   Datensätze hinzufügen, aktualisieren oder löschen \(falls sowohl die Datenquelle als auch das Recordset aktualisierbar sind\);  
  
-   überprüfen, ob das Recordset Neuabfragen ermöglicht, und den Inhalt des Recordsets aktualisieren.  
  
 Wenn Sie das Recordset\-Objekt nicht mehr verwenden, schließen und zerstören Sie es.  Weitere Informationen über Recordsets finden Sie unter [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md).  
  
## Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)