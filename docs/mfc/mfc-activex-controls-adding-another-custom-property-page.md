---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a0e8713bc228e65cb06e58d7ccb5389f7366e76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350780"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC-ActiveX-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite
In einigen Fällen müssen ein ActiveX-Steuerelement mehr Eigenschaften als angemessen auf eine Seite passen. In diesem Fall können Sie die Eigenschaftenseiten für das ActiveX-Steuerelement zum Anzeigen dieser Eigenschaften hinzufügen.  
  
 In diesem Artikel wird erläutert, ein ActiveX-Steuerelement, die bereits mindestens eine Eigenschaftenseite neue Eigenschaftenseiten hinzugefügt. Weitere Informationen zum Hinzufügen von Systemeigenschaft Seiten (Schriftart, Bild oder Farbe), finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md).  
  
 Ein Beispiel ActiveX-Steuerelement-Framework, das von der ActiveX-Steuerelement-Assistent erstellt mithilfe der folgenden Verfahren. Aus diesem Grund sind die Klassennamen und IDs für dieses Beispiel eindeutig.  
  
 Weitere Informationen zum Verwenden von Eigenschaftenseiten in einem ActiveX-Steuerelement finden Sie unter den folgenden Artikeln:  
  
-   [MFC-ActiveX-Steuerelemente: Eigenschaftenseite](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  Es wird stark diese neue Eigenschaft empfohlen, die Seiten auf die Größe für Eigenschaftenseiten von ActiveX-Steuerelement standard zu entsprechen. Der Systemeigenschaft Bild und Farbe-Measure 250 x 62 Dialogeinheiten (DLU) Seiten. Auf der Seite der Standardschriftart ist 250 x 110 DLUs. Die Eigenschaft-Standardseite, die von der ActiveX-Steuerelement-Assistent erstellt verwendet die 250 x 62 DLUs.  
  
### <a name="to-insert-a-new-property-page-template-into-your-project"></a>So fügen Sie Ihrem Projekt eine neue Seite eigenschaftsvorlage  
  
1.  Öffnen Sie mit dem Steuerelementprojekt öffnen Ressourcenansicht im Arbeitsbereich "Projekt" aus.  
  
2.  Mit der rechten Maustaste in der Ressourcenansicht, öffnen Sie das Kontextmenü, und klicken Sie auf **Ressource hinzufügen**.  
  
3.  Erweitern Sie die **Dialogfeld** Knoten, und wählen **IDD_OLE_PROPPAGE_SMALL aus**.  
  
4.  Klicken Sie auf `New` die Ressource zu Ihrem Projekt hinzugefügt.  
  
5.  Wählen Sie die neue Eigenschaft Seitenvorlage, um das Eigenschaftenfenster zu aktualisieren.  
  
6.  Geben Sie einen neuen Wert für die **ID** Eigenschaft. Dieses Beispiel verwendet **IDD_PROPPAGE_NEWPAGE**.  
  
7.  Klicken Sie auf **speichern** auf der Symbolleiste.  
  
### <a name="to-associate-the-new-template-with-a-class"></a>Die neue Vorlage mit einer Klasse zuordnen  
  
1.  Klassenansicht zu öffnen.  
  
2.  Mit der rechten Maustaste in der Klassenansicht, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.  
  
     Daraufhin wird die [Klasse hinzufügen](../ide/add-class-dialog-box.md) (Dialogfeld).  
  
4.  Doppelklicken Sie auf die **MFC-Klasse** Vorlage.  
  
5.  In der **Klassenname** Feld der [MFC-Klassen-Assistent](../mfc/reference/mfc-add-class-wizard.md), geben Sie einen Namen für das neue Dialogfeldklasse. (In diesem Beispiel `CAddtlPropPage`.)  
  
6.  Wenn Sie den Dateinamen ändern möchten, klicken Sie auf **ändern**. Geben Sie den Namen für die Implementierung und Header-Dateien, oder übernehmen Sie den Standardnamen.  
  
7.  In der **Basisklasse** wählen Sie im `COlePropertyPage`.  
  
8.  In der **Dialogfeld ID** wählen Sie im **IDD_PROPPAGE_NEWPAGE**.  
  
9. Klicken Sie auf **Fertig stellen** zum Erstellen der Klasse.  
  
 Damit Benutzer das Steuerelement den Zugriff auf dieses neue Eigenschaftsseite können, müssen Sie die folgenden Änderungen auf das Steuerelement Eigenschaft-IDs-Makro Seitenabschnitt (befindet sich in der Implementierungsdatei des Steuerelements) aus:  
  
 [!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]  
  
 Beachten Sie, dass den zweiten Parameter der zu erhöhen, müssen die `BEGIN_PROPPAGEIDS` Makro (die Eigenschaft Seitenanzahl) von 1 auf 2.  
  
 Sie müssen auch die Implementierungsdatei des Steuerelements ändern (. CPP)-Datei, die den Header enthalten (. H)-Datei von der neuen Eigenschaft Page-Klasse.  
  
 Der nächste Schritt umfasst das Erstellen von zwei neue Zeichenfolgenressourcen, die einen Typnamen und eine Beschriftung für das neue Eigenschaftsseite bereitstellt.  
  
#### <a name="to-add-new-string-resources-to-a-property-page"></a>Eine Eigenschaftenseite neue Zeichenfolgenressourcen hinzu  
  
1.  Öffnen Sie mit dem Steuerelementprojekt öffnen die Ressourcenansicht.  
  
2.  Doppelklicken Sie auf die **Zeichenfolgentabelle** Ordner und doppelklicken Sie dann auf die vorhandene Zeichenfolge Tabelle Ressource, die Sie eine Zeichenfolge hinzufügen möchten.  
  
     Dadurch wird die Zeichenfolgentabelle in einem Fenster geöffnet.  
  
3.  Wählen Sie die leere Zeile am Ende der Zeichenfolgentabelle, und geben Sie den Text oder die Beschriftung der Zeichenfolge: z. B. "Zusätzliche Eigenschaftenseite."  
  
     Daraufhin wird eine **Zeichenfolgeneigenschaften** Seite mit **Beschriftung** und **ID** Felder. Die **Beschriftung** Feld enthält die Zeichenfolge, die Sie eingegeben haben.  
  
4.  In der **ID** Feld, wählen Sie aus, oder geben Sie eine ID für die Zeichenfolge. Drücken Sie die EINGABETASTE, wenn Sie fertig sind.  
  
     Dieses Beispiel verwendet **IDS_SAMPLE_ADDPAGE als** für den Typnamen für die neue Eigenschaftenseite.  
  
5.  Wiederholen Sie die Schritte 3 und 4 mit **IDS_SAMPLE_ADDPPG_CAPTION** für die ID und die "Zusätzliche Eigenschaftenseite" für die Beschriftung.  
  
6.  In der. CPP-Datei mit der neuen Eigenschaft Page-Klasse (in diesem Beispiel `CAddtlPropPage`) ändern Sie die `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` , damit IDS_SAMPLE_ADDPAGE als übergeben wird, indem Sie [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass), wie im folgenden Beispiel:  
  
     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]  
  
7.  Ändern Sie den Konstruktor des `CAddtlPropPage` , damit **IDS_SAMPLE_ADDPPG_CAPTION** wird zum Übergeben der `COlePropertyPage` -Konstruktor wie folgt:  
  
     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]  
  
 Nachdem Sie die erforderlichen Änderungen vor, erstellen Sie das Projekt neu, und verwenden Sie den Testcontainer So testen Sie die neue Eigenschaftsseite vorgenommen haben. Informationen zum Zugriff auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) .  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

