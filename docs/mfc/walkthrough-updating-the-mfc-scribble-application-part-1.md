---
title: 'Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1)'
ms.date: 04/25/2019
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
ms.openlocfilehash: a12c2bd2c1c1963630a1bd74b56f2c832573cc94
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450515"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1)

In dieser exemplarischen Vorgehensweise wird beschrieben, wie Sie eine vorhandene MFC-Anwendung so ändern, dass die Menüband-Benutzeroberfläche verwendet wird. Visual Studio unterstützt sowohl das Menüband von Office 2007 als auch das "Scenic Ribbon" von Windows 7. Weitere Informationen zu den Multifunktionsleisten-Benutzeroberfläche, finden Sie unter [Menübänder](/windows/desktop/uxguide/cmd-ribbons).

In dieser exemplarischen Vorgehensweise wird das klassische MFC-Beispiel Scribble 1.0 geändert, das Ihnen ermöglicht, mit der Maus Strichzeichnungen zu erstellen. In diesem Teil der exemplarischen Vorgehensweise wird gezeigt, wie das Scribble-Beispiel so geändert wird, dass es eine Menübandleiste anzeigt. [Teil 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) der menübandleiste Weitere Schaltflächen hinzugefügt.

## <a name="prerequisites"></a>Vorraussetzungen

Die [1.0 MFC Scribble-Beispiel](https://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe). Hilfe zum Konvertieren von Visual Studio 2017 oder höher, finden Sie unter [Portierungsanleitung: MFC Scribble](../porting/porting-guide-mfc-scribble.md).

##  <a name="top"></a> Abschnitte

Dieser Teil der exemplarischen Vorgehensweise enthält die folgenden Abschnitte:

- [Ersetzen der Basisklassen](#replaceclass)

- [Hinzufügen von Bitmaps zum Projekt](#addbitmap)

- [Hinzufügen einer Menübandressource zum Projekt](#addribbon)

- [Erstellen einer Instanz der Menübandleiste](#createinstance)

- [Hinzufügen einer Menübandkategorie](#addcategory)

- [Festlegen der Darstellung der Anwendung](#setlook)

##  <a name="replaceclass"></a> Ersetzen der Basisklassen

Zum Konvertieren einer Anwendung, die ein Menü unterstützt, in eine Anwendung, die ein Menüband unterstützt, müssen Sie die Anwendung, das Rahmenfenster und die Symbolleistenklassen von den aktualisierten Basisklassen ableiten. (Es wird empfohlen, dass Sie nicht, dass das ursprüngliche Scribble-Beispiel ändern. Stattdessen bereinigen Sie das Scribble-Projekt zu, kopieren Sie ihn in ein anderes Verzeichnis und ändern Sie die Kopie dann.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>So ersetzen Sie die Basisklassen in der Scribble-Anwendung

1. Stellen Sie sicher, die in der Datei "Scribble.cpp", `CScribbleApp::InitInstance` enthält einen Aufruf an [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit).

1. Fügen Sie der Datei "stdafx.h" den folgenden Code hinzu.

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. In der Datei "Scribble.h", ändern Sie die Definition für die `CScribbleApp` Klasse, sodass es von abgeleitet ist [CWinAppEx-Klasse](../mfc/reference/cwinappex-class.md).

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Scribble 1.0 wurde geschrieben, als Windows-Anwendungen eine Initialisierungsdatei (.ini) verwendeten, um die Benutzereinstellungen zu speichern. Ändern Sie Scribble so, dass die Benutzereinstellungen statt in einer Initialisierungsdatei in der Registrierung gespeichert werden. Um den Registrierungsschlüssel und die Basis festzulegen, geben Sie den folgenden Code in `CScribbleApp::InitInstance` nach der `LoadStdProfileSettings()`-Anweisung ein.

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. Der Hauptframe für eine MDI-Anwendung (Multiple Document Interface) wird nicht mehr von der `CMDIFrameWnd`-Klasse abgeleitet. Abgeleitet aus den [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md) Klasse.

    Ersetzen Sie in den Dateien "mainfrm.h" und "mainfrm.cpp" alle Verweise auf `CMDIFrameWnd` durch `CMDIFrameWndEx`.

1. Ersetzen Sie in den Dateien "childfrm.h" und "childfrm.cpp" `CMDIChildWnd` durch `CMDIChildWndEx`.

    In der "ChildFrm.h". h-Datei ersetzen `CSplitterWnd` mit `CSplitterWndEx`.

1. Ändern Sie die Symbolleisten und die Statusleisten so, dass die neuen MFC-Klassen verwendet werden.

    Führen Sie in der Datei "mainfrm.h" folgende Schritte aus:

    1. Ersetzen Sie `CToolBar` durch `CMFCToolBar`.

    1. Ersetzen Sie `CStatusBar` durch `CMFCStatusBar`.

1. Führen Sie in der Datei "mainfrm.cpp" folgende Schritte aus:

    1. Ersetzen Sie `m_wndToolBar.SetBarStyle` durch `m_wndToolBar.SetPaneStyle`

    1. Ersetzen Sie `m_wndToolBar.GetBarStyle` durch `m_wndToolBar.GetPaneStyle`

    1. Ersetzen Sie `DockControlBar(&m_wndToolBar)` durch `DockPane(&m_wndToolBar)`

1. Kommentieren Sie in der Datei "ipframe.cpp" die folgenden drei Codezeilen aus.

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.

##  <a name="addbitmap"></a> Hinzufügen von Bitmaps zum Projekt

Für die nächsten vier Schritte dieser exemplarischen Vorgehensweise sind Bitmapressourcen erforderlich. Sie können die entsprechenden Bitmaps auf verschiedene Weise abrufen:

- Verwenden der [Ressourcen-Editoren](../windows/resource-editors.md) auf Ihre eigenen Bitmaps. Oder verwenden Sie die Ressourcen-Editoren, um Bitmaps portable Network Graphics (PNG) über Images aus dem zusammenzustellen, die in Visual Studio enthalten und kann heruntergeladen werden die [Visual Studio-Bildbibliothek](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library).

    Allerdings die **Menüband** Benutzeroberfläche erfordert, dass bestimmte Bitmaps transparente Bilder unterstützen. Transparente Bitmaps verwenden 32 Bits / Pixel, in denen 24 Bits geben die Rot-, Grün- und blauen-Komponenten der Farbe, und Definieren von 8 Bits einen *alpha-Kanal* , der die Transparenz der Farbe angibt. Die aktuellen Ressourcen-Editoren können Bitmaps mit 32 Bits/Pixel anzeigen, aber nicht ändern. Verwenden Sie daher einen externen Bild-Editor anstelle der Ressourcen-Editoren, um transparente Bitmaps zu bearbeiten.

- Kopieren Sie eine entsprechende Ressourcendatei aus einer anderen Anwendung in Ihr Projekt, und importieren Sie dann Bitmaps von dieser Datei.

In dieser exemplarischen Vorgehensweise werden Ressourcendateien aus dem Beispiel in erstellt kopiert [Exemplarische Vorgehensweise: Erstellen einer Menübandanwendung mithilfe von MFC](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md).

### <a name="to-add-bitmaps-to-the-project"></a>So fügen Sie dem Projekt Bitmaps hinzu

1. Datei-Explorer verwenden, kopieren Sie die folgenden BMP-Dateien aus dem Verzeichnis "Resources" (`res`) des Beispiels Menüband des Ressourcenverzeichnisses (`res`) von das Scribble-Projekt:

   1. Kopieren Sie "main.bmp" in Ihr Scribble-Projekt.

   1. Kopieren Sie "filesmall.bmp" und "filelarge.bmp" in Ihr Scribble-Projekt.

   1. Erstellen Sie neue Kopien der Dateien "filelarge.bmp" und "filesmall.bmp", speichern Sie Sie jedoch in der Menüband-Beispiel. Benennen Sie die Kopien in "homesmall.bmp" und "homelarge.bmp" um, und verschieben Sie sie dann in das Scribble-Projekt.

   1. Erstellen einer Kopie der Datei "toolbar.bmp", speichern Sie Sie jedoch in der Menüband-Beispiel. Benennen Sie die Kopie in "panelicons.bmp" um, und verschieben Sie sie dann in das Scribble-Projekt.

1. Importieren Sie die Bitmap für eine MFC-Anwendung. In **Ressourcenansicht**, doppelklicken Sie auf die **scribble.rc** Knoten doppelklicken Sie auf die **Bitmap** Knoten, und klicken Sie dann auf **Ressource hinzufügen**. Klicken Sie auf das Dialogfeld, das angezeigt wird, auf **Import**. Navigieren Sie zu der `res` Directory, wählen Sie die Datei "Main.bmp", und klicken Sie dann auf **öffnen**.

   Die Bitmap "main.bmp" enthält ein 26x26-Bild. Ändern Sie die ID der Bitmap auf `IDB_RIBBON_MAIN`.

1. Importieren Sie die Bitmaps für das Menü "Datei", die angefügt wird, die **Anwendung** Schaltfläche.

   1. Importieren Sie die Datei "filesmall.bmp", die elf 16 x 16 (16 x 176) enthält Images. Ändern Sie die ID der Bitmap auf `IDB_RIBBON_FILESMALL`.

   > [!NOTE]
   > Da wir nur die ersten acht 16 x 16-Bilder (16 x 128) benötigen, können Sie optional die rechten Breite dieser Bitmap von 176 128 zuschneiden.

   1. Importieren Sie die "filelarge.bmp", die neun 32 x 32 (32 x 288) enthält Images. Ändern Sie die ID der Bitmap auf `IDB_RIBBON_FILELARGE`.

1. Importieren Sie die Bitmaps für die Menübandkategorien und -bereiche. Jede Registerkarte in der Menübandleiste ist eine Kategorie und besteht aus einer Textbezeichnung und einem optionalen Bild.

   1. Importieren Sie die Bitmap "homesmall.bmp", die elf 16 x 16-Bilder für Bitmaps für kleine Schaltflächen enthält. Ändern Sie die ID der Bitmap auf `IDB_RIBBON_HOMESMALL`.

   1. Importieren Sie die Bitmap "homelarge.bmp", die neun 32 x 32-Bilder für Bitmaps für große Schaltflächen enthält. Ändern Sie die ID der Bitmap auf `IDB_RIBBON_HOMELARGE`.

1. Importieren Sie Bitmaps für die Menübandbereiche, deren Größe geändert wurde. Diese Bitmaps oder Bereichssymbole werden nach einer Größenänderung verwendet, wenn das Menüband zu klein ist, um den gesamten Bereich anzuzeigen.

   1. Importieren Sie die Bitmap "panelicons.bmp", die acht 16x16-Bilder enthält. In der **Eigenschaften** Fenster die **Bitmap-Editor**, passt die Breite der Bitmap auf 64 (16 x 64). Ändern Sie die ID der Bitmap auf `IDB_PANEL_ICONS`.

   > [!NOTE]
   > Da wir nur die ersten vier 16 x 16-Bilder (16 x 64) benötigen, können Sie optional die rechten Breite dieser Bitmap von 128 auf 64 zuschneiden.

##  <a name="addribbon"></a> Hinzufügen einer Menübandressource zum Projekt

Wenn Sie eine Anwendung, die Menüs zu einer Anwendung verwendet, die ein Menüband verwendet konvertieren, müssen Sie nicht entfernen oder deaktivieren Sie die vorhandenen Menüs. Erstellen Sie einfach eine menübandressource, fügen Menübandschaltflächen hinzu und ordnen Sie die neuen Schaltflächen dann den vorhandenen Menüelementen. Obwohl die Menüs nicht mehr sichtbar sind, Nachrichten von der menübandleiste über die Menüs weitergeleitet werden, und Tastenkombinationen für Menüs weiterhin funktionieren.

Ein Menüband besteht aus den **Anwendung** Schaltfläche, die die große Schaltfläche auf der oberen linken Seite des Menübands befindet, und mindestens einer kategorienregisterkarte. Jede Kategorienregisterkarte enthält einen oder mehrere Bereiche, die als Container für Menübandschaltflächen und Steuerelemente dienen. Das folgende Verfahren zeigt, wie Sie eine menübandressource erstellen, und klicken Sie dann Anpassen der **Anwendung** Schaltfläche.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>So fügen Sie dem Projekt eine Menübandressource hinzu

1. Mit dem Scribble-Projekt, das in ausgewählten **Projektmappen-Explorer**in die **Projekt** Menü klicken Sie auf **Ressource hinzufügen**.

1. In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Menüband** , und klicken Sie dann auf **neu**.

   Visual Studio erstellt eine Menübandressource und öffnet sie in der Designansicht. Das Menübandressourcen-ID ist `IDR_RIBBON1`, die in angezeigt **Ressourcenansicht**. Das Menüband enthält eine Kategorie und einen Bereich.

1. Sie können anpassen, die **Anwendung** Schaltfläche durch Ändern der Eigenschaften. Die Meldungs-IDs, die in diesem Code verwendet werden, sind bereits im Menü für Scribble 1.0 definiert.

1. Klicken Sie in der Entwurfsansicht auf die **Anwendung** Schaltfläche, um ihre Eigenschaften anzuzeigen. Ändern Sie die Eigenschaftswerte wie folgt: **Image** zu `IDB_RIBBON_MAIN`, **Eingabeaufforderung** zu `File`, **Schlüssel** zu `f`, **große Bilder** zu `IDB_RIBBON_FILELARGE`, und **Kleine Bilder** zu `IDB_RIBBON_FILESMALL`.

1. Die folgenden Änderungen wird das Menü erstellt, die angezeigt wird, wenn der Benutzer klickt auf die **Anwendung** Schaltfläche. Klicken Sie auf die Auslassungspunkte ( **...** ) neben **Main Items** zum Öffnen der **Elemente-Editor**.

   1. Mit der **Element** Typ **Schaltfläche** ausgewählt ist, klicken Sie auf **hinzufügen** um eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `&New`, **ID** zu `ID_FILE_NEW`, **Image** zu `0`, **Bild groß** zu `0`.

   1. Klicken Sie auf **hinzufügen** um eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `&Save`, **ID** zu `ID_FILE_SAVE`, **Image** zu `2`, und **Bild groß** zu `2`.

   1. Klicken Sie auf **hinzufügen** um eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `Save &As`, **ID** zu `ID_FILE_SAVE_AS`, **Image** zu `3`, und **Bild groß** zu `3`.

   1. Klicken Sie auf **hinzufügen** um eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `&Print`, **ID** zu `ID_FILE_PRINT`, **Image** zu `4`, und **Bild groß** zu `4`.

   1. Ändern der **Element** Typ **Trennzeichen** , und klicken Sie dann auf **hinzufügen**.

   1. Ändern der **Element** Typ **Schaltfläche**. Klicken Sie auf **hinzufügen** um eine fünfte Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `&Close`, **ID** zu `ID_FILE_CLOSE`, **Image** zu `5`, und **Bild groß** zu `5`.

1. Die folgenden Änderungen erstellt ein Untermenü unter der **Drucken** Schaltfläche, die Sie im vorherigen Schritt erstellt haben.

   1. Klicken Sie auf die **Drucken** Schaltfläche, ändern Sie die **Element** Typ **Bezeichnung**, und klicken Sie dann auf **einfügen**. Änderung **Beschriftung** zu `Preview and print the document`.

   1. Klicken Sie auf die **Drucken** Schaltfläche, ändern Sie die **Element** Typ **Schaltfläche**, und klicken Sie auf **einfügen**. Änderung **Beschriftung** zu `&Print`, **ID** zu `ID_FILE_PRINT`, **Image** zu `4`, und **Bild groß** zu `4`.

   1. Klicken Sie auf die **Drucken** Schaltfläche, und klicken Sie dann auf **einfügen** um eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `&Quick Print`, **ID** zu `ID_FILE_PRINT_DIRECT`, **Image** zu `7`, und **Bild groß** zu `7`.

   1. Klicken Sie auf die **Drucken** Schaltfläche, und klicken Sie dann auf **einfügen** um eine weitere Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `Print Pre&view`, **ID** zu `ID_FILE_PRINT_PREVIEW`, **Image** zu `6`, und **Bild groß** zu `6`.

   1. Sie haben nun geändert. die **Main Items**. Klicken Sie auf **schließen** zum Beenden der **Elemente-Editor**.

1. Die folgende Änderung wird eine beendigungsschaltfläche erstellt, der angezeigt wird am unteren Rand der **Anwendung** im Menü der Schaltfläche.

   1. In der **Eigenschaften** Fenster, klicken Sie auf die Auslassungspunkte ( **...** ) neben **Schaltfläche** zum Öffnen der **Elemente-Editor**.

   1. Mit der **Element** Typ **Schaltfläche** ausgewählt ist, klicken Sie auf **hinzufügen** um eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** zu `E&xit`, **ID** zu `ID_APP_EXIT`, **Image** zu `8`.

   1. Verändert die **Schaltflächen**. Klicken Sie auf **schließen** zum Beenden der **Elemente-Editor**.

##  <a name="createinstance"></a> Erstellen einer Instanz der Menübandleiste

Die folgenden Schritte zeigen, wie beim Starten Ihrer Anwendung eine Instanz der Menübandleiste erstellt wird. Um eine Menübandleiste zu einer Anwendung hinzuzufügen, deklarieren Sie die Menübandleiste in der Datei "mainfrm.h". Schreiben Sie dann in der Datei "mainfrm.cpp" Code zum Laden der Menübandressource.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>So erstellen Sie eine Instanz der Menübandleiste

1. Fügen Sie in der Datei "mainfrm.h" einen Datenmember zum geschützten Abschnitt von `CMainFrame`, der Klassendefinition für den Hauptframe, hinzu. Dieser Member ist für die menübandleiste.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. Fügen Sie in der Datei "mainfrm.cpp" den folgenden Code vor der letzten `return`-Anweisung am Ende der `CMainFrame::OnCreate`-Funktion hinzu. Erstellt eine Instanz der menübandleiste.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

##  <a name="addcategory"></a> Anpassen der Menübandressource

Sie erstellt haben die **Anwendung** Schaltfläche können Sie Elemente zum Menüband hinzufügen.

> [!NOTE]
> In dieser exemplarischen Vorgehensweise wird das gleiche Bereichssymbol für alle Bereiche verwendet. Sie können jedoch auch andere Bildlistenindizes verwenden, um andere Symbole anzuzeigen.

### <a name="to-add-a-home-category-and-edit-panel"></a>So fügen Sie eine Kategorie "Startseite" und einen Bereich "Bearbeiten" hinzu

1. Das Scribble-Programm erfordert nur eine Kategorie. In der Entwurfsansicht in der **Toolbox**, doppelklicken Sie auf **Kategorie** hinzufügen und seine Eigenschaften anzuzeigen. Ändern Sie die Eigenschaftswerte wie folgt: **Beschriftung** zu `&Home`, **große Bilder** zu `IDB_RIBBON_HOMELARGE`, **kleine Bilder** zu `IDB_RIBBON_HOMESMALL`.

1. Jede Menübandkategorie ist in benannte Bereiche unterteilt. Jeder Bereich enthält einem Satz von Steuerelementen, dass vollständige verwandte Vorgänge. Diese Kategorie verfügt über einen Bereich. Klicken Sie auf **Bereich**, und ändern Sie dann **Beschriftung** zu `Edit`.

1. Um die **bearbeiten** panel, fügen Sie eine Schaltfläche, die verantwortlich für das Löschen des Inhalts des Dokuments. Die Nachrichten-ID für diese Schaltfläche wurde bereits definiert wurde, der `IDR_SCRIBBTYPE` Menüressource. Geben Sie `Clear All` als Text der Schaltfläche und der Index der Bitmap, die die Schaltfläche dekoriert. Öffnen der **Toolbox**, und ziehen Sie dann eine **Schaltfläche** auf die **bearbeiten** Bereich. Klicken Sie auf die Schaltfläche, und ändern Sie dann **Beschriftung** zu `Clear All`, **ID** zu `ID_EDIT_CLEAR_ALL`, **Abbildindex** zu `0`, **Large Image Index**  zu `0`.

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Die Scribble-Anwendung sollte angezeigt werden, und sie sollte am oberen Rand des Fensters über eine Menübandleiste anstelle einer Menüleiste verfügen. Die menübandleiste sollte eine Kategorie verfügen **Startseite**, und **Startseite** müssen Sie einen Bereich **bearbeiten**. Die Menübandschaltflächen, die Sie hinzugefügt haben mit den vorhandenen Ereignishandlern zugeordnet werden soll und die **öffnen**, **schließen**, **speichern**, **Drucken**, und **alle löschen** Schaltflächen sollte wie erwartet funktionieren.

##  <a name="setlook"></a> Festlegen der Darstellung der Anwendung

Ein *visuellen Manager* ist ein globales Objekt, das alle Zeichnungen für eine Anwendung steuert. Da die ursprüngliche Scribble-Anwendung die Benutzeroberfläche im Office 2000-Stil nutzt, sieht die Anwendung möglicherweise altmodisch aus. Sie können die Anwendung zurücksetzen, um den visuellen Manager "Office 2007" zu verwenden, sodass sie einer Office 2007-Anwendung ähnelt.

### <a name="to-set-the-look-of-the-application"></a>So legen Sie die Darstellung der Anwendung fest

1. In der `CMainFrame::OnCreate` funktionieren, und geben Sie den folgenden Code vor der `return 0;` Anweisung, um die standardmäßigen visuellen Manager und den Stil zu ändern.

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Die Anwendungsbenutzeroberfläche sollte der Office 2007-Benutzeroberfläche ähneln.

## <a name="next-steps"></a>Nächste Schritte

Verändert das klassische 1.0 MFC Scribble-Beispiel verwendet die **Menüband-Designer**. Wechseln Sie nun zur [Teil 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md).

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)<br/>
[Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)
