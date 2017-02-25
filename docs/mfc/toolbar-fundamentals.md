---
title: "Grundlegendes &#252;ber Symbolleisten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RT_TOOLBAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsassistenten [C++], Installieren von Systemleisten für Standardanwendung"
  - "Befehls-IDs, Schaltflächen der Symbolleiste"
  - "CToolBar-Klasse, Standardsymbolleiten im Anwendungs-Assistent"
  - "Einbetten von Symbolleiten in Rahmenfenster (Klasse)"
  - "Rahmenfensterklassen, Symbolleisten einbetten in"
  - "LoadBitmap-Methode, Symbolleisten"
  - "LoadToolBar-Methode"
  - "Ressourcen [MFC], Symbolleiste"
  - "RT_TOOLBAR-Ressource"
  - "SetButtons-Methode"
  - "Symbolleisten-Steuerelemente [MFC], Befehls-ID"
  - "Symbolleisten-Steuerelemente [MFC], mit Anwendungs-Assistent erstellte Symbolleisten"
  - "Symbolleisten-Editor, Anwendungs-Assistent"
  - "Symbolleisten [C++], Hinzufügen von Standardwerten mit Anwendungs-Assistenten"
  - "Symbolleisten [C++], Erstellen"
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Grundlegendes &#252;ber Symbolleisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die grundlegende MFC\-Implementierung, die Sie der Anwendung eine Standardsymbolleiste hinzufügen können, indem eine Option im Anwendungs\-Assistenten auswählt.  Folgende Themen werden behandelt:  
  
-   [Die Anwendungs\-Assistenten\-Symbolleistenoption](#_core_the_appwizard_toolbar_option)  
  
-   [Die Symbolleiste im Code](#_core_the_toolbar_in_code)  
  
-   [Bearbeiten der Symbolleistenressource](#_core_editing_the_toolbar_resource)  
  
-   [Mehrere Symbolleisten](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a> Die Anwendungs\-Assistenten\-Symbolleisten\-Option  
 Um eine einzelne Symbolleiste mit Standardschaltflächen abzurufen, wählen Sie die Standardandockensymbolleistenoption auf der Seite aus, die Benutzeroberflächen\-Funktionen angezeigt.  Dies fügt das Code der Anwendung hinzu:  
  
-   Erstellt das Symbolleistenobjekt.  
  
-   Verwaltet die Symbolleiste, einschließlich der Möglichkeit andocken oder frei verschieben zu.  
  
##  <a name="_core_the_toolbar_in_code"></a> Die Symbolleiste im Code  
 Die Symbolleiste [CToolBar](../mfc/reference/ctoolbar-class.md) ist ein Objekt, das als Datenmember von **CMainFrame**\-Klasse der Anwendung deklariert ist.  Das bedeutet, dass das Symbolleistenobjekt im Hauptrahmenfensterobjekt eingebettet.  Dies bedeutet, dass MFC die Symbolleiste erstellt, wenn es das Rahmenfenster und die Symbolleiste zerstört, wenn es das Rahmenfenster zerstört.  Die folgende Auszug Klassendeklaration, für eine Multiple Document Interface \(MDI\)\- Anwendung, werden Datenmember für eingebettete Symbolleiste und einer eingebetteten Statusleiste an.  Sie wird auch die Überschreibung der `OnCreate`\-Memberfunktion an.  
  
 [!CODE [NVC_MFCListView#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#6)]  
  
 Symbolleistenerstellung tritt in **CMainFrame::OnCreate** auf.  MFC ruft [OnCreate](../Topic/CWnd::OnCreate.md) auf, nachdem es das Fenster für denjenigen Frame erstellt jedoch hat, bevor sie sichtbar wird.  Der `OnCreate`, den der Anwendungs\-Assistent generiert, führt die folgenden Symbolleistenaufgaben:  
  
1.  Ruft die `CToolBar`[Erstellen](../Topic/CToolBar::Create.md)\-Memberfunktion des Objekts auf, um das zugrunde liegende Objekt [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) zu erstellen.  
  
2.  Ruft [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) auf, um die Symbolleistenressourceninformationen zu laden.  
  
3.  Aufrufe funktioniert, um das Andocken, das unverankert und die QuickInfo zu aktivieren.  Ausführliche Informationen über diese Aufrufe, finden Sie im Artikel [Andocken und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md).  
  
> [!NOTE]
>  Das allgemeine Beispiel [DOCKTOOL](../top/visual-cpp-samples.md) MFC enthält Darstellungen der alten und neuen MFC\-Symbolleisten ein.  Die Symbolleisten, die **COldToolbar** verwenden, benötigen Aufrufe in Schritt 2 auf `LoadBitmap` \(und nicht `LoadToolBar`\) und `SetButtons`.  Die Symbolleisten erfordern neuen Aufrufe von `LoadToolBar`.  
  
 Das Andocken, das unverankert und die QuickInfoaufrufe sind optional.  Sie können diese Zeilen von `OnCreate` entfernen, falls gewünscht.  Das Ergebnis ist eine Symbolleiste, die festgelegt, kann weiterhin auf frei verschieben oder redock und kann, QuickInfo anzuzeigen.  
  
##  <a name="_core_editing_the_toolbar_resource"></a> Bearbeiten der Symbolleisten\-Ressource  
 Die Standardsymbolleiste, die Sie mit dem Anwendungs\-Assistenten abrufen, ist auf Grundlage einer benutzerdefinierten Ressource **RT\_TOOLBAR**, eingeführt in MFC 4.0.  Sie können diese Ressource mit [Symbolleisten\-Editor](../mfc/toolbar-editor.md) bearbeiten.  Der Editor können Sie einfache Schaltflächen hinzufügen, löschen und neu anordnen.  Er enthält einen grafischen Editor für die Schaltflächen, der dem allgemeinen Grafikeditor in Visual C\+\+ sehr ähnelt.  Wenn Sie Symbolleisten in früheren Versionen von Visual C\+\+ bearbeitet haben, suchen Sie die Aufgabe jetzt, die einfacher ist.  
  
 Um eine Symbolleisten\-Schaltfläche an einen Befehl herzustellen, geben Sie der Schaltfläche eine Befehls\-ID, wie `ID_MYCOMMAND`.  Geben Sie der Befehls\-ID in der Eigenschaftenseite der Schaltfläche im Symbolleisten\-Editor angezeigt.  Erstellen Sie dann eine Handlerfunktion für den Befehl \(weitere Informationen finden Sie unter [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md) \).  
  
 Neue [CToolBar](../mfc/reference/ctoolbar-class.md)\-Memberfunktionsarbeit mit der **RT\_TOOLBAR** Ressource.  [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) wird jetzt mit [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) statt, um die Bitmap der Symbolleistenschaltflächenbilder zu laden und die [SetButtons](../Topic/CToolBar::SetButtons.md), um die Schaltflächenformate festzulegen und Schaltflächen mit Bitmap\-Bildern herzustellen.  
  
 Details zum Verwenden des Symbolleisten\-Editors, finden Sie unter [Symbolleisten\-Editor](../mfc/toolbar-editor.md).  
  
##  <a name="_core_multiple_toolbars"></a> Mehrere Symbolleisten  
 Der Anwendungs\-Assistent bietet eine Standardsymbolleiste.  Wenn Sie mehr als eine Symbolleiste in der Anwendung benötigen, können Sie den Code für zusätzliche Symbolleisten auf Grundlage des vom Assistenten generierten Code für die Standardsymbolleiste modellieren.  
  
 Wenn Sie eine Symbolleiste als Ergebnis eines Befehls anzeigen möchten, benötigen Sie:  
  
-   Erstellen Sie eine neue mit dem Symbolleistenressource Symbolleisten\-Editor und laden Sie sie in `OnCreate` mit der Memberfunktion [LoadToolbar](../Topic/CToolBar::LoadToolBar.md).  
  
-   Betten Sie ein neues [CToolBar](../mfc/reference/ctoolbar-class.md)\-Objekt in der Hauptrahmenfensterklasse ein.  
  
-   Führen Sie die entsprechenden Funktionsaufrufe in `OnCreate` andocken, oder, Symbolleiste zu Float, legen Sie die Stile, usw. fest.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [MFC\-Symbolleisten\-Implementierung \(Übersichtsinformationen über Symbolleisten\)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)  
  
-   [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)  
  
-   Die Klassen [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
-   [Arbeiten mit dem ToolBar\-Steuerelement](../mfc/working-with-the-toolbar-control.md)  
  
-   [Mit der alten Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
## Siehe auch  
 [Implementieren der MFC\-Symbolleiste](../mfc/mfc-toolbar-implementation.md)