---
title: "Anzeigen und Ver&#228;ndern von Daten in einem Formular | Microsoft Docs"
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
  - "Daten [MFC]"
  - "Daten [MFC], Anzeigen in einem Formular"
  - "Anzeigen von Daten [C++], Formulare"
  - "Formulare [C++], Anzeigen von Daten"
  - "ODBC [C++], Formulare"
  - "Datensatzansichten [C++], Anzeigen von Daten"
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Anzeigen und Ver&#228;ndern von Daten in einem Formular
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Viele Datenzugriffsanwendungen wählen Daten aus und zeigen sie in den Feldern eines Formulars an.  Die [CRecordView](../../mfc/reference/crecordview-class.md)\-Datenbankklasse stellt ein [CFormView](../../mfc/reference/cformview-class.md)\-Objekt zur Verfügung, das direkt mit einem Recordset\-Objekt verbunden ist.  Die Datensatzansicht verwendet den [Dialogdatenaustausch \(DDX\)](../../mfc/dialog-data-exchange-and-validation.md), um die Feldwerte des aktuellen Datensatzes vom Recordset in die Steuerelemente des Formulars zu verschieben bzw. um aktualisierte Informationen zurück in das Recordset zu verschieben.  Das Recordset verwendet wiederum den Datensatzfeldaustausch \(Record Field Exchange; RFX\), um Daten zwischen seinen Felddatenmembern und den entsprechenden Spalten in einer Tabelle der Datenquelle zu übertragen.  
  
 Sie können den MFC\-Anwendungs\-Assistenten oder **Klasse hinzufügen** verwenden \(wie unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) beschrieben\), um die Ansichtsklasse zusammen mit der zugehörigen Recordset\-Klasse zu erstellen.  
  
 Die Datensatzansicht und ihr Recordset werden zerstört, wenn Sie das Dokument schließen.  Weitere Informationen über Datensatzansichten finden Sie unter [Datensatzansichten](../../data/record-views-mfc-data-access.md).  Weitere Informationen über RFX finden unter [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md).  
  
## Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)