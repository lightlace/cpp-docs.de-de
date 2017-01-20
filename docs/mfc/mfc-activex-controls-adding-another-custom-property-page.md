---
title: "MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen einer weiteren benutzerdefinierten Eigenschaftenseite"
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
  - "ActiveX-Steuerelemente [C++], Eigenschaftenseiten"
  - "Benutzerdefinierte Eigenschaftenseiten"
  - "MFC ActiveX-Steuerelemente [C++], Eigenschaftenseiten"
  - "Eigenschaftenseiten [C++], MFC-ActiveX-Steuerelemente"
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen einer weiteren benutzerdefinierten Eigenschaftenseite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gelegentlich ist ein ActiveX\-Steuerelement mehr Eigenschaften, als auf einer Eigenschaftenseite angemessen anpassen kann.  In diesem Fall können Sie Eigenschaftenseiten dem ActiveX\-Steuerelement hinzufügen, diese Eigenschaften anzuzeigen.  
  
 In diesem Artikel werden das Hinzufügen neuer Eigenschaftenseiten zu einem ActiveX\-Steuerelement, das bereits mindestens eine Eigenschaftenseite hat.  Weitere Informationen zum Hinzufügen vordefinierter Eigenschaftenseiten \(Schriftart, Bild oder die Farbe\), finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Verwenden vordefinierter Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md).  
  
 Die folgenden Verfahren ein Beispielactivex\-steuerelement\-Framework, das vom ActiveX\-Steuerelement\-Assistenten erstellt wird.  Daher sind die Klassennamen und die Bezeichner zu diesem Beispiel eindeutig.  
  
 Weitere Informationen zur Verwendung von Eigenschaftenseiten in einem ActiveX\-Steuerelement, finden Sie:  
  
-   [MFC\-ActiveX\-Steuerelemente: Eigenschaftenseiten](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Verwenden vordefinierter Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  Es wird dringend empfohlen, dass neue Eigenschaftenseiten den Größenstandard für Eigenschaftenseiten für ActiveX\-Steuerelemente befolgen.  Das vordefinierte Bild und Measures der Farbeigenschaftenseiten 250x62 Dialogfeld\-Steuerelemente Einheiten \(DLU\).  Die Standardschriftarteigenschaftenseite ist 250x110 DLUs.  Die Standardeigenschaftsseite, die vom ActiveX\-Steuerelement\-Assistenten erstellt wird, verwendet den standardmäßigen 250x62 DLU.  
  
### So fügen Sie eine neue Eigenschaftenseitenvorlage in Ihr Projekt einfügen  
  
1.  Öffnen Sie das Steuerelementprojekt geöffnet, offene Ressourcenansicht in den Projektarbeitsbereich.  
  
2.  Klicken Sie mit der rechten Maustaste in der Ressourcenansicht, um das Kontextmenü zu öffnen und auf **Ressource hinzufügen** zu klicken.  
  
3.  Erweitern Sie den Knoten **Dialogfeld**, und wählen Sie **IDD\_OLE\_PROPPAGE\_SMALL** aus.  
  
4.  Klicken Sie auf `New`, um die Ressource dem Projekt hinzuzufügen.  
  
5.  Wählen Sie die neue Eigenschaftenseitenvorlage aus, um das Eigenschaftenfenster zu aktualisieren.  
  
6.  Geben Sie einen neuen Wert für die **ID**\-Eigenschaft ein.  In diesem Beispiel verwendet **IDD\_PROPPAGE\_NEWPAGE**.  
  
7.  Klicken Sie in der Symbolleiste auf **Speichern**.  
  
### Um die neue Vorlage mit einer Klasse zuordnen  
  
1.  Öffnen Sie die Klassenansicht.  
  
2.  Klicken Sie mit der rechten Maustaste in der Klassenansicht, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü zunächst auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
     Dadurch wird das Dialogfeld [Klasse hinzufügen](../ide/add-class-dialog-box.md).  
  
4.  Doppelklicken Sie auf die **MFC\-Klasse** Vorlage.  
  
5.  Im Feld **Klassenname** in [MFC\-Klassen\-Assistent](../mfc/reference/mfc-add-class-wizard.md), geben Sie einen Namen für die neue Dialogfeldklasse ein. \(In diesem Beispiel, `CAddtlPropPage`\).  
  
6.  Wenn Sie Dateinamen ändern möchten, klicken Sie auf **Ändern**.  Geben Sie die Namen für die Implementierung und Headerdateien ein, oder übernehmen Sie den Standardnamen.  
  
7.  Im Feld **Basisklasse**  die Option `COlePropertyPage`.  
  
8.  Im Feld **Dialogfeld\-ID**  die Option **IDD\_PROPPAGE\_NEWPAGE** aus.  
  
9. Klicken Sie auf **Fertig stellen** , um die Klasse zu erstellen.  
  
 Um dem Benutzerzugriff des Steuerelements in dieser neuen Eigenschaftenseite zuzulassen, nehmen Sie die folgenden Änderungen am ID\-Makroabschnitt die Eigenschaftenseite des Steuerelements vor \(in der Steuerimplementierungsdatei\):  
  
 [!CODE [NVC_MFC_AxUI#32](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#32)]  
  
 Beachten Sie, dass Sie den zweiten Parameter des `BEGIN_PROPPAGEIDS`\-Makros \(mit Eigenschaftenseitenanzahl\) von 1 bis 2. erweitern müssen.  
  
 Sie müssen die Datei der Steuerimplementierungsdatei auch ändern \(.CPP\), um die Header einzuschließen \(.H\) Datei der neuen Eigenschaftenseitenklasse.  
  
 Der nächste Schritt, scrollen zwei Zeichenfolgenressourcen neue erstellen, die einen Typnamen und eine Beschriftung für die neue Seite bereitstellen.  
  
#### So neuen Zeichenfolgenressourcen einer Eigenschaftenseite hinzufügen  
  
1.  Öffnen Sie das Steuerelementprojekt geöffnet, offene Ressourcenansicht.  
  
2.  Doppelklicken Sie auf den Ordner **Zeichenfolgentabelle** und doppelklicken Sie dann auf die vorhandene Zeichenfolgentabellenressource, der eine Zeichenfolge hinzufügen möchten.  
  
     Dadurch wird die Zeichenfolgentabelle in einem Fenster.  
  
3.  Wählen Sie die leere Zeile am Ende der Zeichenfolgentabelle aus und geben Sie den Text oder Beschriftung, die Zeichenfolge ein: beispielsweise "zusätzliche Eigenschaftenseite."  
  
     In **String Properties** öffnet eine Seite, die **Beschriftung** und **ID** Felder angezeigt werden.  Das Feld **Beschriftung** enthält die Zeichenfolge, die Sie eingegeben haben.  
  
4.  Im Feld **ID** aktivieren oder geben Sie eine ID für die Zeichenfolge ein.  Drücken Sie EINGABETASTE wenn Sie beenden.  
  
     In diesem Beispiel verwendet **IDS\_SAMPLE\_ADDPAGE** für den Typnamen der neuen Eigenschaftenseite.  
  
5.  Wiederholen Sie Schritte 3 und 4 mit **IDS\_SAMPLE\_ADDPPG\_CAPTION** für die ID "und die zusätzliche Eigenschaftenseite" für den Titel.  
  
6.  in der CPP\-Datei der neuen Eigenschaftenseitenklasse \(in diesem Beispiel `CAddtlPropPage`\), ändern Sie `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry`, damit IDS\_SAMPLE\_ADDPAGE von [AfxOleRegisterPropertyPageClass](../Topic/AfxOleRegisterPropertyPageClass.md) übergeben wird, wie im folgenden Beispiel:  
  
     [!CODE [NVC_MFC_AxUI#33](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#33)]  
  
7.  Ändern Sie den Konstruktor von `CAddtlPropPage`, sodass **IDS\_SAMPLE\_ADDPPG\_CAPTION** an `COlePropertyPage`\-Konstruktor übergeben wird, wie folgt:  
  
     [!CODE [NVC_MFC_AxUI#34](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#34)]  
  
 Nachdem Sie festgelegt haben, ergeben die notwendigen Änderungen das Projekt neu und verwenden Testcontainer, um die neue Eigenschaftenseite zu testen.  Informationen zum Zugreifen auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md).  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)