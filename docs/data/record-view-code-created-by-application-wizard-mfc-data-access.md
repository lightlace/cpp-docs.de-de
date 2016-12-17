---
title: "Vom Anwendungs-Assistenten erstellter Datensatzansichts-Code (MFC-Datenzugriff)"
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
  - "Anwendungsassistenten [C++], Datensatzansichtscode"
  - "Datensatzansichten, Anwendungs-Assistent-Code"
  - "Datensatzansichten, Aktualisieren von Steuerelementen"
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Vom Anwendungs-Assistenten erstellter Datensatzansichts-Code (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der [MFC\-Anwendungs\-Assistent](../mfc/reference/database-support-mfc-application-wizard.md) überschreibt die `OnInitialUpdate`\- und `OnGetRecordset`\-Memberfunktionen der Ansicht.  Nachdem das Framework das Rahmenfenster, Dokument und die Ansicht erstellt hat, wird `OnInitialUpdate` aufgerufen, um die Ansicht zu initialisieren.  `OnInitialUpdate` erhält einen Zeiger auf das Recordset aus dem Dokument.  Durch einen Aufruf der Basisklassenfunktion [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) wird das Recordset geöffnet.  Der folgende Code veranschaulicht diesen Prozess für einen `CRecordView` – der Code für einen `CDaoRecordView` ist ähnlich:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 Beim Öffnen des Recordsets werden Datensätze ausgewählt.  Mit [CRecordset::Open](../Topic/CRecordset::Open.md) oder [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md) macht den ersten Datensatz zum aktuellen Datensatz; DDX verschiebt Daten aus dem Recordset\-Felddatenmember in die entsprechenden Formularsteuerelemente in der Ansicht.  Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und \-validierung](../mfc/dialog-data-exchange-and-validation.md).  Informationen zum Erstellungsprozess von Dokumenten\/Ansichten finden Sie unter [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
> [!NOTE]
>  Sie sollten den Endbenutzern die Möglichkeit geben, die Steuerelemente der Datensatzansicht vom Recordset zu aktualisieren.  Ohne diese Funktion kann der Benutzer den aktuellen Datensatz möglicherweise nicht verlassen, wenn er als Wert für ein Steuerelement einen unzulässigen Wert eingibt.  Um die Steuerelemente zu aktualisieren, rufen Sie die `CWnd`\-Memberfunktion [UpdateData](../Topic/CWnd::UpdateData.md) mit dem Parameter **FALSE** auf.  
  
## Siehe auch  
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)