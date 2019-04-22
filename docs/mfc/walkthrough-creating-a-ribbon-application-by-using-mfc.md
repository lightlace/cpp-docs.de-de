---
title: 'Exemplarische Vorgehensweise: Erstellen einer Menübandanwendung mithilfe von MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
ms.openlocfilehash: 29991a389a09e1fe3dc0074b80fd9a255458f673
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781223"
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>Exemplarische Vorgehensweise: Erstellen einer Menübandanwendung mithilfe von MFC

In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie mit der **MFS-Anwendungsassistenten** zum Erstellen einer Anwendung, die ein Menüband in der Standardeinstellung verfügt. Sie können dann im Menüband erweitern, durch das Hinzufügen einer **benutzerdefinierte** Menübandkategorie ein **Favoriten** Bereich, und das anschließende Hinzufügen einige häufig verwendete Befehle aus, um den Bereich des Menübands.

## <a name="prerequisites"></a>Vorraussetzungen

In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie Visual Studio für die Verwendung festgelegt haben **allgemeine Entwicklungseinstellungen**. Wenn Sie andere Einstellungen verwenden, können einige der Elemente der Benutzeroberfläche (UI), die in den folgenden Anweisungen referenziert werden nicht angezeigt.

### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>So erstellen Sie eine MFC-Anwendung mit einem Menüband

1. Verwenden der **MFS-Anwendungsassistenten** zum Erstellen einer MFC_Anwendung, die ein Menüband verfügt. Zum Ausführen des Assistenten die **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**.

1. In der **neues Projekt** Dialogfeld erweitern Sie die **Visual C++** Knoten unter **installierte Vorlagen**Option **MFC**, und wählen Sie dann auf  **MFC-Anwendung**. Geben Sie einen Namen für das Projekt, z. B. *MFCRibbonApp*, und klicken Sie dann auf **OK**.

1. Die folgenden Optionen festlegen, der **MFS-Anwendungsassistenten**:

    1. In der **Anwendungstyp** -Abschnitt unter **visueller Stil und Farben**Option **Office 2007 (blaues Design)**.

    1. In der **Verbunddokumente** Abschnitt, stellen Sie sicher, dass **keine** ausgewählt ist.

    1. In der **Eigenschaften für Dokumentvorlagen** im Abschnitt der **Dateierweiterung** geben eine Dateinamenerweiterung für Dokumente, die diese Anwendung erstellt werden, z. B. *Mfcrbnapp*.

    1. In der **Datenbankunterstützung** Abschnitt, stellen Sie sicher, dass **keine** ausgewählt ist.

    1. In der **Benutzeroberflächenfunktionen** Abschnitt, stellen Sie sicher, dass **Menüband verwenden** ausgewählt ist.

    1. In der Standardeinstellung die **MFS-Anwendungsassistenten** fügt Unterstützung für einige andockbare Bereiche hinzu. Da in dieser exemplarischen Vorgehensweise nur das Menüband erläutert wird, können Sie diese Optionen aus der Anwendung entfernen. In der **erweiterte Features** Abschnitt, deaktivieren Sie alle Optionen.

1. Klicken Sie auf **Fertig stellen** die MFC-Anwendung zu erstellen.

1. Um zu überprüfen, ob die Anwendung erfolgreich erstellt wurde, erstellen Sie sie und führen sie aus. Erstellen Sie die Anwendung, auf die **erstellen** im Menü klicken Sie auf **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wurde, führen Sie es, indem Sie auf **Debuggen starten** auf die **Debuggen** Menü.

    Der Assistent erstellt automatisch ein Menüband, die einer Menübandkategorie mit dem Namen **Startseite**. Dieses Menüband enthält drei menübandbereiche, die benannt werden **Zwischenablage**, **Ansicht**, und **Fenster**.

### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>So fügen Sie dem Menüband eine Kategorie und einen Bereich hinzu

1. Um die menübandressource zu öffnen, die der Assistent erstellt werden, auf die **Ansicht** , zeigen Sie auf **Other Windows** , und klicken Sie dann auf **Ressourcenansicht**. In **Ressourcenansicht**, klicken Sie auf **Menüband** und doppelklicken Sie dann auf **IDR_RIBBON**.

1. Fügen Sie zunächst eine benutzerdefinierte Kategorie hinzu des Menübands durch Doppelklicken auf **Kategorie** in die **Toolbox**.

    Eine Kategorie mit der Beschriftung **Category1** erstellt wird. Standardmäßig enthält die Kategorie einen Bereich.

    Mit der rechten Maustaste **Category1** , und klicken Sie dann auf **Eigenschaften**. In der **Eigenschaften** ändern **Beschriftung** zu *benutzerdefinierte*.

    Die **große Bilder** und **kleine Bilder** Eigenschaften angeben, die Bitmaps, die als Symbole, die für die Menübandelemente in dieser Kategorie verwendet werden. Da die Erläuterungen zum Erstellen von benutzerdefinierten Bitmaps über den Rahmen dieser exemplarischen Vorgehensweise hinausgehen, verwenden Sie einfach die vom Assistenten erstellten Bitmaps erneut. Kleine Bitmaps sind 16 Pixel x 16 Pixel. Für kleine Bilder verwenden Sie die Bitmaps, indem zugegriffen werden, die `IDB_FILESMALL` Ressourcen-ID. Große Bitmaps sind 32 Pixel x 32 Pixel. Verwenden Sie für große Bilder, Bitmaps, die von zugegriffen wird die `IDB_FILELARGE` Ressourcen-ID.

    > [!NOTE]
    > In HDPI-Anzeigen, die mehr Pixel pro Zoll enthalten, werden automatisch die HDPI-Versionen der Bilder verwendet.

1. Passen Sie danach den Bereich an. Bereiche werden zum Gruppieren von Elementen verwendet, die sich logisch aufeinander beziehen. Z. B. auf die **Startseite** dieser Anwendung auf der Registerkarte die **Ausschneiden**, **Kopie**, und **einfügen** Befehle alle befinden sich auf die  **Zwischenablage** Bereich. Um den Bereich anzupassen, Maustaste **Panel1** , und klicken Sie dann auf **Eigenschaften**. In der **Eigenschaften** ändern **Beschriftung** zu *Favoriten*.

    Sie können angeben, die **Abbildindex** für den Bereich. Diese Zahl gibt das Symbol, das angezeigt wird, wenn der Menübandbereich hinzugefügt wird die **Symbolleiste für den Schnellzugriff**. Das Symbol ist nicht im Menübandbereich selbst angezeigt.

1. Um sicherzustellen, dass die Menübandkategorie und der entsprechende Bereich erfolgreich erstellt wurden, rufen Sie eine Vorschau des Menüband-Steuerelements auf. Auf der **Ribbon-Editor-Symbolleiste**, klicken Sie auf die **Ribbon testen** Schaltfläche. Ein **benutzerdefinierte** Registerkarte und **Favoriten** Bereich im Menüband angezeigt werden soll.

### <a name="to-add-elements-to-the-ribbon-panels"></a>So fügen Sie den Menübandbereichen Elemente hinzu

1. Zum Hinzufügen von Elementen in den Bereich, den Sie im vorherigen Verfahren erstellt haben, ziehen Sie Steuerelemente aus der **Ribbon-Editor** Teil der **Toolbox** in den Bereich in der Entwurfsansicht.

1. Fügen Sie zunächst eine **Drucken** Schaltfläche. Die **Drucken** Schaltfläche weist einem Untermenü, das enthält eine **Schnelldruck** -Befehl, der mit dem Standarddrucker gedruckt. Beide Befehle sind bereits für diese Anwendung definiert. Sie sind auf dem Anwendungsmenü befindet.

    Zum Erstellen der **Drucken** Schaltfläche, ziehen Sie ein schaltflächentool in den Zugriffsbereich.

    In der **Eigenschaften** Ändern der **ID** Eigenschaft **ID_FILE_PRINT**, die bereits definiert sein sollte. Änderung **Beschriftung** zu *Drucken*. Änderung **Image Index** zu *4*.

    Zum Erstellen der **Schnelldruck** , zeigen Sie auf Spalte mit den Eigenschaftswerten neben **Menüelemente**, und klicken Sie dann auf die Auslassungspunkte (**...** ). In der **Elemente-Editor**, klicken Sie auf die unbeschriftete **hinzufügen** klicken, um ein Menüelement zu erstellen. In der **Eigenschaften** ändern **Beschriftung** zu *Schnelldruck*, **ID** zu *ID_FILE_PRINT_DIRECT*, und **Image** zu *5*. Gibt an, die Image-Eigenschaft der **Schnelldruck** Symbol in der `IDB_FILESMALL` bitmap-Ressource.

1. Um zu überprüfen, ob die Schaltflächen zum Menübandbereich hinzugefügt wurden, erstellen Sie die Anwendung, und führen Sie sie aus. Erstellen Sie die Anwendung, auf die **erstellen** im Menü klicken Sie auf **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wurde, führen Sie die Anwendung, indem Sie auf **Debuggen starten** auf die **Debuggen** Menü. Die **Drucken** Schaltfläche und das Kombinationsfeld Feld der **Favoriten** panel auf die **benutzerdefinierte** Menüband auf der Registerkarte angezeigt werden soll.

## <a name="next-steps"></a>Nächste Schritte

[Vorgehensweise: Anpassen der Symbolleiste für den Schnellzugriff](../mfc/how-to-customize-the-quick-access-toolbar.md)

[Vorgehensweise: Anpassen der Anwendungsschaltfläche](../mfc/how-to-customize-the-application-button.md)

End-to-End-Beispiele finden Sie unter [Beispiele (MFC Feature Pack)](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)<br/>
[Beispiele (MFC FeaturePack)](../overview/visual-cpp-samples.md)
