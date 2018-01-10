---
title: AFX-Meldungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
dev_langs: C++
helpviewer_keywords: AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41f300f285fb4eaf1a6154a21cbbabc0253fc730
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="afx-messages"></a>AFX-Meldungen
Diese Nachrichten werden in MFC verwendet.  
  
## <a name="messages"></a>Mitteilungen  
 Die folgende Tabelle enthält die Nachrichten, die in der MFC-Bibliothek verwendet werden:  
  
||||||  
|-|-|-|-|-|  
|Meldung|Beschreibung|[in] `wParam`|`lParam`(Alle Parameter sind [in], sofern nicht anders angegeben.)|Rückgabewert|  
|AFX_WM_ACCGETOBJECT|Nicht verwendet.|Nicht verwendet.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ACCGETSTATE|Für Accessibility-Unterstützung verwendet. Senden Sie diese Nachricht an `CMFCPopupMenu` oder `CMFCRibbonPanelMenu` beim Abrufen des Status des aktuellen Elements.|Der Index des Elements, die eine Menüschaltfläche oder Trennzeichen sein könnte.|Nicht verwendet.|Der Status des Elements. Es ist 1, wenn der Index ungültig ist, ist 0, wenn die Menüschaltfläche keine besonderen Attribute hat. Andernfalls ist es eine Kombination der folgenden Flags:<br /><br /> TBBS_DISABLED: "Item" ist deaktiviert.<br /><br /> TBBS_CHECKED – Element aktiviert ist<br /><br /> TBBS_BUTTON – das Element ist eine standardmäßige pushbutton<br /><br /> TBBS_PRESSED – gedrückt wird<br /><br /> TBBS_INDETERMINATE – nicht definierten Zustand<br /><br /> TBBS_SEPARATOR - anstelle einer Menüschaltfläche, dieses Element Forms Trennung zwischen anderen Menüelementen|  
|AFX_WM_CHANGE_ACTIVE_TAB|Das Framework sendet diese Nachricht an das Steuerelement in der Größe veränderbaren Steuerelement. Diese Meldung für den Empfang von Benachrichtigungen verarbeiten `CMFCTabCtrl` Objekte, wenn ein Benutzer mit eine aktive Registerkarte ändert.|Der Index einer Registerkarte.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_CHANGE_CURRENT_FOLDER|Das Framework sendet diese Nachricht an das übergeordnete Element des `CMFCShellListCtrl` Wenn der Benutzer den aktuellen Ordner geändert hat.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_CHANGEVISUALMANAGER|Das Framework sendet diese Nachricht an alle Rahmenfenster, wenn der Benutzer den aktuellen Visual Manager ändert. Reaktion auf diese Meldung ein Rahmenfensters seine Region berechnet und passt andere Parameter nach Bedarf. Wenn Sie dieses Ereignis benachrichtigt werden müssen, können Sie die AFX_WM_CHANGEVISUALMANAGER-Nachricht in der Anwendung verarbeiten. Rufen Sie die Basisklassenhandler (`OnChangeVisualManager`), stellen Sie sicher, die das Framework intern mit der Verarbeitung dieses Ereignisses findet.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_CHANGING_ACTIVE_TAB|An das übergeordnete Element der gesendet `CMFCTabCtrl` Objekt.  Diese Meldung verarbeiten, wenn Sie Benachrichtigungen von erhalten möchten `CMFCTabCtrl` Objekte, wenn ein Benutzer eine Registerkarte zurücksetzt.|Der Index der Registerkarte, die aktiviert wird.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_CHECKEMPTYMINIFRAME|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_CREATETOOLBAR|Gesendet vom `CMFCToolBarsListPropertyPage` Wenn ein Benutzer eine neue Symbolleiste während Anpassungsvorgangs erstellt. Sie können diese Meldung beim Instanziieren eines benutzerdefinierten CMFCToolBar abgeleitetes Objekts verarbeiten. Wenn Sie diese Meldung verarbeiten und erstellen Sie eine eigene Symbolleiste, lassen Sie den Aufruf der Standardhandler.|Nicht verwendet.|Ein Zeiger auf eine Zeichenfolge, die den Namen der Symbolleiste enthält.|Ein Zeiger auf die neu erstellte-Symbolleiste. NULL gibt an, dass die Symbolleiste Erstellung abgebrochen wurde.|  
|AFX_WM_CUSTOMIZEHELP|An das Hauptrahmenfenster gesendet, aus dem Eigenschaftenblatt Anpassung `CMFCToolbarCustomize Dialog` Wenn der Benutzer drückt die **Hilfe** Schaltfläche oder die Taste F1 drücken.|Gibt die aktive Seite des Eigenschaftsblatt Anpassung an.|Ein Zeiger auf eine `CMFCToolbarCustomize Dialog` Objekt.|0 (null).|  
|AFX_WM_CUSTOMIZETOOLBAR|Die `CMFCToolbarCustomize Dialog` sendet diese Nachricht an dem übergeordneten Frame zu benachrichtigen, dass der Benutzer eine neue Symbolleiste erstellt.|`TRUE`Beginn der Anpassung `FALSE` Wenn Anpassung abgeschlossen ist.|Nicht verwendet.|0 (null).|  
|AFX_WM_DELETETOOLBAR|An das Hauptrahmenfenster gesendet, wenn der Benutzer ist dabei, eine Symbolleiste in den Anpassungsmodus zu löschen.<br /><br /> Verarbeiten Sie diese Meldung zusätzliche Aktionen ausführen, wenn ein Benutzer eine Symbolleiste im Anpassungsmodus löscht. Sie sollten auch den Standardhandler aufrufen (`OnToolbarDelete`), die die Symbolleiste gelöscht. Der Standardhandler gibt einen Wert, der angibt, ob es möglich ist, löschen Sie die Symbolleiste zurück.|Nicht verwendet.|Zeiger auf eine `CMFCToolBar` zu löschendes Objekt.|Der Wert ist ungleich NULL, wenn eine Symbolleiste kann nicht gelöscht werden; andernfalls 0.|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`sendet diese Nachricht an das Hauptrahmenfenster die Farben des Dokuments abgerufen.|Nicht verwendet.|[in, out] Zeiger auf eine `CList<COLORREF, COLORREF>` Objekt.|0 (null).|  
|AFX_WM_GETDRAGBOUNDS|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|An das Hauptrahmenfenster gesendet, wenn ein Benutzer ein Element "Menüband-Liste" hervorhebt.|Index des markierten Elements|Ein Zeiger auf`CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|Zu einem übergeordneten Element der gesendet `CMFCShellListCtrl` oder `CMFCShellTreeCtrl` steuert, wenn ein Benutzer beendet einen Shellbefehl ausführen.|Die ID des Befehls, die der Benutzer ausgeführt.|Nicht verwendet.|Wenn die Anwendung diese Nachricht verarbeitet, sollte er 0 (null) zurück.|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Das Framework sendet diese Nachricht mit dem Menüband der übergeordneten, bevor das Menü das Popupmenü angezeigt. Sie können diese Meldung verarbeiten und Popupmenüs jederzeit ändern.|Nicht verwendet.|Ein Zeiger auf`CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX_WM_ON_CANCELTABMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Das Framework sendet diese Nachricht an den Hauptframe, wenn der Benutzer das aktive Steuerelement im Menüband Kategorie ändert.|Nicht verwendet.|Ein Zeiger auf die `CMFCRibbonBar` , deren Kategorie wurde geändert.|Nicht verwendet.|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|Das Framework sendet diese Nachricht an den Besitzer des zu benachrichtigen `CMFCDesktopAlertWnd` , dass das Fenster geschlossen werden.|Nicht verwendet.|Ein Zeiger auf `CMFCDesktopAlertWnd` Objekt.|Nicht verwendet.|  
|AFX_WM_ON_DRAGCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ON_GET_TAB_TOOLTIP|An das Hauptrahmenfenster gesendet, wenn eine "Verwaltung" ist zu eine QuickInfo für eine Registerkarte angezeigt, wenn QuickInfos aktiviert sind.|Nicht verwendet.|Ein Zeiger auf eine `CMFCTabToolTipInfo` Struktur.|Nicht verwendet.|  
|AFX_WM_ON_HSCROLL|An das Steuerelement in der Größe veränderbaren Steuerelement gesendet wird. Diese Meldung für den Empfang von Benachrichtigungen verarbeiten `CMFCTabCtrl` tritt ein Scroll-Ereignis in der horizontalen Bildlaufleiste im Registerkartenformat Widget-Objekten.|Das niederwertige Wort gibt an, dass ein Scroll Bar-Wert, der den Benutzer angibt Anforderung Bildlauf des.  Weitere Informationen finden Sie in der Tabelle weiter unten in diesem Thema.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_ON_MOVE_TAB|An das übergeordnete Element von einem Fenster im Registerkartenformat gesendet, wenn ein Benutzer auf eine neue Position eine Registerkarte zieht.|Der nullbasierte Index der Registerkarte in seiner ursprünglichen Position.|[out] Der nullbasierte Index der Registerkarte in seiner neuen Position.|0 (null).|  
|AFX_WM_ON_MOVETABCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ON_MOVETOTABGROUP|An das Hauptrahmenfenster gesendet, wenn ein Benutzer ein untergeordnetes MDI-Fenster von einer im Registerkartenformat Gruppe zu einem anderen bewegt wird.|Ein Handle für Fenster im Registerkartenformat (`CMFCTabCtrl`) aus dem das untergeordnete MDI-Fenster entfernt wurde.|[out] Ein Handle für Fenster im Registerkartenformat (`CMFCTabCtrl`), die die untergeordneten MDI-Fensters eingefügt wurde.|Ignoriert.|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|Zu einem übergeordneten Element der gesendet `CDockablePane` Wenn der Benutzer klickt auf die **schließen** Schaltfläche für die Beschriftung der Steuerleiste.|Nicht verwendet.|Ein Zeiger auf einen andockbaren Bereich, auf dem der Benutzer geklickt hat, die **schließen** Schaltfläche.|`TRUE`Wenn ein Bereich kann nicht geschlossen werden; andernfalls "false".|  
|AFX_WM_ON_RENAME_TAB|Das dem übergeordneten Fenster im Registerkartenformat gesendet, nachdem der Benutzer eine Registerkarte "bearbeitbare" umbenannt.|Der nullbasierte Index der Registerkarte für die umbenannt werden soll.|[out] Ein Zeiger auf eine Zeichenfolge, die den Namen der neuen Registerkarte enthält.|Wert ungleich NULL, wenn die Anwendung diese Nachricht verarbeitet; Das Framework wird unterdrückt den Aufruf von `CMFCBaseTabCtrl::SetTabLabel`.  Wenn 0 (null), klicken Sie dann zurückgegeben wird `CMFCBaseTabCtrl::SetTabLabel` vom Framework aufgerufen wird.|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|An den übergeordneten Frame gesendet, wenn Benutzer die Anpassung startet. Verarbeiten Sie diese Meldung, wenn Sie eine eigene Anpassungsdialogfelds anzeigen möchten.|Nicht verwendet.|Ein Zeiger auf das Steuerelement im Menüband angepasst werden.|Wert ungleich NULL, wenn die Anwendung diese Nachricht verarbeitet und ein eigenes Dialogfeld Anpassung angezeigt. Wenn die Anwendung auf 0 (null) zurückgibt, wird das Framework integrierten Anpassungsdialogfelds angezeigt.|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_POSTSETPREVIEWFRAME|Der Hauptframe benachrichtigen, dass der Benutzer die Seitenansicht geändert gesendet|`TRUE`Gibt an, dass die Seitenansicht festgelegt ist. `FALSE`Gibt an, dass diese Seitenansicht deaktiviert wurde.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_PROPERTY_CHANGED|An den Besitzer des Rastersteuerelements Eigenschaft gesendet (`CMFCPropertyGridCtrl`) Wenn der Benutzer den Wert der ausgewählten Eigenschaft ändert.|Die Steuerelement-ID der Eigenschaftenliste.|Ein Zeiger auf die Eigenschaft (`CMFCPropertyGridProperty`), die sich geändert.|Nicht verwendet.|  
|AFX_WM_RESETCONTEXTMENU|An das Hauptrahmenfenster gesendet, wenn der Benutzer im Kontextmenü den Befehl während der Anpassung zurückgesetzt.|Die Ressourcen-ID des Kontextmenüs.|Ein Zeiger auf das aktuelle Kontextmenü `CMFCPopupMenu`.|Nicht verwendet.|  
|AFX_WM_RESETKEYBOARD|Das Framework sendet diese Nachricht an das Hauptrahmenfenster, wenn der Benutzer alle Zugriffstasten während der Anpassung zurückgesetzt.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETMENU|Das Framework sendet diese Nachricht an den Menü-Besitzer (Rahmenfenster) Wenn der Benutzer ein Frame Anwendungsmenü während der Anpassung zurückgesetzt|Der Menü-Ressourcen-ID.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETPROMPT|Das Framework sendet diese Nachricht, wenn der Benutzer setzt eine Symbolleiste, über die Symbolleiste im Dialogfeld Anpassen. Der Standardhandler zeigt ein Meldungsfeld mit der Frage, ob der Benutzer möchte die Symbolleiste zurücksetzen.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETTOOLBAR|Ein `CMFCToolBar` Objekt sendet diese Nachricht, wenn eine Symbolleiste, also in seinen ursprünglichen Zustand von den Ressourcen geladen wiederhergestellt wird. Diese Meldung, Symbolleistenschaltflächen Wert erneut einzufügen, deren Klassen abgeleitet werden, verarbeiten `CMFCToolbarButton`. Weitere Informationen finden Sie unter `CMFCToolbarComboBoxButton`.|Die Ressourcen-ID, einer Symbolleiste, deren Zustand wiederhergestellt wurde.|Nicht verwendet.|0 (null).|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`Objekt sendet diese Nachricht an den Besitzer, klickt der Benutzer eine reguläre Menüschaltfläche. Diese Meldung jedes Mal, mit denen Sie verarbeiten `CMFCToolbarMenuButton` ein Popupmenü angezeigt, wenn der Benutzer eine Schaltfläche klickt.|Die Befehls-ID einer Schaltfläche, die die Nachricht gesendet werden soll.|Die Bildschirmkoordinaten des Cursors. Das niederwertige Wort gibt die X-Koordinate. Das höherwertige Wort gibt die y-Koordinate.|Nicht verwendet.|  
|AFX_WM_TOOLBARMENU|An das Hauptrahmenfenster gesendet, wenn der Benutzer den rechte Schaltfläche der Maus loslässt, während der Mauszeiger in den Client- oder nicht-Clientbereich eines Bereichs befindet.|Nicht verwendet.|Die Bildschirmkoordinaten des Mauszeigers. Das niederwertige Wort gibt die X-Koordinate. Das höherwertige Wort gibt die y-Koordinate.|NULL, wenn die Anwendung diese Nachricht verarbeitet; andernfalls, ungleich NULL.|  
|AFX_WM_UPDATETOOLTIPS|Für alle QuickInfo-Besitzer gesendet, um anzugeben, dass die QuickInfo-Steuerelemente neu erstellt werden soll.|Der Typ des Steuerelements, das diese Nachricht verarbeiten soll. Finden Sie in der Tabelle weiter unten in diesem Thema eine Liste der möglichen Werte.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`sendet diese Nachricht an den übergeordneten Frame, klickt der Benutzer die **Hilfe** klicken, oder wechselt in den Hilfemodus durch Klicken auf die **Hilfe** Titelleistenschaltfläche oder die Taste F1 drücken.|Nicht verwendet.|Ein Zeiger auf die Instanz von `CMFCWindowsManagerDialog`.|Nicht verwendet.|  
  
 Die folgende Tabelle zeigt die Werte für das niedrige Wort von der `lParam` Parameters der Methode AFX_WM_HSCROLL:  
  
|||  
|-|-|  
|Wert|Bedeutung|  
|SB_ENDSCROLL|Der Benutzer beendet den Bildlauf.|  
|SB_LEFT|Der Benutzer einen Bildlauf auf der linken oberen Ecke.|  
|SB_RIGHT|Der Benutzer einen Bildlauf nach rechts unten.|  
|SB_LINELEFT|Der Benutzer einen Bildlauf nach links, um eine Einheit.|  
|SB_LINERIGHT|Der Benutzer einen Bildlauf nach rechts eine Einheit.|  
|SB_PAGELEFT|Der Benutzer einen Bildlauf nach links durch die Breite des Fensters.|  
|SB_PAGERIGHT|Der Benutzer führt einen Bildlauf rechts von der Breite des Fensters.|  
|SB_THUMBPOSITION|Der Benutzer hat das Bildlauffeld (Ziehpunkt) gezogen und Loslassen der Maustaste. Das höherwertige Wort gibt die Position des Bildlauffelds am Ende des Ziehvorgangs an.|  
|SB_THUMBTRACK|Der Benutzer ist die bildlaufbox. Die AFX_WM_ON_HSCROLL-Nachricht wird mit diesem Wert wiederholt gesendet, bis der Benutzer die Maustaste loslässt. Das höherwertige Wort gibt an, die Position, an der das Bildlauffeld gezogen wurde.|  
  
> [!NOTE]
>  Das höherwertige Wort von der `lParam` Parameter gibt die aktuelle Position des Bildlauffelds an, wenn das niederwertige Wort SB_THUMBPOSITION oder SB_THUMBTRACK ist; andernfalls wird dieses Wort nicht verwendet.  
  
 Die folgende Tabelle enthält die Flagwerte für die `lParam` -Parameter der Nachricht AFX_WM_UPDATETOOLTIPS:  
  
|||  
|-|-|  
|Flag|Wert|  
|AFX_TOOLTIP_TYPE_DEFAULT|0 x 0001|  
|AFX_TOOLTIP_TYPE_TOOLBAR|0 x 0002|  
|AFX_TOOLTIP_TYPE_TAB|0 x 0004|  
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|  
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|  
|AFX_TOOLTIP_TYPE_EDIT|0x0020|  
|AFX_TOOLTIP_TYPE_BUTTON|0 x 0040|  
|AFX_TOOLTIP_TYPE_TOOLBOX|0 x 0080|  
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
