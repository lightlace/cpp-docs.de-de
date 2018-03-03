---
title: "Klassen für | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- static display controls [MFC]
- control classes [MFC]
- buttons, MFC control classes
- controls [MFC], MFC control classes
- controls [MFC]
- list boxes [MFC], MFC control classes
- control classes [MFC], MFC
- text, controls for input [MFC]
- user input [MFC], MFC control classes
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 376fb3836d92a1fae348929a7faa49b44dfd866e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="control-classes"></a>Steuerelementklassen
Steuerelementklassen kapseln eine Vielzahl von Windows-Standardsteuerelemente von statischem Textsteuerelemente bis hin zu Tree-Steuerelementen. Darüber hinaus bietet MFC einige neue Steuerelemente, z. B. Schaltflächen, Bitmaps und Steuerelement Balken an.  
  
 Die Steuerelemente, deren Klassennamen enden "**STRG**" sind neu in Windows 95 und Windows NT, Version 3.51.  
  
## <a name="static-display-controls"></a>Statische Anzeigesteuerelemente  
 [CStatic](../mfc/reference/cstatic-class.md)  
 Eine statische Anzeige des Ablaufverfolgungsfensters. Statische Steuerelemente dienen zum bezeichnen, Feld oder andere Steuerelemente in einem Dialogfeld oder Fenster zu trennen. Sie können auch grafische Bilder statt Text oder ein Feld angezeigt.  
  
## <a name="text-controls"></a>Textsteuerelemente  
 [CEdit](../mfc/reference/cedit-class.md)  
 Ein bearbeitbares Textfeld Steuerelementfenster. Bearbeiten Sie Steuerelemente werden verwendet, um Text Benutzereingaben akzeptieren.  
  
 [CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)  
 Unterstützt ein Bearbeitungsfeld für die Bearbeitung von einer Adresse Internetprotokoll (IP).  
  
 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)  
 Ein Steuerelement, in dem der Benutzer eingeben kann, und Bearbeiten von Text. Im Gegensatz zu das Steuerelement in den gekapselt `CEdit`, ein rich-Edit-Steuerelement unterstützt Zeichen- und absatzformatierung und OLE-Objekte.  
  
## <a name="controls-that-represent-numbers"></a>Steuerelemente, die Zahlen darstellen.  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 Ein Steuerelement, das einen Schieberegler, der der Benutzer wechselt, wählen Sie einen Wert oder einen Satz von Werten enthält.  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 Ein Paar von Pfeilschaltflächen, kann der Benutzer klicken, um einen Wert inkrementiert oder dekrementiert.  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 Zeigt ein Rechteck, das von links nach rechts zum Anzeigen des Status eines Vorgangs allmählich gefüllt ist.  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 Ein Bildlaufleisten-Steuerelement-Fenster. Die Klasse stellt die Funktionalität einer Bildlaufleiste, für die Verwendung als ein Steuerelement in einem Dialogfeld oder Fenster, über die der Benutzer, eine Position innerhalb eines Bereichs angeben können bereit.  
  
## <a name="buttons"></a>Schaltflächen  
 [CButton](../mfc/reference/cbutton-class.md)  
 Eine Schaltfläche Steuerelementfensters. Die Klasse stellt eine programmgesteuerte Schnittstelle für Schaltflächen, Kontrollkästchen oder Optionsfeld in einem Dialogfeld oder Fenster bereit.  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 Eine Schaltfläche eine Bitmap, anstatt einen Beschriftungstext.  
  
## <a name="lists"></a>Listen  
 [CListBox](../mfc/reference/clistbox-class.md)  
 Ein Listenfeld Steuerelement-Fenster. Ein Listenfeld zeigt eine Liste von Elementen, die der Benutzer anzeigen und auswählen kann.  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Stellt die Funktionalität eines Windows-Listenfelds bereit; ermöglicht es dem Benutzer Listenfeldelemente, z. B. Dateinamen und Zeichenfolgenliterale, innerhalb des Listenfelds verschieben. Listenfelder mit dieser Funktion eignen sich für eine Liste der in anderen als alphabetischer Reihenfolge, z. B. Pfadnamen oder Dateien in einem Projekt einzuschließen.  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 Ein Kombinationsfeld Steuerelement-Fenster. Ein Kombinationsfeld besteht aus einem Bearbeitungssteuerelement sowie ein Listenfeld.  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 Erweitert das Kombinationsfeld-Steuerelement durch die Unterstützung für Bildlisten.  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 Zeigt eine Liste von Elementen mit Kontrollkästchen, die der Benutzer überprüfen oder zu löschen, neben jedem Element.  
  
 [CListCtrl](../mfc/reference/clistctrl-class.md)  
 Zeigt eine Auflistung von Elementen in der jedes ein Symbol und eine Bezeichnung, ähnlich wie in den rechten Bereich des Datei-Explorer besteht.  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 Zeigt eine hierarchische Liste der Symbole und Bezeichnungen auf ähnliche Weise im linken Bereich des Datei-Explorers auf bestimmte Weise angeordnet.  
  
## <a name="toolbars-and-status-bars"></a>Symbolleisten und Statusleisten  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Stellt die Funktionalität des allgemeinen Windows-Symbolleisten-Steuerelements bereit. Die meisten MFC Programme, von denen [CToolBar](../mfc/reference/ctoolbar-class.md) anstelle von dieser Klasse.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Ein horizontales Fenster unterteilt in der Regel Bereiche, in dem eine Anwendung Statusinformationen anzeigen kann. Die meisten MFC Programme, von denen [CStatusBar](../mfc/reference/cstatusbar-class.md) anstelle von dieser Klasse.  
  
## <a name="miscellaneous-controls"></a>Verschiedene Steuerelemente  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 Zeigt eine einfache Videoclips an.  
  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Ein kleines Popupfenster, in dem eine einzelne Textzeile, beschreibt den Zweck eines Tools in einer Anwendung angezeigt.  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 Unterstützt ein erweitertes Bearbeitungssteuerelement oder eine einfache Schnittstelle Kalendersteuerelement, die einem Benutzer ermöglicht, wählen ein bestimmtes Datum oder Uhrzeitwert.  
  
 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)  
 Zeigt an, Titeln oder Bezeichnungen für Spalten.  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 Unterstützt eine einfache Schnittstelle Kalendersteuerelement, die einem Benutzer ermöglicht, ein Datum auswählen.  
  
 [CTabCtrl](../mfc/reference/ctabctrl-class.md)  
 Ein Steuerelement mit Registerkarten, auf denen der Benutzer, analog zu den Trennblättern in einem Notizbuch klicken kann.  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 Ermöglicht dem Benutzer eine Tastenkombination erstellen, in der der Benutzer drücken kann, um eine Aktion schnell ausgeführt.  
  
 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)  
 Markierte Text gerendert und entsprechende Anwendungen startet, wenn der Benutzer den eingebetteten Link klickt.  
  
 [CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)  
 Stellt die Funktionalität des WebBrowser-ActiveX-Steuerelements in einem MFC-Fenster bereit.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Stellt die Funktionalität der Liste der Windows-Image bereit. Bilderliste für das werden mit List-Steuerelemente und Struktursteuerelemente verwendet. Sie können auch verwendet werden, zum Speichern und einen Satz von Bitmaps mit derselben Größe zu archivieren.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Die Basisklasse für alle Ansichten, die Windows-Steuerelementen zugeordnet. Die Ansichten, die basierend auf Steuerelemente werden nachfolgend beschrieben.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Bearbeitungssteuerelement für eine Sicht, die einen Windows-Standard enthält.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Eine Ansicht, die enthält ein Windows-Rich, edit-Steuerelement.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Eine Sicht, die eine Windows-Strukturelement-Steuerelement enthält.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Eine Sicht, die ein Windows-Strukturansicht-Steuerelement enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

