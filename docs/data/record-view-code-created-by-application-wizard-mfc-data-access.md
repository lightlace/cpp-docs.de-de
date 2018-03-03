---
title: Zeichnen Sie Code anzeigen, die vom Anwendungs-Assistenten (MFC-Datenzugriff) erstellt | Microsoft Docs
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
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 239ace3f23987bc4f704515e7f87d62ba2e26543
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Vom Anwendungs-Assistenten erstellter Datensatzansichts-Code (MFC-Datenzugriff)
Die [MFC-Anwendung-Assistent](../mfc/reference/database-support-mfc-application-wizard.md) überschreibt der Ansicht `OnInitialUpdate` und `OnGetRecordset` Memberfunktionen. Nachdem das Framework das Rahmenfenster, Dokument und die Ansicht erstellt hat, wird `OnInitialUpdate` aufgerufen, um die Ansicht zu initialisieren. `OnInitialUpdate` erhält einen Zeiger auf das Recordset aus dem Dokument. Ein Aufruf der Basisklasse [CView:: OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) Funktion wird das Recordset geöffnet. Der folgende Code veranschaulicht diesen Prozess für eine `CRecordView`:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 Beim Öffnen des Recordsets werden Datensätze ausgewählt. [CRecordset:: Open](../mfc/reference/crecordset-class.md#open) macht den ersten Datensatz, den aktuellen Datensatz, und DDX verschiebt Daten aus der Recordset-Felddatenmember in die entsprechenden Formularsteuerelemente in der Ansicht. Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch (RFX)](../data/odbc/record-field-exchange-rfx.md). Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md). Informationen zu der Dokument-/Ansichtarchitektur Erstellungsvorgang, finden Sie unter [mithilfe der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
> [!NOTE]
>  Sie sollten den Endbenutzern die Möglichkeit geben, die Steuerelemente der Datensatzansicht vom Recordset zu aktualisieren. Ohne diese Funktion kann der Benutzer den aktuellen Datensatz möglicherweise nicht verlassen, wenn er als Wert für ein Steuerelement einen unzulässigen Wert eingibt. Um die Steuerelemente zu aktualisieren, rufen Sie die `CWnd` Memberfunktion [UpdateData](../mfc/reference/cwnd-class.md#updatedata) mit einem Parameter des **"false"**.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)