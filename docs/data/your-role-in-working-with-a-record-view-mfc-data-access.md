---
title: "Aufgaben bei der Arbeit mit Datensatzansichten (MFC-Datenzugriff)"
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
  - "MFC, Datensatzansichten"
  - "Datensatzansichten, Anpassen des Standardcodes"
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Aufgaben bei der Arbeit mit Datensatzansichten (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgende Tabelle zeigt, was Sie in der Regel tun müssen, um mit einer Datensatzansicht zu arbeiten, und wie das Framework Sie unterstützt.  
  
### Arbeiten mit einer Datensatzansicht: Sie und das Framework  
  
|Benutzer|Das Framework|  
|--------------|-------------------|  
|Verwenden Sie zum Entwerfen des Formulars den Visual C\+\+\-Dialog\-Editor.|Erstellt eine Dialogfeldvorlagen\-Ressource mit Steuerelementen.|  
|Verwenden Sie den [MFC\-Anwendungs\-Assistenten](../mfc/reference/database-support-mfc-application-wizard.md) zur Erstellung von Klassen, die von [CRecordView](../mfc/reference/crecordview-class.md) und [CRecordset](../mfc/reference/crecordset-class.md) oder von [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) und [CDaoRecordset](../mfc/reference/cdaorecordset-class.md) abgeleitet wurden.|Schreibt die Klassen für Sie.|  
|Weisen Sie Datensatzansichts\-Steuerelemente Recordset\-Felddatenmembern zu.|Stellt DDX zwischen den Steuerelementen und den Recordset\-Feldern bereit.|  
||Stellt Standardbefehlshandler für die Befehle **Erste verschieben**, **Letzte verschieben**, **Nächste verschieben** und **Vorherige verschieben** über Menüs und Symbolleisten\-Schaltflächen bereit.|  
||Aktualisiert Änderungen in der Datenbank.|  
|\[Optional\] Schreiben Sie Code, um Listen\- oder Kombinationsfelder oder andere Steuerelemente mit Daten aus einem zweiten Recordset zu füllen.||  
|\[Optional\] Schreiben Sie Code für spezielle Validierungen.||  
|\[Optional\] Schreiben Sie Code zum Hinzufügen oder Löschen von Datensätzen.||  
  
 Formularbasierte Programmierung ist nur eine Herangehensweise für die Arbeit mit einer Datenbank.  Informationen zu Anwendungen, die andere oder gar keine Benutzeroberflächen verwenden, finden Sie unter [MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten](../data/mfc-using-database-classes-with-documents-and-views.md) und [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md).  Alternative Ansätze zum Anzeigen von Datenbankdatensätzen finden Sie unter den Klassen [CListView](../mfc/reference/clistview-class.md) und [CTreeView](../mfc/reference/ctreeview-class.md).  
  
## Siehe auch  
 [Datensatzansichten \(MFC\-Datenzugriff\)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)