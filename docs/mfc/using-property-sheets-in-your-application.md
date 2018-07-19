---
title: Verwenden von Eigenschaftenseiten in Ihrer Anwendung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74e63faf5b1cac5e0cb841a28fd59ecee47c9970
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383892"
---
# <a name="using-property-sheets-in-your-application"></a>Verwenden von Eigenschaftenseiten in einer Anwendung
Um ein Eigenschaftenblatt in Ihrer Anwendung verwenden zu können, müssen führen Sie die folgenden Schritte aus:  
  
1.  Erstellen Sie für jede Eigenschaftsseite auf eine Dialogfeldvorlagen-Ressource. Bedenken Sie, die der Benutzer von einer Seite zu, wechseln kann damit Layout einzelnen Seite so konsistent wie möglich.  
  
     Der Dialogfeldvorlagen für alle Seiten müssen nicht die gleiche Größe aufweisen. Das Framework verwendet die Größe der größten Seite, um zu bestimmen, wie viel Speicherplatz im Eigenschaftenblatt für die Eigenschaftenseiten zu reservieren.  
  
     Bei der Erstellung der Dialogfeldvorlagen-Ressource für eine Eigenschaftenseite müssen Sie die folgenden Stile im Eigenschaftenblatt Dialogfeldeigenschaften angeben:  
  
    -   Festlegen der **Beschriftung** Eingabefeld für die **allgemeine** Seite auf den Text auf der Registerkarte für diese Seite angezeigt werden sollen.  
  
    -   Festlegen der **Stil** im Listenfeld auf der **Stile** Seite **untergeordneten**.  
  
    -   Legen Sie die **Rahmen** Listenfeld auf der **Stile** Seite **dünn**.  
  
    -   Sicherstellen, dass die **"TitleBar"** Kontrollkästchen auf der **Stile** Seite ausgewählt ist.  
  
    -   Sicherstellen, dass die **deaktiviert** Kontrollkästchen auf der **Weitere Formate** Seite ausgewählt ist.  
  
2.  Erstellen einer [CPropertyPage](../mfc/reference/cpropertypage-class.md)-abgeleitete Klasse, die für jede Eigenschaft Seite Dialogfeldvorlage. Finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md). Wählen Sie `CPropertyPage` als Basisklasse.  
  
3.  Erstellen Sie Membervariablen zum Speichern der Werte für diese Eigenschaftenseite. Die Vorgehensweise zum Hinzufügen von Membervariablen auf einer Eigenschaftenseite ist identisch mit dem Hinzufügen von Membervariablen in einem Dialogfeld genau, da eine Eigenschaftenseite ein spezialisiertes Dialogfeld ist. Weitere Informationen finden Sie unter [Definieren von Membervariablen für Dialogfeld-Steuerelemente](../windows/defining-member-variables-for-dialog-controls.md).  
  
4.  Erstellen einer [CPropertySheet](../mfc/reference/cpropertysheet-class.md) Objekt im Quellcode. Erstellen Sie in der Regel die `CPropertySheet` Objekt im Handler für den Befehl, das Eigenschaftenblatt angezeigt. Dieses Objekt stellt die gesamte Eigenschaftenblatt dar. Wenn Sie ein modales Eigenschaftenblatt mit Erstellen der [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) -Funktion, das Framework stellt drei Befehlsschaltflächen standardmäßig: OK, "Abbrechen", und übernehmen. Nicht modulare Eigenschaftenblätter mit erstellt, erstellt das Framework keine Befehlsschaltflächen der [erstellen](../mfc/reference/cpropertysheet-class.md#create) Funktion. Sie müssen nicht Ableiten einer Klasse von `CPropertySheet` , wenn Sie andere Steuerelemente (z. B. in einem Vorschaufenster) hinzufügen, oder ein nicht modalen Eigenschaftenblatts anzeigen möchten. Dieser Schritt ist erforderlich für nicht modulare Eigenschaftenblätter, da sie keine Standardsteuerelemente enthalten, die verwendet werden können, um die Eigenschaftenseite zu schließen.  
  
5.  Führen Sie für jede Seite der Eigenschaftenseite hinzugefügt werden folgende Schritte aus:  
  
    -   Erstellen Sie ein Objekt für jeden `CPropertyPage`-abgeleitete Klasse, die Sie zuvor erstellt haben.  
  
    -   Rufen Sie [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage) für jede Seite.  
  
     In der Regel auf das Objekt, erstellt der `CPropertySheet` erstellt außerdem die `CPropertyPage` Objekte in diesem Schritt. Allerdings bei Implementierung eine `CPropertySheet`-abgeleitete Klasse, können Sie einbetten der `CPropertyPage` Objekte in der `CPropertySheet` Objekt, und rufen `AddPage` für jede Seite aus der `CPropertySheet`-abgeleiteten Klassenkonstruktor. `AddPage` Fügt der `CPropertyPage` Objekt auf dem Eigenschaftenblatt Liste von Seiten, jedoch das Fenster für diese Seite nicht tatsächlich erstellt. Aus diesem Grund ist es nicht notwendig, warten, bis die Erstellung des Eigenschaftenfensters Blatt aufrufen `AddPage`; Sie können Aufrufen `AddPage` aus dem Eigenschaftenblatt-Konstruktor.  
  
     Verfügt ein Eigenschaftenblatt weitere Registerkarten als in eine einzelne Zeile mit dem Eigenschaftenblatt passt, werden standardmäßig die Registerkarten in mehreren Zeilen Stapeln. Rufen Sie zum Deaktivieren von Stapeln [CPropertySheet::EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) mit den Parametersatz hinzu **"false"**. Rufen Sie `EnableStackedTabs` beim Erstellen der Eigenschaftenseite.  
  
6.  Rufen Sie [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../mfc/reference/cpropertysheet-class.md#create) um das Eigenschaftenfenster anzuzeigen. Rufen Sie `DoModal` ein Eigenschaftenblatt als modales Dialogfeld erstellen. Rufen Sie **erstellen** Eigenschaftenblatt als ein nicht modales Dialogfeld erstellen.  
  
7.  Austauschen von Daten zwischen Eigenschaftenseiten und der Besitzer der Eigenschaftenseite. Dies wird im Artikel erläutert [Austauschen von Daten](../mfc/exchanging-data.md).  
  
 Ein Beispiel zum Verwenden von Eigenschaftenblättern finden Sie im allgemeinen MFC-Beispiel [PROPDLG](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

