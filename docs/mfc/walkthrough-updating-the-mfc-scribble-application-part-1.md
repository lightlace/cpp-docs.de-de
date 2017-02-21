---
title: "Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Beispiele [C++], Update bestehender Anwendungen"
  - "MFC-Feature Pack, Update bestehender Anwendungen"
  - "Office Fluent-UI, Portieren auf"
  - "Menüband-UI, Portieren auf"
  - "Beispiele [C++], Update bestehender Anwendungen"
  - "Exemplarische Vorgehensweisen [C++], Update bestehender Anwendungen"
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
caps.latest.revision: 54
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 50
---
# Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird beschrieben, wie Sie eine vorhandene MFC\-Anwendung so ändern, dass die Menüband\-Benutzeroberfläche verwendet wird.  Visual Studio unterstützt sowohl das Menüband von Office 2007 als auch das "Scenic Ribbon" von Windows 7.  Weitere Informationen über die Menüband\-Benutzeroberfläche finden Sie unter [Menübänder](http://go.microsoft.com/fwlink/?LinkId=129233) auf der MSDN\-Website.  
  
 In dieser exemplarischen Vorgehensweise wird das klassische MFC\-Beispiel Scribble 1.0 geändert, das Ihnen ermöglicht, mit der Maus Strichzeichnungen zu erstellen.  In diesem Teil der exemplarischen Vorgehensweise wird gezeigt, wie das Scribble\-Beispiel so geändert wird, dass es eine Menübandleiste anzeigt.  In [Teil 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) werden der Menübandleiste weitere Schaltflächen hinzugefügt.  
  
## Vorbereitungsmaßnahmen  
 [Visual C\+\+\-Beispiele](../top/visual-cpp-samples.md)  
  
 [Visual C\+\+\-Beispiele](../top/visual-cpp-samples.md)  
  
##  <a name="top"></a> Abschnitte  
 Dieser Teil der exemplarischen Vorgehensweise enthält die folgenden Abschnitte:  
  
-   [Ersetzen der Basisklassen](#replaceClass)  
  
-   [Hinzufügen von Bitmaps zum Projekt](#addBitmap)  
  
-   [Hinzufügen einer Menübandressource zum Projekt](#addRibbon)  
  
-   [Erstellen einer Instanz der Menübandleiste](#createInstance)  
  
-   [Hinzufügen einer Menübandkategorie](#addCategory)  
  
-   [Festlegen der Darstellung der Anwendung](#setLook)  
  
##  <a name="replaceClass"></a> Ersetzen der Basisklassen  
 Zum Konvertieren einer Anwendung, die ein Menü unterstützt, in eine Anwendung, die ein Menüband unterstützt, müssen Sie die Anwendung, das Rahmenfenster und die Symbolleistenklassen von den aktualisierten Basisklassen ableiten. \(Es wird empfohlen, das ursprüngliche Scribble\-Beispiel nicht zu ändern. Bereinigen Sie stattdessen das Scribble\-Projekt, kopieren Sie es in ein anderes Verzeichnis, und ändern Sie dann die Kopie.\)  
  
#### So ersetzen Sie die Basisklassen in der Scribble\-Anwendung  
  
1.  Überprüfen Sie in der Datei "scribble.cpp", ob `CScribbleApp::InitInstance` einen Aufruf von [AfxOleInit](../Topic/AfxOleInit.md) enthält.  
  
2.  Fügen Sie der Datei "stdafx.h" den folgenden Code hinzu.  
  
    ```  
    #include <afxcontrolbars.h>  
    ```  
  
3.  Ändern Sie in der Datei "scribble.h" die Definition für die `CScribbleApp`\-Klasse, sodass sie von [CWinAppEx Class](../mfc/reference/cwinappex-class.md) abgeleitet wird.  
  
    ```  
    class CScribbleApp: public CWinAppEx  
    ```  
  
4.  Scribble 1.0 wurde geschrieben, als Windows\-Anwendungen eine Initialisierungsdatei \(.ini\) verwendeten, um die Benutzereinstellungen zu speichern.  Ändern Sie Scribble so, dass die Benutzereinstellungen statt in einer Initialisierungsdatei in der Registrierung gespeichert werden.  Um den Registrierungsschlüssel und die Basis festzulegen, geben Sie den folgenden Code in `CScribbleApp::InitInstance` nach der `LoadStdProfileSettings()`\-Anweisung ein.  
  
    ```  
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));  
    SetRegistryBase(_T("Settings"));  
    ```  
  
5.  Der Hauptframe für eine MDI\-Anwendung \(Multiple Document Interface\) wird nicht mehr von der `CMDIFrameWnd`\-Klasse abgeleitet.  Stattdessen wird er von der [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md)\-Klasse abgeleitet.  
  
     Ersetzen Sie in den Dateien "mainfrm.h" und "mainfrm.cpp" alle Verweise auf `CMDIFrameWnd` durch `CMDIFrameWndEx`.  
  
6.  Ersetzen Sie in den Dateien "childfrm.h" und "childfrm.cpp" `CMDIChildWnd` durch `CMDIChildWndEx`.  
  
     Ersetzen Sie in der Datei "childfrm.h" `CSplitterWnd` durch `CSplitterWndEx`.  
  
7.  Ändern Sie die Symbolleisten und die Statusleisten so, dass die neuen MFC\-Klassen verwendet werden.  
  
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
  
10. Wenn Sie beabsichtigen, Ihre Anwendung statisch zu verknüpfen, fügen Sie am Anfang der Projektressourcendatei \(.rc\) folgenden Code hinzu.  
  
    ```  
    #include "afxribbon.rc"  
    ```  
  
     Die Datei "afxribbon.rc" enthält Ressourcen, die zur Laufzeit erforderlich sind.  Der [MFC\-Anwendungs\-Assistent](../mfc/reference/mfc-application-wizard.md) schließt diese Datei bei der Erstellung einer Anwendung automatisch ein.  
  
11. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="addBitmap"></a> Hinzufügen von Bitmaps zum Projekt  
 Für die nächsten vier Schritte dieser exemplarischen Vorgehensweise sind Bitmapressourcen erforderlich.  Sie erhalten die entsprechenden Bitmaps auf verschiedene Arten:  
  
-   Erstellen Sie mit [Resource Editors](../mfc/resource-editors.md) Ihre eigenen Bitmaps.  Oder verwenden Sie die Ressourcen\-Editoren, um Bitmaps aus PNG\-Bildern \(Portable Network Graphics\) zusammenzufügen, die in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthalten sind.  Diese Bilder befinden sich im `VS2008ImageLibrary`\-Verzeichnis.  
  
     Für die Menüband\-Benutzeroberfläche ist es jedoch erforderlich, dass bestimmte Bitmaps transparente Bilder unterstützen.  Transparente Bitmaps verwenden 32 Bits\/Pixel, wobei 24 Bits den Rot\-, Grün\- und Blauanteil der Farbe angeben und 8 Bits einen *Alphakanal,* definieren, der die Transparenz der Farbe angibt.  Die aktuellen Ressourcen\-Editoren können Bitmaps mit 32 Bits\/Pixel anzeigen, aber nicht ändern.  Verwenden Sie daher einen externen Bild\-Editor anstelle der Ressourcen\-Editoren, um transparente Bitmaps zu bearbeiten.  
  
-   Kopieren Sie eine entsprechende Ressourcendatei aus einer anderen Anwendung in Ihr Projekt, und importieren Sie dann Bitmaps von dieser Datei.  
  
 In dieser exemplarischen Vorgehensweise werden Ressourcendateien aus einer Anwendung in das Beispielverzeichnis kopiert.  
  
#### So fügen Sie dem Projekt Bitmaps hinzu  
  
1.  Verwenden Sie Datei\-Explorer, um die folgenden BMP\-Dateien aus dem Ressourcenverzeichnis \(`res`\) des RibbonGadgets\-Beispiels zu kopieren:  
  
    1.  Kopieren Sie "main.bmp" in Ihr Scribble\-Projekt.  
  
    2.  Kopieren Sie "filesmall.bmp" und "filelarge.bmp" in Ihr Scribble\-Projekt.  
  
    3.  Erstellen Sie neue Kopien der Dateien "filelarge.bmp" und "filesmall.bmp", speichern Sie sie jedoch im RibbonGadgets\-Beispiel.  Benennen Sie die Kopien in "homesmall.bmp" und "homelarge.bmp" um, und verschieben Sie sie dann in das Scribble\-Projekt.  
  
    4.  Erstellen Sie eine Kopie der Datei "toolbar.bmp", speichern Sie sie jedoch im RibbonGadgets\-Beispiel.  Benennen Sie die Kopie in "panelicons.bmp" um, und verschieben Sie sie dann in das Scribble\-Projekt.  
  
2.  Importieren Sie die Bitmap für eine MFC\-Anwendung.  Doppelklicken Sie in **Ressourcenansicht** auf den Knoten **scribble.rc**, doppelklicken Sie auf den Knoten **Bitmap**, und klicken Sie dann auf **Ressource hinzufügen**.  Klicken Sie im angezeigten Dialogfeld auf **Importieren**.  Navigieren Sie zum `res`\-Verzeichnis, wählen Sie die Datei "main.bmp" aus, und klicken Sie dann auf **Öffnen**.  
  
     Die Bitmap "main.bmp" enthält ein 26x26\-Bild.  Ändern Sie die ID der Bitmap in IDB\_RIBBON\_MAIN.  
  
3.  Importieren Sie die Bitmaps für das Dateimenü, das an die Anwendungsschaltfläche angefügt ist.  
  
    1.  Importieren Sie die Datei "filesmall.bmp", die zehn 16x16\-Bilder \(16x160\) enthält.  Da nur acht 16x16\-Bilder \(16x128\) benötigen werden, ändern Sie in der **Ressourcenansicht** die Breite dieser Bitmap von 160 in 128.  Ändern Sie die ID der Bitmap in IDB\_RIBBON\_FILESMALL.  
  
    2.  Importieren Sie die Datei "filelarge.bmp", die acht 32x32\-Bilder \(32x256\) enthält.  Ändern Sie die ID der Bitmap in IDB\_RIBBON\_FILELARGE.  
  
4.  Importieren Sie die Bitmaps für die Menübandkategorien und \-bereiche.  Jede Registerkarte in der Menübandleiste ist eine Kategorie und besteht aus einer Textbezeichnung und einem optionalen Bild.  
  
    1.  Importieren Sie die Bitmap "homesmall.bmp", die acht 16x16\-Bilder für Bitmaps für kleine Schaltflächen enthält.  Ändern Sie die ID der Bitmap in IDB\_RIBBON\_HOMESMALL.  
  
    2.  Importieren Sie die Bitmap "homelarge.bmp", die acht 32x32\-Bilder für Bitmaps für große Schaltflächen enthält.  Ändern Sie die ID der Bitmap in IDB\_RIBBON\_HOMELARGE.  
  
5.  Importieren Sie Bitmaps für die Menübandbereiche, deren Größe geändert wurde.  Diese Bitmaps oder Bereichssymbole werden nach einer Größenänderung verwendet, wenn das Menüband zu klein ist, um den gesamten Bereich anzuzeigen.  
  
    1.  Importieren Sie die Bitmap "panelicons.bmp", die acht 16x16\-Bilder enthält.  Legen Sie im Fenster **Eigenschaften** vom **Bitmap\-Editor** die Breite der Bitmap auf 64 \(16x64\) fest.  Ändern Sie die ID der Bitmap in IDB\_PANEL\_ICONS.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="addRibbon"></a> Hinzufügen einer Menübandressource zum Projekt  
 Wenn Sie eine Anwendung, die Menüs verwendet, in eine Anwendung konvertieren, die ein Menüband verwendet, müssen Sie die vorhandenen Menüs nicht entfernen oder deaktivieren.  Stattdessen erstellen Sie eine Menübandressource, fügen Menübandschaltflächen hinzu, und weisen die neuen Schaltflächen dann den vorhandenen Menüelementen zu.  Obwohl die Menüs nicht mehr sichtbar sind, werden Meldungen von der Menübandleiste über die Menüs weitergeleitet.  Darüber hinaus funktionieren Tastenkombinationen für Menüs weiterhin.  
  
 Ein Menüband besteht aus der Anwendungsschaltfläche, bei der es sich um die große Schaltfläche auf der oberen linken Seite des Menübands handelt, und mindestens einer Kategorienregisterkarte.  Jede Kategorienregisterkarte enthält einen oder mehrere Bereiche, die als Container für Menübandschaltflächen und Steuerelemente dienen.  Das folgende Verfahren veranschaulicht, wie eine Menübandressource erstellt und anschließend die Anwendungsschaltfläche angepasst wird.  
  
#### So fügen Sie dem Projekt eine Menübandressource hinzu  
  
1.  Klicken Sie im Menü **Projekt** auf **Ressource hinzufügen**.  
  
2.  Wählen Sie im Dialogfeld **Ressource hinzufügen** die Option **Menüband** aus, und klicken Sie dann auf **Neu**.  
  
     Visual Studio erstellt eine Menübandressource und öffnet sie in der Designansicht.  Das Menübandressourcen\-ID lautet IDR\_RIBBON1 und wird in **Ressourcenansicht** angezeigt.  Das Menüband enthält eine Kategorie und einen Bereich.  
  
3.  Sie können die Anwendungsschaltfläche anpassen, indem Sie ihre Eigenschaften ändern.  Die Meldungs\-IDs, die in diesem Code verwendet werden, sind bereits im Menü für Scribble 1.0 definiert.  
  
4.  Klicken Sie in der Designansicht auf die Anwendungsschaltfläche, um ihre Eigenschaften anzuzeigen.  Ändern Sie die Eigenschaftswerte wie folgt: **Bild** in `IDB_RIBBON_MAIN`, **Eingabeaufforderung** in `Datei`, **Schlüssel** in `f`, **Große Bilder** in `IDB_RIBBON_FILELARGE` und **Kleine Bilder** in `IDB_RIBBON_FILESMALL`.  
  
5.  Durch die folgenden Änderungen wird das Menü erstellt, das angezeigt wird, wenn der Benutzer auf die Anwendungsschaltfläche klickt.  Klicken Sie auf die Auslassungszeichen \(**...**\) neben **Main Items**, um den **Elemente\-Editor** zu öffnen.  
  
    1.  Klicken Sie auf **Hinzufügen**, um eine Schaltfläche hinzuzufügen.  Ändern Sie **Beschriftung** in `&Neu`, **ID** in `ID_FILE_NEW`, **Bild** in `0` und **Bild groß** in `0`.  
  
    2.  Klicken Sie auf **Hinzufügen**, um eine zweite Schaltfläche hinzuzufügen.  Ändern Sie **Beschriftung** in `&Speichern`, **ID** in `ID_FILE_SAVE`, **Bild** in `2` und **Bild groß** in `2`.  
  
    3.  Klicken Sie auf **Hinzufügen**, um eine dritte Schaltfläche hinzuzufügen.  Ändern Sie **Beschriftung** in `Speichern &unter`, **ID** in `ID_FILE_SAVE_AS`, **Bild** in `3` und **Bild groß** in `3`.  
  
    4.  Klicken Sie auf **Hinzufügen**, um eine vierte Schaltfläche hinzuzufügen.  Ändern Sie **Beschriftung** in `&Drucken`, **ID** in `ID_FILE_PRINT`, **Bild** in `4` und **Bild groß** in `4`.  
  
    5.  Ändern Sie den Typ **Element** in **Trennzeichen**, und klicken Sie dann auf **Hinzufügen**.  
  
    6.  Ändern Sie den Typ **Element** in **Schaltfläche**.  Klicken Sie auf **Hinzufügen**, um eine fünfte Schaltfläche hinzuzufügen.  Ändern Sie **Beschriftung** in `&Schließen`, **ID** in `ID_FILE_CLOSE`, **Bild** in `5` und **Bild groß** in `5`.  
  
6.  Durch die folgenden Änderungen wird ein Untermenü unter der Druckschaltfläche erstellt, die Sie im vorherigen Schritt erstellt haben.  
  
    1.  Klicken Sie auf die Schaltfläche **Drucken**, ändern Sie den Typ **Element** in **Bezeichnung**, und klicken Sie dann auf **Einfügen**.  Ändern Sie **Beschriftung** in `Dokument in der Vorschau anzeigen und drucken`.  
  
    2.  Klicken Sie auf die Schaltfläche **Drucken**, ändern Sie den Typ **Element** in **Schaltfläche**, und klicken Sie dann auf **Einfügen**.  Ändern Sie **Beschriftung** in `&Drucken`, **ID** in `ID_FILE_PRINT`, **Bild** in `4` und **Bild groß** in `4`.  
  
    3.  Klicken Sie auf die Schaltfläche **Drucken** und dann auf **Einfügen**, um eine Schaltfläche hinzuzufügen.  Ändern Sie **Beschriftung** in `&Schnelldruck`, **ID** in `ID_FILE_PRINT_DIRECT`, **Bild** in `7` und **Bild groß** in `7`.  
  
    4.  Klicken Sie auf die Schaltfläche **Drucken** und dann auf **Einfügen**, um eine weitere Schaltfläche hinzuzufügen.  Änderung **Beschriftung** in `Druckt vor &Ansicht`, mit **ID** in `ID_FILE_PRINT_PREVIEW`, an **Bild** auf `6` und an **Bild groß** in `6`.  
  
    5.  Sie haben die **Main Items** nun geändert.  Klicken Sie auf **Schließen**, um den **Elemente\-Editor** zu beenden.  
  
7.  Durch die folgende Änderung wird eine Beendigungsschaltfläche erstellt, die am unteren Rand des Anwendungsschaltflächenmenüs angezeigt wird.  
  
    1.  Klicken Sie im Fenster **Eigenschaften** auf die Auslassungszeichen \(**...**\) neben **Schaltfläche**, um den **Elemente\-Editor** zu öffnen.  
  
    2.  Klicken Sie auf **Hinzufügen**, um eine Schaltfläche hinzuzufügen.  Änderung **Beschriftung** in `E &xit`, **ID** auf `ID_APP_EXIT`, **Bild** zu `8`.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="createInstance"></a> Erstellen einer Instanz der Menübandleiste  
 Die folgenden Schritte zeigen, wie beim Starten Ihrer Anwendung eine Instanz der Menübandleiste erstellt wird.  Um eine Menübandleiste zu einer Anwendung hinzuzufügen, deklarieren Sie die Menübandleiste in der Datei "mainfrm.h".  Schreiben Sie dann in der Datei "mainfrm.cpp" Code zum Laden der Menübandressource.  
  
#### So erstellen Sie eine Instanz der Menübandleiste  
  
1.  Fügen Sie in der Datei "mainfrm.h" einen Datenmember zum geschützten Abschnitt von `CMainFrame`, der Klassendefinition für den Hauptframe, hinzu.  Dieser Member stellt die Menübandleiste dar.  
  
    ```  
    // Ribbon bar for the application  
    CMFCRibbonBar  m_wndRibbonBar;  
    ```  
  
2.  Fügen Sie in der Datei "mainfrm.cpp" den folgenden Code vor der letzten `return`\-Anweisung am Ende der `CMainFrame::OnCreate`\-Funktion hinzu.  Dadurch wird eine Instanz der Menübandleiste erstellt.  
  
    ```  
    // Create the ribbon bar  
    if (!m_wndRibbonBar.Create(this))  
    {  
    return -1;   //Failed to create ribbon bar  
    }  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);  
    ```  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="addCategory"></a> Anpassen der Menübandressource  
 Nachdem Sie die Anwendungsschaltfläche erstellt haben, können Sie Elemente zum Menüband hinzufügen.  
  
> [!NOTE]
>  In dieser exemplarischen Vorgehensweise wird das gleiche Bereichssymbol für alle Bereiche verwendet.  Sie können jedoch auch andere Bildlistenindizes verwenden, um andere Symbole anzuzeigen.  
  
#### So fügen Sie eine Kategorie "Startseite" und einen Bereich "Bearbeiten" hinzu  
  
1.  Das Scribble\-Programm erfordert nur eine Kategorie.  Klicken Sie in der Designansicht auf **Kategorie**, um ihre Eigenschaften anzuzeigen.  Ändern Sie die Eigenschaftswerte wie folgt: **Beschriftung** in `&Startseite`, **Große Bilder** in `IDB_RIBBON_HOMELARGE` und **Kleine Bilder** in `IDB_RIBBON_HOMESMALL`.  
  
2.  Jede Menübandkategorie ist in benannte Bereiche unterteilt.  Jeder Bereich enthält einen Satz von Steuerelementen, die verwandte Vorgänge ausführen.  Diese Kategorie verfügt über einen Bereich.  Klicken Sie auf **Bereich**, und ändern Sie dann **Beschriftung** in `Bearbeiten` und **Image Index** in `0`.  
  
3.  Fügen Sie dem Bereich **Bearbeiten** eine Schaltfläche hinzu, mit der der Inhalt des Dokuments gelöscht werden kann.  Die Meldungs\-ID für diese Schaltfläche wurde bereits in der Menüressource IDR\_SCRIBBTYPE definiert.  Geben Sie `Alle löschen` als Schaltflächentext und Index der Bitmap an, die die Schaltfläche dekoriert.  Öffnen Sie den **Werkzeugkasten**, und ziehen Sie dann eine **Schaltfläche** zum Bereich **Bearbeiten**.  Klicken Sie auf die Schaltfläche, und ändern Sie dann **Beschriftung** in `Alle löschen`, **ID** in `ID_EDIT_CLEAR_ALL`, **Image Index** in `0` und **Large Image Index** in `0`.  
  
4.  Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  Die Scribble\-Anwendung sollte angezeigt werden, und sie sollte am oberen Rand des Fensters über eine Menübandleiste anstelle einer Menüleiste verfügen.  Die Menübandleiste sollte eine Kategorie **Startseite** aufweisen und **Startseite** einen Bereich **Bearbeiten** aufweisen.  Die Menübandschaltflächen, die Sie hinzugefügt haben, sollten den vorhandenen Ereignishandlern zugeordnet sein, und die Schaltflächen **Öffnen**, **Schließen**, **Speichern**, **Drucken** und **Alle löschen** sollten erwartungsgemäß funktionieren.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="setLook"></a> Festlegen der Darstellung der Anwendung  
 Ein *visueller Manager* ist ein globales Objekt, das alle Zeichnungen für eine Anwendung steuert.  Da die ursprüngliche Scribble\-Anwendung die Benutzeroberfläche im Office 2000\-Stil nutzt, sieht die Anwendung möglicherweise altmodisch aus.  Sie können die Anwendung zurücksetzen, um den visuellen Manager "Office 2007" zu verwenden, sodass sie einer Office 2007\-Anwendung ähnelt.  
  
#### So legen Sie die Darstellung der Anwendung fest  
  
1.  Geben Sie in der `CMainFrame::OnCreate`\-Funktion den folgenden Code ein, um den standardmäßigen visuellen Manager und den Stil zu ändern.  
  
    ```  
    // Set the default manager to Office 2007   
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));  
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);  
    ```  
  
2.  Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  Die Anwendungsbenutzeroberfläche sollte der Office 2007\-Benutzeroberfläche ähneln.  
  
 \[[Abschnitte](#top)\]  
  
## Nächste Schritte  
 Sie haben das klassische MFC\-Beispiel Scribble 1.0 so geändert, das der Menüband\-Designer verwendet wird.  Fahren Sie jetzt mit [Teil 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) fort.  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)   
 [Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble\-Anwendung \(Teil 2\)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)