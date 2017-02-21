---
title: "Steuerelementklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schaltflächen, MFC-Steuerelementklassen"
  - "Steuerelementklassen"
  - "Steuerelementklassen, MFC"
  - "Steuerelemente [C++], MFC-Steuerelementklassen"
  - "Steuerelemente [MFC]"
  - "Listenfelder, MFC-Steuerelementklassen"
  - "Statische Anzeigesteuerelemente"
  - "Text, Steuerelemente für Eingabe"
  - "Benutzereingabe, MFC-Steuerelementklassen"
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Steuerelementklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Steuerelementklassen kapseln eine Vielzahl von standardmäßigen, die von Steuerelementen des statischen Text zu Tree\-Steuerelementen reichen.  Darüber hinaus bietet MFC einige neue Steuerelemente, u Schaltflächen mit Bitmaps und Steuerleisten.  
  
 Die Steuerelemente, deren Klassennamen in "**Strg**" enden, waren in Windows 95 und Windows NT 3,51 neu.  
  
## Statische Anzeigesteuerelemente  
 [CStatic](../mfc/reference/cstatic-class.md)  
 Ein STATICAnzeigenfenster.  Statische Steuerelemente werden verwendet, um andere Steuerelemente in einem Dialogfeld oder in einem Fenster zu bezeichnen, entfällt oder zu trennen.  Sie zeigen auch grafische Bilder anstatt Text oder ein Feld.  
  
## Textsteuerelemente  
 [CEdit](../mfc/reference/cedit-class.md)  
 Ein BearbeitbarTextsteuerfenster.  Bearbeitungssteuerelemente werden verwendet, um den Text zu akzeptieren, der vom Benutzer eingegeben werden.  
  
 [CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)  
 Unterstützt ein Eingabefeld für das Bearbeiten einer Internetprotokoll Adresse \(ip\)\-.  
  
 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)  
 Ein Steuerelement, in das der Benutzer Text eingeben und bearbeiten kann.  Anders als das Steuerelement, das in `CEdit` gekapselt wird, unterstützt ein Rich\-Edit\-Steuerelement Zeichen und Absatzformatierung und OLE\-Objekte.  
  
## Steuerelemente, die Zahlen darstellen  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 Ein Steuerelement, das einen Schieberegler enthält, den der Benutzer wechselt, um einen Wert oder einen Satz Werte auszuwählen.  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 Ein Paar auf Pfeilschaltflächen, die der Benutzer klicken kann, um einen Wert zu erhöhen oder zu vermindern.  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 Zeigt ein Rechteck, das allmählich von links nach rechts gefüllt wird, um den Fortschritt eines Vorgangs an.  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 Ein Bildlaufleisten\-Steuerelement\-Fenster.  Die Klasse stellt die Funktionalität einer Bildlaufleiste, die als Steuerelement in einem Dialogfeld oder in einem Fenster bereit, durch die der Benutzer eine Position innerhalb eines Bereichs festlegen kann.  
  
## Schaltflächen  
 [CButton](../mfc/reference/cbutton-class.md)  
 Ein Schaltflächen\-Steuerelement\-Fenster.  Die Klasse bietet eine programmgesteuerte Schnittstelle für eine Schaltfläche, ein Kontrollkästchen oder ein Optionsfeld aus einem Dialogfeld oder in einem Fenster.  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 Eine Schaltfläche mit einer Bitmap anstatt eine Textbeschriftung.  
  
## Listen  
 [CListBox](../mfc/reference/clistbox-class.md)  
 Ein Listenfeld\-Steuerelement\-Fenster.  Ein Listenfeld wird eine Liste von Elementen an, die der Benutzer anzeigen und auswählen kann.  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Stellt die Funktionalität eines Windows\-Listenfelds bereit; kann der Benutzer den Verschiebungslistenfeldelementen, wie Dateinamen und Zeichenfolgenliterale, innerhalb des Listenfelds.  Listenfelder mit dieser Funktion sind für eine Elementliste in einer Reihenfolge anders alphabetisches, wie Einschließungspfadnamen oder Dateien in einem Projekt sinnvoll.  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 Ein Kombinationsfeld\-Steuerelement\-Fenster.  Ein Kombinationsfeld besteht aus einem Bearbeitungssteuerelement sowie ein Listenfeld.  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 Erweitert das Kombinationsfeld\-Steuerelement durch die Unterstützung für Bildlisten.  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 Zeigt eine Liste von Elementen mit Kontrollkästchen, die der Benutzer überprüfen oder deaktivieren kann, neben jedem Element.  
  
 [CListCtrl](../mfc/reference/clistctrl-class.md)  
 Zeigt eine Auflistung von Elementen, jede an, die einem Symbol und einer Bezeichnung, besteht fast genauso den rechten Bereich des Datei\-Explorers.  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 Zeigt eine hierarchische Liste von Symbolen und von Bezeichnungen angeordnetem in ähnlicher Weise ähnlichem in den linken Bereich des Datei\-Explorers an.  
  
## Symbolleisten und Statusleisten  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Stellt die Funktionalität des allgemeinen Windows\-Symbolleisten\-Steuerelements bereit.  Die meisten Programme verwenden [CToolBar](../mfc/reference/ctoolbar-class.md) statt von dieser Klasse.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Ein horizontales Fenster, normalerweise unterteilt in Bereiche, in denen eine Anwendung Statusinformationen anzeigen kann.  Die meisten Programme verwenden [CStatusBar](../mfc/reference/cstatusbar-class.md) statt von dieser Klasse.  
  
## Verschiedene Steuerelemente  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 Zeigt einen einfachen Videoclip an.  
  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Ein kleines Popupfenster, das eine einzelne Textzeile den Zweck eines Tools in einer Anwendung beschreibt anzeigt.  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 Unterstützt entweder ein erweitertes Bearbeitungssteuerelement oder ein einfaches Kalenderschnittstellensteuerelement, das einem Benutzer ermöglicht, ein bestimmtes Datum auszuwählen oder Uhrzeitwert.  
  
 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)  
 Anzeigentitel oder \-Bezeichnungen für Spalten.  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 Unterstützt ein einfaches Kalenderschnittstellensteuerelement, das einem Benutzer ermöglicht, ein Datum auszuwählen.  
  
 [CTabCtrl](../mfc/reference/ctabctrl-class.md)  
 Ein Steuerelement mit den Registerkarten, die der Benutzer klicken kann, analog den Trennblättern in einem Ordner.  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 Ermöglicht es dem Benutzer, eine Abkürzungstastenkombination zu erstellen, die der Benutzer klicken kann, um eine Aktion schnell auszuführen.  
  
 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)  
 Rendert markierten Text und startet entsprechende Anwendungen, wenn der Benutzer auf den eingebetteten Link klickt.  
  
 [CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)  
 Stellt die Funktionalität des WebBrowser\-ActiveX\-Steuerelements in einem MFC\-Fenster bereit.  
  
## Verwandte Klassen  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Stellt die Funktionalität der Windows\-Image\-Liste bereit.  Grafiklisten werden mit Strukturansicht\-Steuerelementen Listen\-Steuerelementen und verwendet.  Sie können auch verwendet werden, um einen Satz gleich\-skalierte Bitmaps zu speichern und zu archivieren.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Alle Basisklasse für zeigt zugeordnet Windows\-Steuerelementen an.  Die Ansichten auf Basis von Steuerelementen sind unten beschrieben.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Eine Ansicht, die ein Windows\-Standardbearbeitungssteuerelement enthält.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Eine Ansicht, die ein Windows\-Rich\-Edit\-Steuerelement enthält.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Eine Ansicht, die ein Windows\-Listensteuerelement enthält.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Eine Ansicht, die ein Windows\-Strukturansicht\-Steuerelement enthält.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)