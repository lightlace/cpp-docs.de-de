---
title: Steuerelementklassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.control
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
ms.openlocfilehash: 79a71a4660cd49f85726d730c9fad0b2f10f83bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338167"
---
# <a name="control-classes"></a>Steuerelementklassen

Benutzersteuerelement-Klassen kapseln eine Vielzahl von standardmäßigen Windows-Steuerelemente, die von statischem Textsteuerelemente bis hin zu Struktur-Steuerelemente. Darüber hinaus bietet MFC einige neue Steuerelemente wie Schaltflächen, Bitmaps und Steuerelement Balken.

Die Steuerelemente, deren Klassennamen enden "**STRG**" im Windows 95 und Windows NT, Version 3.51 wurden.

## <a name="static-display-controls"></a>Statische Anzeigesteuerelemente

[CStatic](../mfc/reference/cstatic-class.md)<br/>
Ein statischer-Anzeige-Fenster. Statische Steuerelemente werden verwendet, um Bezeichnung, Feld oder andere Steuerelemente in einem Dialogfeld oder Fenster zu trennen. Sie können auch grafische Bilder anstelle von Text oder ein Feld angezeigt.

## <a name="text-controls"></a>Textsteuerelemente

[CEdit](../mfc/reference/cedit-class.md)<br/>
Ein Fenster bearbeitbaren Text-Steuerelement. Bearbeiten Sie Steuerelemente werden verwendet, um die Texteingabe des Benutzers zu übernehmen.

[CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)<br/>
Unterstützt ein Eingabefeld für die Bearbeitung von einer Adresse (Internetprotokoll).

[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)<br/>
Ein Steuerelement, in dem der Benutzer kann Text eingeben und bearbeiten. Im Gegensatz zu das Steuerelement in gekapselt `CEdit`, ein rich-Edit-Steuerelement unterstützt Zeichen- und absatzformatierung und OLE-Objekte.

## <a name="controls-that-represent-numbers"></a>Steuerelemente, die Zahlen darstellen.

[CSliderCtrl](../mfc/reference/csliderctrl-class.md)<br/>
Ein Steuerelement, das einen Schieberegler, der der Benutzer bewegt, wählen Sie einen Wert oder einen Satz von Werten enthält.

[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)<br/>
Ein Paar von Pfeilschaltflächen, kann der Benutzer klicken, um einen Wert inkrementiert oder dekrementiert wird.

[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)<br/>
Zeigt ein Rechteck, das allmählich von links nach rechts, um den Status eines Vorgangs angeben gefüllt wird.

[CScrollBar](../mfc/reference/cscrollbar-class.md)<br/>
Ein Fenster des Schiebeleisten-Steuerelement. Die Klasse bietet die Funktionalität eine Bildlaufleiste angezeigt, für die Verwendung als ein Steuerelement in einem Dialogfeld oder Fenster über die der Benutzer eine Position innerhalb eines Bereichs angeben kann.

## <a name="buttons"></a>Schaltflächen

[CButton](../mfc/reference/cbutton-class.md)<br/>
Eine Schaltfläche Steuerelement-Fenster. Die Klasse stellt eine programmgesteuerte Schnittstelle für einen Schaltflächen, Kontrollkästchen oder Optionsfeld "in einem Dialogfeld oder Fenster an.

[CBitmapButton](../mfc/reference/cbitmapbutton-class.md)<br/>
Schaltfläche mit einer Bitmap anstatt einen Beschriftungstext.

## <a name="lists"></a>Listen

[CListBox](../mfc/reference/clistbox-class.md)<br/>
Ein Listenfeld-Steuerelement-Fenster. Ein Listenfeld zeigt eine Liste von Elementen, die der Benutzer anzeigen und auswählen kann.

[CDragListBox](../mfc/reference/cdraglistbox-class.md)<br/>
Stellt die Funktionalität eines Windows-Listenfelds bereit; ermöglicht dem Benutzer Listenfeldelemente, z. B. den Dateinamen und Zeichenfolgenliterale, innerhalb des Listenfelds verschieben. Listenfelder, die mit dieser Funktion sind nützlich für eine Elementliste in anderen als alphabetischer Reihenfolge, z. B. Pfadnamen oder Dateien in einem Projekt einzuschließen.

[CComboBox](../mfc/reference/ccombobox-class.md)<br/>
Ein Kombinationsfeld-Steuerelement-Fenster. Ein Kombinationsfeld besteht aus einem Bearbeitungssteuerelement sowie ein Listenfeld.

[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)<br/>
Erweitert das Kombinationsfeld-Steuerelement durch die Unterstützung für Bildlisten.

[CCheckListBox](../mfc/reference/cchecklistbox-class.md)<br/>
Zeigt eine Liste von Elementen mit Kontrollkästchen, die der Benutzer aktivieren oder deaktivieren, neben jedem Element.

[CListCtrl](../mfc/reference/clistctrl-class.md)<br/>
Zeigt eine Auflistung von Elementen, jedes ein Symbol und eine Bezeichnung, ähnlich wie in den rechten Bereich des Datei-Explorers aus.

[CTreeCtrl](../mfc/reference/ctreectrl-class.md)<br/>
Zeigt eine hierarchische Liste der Symbole und Bezeichnungen, die auf ähnliche Weise im linken Bereich des Datei-Explorers auf bestimmte Weise angeordnet.

## <a name="toolbars-and-status-bars"></a>Symbolleisten und Statusleisten

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Stellt die Funktionalität des allgemeinen Windows-Symbolleisten-Steuerelements bereit. Die meisten MFC Programme [CToolBar](../mfc/reference/ctoolbar-class.md) anstelle von dieser Klasse.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
Ein horizontaler Fenster unterteilt in der Regel, die Bereiche, in denen eine Anwendung Statusinformationen anzeigen kann. Die meisten MFC Programme [CStatusBar](../mfc/reference/cstatusbar-class.md) anstelle von dieser Klasse.

## <a name="miscellaneous-controls"></a>Verschiedene Steuerelemente

[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)<br/>
Zeigt eine einfache Videoclips an.

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
Ein kleines Popupfenster, in dem eine einzelne Textzeile, beschreibt den Zweck eines Tools in einer Anwendung angezeigt.

[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)<br/>
Unterstützt ein erweitertes Bearbeitungssteuerelement oder eine einfache Schnittstelle Kalendersteuerelement, die einem Benutzer ermöglicht, wählen Sie ein bestimmtes Datum oder Uhrzeit-Wert.

[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)<br/>
Zeigt an, Titeln oder Bezeichnungen für Spalten.

[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)<br/>
Unterstützt eine einfache Schnittstelle Kalendersteuerelement, die ein Benutzer ein Datum auswählen kann.

[CTabCtrl](../mfc/reference/ctabctrl-class.md)<br/>
Ein Steuerelement mit Registerkarten, die auf denen der Benutzer, vergleichbar mit den Trennblättern in einem Notizbuch klicken kann.

[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)<br/>
Ermöglicht dem Benutzer eine Tastenkombination "Hot", zu erstellen, die der Benutzer drücken kann, um eine Aktion schnell ausgeführt.

[CLinkCtrl](../mfc/reference/clinkctrl-class.md)<br/>
Markierte Text gerendert, und entsprechende Anwendungen startet, wenn der Benutzer den eingebetteten Link klickt.

[CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)<br/>
Stellt die Funktionalität des WebBrowser-ActiveX-Steuerelements in einem MFC-Fenster bereit.

## <a name="related-classes"></a>Verwandte Klassen

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Stellt die Funktionen der Liste der Windows-Bilder. Bilderliste für das werden mit Listensteuerelementen und Struktursteuerelementen verwendet. Sie können auch zum Speichern und archivieren eine Reihe von Bitmaps mit derselben Größe verwendet werden.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Die Basisklasse für alle Ansichten, die Windows-Steuerelementen zugeordnet. Die Ansichten, die basierend auf werden nachfolgend beschrieben.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Bearbeitungssteuerelement für eine Sicht, die einen Windows-Standard enthält.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Eine Ansicht, die enthält eine umfassende Windows-Bearbeitungssteuerelements.

[CListView](../mfc/reference/clistview-class.md)<br/>
Eine Sicht, die ein Windows-Steuerelement enthält.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Eine Sicht, die ein Windows-Strukturansicht-Steuerelement enthält.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
