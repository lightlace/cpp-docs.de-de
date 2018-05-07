---
title: 'Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2d55768f423feef3b5093ec0af6365aecfaafee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1)
In dieser exemplarischen Vorgehensweise wird beschrieben, wie Sie eine vorhandene MFC-Anwendung so ändern, dass die Menüband-Benutzeroberfläche verwendet wird. Visual Studio unterstützt sowohl das Menüband von Office 2007 als auch das "Scenic Ribbon" von Windows 7. Weitere Informationen zur Menüband-Benutzeroberfläche finden Sie unter [Menübänder](http://go.microsoft.com/fwlink/p/?linkid=129233) auf der MSDN-Website.  
  
 In dieser exemplarischen Vorgehensweise wird das klassische MFC-Beispiel Scribble 1.0 geändert, das Ihnen ermöglicht, mit der Maus Strichzeichnungen zu erstellen. In diesem Teil der exemplarischen Vorgehensweise wird gezeigt, wie das Scribble-Beispiel so geändert wird, dass es eine Menübandleiste anzeigt. [Teil 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) der menübandleiste Weitere Schaltflächen hinzugefügt.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 [Visual C++-Beispiele](../visual-cpp-samples.md)  
  
 [Visual C++-Beispiele](../visual-cpp-samples.md)  
  
##  <a name="top"></a> Abschnitte  
 Dieser Teil der exemplarischen Vorgehensweise enthält die folgenden Abschnitte:  
  
- [Ersetzen der Basisklassen](#replaceclass)  
  
- [Hinzufügen von Bitmaps zum Projekt](#addbitmap)  
  
- [Hinzufügen einer Menübandressource zum Projekt](#addribbon)  
  
- [Erstellen einer Instanz der Menübandleiste](#createinstance)  
  
- [Hinzufügen einer Menübandkategorie](#addcategory)  
  
- [Festlegen der Darstellung der Anwendung](#setlook)  
  
##  <a name="replaceclass"></a> Ersetzen der Basisklassen  
 Zum Konvertieren einer Anwendung, die ein Menü unterstützt, in eine Anwendung, die ein Menüband unterstützt, müssen Sie die Anwendung, das Rahmenfenster und die Symbolleistenklassen von den aktualisierten Basisklassen ableiten. (Es wird empfohlen, das ursprüngliche Scribble-Beispiel nicht zu ändern. Bereinigen Sie stattdessen das Scribble-Projekt, kopieren Sie es in ein anderes Verzeichnis, und ändern Sie dann die Kopie.)  
  
#### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>So ersetzen Sie die Basisklassen in der Scribble-Anwendung  
  
1.  Überprüfen Sie in scribble.cpp, dass `CScribbleApp::InitInstance` enthält einen Aufruf an [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit).  
  
2.  Fügen Sie der Datei "stdafx.h" den folgenden Code hinzu.  
  
 ```  
    #include <afxcontrolbars.h>  
 ```  
  
3.  In scribble.h, ändern Sie die Definition der `CScribbleApp` Klasse abgeleitet ist [CWinAppEx Class](../mfc/reference/cwinappex-class.md).  
  
 ```  
    class CScribbleApp: public CWinAppEx  
 ```  
  
4.  Scribble 1.0 wurde geschrieben, als Windows-Anwendungen eine Initialisierungsdatei (.ini) verwendeten, um die Benutzereinstellungen zu speichern. Ändern Sie Scribble so, dass die Benutzereinstellungen statt in einer Initialisierungsdatei in der Registrierung gespeichert werden. Um den Registrierungsschlüssel und die Basis festzulegen, geben Sie den folgenden Code in `CScribbleApp::InitInstance` nach der `LoadStdProfileSettings()`-Anweisung ein.  
  
 ```  
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));

 SetRegistryBase(_T("Settings"));

 ```  
  
5.  Der Hauptframe für eine MDI-Anwendung (Multiple Document Interface) wird nicht mehr von der `CMDIFrameWnd`-Klasse abgeleitet. Stattdessen abgeleitet aus dem [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md) Klasse.  
  
     Ersetzen Sie in den Dateien "mainfrm.h" und "mainfrm.cpp" alle Verweise auf `CMDIFrameWnd` durch `CMDIFrameWndEx`.  
  
6.  Ersetzen Sie in den Dateien "childfrm.h" und "childfrm.cpp" `CMDIChildWnd` durch `CMDIChildWndEx`.  
  
     In der Childfrm. h-Datei ersetzen `CSplitterWnd` mit `CSplitterWndEx`.  
  
7.  Ändern Sie die Symbolleisten und die Statusleisten so, dass die neuen MFC-Klassen verwendet werden.  
  
     Führen Sie in der Datei "mainfrm.h" folgende Schritte aus:  
  
    1.  Ersetzen Sie `CToolBar` durch `CMFCToolBar`.  
  
    2.  Ersetzen Sie `CStatusBar` durch `CMFCStatusBar`.  
  
8.  Führen Sie in der Datei "mainfrm.cpp" folgende Schritte aus:  
  
    1.  Ersetzen Sie `m_wndToolBar.SetBarStyle` durch `m_wndToolBar.SetPaneStyle`  
  
    2.  Ersetzen Sie `m_wndToolBar.GetBarStyle` durch `m_wndToolBar.GetPaneStyle`  
  
    3.  Ersetzen Sie `DockControlBar(&m_wndToolBar)` durch `DockPane(&m_wndToolBar)`  
  
9. Kommentieren Sie in der Datei "ipframe.cpp" die folgenden drei Codezeilen aus.  
  
 ```  
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);

 pWndFrame->EnableDocking(CBRS_ALIGN_ANY);

    pWndFrame->DockPane(&m_wndToolBar);

 ```  
  
10. Wenn Sie beabsichtigen, Ihre Anwendung statisch zu verknüpfen, fügen Sie am Anfang der Projektressourcendatei (.rc) folgenden Code hinzu.  
  
 ```  
    #include "afxribbon.rc"  
 ```  
  
     Die Datei "afxribbon.rc" enthält Ressourcen, die zur Laufzeit erforderlich sind. Die [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md) enthält diese Datei automatisch, wenn Sie eine Anwendung erstellen.  
  
11. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  
  
 [[Abschnitte](#top)]  
  
##  <a name="addbitmap"></a> Hinzufügen von Bitmaps zum Projekt  
 Für die nächsten vier Schritte dieser exemplarischen Vorgehensweise sind Bitmapressourcen erforderlich. Sie erhalten die entsprechenden Bitmaps auf verschiedene Arten:  
  
-   Verwenden der [Ressourcen-Editoren](../windows/resource-editors.md) auf Ihren eigenen Bitmaps auswählen. Oder verwenden Sie die Ressourcen-Editoren, um Bitmaps aus PNG-Bildern (Portable Network Graphics) zusammenzufügen, die in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthalten sind. Diese Bilder befinden sich der `VS2008ImageLibrary` Verzeichnis.  
  
     Für die Menüband-Benutzeroberfläche ist es jedoch erforderlich, dass bestimmte Bitmaps transparente Bilder unterstützen. Transparente Bitmaps verwenden 32 Bits / Pixel, in denen 24 Bits den Rot-, Grün- und blauen-Komponenten der Farbe angeben und Definieren von 8 Bits einen *alpha-Kanal* , der die Transparenz der Farbe angibt. Die aktuellen Ressourcen-Editoren können Bitmaps mit 32 Bits/Pixel anzeigen, aber nicht ändern. Verwenden Sie daher einen externen Bild-Editor anstelle der Ressourcen-Editoren, um transparente Bitmaps zu bearbeiten.  
  
-   Kopieren Sie eine entsprechende Ressourcendatei aus einer anderen Anwendung in Ihr Projekt, und importieren Sie dann Bitmaps von dieser Datei.  
  
 In dieser exemplarischen Vorgehensweise werden Ressourcendateien aus einer Anwendung in das Beispielverzeichnis kopiert.  
  
#### <a name="to-add-bitmaps-to-the-project"></a>So fügen Sie dem Projekt Bitmaps hinzu  
  
1.  Verwenden Sie Datei-Explorer, um die folgenden BMP-Dateien aus dem Ressourcenverzeichnis (`res`) des RibbonGadgets-Beispiels zu kopieren:  
  
    1.  Kopieren Sie "main.bmp" in Ihr Scribble-Projekt.  
  
    2.  Kopieren Sie "filesmall.bmp" und "filelarge.bmp" in Ihr Scribble-Projekt.  
  
    3.  Erstellen Sie neue Kopien der Dateien "filelarge.bmp" und "filesmall.bmp", speichern Sie sie jedoch im RibbonGadgets-Beispiel. Benennen Sie die Kopien in "homesmall.bmp" und "homelarge.bmp" um, und verschieben Sie sie dann in das Scribble-Projekt.  
  
    4.  Erstellen Sie eine Kopie der Datei "toolbar.bmp", speichern Sie sie jedoch im RibbonGadgets-Beispiel. Benennen Sie die Kopie in "panelicons.bmp" um, und verschieben Sie sie dann in das Scribble-Projekt.  
  
2.  Importieren Sie die Bitmap für eine MFC-Anwendung. In **Ressourcenansicht**, doppelklicken Sie auf die **scribble.rc** Knoten, doppelklicken Sie auf die **Bitmap** Knoten, und klicken Sie dann auf **Ressource hinzufügen**. Klicken Sie im Dialogfeld auf **Import**. Navigieren Sie zu der `res` Verzeichnis ist, wählen Sie die Datei "Main.bmp", und klicken Sie dann auf **öffnen**.  
  
     Die Bitmap "main.bmp" enthält ein 26x26-Bild. Ändern Sie die ID der Bitmap in IDB_RIBBON_MAIN.  
  
3.  Importieren Sie die Bitmaps für das Dateimenü, das an die Anwendungsschaltfläche angefügt ist.  
  
    1.  Importieren Sie die Datei "filesmall.bmp", die zehn 16x16-Bilder (16x160) enthält. Da wir nur acht 16 x 16-Bilder (16 x 128) benötigen, verwenden Sie die **Ressourcenansicht** auf die Breite dieser Bitmap von 160 in 128 zu ändern. Ändern Sie die ID der Bitmap in IDB_RIBBON_FILESMALL.  
  
    2.  Importieren Sie die Datei "filelarge.bmp", die acht 32x32-Bilder (32x256) enthält. Ändern Sie die ID der Bitmap in IDB_RIBBON_FILELARGE.  
  
4.  Importieren Sie die Bitmaps für die Menübandkategorien und -bereiche. Jede Registerkarte in der Menübandleiste ist eine Kategorie und besteht aus einer Textbezeichnung und einem optionalen Bild.  
  
    1.  Importieren Sie die Bitmap "homesmall.bmp", die acht 16x16-Bilder für Bitmaps für kleine Schaltflächen enthält. Ändern Sie die ID der Bitmap in IDB_RIBBON_HOMESMALL.  
  
    2.  Importieren Sie die Bitmap "homelarge.bmp", die acht 32x32-Bilder für Bitmaps für große Schaltflächen enthält. Ändern Sie die ID der Bitmap in IDB_RIBBON_HOMELARGE.  
  
5.  Importieren Sie Bitmaps für die Menübandbereiche, deren Größe geändert wurde. Diese Bitmaps oder Bereichssymbole werden nach einer Größenänderung verwendet, wenn das Menüband zu klein ist, um den gesamten Bereich anzuzeigen.  
  
    1.  Importieren Sie die Bitmap "panelicons.bmp", die acht 16x16-Bilder enthält. In der **Eigenschaften** Fenster von der **Bitmap-Editor**, passt die Breite der Bitmap auf 64 (16 x 64). Ändern Sie die ID der Bitmap in IDB_PANEL_ICONS.  
  
 [[Abschnitte](#top)]  
  
##  <a name="addribbon"></a> Hinzufügen einer Menübandressource zum Projekt  
 Wenn Sie eine Anwendung, die Menüs verwendet, in eine Anwendung konvertieren, die ein Menüband verwendet, müssen Sie die vorhandenen Menüs nicht entfernen oder deaktivieren. Stattdessen erstellen Sie eine Menübandressource, fügen Menübandschaltflächen hinzu, und weisen die neuen Schaltflächen dann den vorhandenen Menüelementen zu. Obwohl die Menüs nicht mehr sichtbar sind, werden Meldungen von der Menübandleiste über die Menüs weitergeleitet. Darüber hinaus funktionieren Tastenkombinationen für Menüs weiterhin.  
  
 Ein Menüband besteht aus der Anwendungsschaltfläche, bei der es sich um die große Schaltfläche auf der oberen linken Seite des Menübands handelt, und mindestens einer Kategorienregisterkarte. Jede Kategorienregisterkarte enthält einen oder mehrere Bereiche, die als Container für Menübandschaltflächen und Steuerelemente dienen. Das folgende Verfahren veranschaulicht, wie eine Menübandressource erstellt und anschließend die Anwendungsschaltfläche angepasst wird.  
  
#### <a name="to-add-a-ribbon-resource-to-the-project"></a>So fügen Sie dem Projekt eine Menübandressource hinzu  
  
1.  Auf der **Projekt** Menü klicken Sie auf **Ressource hinzufügen**.  
  
2.  In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Menüband** , und klicken Sie dann auf **neu**.  
  
     Visual Studio erstellt eine Menübandressource und öffnet sie in der Designansicht. Das Menübandressourcen-ID lautet IDR_RIBBON1 und in angezeigt wird **Ressourcenansicht**. Das Menüband enthält eine Kategorie und einen Bereich.  
  
3.  Sie können die Anwendungsschaltfläche anpassen, indem Sie ihre Eigenschaften ändern. Die Meldungs-IDs, die in diesem Code verwendet werden, sind bereits im Menü für Scribble 1.0 definiert.  
  
4.  Klicken Sie in der Designansicht auf die Anwendungsschaltfläche, um ihre Eigenschaften anzuzeigen. Eigenschaftswerte wie folgt ändern: **Image** auf `IDB_RIBBON_MAIN`, **Prompt** auf `File`, **Schlüssel** auf `f`, **große Bilder** auf `IDB_RIBBON_FILELARGE`, und **kleine Bilder** auf `IDB_RIBBON_FILESMALL`.  
  
5.  Durch die folgenden Änderungen wird das Menü erstellt, das angezeigt wird, wenn der Benutzer auf die Anwendungsschaltfläche klickt. Klicken Sie auf die Auslassungspunkte (**...** ) neben **Main Items** So öffnen die **Elemente-Editor**.  
  
    1.  Klicken Sie auf **hinzufügen** , eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `&New`, **ID** auf `ID_FILE_NEW`, **Image** auf `0`, **Bild groß** auf `0`.  
  
    2.  Klicken Sie auf **hinzufügen** um eine zweite Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `&Save`, **ID** auf `ID_FILE_SAVE`, **Image** auf `2`, und **Bild groß** zu `2`.  
  
    3.  Klicken Sie auf **hinzufügen** um eine dritte Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `Save &As`, **ID** auf `ID_FILE_SAVE_AS`, **Image** auf `3`, und **Bild groß** zu `3`.  
  
    4.  Klicken Sie auf **hinzufügen** um eine vierte Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `&Print`, **ID** auf `ID_FILE_PRINT`, **Image** auf `4`, und **Bild groß** zu `4`.  
  
    5.  Ändern der **Element** zu Typ **Trennzeichen** , und klicken Sie dann auf **hinzufügen**.  
  
    6.  Ändern der **Element** zu Typ **Schaltfläche**. Klicken Sie auf **hinzufügen** um eine fünfte Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `&Close`, **ID** auf `ID_FILE_CLOSE`, **Image** auf `5`, und **Bild groß** zu `5`.  
  
6.  Durch die folgenden Änderungen wird ein Untermenü unter der Druckschaltfläche erstellt, die Sie im vorherigen Schritt erstellt haben.  
  
    1.  Klicken Sie auf die **Drucken** Schaltfläche, ändern Sie die **Element** geben **Bezeichnung**, und klicken Sie dann auf **einfügen**. Änderung **Beschriftung** auf `Preview and print the document`.  
  
    2.  Klicken Sie auf die **Drucken** Schaltfläche, ändern Sie die **Element** geben **Schaltfläche**, und klicken Sie auf **einfügen**. Änderung **Beschriftung** auf `&Print`, **ID** auf `ID_FILE_PRINT`, **Image** auf `4`, und **Bild groß** zu `4`.  
  
    3.  Klicken Sie auf die **Drucken** Schaltfläche, und klicken Sie dann auf **einfügen** , eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `&Quick Print`, **ID** auf `ID_FILE_PRINT_DIRECT`, **Image** auf `7`, und **Bild groß** zu `7`.  
  
    4.  Klicken Sie auf die **Drucken** Schaltfläche, und klicken Sie dann auf **einfügen** um eine weitere Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `Print Pre&view`, **ID** auf `ID_FILE_PRINT_PREVIEW`, **Image** auf `6`, und **Bild groß** zu `6`.  
  
    5.  Sie haben nun geändert. die **Main Items**. Klicken Sie auf **schließen** zum Beenden der **Elemente-Editor**.  
  
7.  Durch die folgende Änderung wird eine Beendigungsschaltfläche erstellt, die am unteren Rand des Anwendungsschaltflächenmenüs angezeigt wird.  
  
    1.  In der **Eigenschaften** Fenster, klicken Sie auf die Auslassungspunkte (**...** ) neben **Schaltfläche** So öffnen die **Elemente-Editor**.  
  
    2.  Klicken Sie auf **hinzufügen** , eine Schaltfläche hinzuzufügen. Änderung **Beschriftung** auf `E&xit`, **ID** auf `ID_APP_EXIT`, **Image** auf `8`.  
  
 [[Abschnitte](#top)]  
  
##  <a name="createinstance"></a> Erstellen einer Instanz der Menübandleiste  
 Die folgenden Schritte zeigen, wie beim Starten Ihrer Anwendung eine Instanz der Menübandleiste erstellt wird. Um eine Menübandleiste zu einer Anwendung hinzuzufügen, deklarieren Sie die Menübandleiste in der Datei "mainfrm.h". Schreiben Sie dann in der Datei "mainfrm.cpp" Code zum Laden der Menübandressource.  
  
#### <a name="to-create-an-instance-of-the-ribbon-bar"></a>So erstellen Sie eine Instanz der Menübandleiste  
  
1.  Fügen Sie in der Datei "mainfrm.h" einen Datenmember zum geschützten Abschnitt von `CMainFrame`, der Klassendefinition für den Hauptframe, hinzu. Dieser Member stellt die Menübandleiste dar.  
  
 "" * / / Multifunktionsleisten-Leiste für die Anwendung  
    CMFCRibbonBar M_wndRibbonBar;  
 ```  
  
2.  In the mainfrm.cpp file, add the following code before the final `return` statement at the end of the `CMainFrame::OnCreate` function. This creates an instance of the ribbon bar.  
  
 ``` *// Create the ribbon bar  
    if (!m_wndRibbonBar.Create(this))  
 {  
    return -1;   //Failed to create ribbon bar  
 }  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
 [[Abschnitte](#top)]  
  
##  <a name="addcategory"></a> Anpassen der Menübandressource  
 Nachdem Sie die Anwendungsschaltfläche erstellt haben, können Sie Elemente zum Menüband hinzufügen.  
  
> [!NOTE]
>  In dieser exemplarischen Vorgehensweise wird das gleiche Bereichssymbol für alle Bereiche verwendet. Sie können jedoch auch andere Bildlistenindizes verwenden, um andere Symbole anzuzeigen.  
  
#### <a name="to-add-a-home-category-and-edit-panel"></a>So fügen Sie eine Kategorie "Startseite" und einen Bereich "Bearbeiten" hinzu  
  
1.  Das Scribble-Programm erfordert nur eine Kategorie. Klicken Sie in der Entwurfsansicht auf **Kategorie** um seine Eigenschaften anzuzeigen. Ändern Sie Eigenschaftswerte wie folgt: **Beschriftung** auf `&Home`, **große Bilder** auf `IDB_RIBBON_HOMELARGE`, **kleine Bilder** auf `IDB_RIBBON_HOMESMALL`.  
  
2.  Jede Menübandkategorie ist in benannte Bereiche unterteilt. Jeder Bereich enthält einen Satz von Steuerelementen, die verwandte Vorgänge ausführen. Diese Kategorie verfügt über einen Bereich. Klicken Sie auf **Bereich**, und ändern Sie dann **Beschriftung** auf `Edit` und **Abbildindex** auf `0`.  
  
3.  Um die **bearbeiten** Bereich, fügen Sie eine Schaltfläche, die für das Löschen des Inhalts des Dokuments zuständig ist. Die Meldungs-ID für diese Schaltfläche wurde bereits in der Menüressource IDR_SCRIBBTYPE definiert. Geben Sie `Clear All` als Schaltflächentext und der Index der Bitmap, die die Schaltfläche dekoriert. Öffnen der **Toolbox**, und ziehen Sie dann eine **Schaltfläche** auf die **bearbeiten** Bereich. Klicken Sie auf die Schaltfläche "", und ändern Sie dann **Beschriftung** auf `Clear All`, **ID** auf `ID_EDIT_CLEAR_ALL`, **Abbildindex** auf `0`, **große Abbildindex**  auf `0`.  
  
4.  Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Die Scribble-Anwendung sollte angezeigt werden, und sie sollte am oberen Rand des Fensters über eine Menübandleiste anstelle einer Menüleiste verfügen. Die menübandleiste sollte eine Kategorie verfügen **Home**, und **Home** sollten einen Bereich haben **bearbeiten**. Die Menübandschaltflächen, die Sie hinzugefügt mit den vorhandenen Ereignishandlern zugeordnet werden soll und die **öffnen**, **schließen**, **speichern**, **Drucken**, und **alle löschen** Schaltflächen sollte wie erwartet funktionieren.  
  
 [[Abschnitte](#top)]  
  
##  <a name="setlook"></a> Festlegen der Darstellung der Anwendung  
 Ein *visuellen Manager* ist ein globales Objekt, das alle Zeichnungen für eine Anwendung steuert. Da die ursprüngliche Scribble-Anwendung die Benutzeroberfläche im Office 2000-Stil nutzt, sieht die Anwendung möglicherweise altmodisch aus. Sie können die Anwendung zurücksetzen, um den visuellen Manager "Office 2007" zu verwenden, sodass sie einer Office 2007-Anwendung ähnelt.  
  
#### <a name="to-set-the-look-of-the-application"></a>So legen Sie die Darstellung der Anwendung fest  
  
1.  Geben Sie in der `CMainFrame::OnCreate`-Funktion den folgenden Code ein, um den standardmäßigen visuellen Manager und den Stil zu ändern.  
  
 "" * / / Legen Sie die Standard-Manager auf Office 2007   
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));

 CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);

 ```  
  
2.  Save the changes, and then build and run the application. The application UI should resemble the Office 2007 UI.  
  
 [[Sections](#top)]  
  
## Next Steps  
 You have modified the classic Scribble 1.0 MFC sample to use the Ribbon Designer. Now go to [Part 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md).  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)   
 [Walkthrough: Updating the MFC Scribble Application (Part 2)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)

