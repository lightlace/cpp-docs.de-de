---
title: Aufgaben bei der Arbeit mit Datensatzansichten (MFC-Datenzugriff) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e7a9d3fa7e828467e73c77736fb5643baf19660f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111093"
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>Aufgaben bei der Arbeit mit Datensatzansichten (MFC-Datenzugriff)
Die folgende Tabelle zeigt, was Sie in der Regel tun müssen, um mit einer Datensatzansicht zu arbeiten, und wie das Framework Sie unterstützt.  
  
### <a name="working-with-a-record-view-you-and-the-framework"></a>Arbeiten mit einer Datensatzansicht: Sie und das Framework  
  
|Benutzer|Das Framework|  
|---------|-------------------|  
|Verwenden Sie zum Entwerfen des Formulars den Visual C++-Dialog-Editor.|Erstellt eine Dialogfeldvorlagen-Ressource mit Steuerelementen.|  
|Verwenden der [MFC-Anwendung-Assistent](../mfc/reference/database-support-mfc-application-wizard.md) zum Erstellen von abgeleiteten Klassen [CRecordView](../mfc/reference/crecordview-class.md) und [CRecordset](../mfc/reference/crecordset-class.md).|Schreibt die Klassen für Sie.|  
|Weisen Sie Datensatzansichts-Steuerelemente Recordset-Felddatenmembern zu.|Stellt DDX zwischen den Steuerelementen und den Recordset-Feldern bereit.|  
||Stellt standardbefehlshandler für **erste verschieben**, **letzte verschieben**, **nächste verschieben**, und **vorherige verschieben** Befehle über Menüs und Symbolleisten Schaltflächen.|  
||Aktualisiert Änderungen in der Datenbank.|  
|[Optional] Schreiben Sie Code, um Listen- oder Kombinationsfelder oder andere Steuerelemente mit Daten aus einem zweiten Recordset zu füllen.||  
|[Optional] Schreiben Sie Code für spezielle Validierungen.||  
|[Optional] Schreiben Sie Code zum Hinzufügen oder Löschen von Datensätzen.||  
  
 Formularbasierte Programmierung ist nur eine Herangehensweise für die Arbeit mit einer Datenbank. Weitere Informationen zu Anwendungen, die andere oder gar keine Benutzeroberflächen verwenden, finden Sie unter [MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten](../data/mfc-using-database-classes-with-documents-and-views.md) und [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md). Alternative Ansätze zum Anzeigen von Datenbankdatensätzen finden Sie in den Klassen [CListView](../mfc/reference/clistview-class.md) und [CTreeView](../mfc/reference/ctreeview-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)