---
title: "ODBC-Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenbankklassen [C++], ODBC"
  - "ODBC-Klassen [C++]"
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ODBC-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen können mit den anderen Anwendungsframeworkklassen, um einfachen Zugriff auf eine Vielzahl von Datenbanken zu geben, für Treiber der Open Database Connectivity \(ODBC\) verfügbar sind.  
  
 Programme, die ODBC\-Datenbanken verwenden, verfügen mindestens ein `CDatabase`\-Objekt und ein `CRecordset`\-Objekt.  
  
 [CDatabase](../mfc/reference/cdatabase-class.md)  
 Kapselt eine Verbindung zu einer Datenquelle, von der Sie die Datenquelle ausgeführt werden können.  
  
 [CRecordset](../mfc/reference/crecordset-class.md)  
 Kapselt eine Gruppe von Datensätzen, die aus einer Datenquelle ausgewählt wird.  Recordsets ermöglichen Bildlauf von Datensatz zu Datensatz und aktualisieren die Datensätze \(Datensätze Hinzufügen, Bearbeiten und Löschen\), qualifizieren die Auswahl mit einem Filter sortieren, die Auswahl, und parametrisieren die Auswahl mit den Informationen, die zur Laufzeit abgerufen oder berechnet werden.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Formularansicht bereit, die direkt mit einem Recordset\-Objekt verbunden ist.  Durch den des Dialogdatenaustauschs \(DDX\) zwischen dem Recordset und den Steuerelementen der Datensatzansicht.  Wie alle Formularansichten ist eine Datensatzansicht auf einer Dialogfeldvorlagen\-Ressource.  Datensatzansichten unterstützen auch das Verschieben von Datensatz zu Datensatz im Recordset, Aktualisieren von Datensätzen und Schließen des zugeordneten Recordsets, wenn die Datensatzansicht enthält.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Eine Ausnahme, erstellten von Fehlern beim Datenzugriffsverarbeiten.  Diese Klasse dient den gleichen Zweck wie andere Ausnahmeklassen im Mechanismus für die Ausnahmenbehandlung der Klassenbibliothek.  
  
 [CFieldExchange](../mfc/reference/cfieldexchange-class.md)  
 Liefert Kontextinformationen, um Datensatzfeldaustausch \(RFX\) zu unterstützen, der dem Austausch von Daten zwischen den Felddatenmembern und den Parameterdatenmember eines Recordset\-Objekts und den entsprechenden Tabellenspalten in der Datenquelle.  Analog [CDataExchange](../mfc/reference/cdataexchange-class.md)\- Klasse, die auf ähnliche Weise für den Dialogdatenaustausch \(DDX\) verwendet wird.  
  
## Verwandte Klassen  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Kapselt ein Handle für Speicher für ein Binary Large Object \(BLOB\), z eine Bitmap.  `CLongBinary`\-Objekte werden verwendet, um die große Datenobjekte zu verwalten, die in den Datenbanktabellen gespeichert werden.  
  
 [CDBVariant](../mfc/reference/cdbvariant-class.md)  
 Ermöglicht es Ihnen, einen Wert ohne zu speichern, um den Datentyp des Werts verloren gehen.  `CDBVariant` verfolgt den Datentyp des aktuellen Werts, der in einer Union gespeichert wird.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)