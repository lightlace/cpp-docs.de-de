---
title: "Datensatzansichten (MFC-Datenzugriff) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], Datensatzansichten"
  - "Datenbanken [C++], Datensatzansichten"
  - "Formulare [C++], Datenzugriffsaufgaben"
  - "MFC [C++], Datensatzansichten"
  - "ODBC-Recordsets [C++], Datensatzansichten"
  - "Datensatzansichten [C++]"
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Datensatzansichten (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Abschnitt bezieht sich nur auf MFC\-ODBC\- und DAO\-Klassen.  Informationen zu OLE DB\-Datensatzansichten finden Sie unter [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) und [Verwenden von OLE DB\-Datensatzansichten](../data/oledb/using-ole-db-record-views.md).  
  
 Zur Unterstützung von formularbasierten Datenzugriffsanwendungen stellt die Klassenbibliothek die Klasse [CRecordView](../mfc/reference/crecordview-class.md) und die Klasse [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) zur Verfügung.  Eine Datensatzansicht ist ein Formularansichtsobjekt, dessen Steuerelemente den Felddatenmembern eines [Recordset](../data/odbc/recordset-odbc.md)\-Objekts zugeordnet sind \(und indirekt den entsprechenden Spalten in einem Abfrageergebnis oder einer Tabelle in der Datenquelle\).  Wie ihre Basisklasse [CFormView](../mfc/reference/cformview-class.md), `CRecordView` und `CDaoRecordView` basieren sie auf einer Dialogfeldvorlagen\-Ressource.  
  
## Verwendungszwecke für Formulare  
 Formulare eignen sich für eine Vielzahl von Datenzugriffsaufgaben:  
  
-   Eingeben von Daten  
  
-   Durchführen von schreibgeschützten Prüfung von Daten  
  
-   Aktualisieren von Daten  
  
## Weitere Informationen zu Datensatzansichten  
 Die Informationen in diesen Themen gelten für die ODBC\-basierten und DAO\-basierte Klassen.  Verwenden Sie `CRecordView` für ODBC und `CDaoRecordView` für DAO.  
  
 Folgende Themen werden behandelt:  
  
-   [Features von Datensatzansichts\-Klassen](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [Datenaustausch für Datensatzansichten](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [Aufgaben bei der Arbeit mit Datensatzansichten](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [Entwerfen und Erstellen einer Datensatzansicht](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)  
  
## Siehe auch  
 [Datenzugriffsprogrammierung \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)   
 [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)