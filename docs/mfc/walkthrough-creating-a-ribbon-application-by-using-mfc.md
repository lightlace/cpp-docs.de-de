---
title: 'Exemplarische Vorgehensweise: Erstellen einer Menü Bandanwendung mithilfe von MFC'
ms.date: 09/09/2019
helpviewer_keywords:
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
ms.openlocfilehash: 41084a78287521610ba400deab32d1052c9217c1
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907392"
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>Exemplarische Vorgehensweise: Erstellen einer Menü Bandanwendung mithilfe von MFC

In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie mit dem **MFC-Anwendungs-Assistenten** eine Anwendung erstellen, die standardmäßig über ein Menüband verfügt. Sie können dann das Menüband erweitern, indem Sie eine **benutzerdefinierte** Menüband-Kategorie hinzufügen, die über einen Menü Band Bereich für **Favoriten** verfügt

## <a name="prerequisites"></a>Erforderliche Komponenten

Diese exemplarische Vorgehensweise setzt voraus, dass Sie Visual Studio für die Verwendung **allgemeiner Entwicklungseinstellungen**festgelegt haben. Wenn Sie andere Einstellungen verwenden, werden möglicherweise einige der Benutzeroberflächen Elemente, auf die in den folgenden Anweisungen verwiesen wird, nicht angezeigt.

### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>So erstellen Sie eine MFC-Anwendung mit einem Menüband

1. Verwenden Sie den **MFC-Anwendungs-Assistenten** , um eine MFC-Anwendung mit einem Menüband zu erstellen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Verwenden der neuen MFC-Shell](walkthrough-using-the-new-mfc-shell-controls.md) -Steuerelemente, um Anweisungen zum Öffnen des Assistenten für Ihre Version von Visual Studio zu finden.

1. Legen Sie im **MFC-Anwendungs-Assistenten**die folgenden Optionen fest:

    1. Wählen Sie im Abschnitt **Anwendungstyp** unter **visueller Stil und Farben**die Option **Office 2007 (blaues Design)** aus.

    1. Stellen Sie im Abschnitt **Unterstützung für Verbund Dokumente** sicher, dass **keine** ausgewählt ist.

    1. Geben Sie im Abschnitt **Eigenschaften von Dokumentvorlagen** im Feld **Dateierweiterung** eine Dateinamenerweiterung für Dokumente ein, die von dieser Anwendung erstellt werden, z. *b. mfcrbnapp*.

    1. Vergewissern Sie sich, dass im Abschnitt **Datenbankunterstützung** (nur Visual Studio 2015) die Option **keine** ausgewählt ist.

    1. Vergewissern Sie sich, dass im Bereich **Benutzeroberflächen Funktionen** die Option **Menüband verwenden** ausgewählt ist.

    1. Standardmäßig fügt der **MFC-Anwendungs-Assistent** Unterstützung für mehrere andockbare Bereiche hinzu. Da in dieser exemplarischen Vorgehensweise nur das Menüband erläutert wird, können Sie diese Optionen aus der Anwendung entfernen. Deaktivieren Sie im Abschnitt **Erweiterte Features** alle Optionen.

1. Klicken Sie zum Erstellen der MFC-Anwendung auf **Fertig** stellen.

1. Um zu überprüfen, ob die Anwendung erfolgreich erstellt wurde, erstellen Sie sie und führen sie aus. Klicken Sie im Menü **Erstellen** auf Projekt Mappe **Erstellen**, um die Anwendung zu erstellen. Wenn die Anwendung erfolgreich erstellt wird, führen Sie Sie aus, indem Sie im Menü **Debuggen** auf **Debugging starten** klicken.

    Der Assistent erstellt automatisch ein Menüband, das eine Menü Band Kategorie namens **Home**hat. Dieses Menüband enthält drei Menü Band Bereiche mit der Bezeichnung " **Zwischenablage**", " **Ansicht**" und " **Fenster**".

### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>So fügen Sie dem Menüband eine Kategorie und einen Bereich hinzu

1. Zeigen Sie im Menü **Ansicht** auf **Weitere Fenster** , und klicken Sie dann auf **Ressourcenansicht**, um die Menü Band Ressource zu öffnen, die vom Assistenten erstellt wurde. Klicken Sie in **Ressourcenansicht**auf **Multifunktionsleiste** , und doppelklicken Sie dann auf **IDR_RIBBON**.

1. Fügen Sie zunächst dem Menüband eine benutzerdefinierte Kategorie hinzu, indem Sie auf **Kategorie** in der **Toolbox**doppelklicken.

    Eine Kategorie, in der die Beschriftung **Category1** erstellt wird, wird erstellt. Standardmäßig enthält die Kategorie einen Bereich.

    Klicken Sie mit der rechten Maustaste auf **Category1** und dann auf **Eigenschaften**. Ändern Sie im Fenster **Eigenschaften** die **Beschriftung** in *Benutzer*definiert.

    In den Eigenschaften für **große Bilder** und **kleine Images** werden die Bitmaps angegeben, die als Symbole für die Menü Band Elemente in dieser Kategorie verwendet werden. Da die Erläuterungen zum Erstellen von benutzerdefinierten Bitmaps über den Rahmen dieser exemplarischen Vorgehensweise hinausgehen, verwenden Sie einfach die vom Assistenten erstellten Bitmaps erneut. Kleine Bitmaps sind 16 Pixel x 16 Pixel. Verwenden Sie bei kleinen Bildern die Bitmaps, auf die über die `IDB_FILESMALL` Ressourcen-ID zugegriffen wird. Große Bitmaps sind 32 Pixel x 32 Pixel. Verwenden Sie bei großen Bildern die Bitmaps, auf die über die `IDB_FILELARGE` Ressourcen-ID zugegriffen wird.

    > [!NOTE]
    > In HDPI-Anzeigen, die mehr Pixel pro Zoll enthalten, werden automatisch die HDPI-Versionen der Bilder verwendet.

1. Passen Sie danach den Bereich an. Bereiche werden zum Gruppieren von Elementen verwendet, die sich logisch aufeinander beziehen. Beispielsweise befinden sich die Befehle zum **Ausschneiden**, **Kopieren**und **Einfügen** auf der Registerkarte **Startseite** dieser Anwendung im **Zwischenablage** Panel. Klicken Sie mit der rechten Maustaste auf **Panel1** , und klicken Sie dann auf **Eigenschaften**. Ändern Sie im Fenster **Eigenschaften** die **Beschriftung** in *Favoriten*.

    Sie können den **Abbild Index** für den Bereich angeben. Diese Zahl gibt das Symbol an, das angezeigt wird, wenn der Menü Band Bereich der **Symbolleiste für den schnell Zugriff**hinzugefügt wird. Das Symbol wird nicht im Menüband-Panel selbst angezeigt.

1. Um sicherzustellen, dass die Menübandkategorie und der entsprechende Bereich erfolgreich erstellt wurden, rufen Sie eine Vorschau des Menüband-Steuerelements auf. Klicken Sie auf der **Symbolleiste des Menüband-Editors**auf die Schaltfläche **Test Ribbon** . Auf dem Menüband sollten eine **benutzerdefinierte** Registerkarte und ein Bereich " **Favoriten** " angezeigt werden.

### <a name="to-add-elements-to-the-ribbon-panels"></a>So fügen Sie den Menübandbereichen Elemente hinzu

1. Um dem Bereich, den Sie in der vorherigen Prozedur erstellt haben, Elemente hinzuzufügen, ziehen Sie die Steuerelemente aus dem **Menüband-Editor** der **Toolbox** in den Bereich in der Entwurfs Ansicht.

1. Fügen Sie zunächst eine **Druck** Schaltfläche hinzu. Die Schaltfläche **Drucken** verfügt über ein Untermenü, das einen **schnell Druck** Befehl enthält, der mit dem Standarddrucker ausgegeben wird. Beide Befehle sind bereits für diese Anwendung definiert. Sie befinden sich im Anwendungsmenü.

    Um die Schaltfläche **Drucken** zu erstellen, ziehen Sie ein Schaltflächen Tool in das Panel.

    Ändern Sie im Fenster **Eigenschaften** die Eigenschaft **ID** in **ID_FILE_PRINT**, die bereits definiert sein sollte. Ändern Sie die **Beschriftung** in *Drucken*. Ändern Sie den **Abbild Index** in *4*.

    Um die Schaltfläche **schnell Druck** zu erstellen, klicken Sie auf die Spalte Eigenschafts Wert neben **Menü Elemente**, und klicken Sie dann auf die Auslassungs Punkte ( **..** .). Klicken Sie im **Items-Editor**auf die Schaltfläche ohne Bezeichnung **Hinzufügen** , um ein Menü Element zu erstellen. Ändern Sie im Fenster **Eigenschaften** die **Beschriftung** in *schnell Druck*, **ID** in *ID_FILE_PRINT_DIRECT*und **Bild** in *5*. Die Image-Eigenschaft gibt das Symbol für den **schnell Druck** in der `IDB_FILESMALL` Bitmap-Ressource an.

1. Um zu überprüfen, ob die Schaltflächen zum Menübandbereich hinzugefügt wurden, erstellen Sie die Anwendung, und führen Sie sie aus. Klicken Sie im Menü **Erstellen** auf Projekt Mappe **Erstellen**, um die Anwendung zu erstellen. Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debuggen** auf **Debugging starten** klicken. Die Schaltfläche **Drucken** und das Kombinations Feld im Bereich **Favoriten** auf der Registerkarte **Benutzer** definiert auf der Multifunktionsleiste sollten angezeigt werden.

## <a name="next-steps"></a>Nächste Schritte

[Vorgehensweise: Anpassen der Symbolleiste für den Schnellzugriff](../mfc/how-to-customize-the-quick-access-toolbar.md)

[Vorgehensweise: Anpassen der Anwendungsschaltfläche](../mfc/how-to-customize-the-application-button.md)

End-to-End-Beispiele finden Sie unter [Samples (MFC Feature Pack)](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)<br/>
[Beispiele (MFC Feature Pack)](../overview/visual-cpp-samples.md)
