---
title: Verwenden von Eigenschaftenseiten in einer Anwendung
ms.date: 11/04/2016
helpviewer_keywords:
- dialog templates [MFC], property sheets
- dialog resources
- property pages [MFC], property sheets
- DoModal method property sheets
- AddPage method [MFC]
- property sheets, about property sheets
- Create method [MFC], property sheets
- CPropertyPage class [MFC], styles
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
ms.openlocfilehash: 76acbfa9625fe6cb9a575244b0ed6954eeaaf3f2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301687"
---
# <a name="using-property-sheets-in-your-application"></a>Verwenden von Eigenschaftenseiten in einer Anwendung

Um ein Eigenschaftenblatt in Ihrer Anwendung verwenden möchten, führen Sie die folgenden Schritte aus:

1. Erstellen einer Dialogfeldvorlagen-Ressource für jede Eigenschaftsseite auf. Bedenken Sie, die der Benutzer möglicherweise von einer Seite zu einem anderen Wechsel werden, damit Layout, jede Seite so konsistent wie möglich.

   Die Dialogfeldvorlagen für alle Seiten müssen nicht die gleiche Größe aufweisen. Das Framework wird die Größe der größten Seite verwendet, um zu bestimmen, wie viel Speicherplatz belegen im Eigenschaftenblatt für die Eigenschaftenseiten.

   Bei der Erstellung der Dialogfeldvorlagen-Ressource für eine Eigenschaftenseite, müssen Sie die folgenden Stile im Eigenschaftenfenster die Eigenschaften des Dialogfelds angeben:

   - Legen Sie die **Beschriftung** Eingabefeld auf der **allgemeine** Seite, um den Text auf der Registerkarte für diese Seite angezeigt werden sollen.

   - Legen Sie die **Stil** Listenfeld auf der **Stile** Seite **untergeordneten**.

   - Legen Sie die **Rahmen** Listenfeld auf der **Stile** Seite **Thin**.

   - Sicherstellen, dass die **Titlebar** auf das Kontrollkästchen der **Stile** Seite ausgewählt ist.

   - Sicherstellen, dass die **deaktiviert** auf das Kontrollkästchen der **mehr Stile** Seite ausgewählt ist.

1. Erstellen Sie eine [CPropertyPage](../mfc/reference/cpropertypage-class.md)-abgeleitete Klasse, die für jede Eigenschaft Dialogfeld Seitenvorlage. Finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md). Wählen Sie `CPropertyPage` als Basisklasse.

1. Erstellen Sie Variablen zum Speichern der Werte für diese Eigenschaftenseite Member. Der Vorgang zum Hinzufügen von Membervariablen auf einer Eigenschaftenseite liegt genau identisch mit dem Hinzufügen von Membervariablen des Typs zu einem Dialogfeld eine Eigenschaftenseite wird geöffnet, ein spezialisiertes Dialogfeld. Weitere Informationen finden Sie unter [Definieren von Membervariablen für Dialogfeld-Steuerelemente](../windows/defining-member-variables-for-dialog-controls.md).

1. Erstellen einer [CPropertySheet](../mfc/reference/cpropertysheet-class.md) Objekt in Ihrem Quellcode. Erstellen Sie in der Regel die `CPropertySheet` Objekt in den Handler für den Befehl, das Eigenschaftenblatt angezeigt. Dieses Objekt darstellt, das gesamte Eigenschaftenblatt. Wenn Sie ein modales Eigenschaftsblatt mit erstellen die [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) Funktion, die das Framework stellt drei Befehlsschaltflächen standardmäßig: OK, Abbrechen, und wenden. Nicht modulare Eigenschaftenblätter mit erstellt, erstellt das Framework keine Befehlsschaltflächen der [erstellen](../mfc/reference/cpropertysheet-class.md#create) Funktion. Sie müssen nicht Ableiten einer Klasse von `CPropertySheet` , wenn Sie weitere Steuerelemente (z. B. ein Vorschaufenster) hinzufügen, oder ein nicht modalen Eigenschaftenblatts anzeigen möchten. Dieser Schritt ist erforderlich für nicht modulare Eigenschaftenblätter, da sie keine Standardsteuerelemente enthalten, die verwendet werden kann, um das Eigenschaftenblatt zu schließen.

1. Führen Sie für jede Seite das Eigenschaftenblatt hinzugefügt werden folgende Schritte aus:

   - Erstellen Sie ein Objekt, für die einzelnen `CPropertyPage`-abgeleitete Klasse, die Sie zuvor erstellt haben.

   - Rufen Sie [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage) für jede Seite.

   In der Regel das Objekt, erstellt die `CPropertySheet` erstellt außerdem die `CPropertyPage` Objekte in diesem Schritt. Allerdings bei der Implementierung einer `CPropertySheet`-abgeleitete Klasse sein, können Sie einbetten der `CPropertyPage` Objekte in der `CPropertySheet` Objekt, und rufen `AddPage` für jede Seite aus der `CPropertySheet`-abgeleiteten Klassenkonstruktor. `AddPage` Fügt der `CPropertyPage` Objekt auf dem Eigenschaftenblatt der Liste der Seiten, jedoch das Fenster für diese Seite nicht tatsächlich erstellt. Aus diesem Grund ist es nicht erforderlich, warten, bis die Erstellung des Fensters für das Eigenschaft aufrufen `AddPage`; Sie können Aufrufen `AddPage` aus dem Eigenschaftenblatt-Konstruktor.

   Wenn ein Eigenschaftenblatt mehrere Registerkarten, die enthält als in einer einzelnen Zeile des Eigenschaftenblatts, passen, werden standardmäßig die Registerkarten in mehreren Zeilen Stapeln. Rufen Sie zum Deaktivieren von Stapeln [CPropertySheet::EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) mit den Parameter auf **"false"**. Rufen Sie `EnableStackedTabs` Wenn Sie das Eigenschaftenblatt erstellen.

1. Rufen Sie [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../mfc/reference/cpropertysheet-class.md#create) um das Eigenschaftenfenster anzuzeigen. Rufen Sie `DoModal` zum Erstellen eines Eigenschaftenblatts als modales Dialogfeld. Rufen Sie **erstellen** Eigenschaftenblatt als ein nicht modales Dialogfeld zu erstellen.

1. Austauschen von Daten zwischen Eigenschaftenseiten und der Besitzer des Eigenschaftenblatts an. Dies wird in diesem Artikel erläutert [Austauschen von Daten](../mfc/exchanging-data.md).

Ein Beispiel zur Verwendung von Eigenschaftenseiten finden Sie im allgemeinen MFC-Beispiel [PROPDLG](../visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)
