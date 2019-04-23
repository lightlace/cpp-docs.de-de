---
title: Vom Anwendungs-Assistenten erstellter Datensatzansichts-Code (MFC-Datenzugriff)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: e25ca9cad1390dd11ab7328ffefed31badf6fc0b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036074"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Vom Anwendungs-Assistenten erstellter Datensatzansichts-Code (MFC-Datenzugriff)

Die [MFS-Anwendungsassistenten](../mfc/reference/database-support-mfc-application-wizard.md) überschreibt der Ansicht `OnInitialUpdate` und `OnGetRecordset` Memberfunktionen. Nachdem das Framework das Rahmenfenster, Dokument und die Ansicht erstellt hat, wird `OnInitialUpdate` aufgerufen, um die Ansicht zu initialisieren. `OnInitialUpdate` erhält einen Zeiger auf das Recordset aus dem Dokument. Ein Aufruf der Basisklasse [CView:: OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) Funktion wird das Recordset geöffnet. Der folgende Code zeigt diesen Vorgang für eine `CRecordView`:

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

Beim Öffnen des Recordsets werden Datensätze ausgewählt. [CRecordset:: Open](../mfc/reference/crecordset-class.md#open) wird der erste Datensatz, den aktuellen Datensatz; DDX verschiebt Daten aus dem Recordset Felddatenmember in die entsprechenden Formularsteuerelemente in der Ansicht. Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch (RFX)](../data/odbc/record-field-exchange-rfx.md). Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../mfc/dialog-data-exchange-and-validation.md). Weitere Informationen zu der Erstellungsvorgang für Dokumente und Ansichten, finden Sie unter [verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

> [!NOTE]
>  Sie sollten den Endbenutzern die Möglichkeit geben, die Steuerelemente der Datensatzansicht vom Recordset zu aktualisieren. Ohne diese Funktion kann der Benutzer den aktuellen Datensatz möglicherweise nicht verlassen, wenn er als Wert für ein Steuerelement einen unzulässigen Wert eingibt. Um die Steuerelemente zu aktualisieren, rufen Sie die `CWnd` Memberfunktion [UpdateData](../mfc/reference/cwnd-class.md#updatedata) mit dem Parameter "false".

## <a name="see-also"></a>Siehe auch

[Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)