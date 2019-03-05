---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen einer anderen benutzerdefinierten Eigenschaftenseite'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 87b71fdddc5b52f66c34cdbcdb234c83616d0850
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289546"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC-ActiveX-Steuerelemente: Hinzufügen einer anderen benutzerdefinierten Eigenschaftenseite

In einigen Fällen hat ein ActiveX-Steuerelement mehr Eigenschaften als angemessen auf einer Eigenschaftenseite eingepasst werden kann. In diesem Fall können Sie die Eigenschaftenseiten an das ActiveX-Steuerelement zum Anzeigen dieser Eigenschaften hinzufügen.

Dieser Artikel beschreibt ein ActiveX-Steuerelement, das bereits mindestens eine Eigenschaftenseite verfügt über neue Eigenschaftenseiten hinzugefügt. Weitere Informationen zum Hinzufügen der Systemeigenschaft Seiten (Schriftart, Bild oder Farbe), finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md).

Die folgenden Verfahren verwenden Sie ein Beispiel ActiveX-Steuerelement-Framework, das von der ActiveX-Steuerelement-Assistent erstellt. Aus diesem Grund sind die Namen und Bezeichner für dieses Beispiel eindeutig.

Weitere Informationen zur Verwendung von Eigenschaftenseiten in einem ActiveX-Steuerelement finden Sie unter den folgenden Artikeln:

- [MFC-ActiveX-Steuerelemente: Eigenschaftenseiten](../mfc/mfc-activex-controls-property-pages.md)

- [MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  Es wird diese neue Eigenschaft, die Seiten der Größe standard für Eigenschaftenseiten von ActiveX-Steuerelements entsprechen, dringend empfohlen. Bild und die Farbe Basiseigenschaft für die Seiten Measure 250 x 62 Dialogeinheiten (DLU). Die Eigenschaftenseite für die Standardschriftart ist 250 x 110 DLUs. Die Standard-Eigenschaftenseite, die von der ActiveX-Steuerelement-Assistent erstellt, verwendet der 250 x 62 DLUs.

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>Um eine neue Vorlage für Eigenschaftenseiten in das Projekt einfügen.

1. Öffnen Sie mit dem Steuerelementprojekt öffnen Ressourcenansicht im Arbeitsbereich "Projekt" aus.

1. Mit der rechten Maustaste in der Ressourcenansicht öffnen das Kontextmenü, und klicken Sie auf **Ressource hinzufügen**.

1. Erweitern Sie die **Dialogfeld** Knoten, und wählen **IDD_OLE_PROPPAGE_SMALL aus**.

1. Klicken Sie auf **neu** die Ressource zu Ihrem Projekt hinzugefügt.

1. Wählen Sie die neue Eigenschaftenseitenvorlage, um das Fenster "Eigenschaften" zu aktualisieren.

1. Geben Sie einen neuen Wert für die **ID** Eigenschaft. Dieses Beispiel verwendet **IDD_PROPPAGE_NEWPAGE**.

1. Klicken Sie auf **speichern** auf der Symbolleiste.

### <a name="to-associate-the-new-template-with-a-class"></a>Um die neue Vorlage mit einer Klasse zuzuordnen.

1. Öffnen Sie die Klassenansicht.

1. Mit der rechten Maustaste in der Klassenansicht, um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.

   Daraufhin wird die [Klasse hinzufügen](../ide/add-class-dialog-box.md) Dialogfeld.

1. Doppelklicken Sie auf die **MFC-Klasse** Vorlage.

1. In der **Klassenname** im Feld der [MFC-Klassenassistent](../mfc/reference/mfc-add-class-wizard.md), geben Sie einen Namen für das neue Dialogfeldklasse. (In diesem Beispiel `CAddtlPropPage`.)

1. Wenn Sie den Dateinamen ändern möchten, klicken Sie auf **ändern**. Geben Sie die Namen für Ihre Implementierung und Header-Dateien, oder übernehmen Sie die Standardnamen.

1. In der **Basisklasse** Kontrollkästchen `COlePropertyPage`.

1. In der **Dialogfeld-ID** Kontrollkästchen **IDD_PROPPAGE_NEWPAGE**.

9. Klicken Sie auf **Fertig stellen** zum Erstellen der Klasse.

Damit des Steuerelements Benutzer Zugriff auf diese neue Eigenschaftenseite, nehmen Sie die folgenden Änderungen an des Steuerelements Eigenschaft-IDs-Makro Seitenabschnitt (befindet sich in der Implementierungsdatei des Steuerelements) ein:

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

Beachten Sie, dass Sie den zweiten Parameter des der BEGIN_PROPPAGEIDS-Makro (die Eigenschaft Seitenanzahl) von 1 auf 2 erhöhen müssen.

Sie müssen auch die Implementierungsdatei des Steuerelements ändern (. CPP)-Datei auf den Header (. H)-Datei von der neuen Eigenschaft Page-Klasse.

Der nächste Schritt umfasst das Erstellen von zwei neuen Zeichenfolgenressourcen, die einen Namen und eine Beschriftung für die neue Eigenschaftenseite bereitstellt.

#### <a name="to-add-new-string-resources-to-a-property-page"></a>Eine Eigenschaftenseite neue Zeichenfolgenressourcen hinzu

1. Öffnen Sie mit dem Steuerelementprojekt öffnen Ressourcenansicht nutzen zu können.

1. Doppelklicken Sie auf die **Zeichenfolgentabelle** Ordner und doppelklicken Sie dann auf die vorhandene Zeichenfolge Ressource, die Sie eine Zeichenfolge hinzufügen möchten.

   Dadurch wird die Tabelle in einem Fenster geöffnet.

1. Wählen Sie die leere Zeile am Ende der Tabelle, und geben Sie den Text oder Beschriftung, der die Zeichenfolge: z. B. "Zusätzliche Eigenschaftenseite."

   Daraufhin wird eine **Zeichenfolgeneigenschaften** Seite zeigt **Beschriftung** und **ID** Felder. Die **Beschriftung** Feld enthält die Zeichenfolge, die Sie eingegeben haben.

1. In der **ID** Feld, wählen Sie aus, oder geben Sie eine ID für die Zeichenfolge. Drücken Sie die EINGABETASTE, wenn Sie fertig sind.

   Dieses Beispiel verwendet **IDS_SAMPLE_ADDPAGE als** für den Typ der neuen Seite.

1. Wiederholen Sie die Schritte 3 und 4 mit **IDS_SAMPLE_ADDPPG_CAPTION** für die ID und die "Zusätzliche Eigenschaftenseite" für die Beschriftung.

1. In der. CPP-Datei von der neuen Eigenschaft Page-Klasse (in diesem Beispiel `CAddtlPropPage`) ändern Sie die `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` , damit IDS_SAMPLE_ADDPAGE als übergeben wird, indem [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass), wie im folgenden Beispiel:

   [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. Ändern Sie den Konstruktor der `CAddtlPropPage` , damit IDS_SAMPLE_ADDPPG_CAPTION übergeben wird, um die `COlePropertyPage` Konstruktor wie folgt:

   [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

Nachdem Sie die notwendigen Änderungen an Ihrer Projekt neu, und verwenden zum Testen der neuen Eigenschaftenseite Testcontainer vorgenommen haben. Informationen zum Zugriff auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)
