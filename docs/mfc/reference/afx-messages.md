---
title: AFX-Meldungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e60b5be200112f8a6a4e1ce7f5627d5d958e329e
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338768"
---
# <a name="afx-messages"></a>AFX-Meldungen
Diese Nachrichten werden in MFC verwendet.  
  
## <a name="messages"></a>Mitteilungen  
 Die folgende Tabelle enthält die Nachrichten, die in der MFC-Bibliothek verwendet werden:  
  
||||||  
|-|-|-|-|-|  
|Meldung|Beschreibung|[in] *wParam-Parameter*|*lParam* (alle Parameter sind [in], sofern nicht anders angegeben.)|Rückgabewert|  
|AFX_WM_ACCGETOBJECT|Nicht verwendet.|Nicht verwendet.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ACCGETSTATE|Für die Unterstützung für Barrierefreiheit verwendet. Senden Sie diese an `CMFCPopupMenu` oder `CMFCRibbonPanelMenu` beim Abrufen des Status des aktuellen Elements.|Der Index des Elements, das eine Schaltfläche oder ein Trennzeichen werden konnte.|Nicht verwendet.|Der Zustand des Elements. Es ist 1, wenn der Index ungültig ist, ist 0, wenn Sie die Menüschaltfläche keine besonderen Attribute hat. Andernfalls ist es eine Kombination der folgenden Flags:<br /><br /> TBBS_DISABLED: Element ist deaktiviert.<br /><br /> TBBS_CHECKED: "Element" ist aktiviert.<br /><br /> TBBS_BUTTON – das Element ist eine standardmäßige pushbutton<br /><br /> TBBS_PRESSED: Schaltfläche ist gedrückt.<br /><br /> TBBS_INDETERMINATE: nicht definierten Zustand<br /><br /> TBBS_SEPARATOR - anstelle einer Menüschaltfläche, bildet diese Element, eine Trennung zwischen anderen Menüelemente|  
|AFX_WM_CHANGE_ACTIVE_TAB|Das Framework sendet diese Nachricht an das Steuerelement in der Größe veränderbaren Steuerelement. Diese Meldung zum Empfangen von Benachrichtigungen von verarbeiten `CMFCTabCtrl` Objekte, wenn ein Benutzer eine aktive Registerkarte ändert.|Der Index einer Registerkarte.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_CHANGE_CURRENT_FOLDER|Das Framework sendet diese Nachricht an das übergeordnete Element des `CMFCShellListCtrl` Wenn sich der Benutzer den aktuellen Ordner geändert hat.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_CHANGEVISUALMANAGER|Das Framework sendet diese Nachricht an alle Rahmenfenster, wenn der Benutzer den aktuellen Visual Manager ändert. Als Reaktion auf diese Nachricht ein Rahmenfenster seine Region berechnet und passt andere Parameter je nach Bedarf. Wenn Sie zu diesem Ereignis benachrichtigt werden möchten, können Sie die Nachricht AFX_WM_CHANGEVISUALMANAGER in Ihrer Anwendung verarbeiten. Sie müssen den Handler für die Basisklasse aufrufen (`OnChangeVisualManager`) um sicherzustellen, dass das Framework intern ist die Verarbeitung dieses Ereignisses findet.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_CHANGING_ACTIVE_TAB|Gesendet, um das übergeordnete Element des `CMFCTabCtrl` Objekt.  Diese Meldung verarbeiten, wenn Sie Benachrichtigungen erhalten möchten `CMFCTabCtrl` Objekte, wenn ein Benutzer eine Registerkarte zurücksetzt.|Der Index der Registerkarte, die aktiviert wird.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_CHECKEMPTYMINIFRAME|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_CREATETOOLBAR|Gesendet von `CMFCToolBarsListPropertyPage` Wenn ein Benutzer erstellt eine neue Symbolleiste während der Anpassung. Sie können diese Nachricht, um ein benutzerdefiniertes CMFCToolBar abgeleitete Objekt instanziieren verarbeiten. Wenn Sie diese Meldung verarbeiten und erstellen eine eigene Symbolleiste, lassen Sie den Aufruf an den Standardhandler.|Nicht verwendet.|Ein Zeiger auf eine Zeichenfolge, die den Namen der Symbolleiste enthält.|Ein Zeiger auf der Symbolleiste des neu erstellten. NULL gibt an, dass die Symbolleiste Erstellung abgebrochen wurde.|  
|AFX_WM_CUSTOMIZEHELP|An das Hauptrahmenfenster gesendet wird, aus dem Eigenschaftenblatt Anpassung `CMFCToolbarCustomize Dialog` Wenn der Benutzer drückt die **Hilfe** Schaltfläche oder die F1-Taste.|Gibt an, die aktive Seite der Eigenschaftenseite anpassen.|Ein Zeiger auf eine `CMFCToolbarCustomize Dialog` Objekt.|0 (null).|  
|AFX_WM_CUSTOMIZETOOLBAR|Die `CMFCToolbarCustomize Dialog` sendet diese Nachricht an dem übergeordneten Frame zu benachrichtigen, dass der Benutzer eine neue Symbolleiste erstellt.|TRUE, wenn die Anpassung "false" gestartet wurde, wird bei der Anpassung abgeschlossen ist.|Nicht verwendet.|0 (null).|  
|AFX_WM_DELETETOOLBAR|An das Hauptrahmenfenster gesendet, wenn der Benutzer zu eine Symbolleiste in den Anpassungsmodus zu löschen.<br /><br /> Verarbeiten Sie diese Meldung zusätzliche Aktionen ausführen, wenn ein Benutzer eine Symbolleiste im Anpassungsmodus löscht. Sie sollten auch den standardmäßige Handler aufrufen (`OnToolbarDelete`), das Sie die Symbolleiste gelöscht. Der standardmäßige Handler gibt einen Wert, der angibt, ob es möglich ist, löschen Sie die Symbolleiste zurück.|Nicht verwendet.|Zeiger auf eine `CMFCToolBar` Objekt gelöscht wird.|Ungleich NULL, wenn eine Symbolleiste kann nicht gelöscht werden; andernfalls 0.|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton` sendet diese Nachricht an das Hauptrahmenfenster den Farben des Dokuments abgerufen.|Nicht verwendet.|[in, out] Zeiger auf eine `CList<COLORREF, COLORREF>` Objekt.|0 (null).|  
|AFX_WM_GETDRAGBOUNDS|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|An das Hauptrahmenfenster gesendet, wenn ein Benutzer ein Element "Menüband-Liste" hervorgehoben.|Index des markierten Elements|Ein Zeiger auf `CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|Gesendet, um ein übergeordnetes Element von `CMFCShellListCtrl` oder `CMFCShellTreeCtrl` steuert, wenn ein Benutzer beendet einen Shell-Befehl ausführen.|Die ID des Befehls, die der Benutzer ausgeführt.|Nicht verwendet.|Wenn die Anwendung diese Nachricht verarbeitet, muss er 0 (null) zurückgeben.|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Das Framework sendet diese Nachricht auf dem Menüband der übergeordneten, bevor Sie im Popupmenü angezeigt. Sie können diese Meldung verarbeiten und Popupmenüs jederzeit ändern.|Nicht verwendet.|Ein Zeiger auf `CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX_WM_ON_CANCELTABMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Das Framework sendet diese Nachricht an das Hauptrahmenfenster, wenn der Benutzer die aktive Steuerelement auf dem Menüband-Kategorie ändert.|Nicht verwendet.|Ein Zeiger auf die `CMFCRibbonBar` , deren Kategorie hat sich geändert.|Nicht verwendet.|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|Das Framework sendet diese Nachricht an den Besitzer benachrichtigen `CMFCDesktopAlertWnd` , dass das Fenster geschlossen werden.|Nicht verwendet.|Ein Zeiger auf `CMFCDesktopAlertWnd` Objekt.|Nicht verwendet.|  
|AFX_WM_ON_DRAGCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ON_GET_TAB_TOOLTIP|An das Hauptrahmenfenster gesendet, wenn ein Registerkartenfenster Begriff ist, eine QuickInfo für eine Registerkarte angezeigt, wenn QuickInfos aktiviert sind.|Nicht verwendet.|Ein Zeiger auf eine `CMFCTabToolTipInfo` Struktur.|Nicht verwendet.|  
|AFX_WM_ON_HSCROLL|An das Steuerelement in der Größe veränderbaren Steuerelement gesendet. Diese Meldung zum Empfangen von Benachrichtigungen von verarbeiten `CMFCTabCtrl` Objekte ein Scroll-Ereignis in der horizontalen Bildlaufleiste im Registerkartenformat Widget.|Das niederwertige Wort gibt an, dass ein Scroll-Leiste-Wert, der den Benutzer angibt Anforderung Bildlauf des.  Weitere Informationen finden Sie in der Tabelle weiter unten in diesem Thema.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_ON_MOVE_TAB|An das übergeordnete Element von einem Fenster im Registerkartenformat gesendet, wenn ein Benutzer eine Registerkarte an eine neue Position zieht.|Der nullbasierte Index der Registerkarte in der ursprünglichen Position.|[out] Der nullbasierte Index der Registerkarte in seiner neuen Position.|0 (null).|  
|AFX_WM_ON_MOVETABCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ON_MOVETOTABGROUP|An das Hauptrahmenfenster gesendet, wenn ein Benutzer ein untergeordneten MDI-Fensters zwischen Gruppen im Registerkartenformat zu einem anderen bewegt.|Ein Handle für das Fenster im Registerkartenformat (`CMFCTabCtrl`) aus dem die untergeordneten MDI-Fensters entfernt wurde.|[out] Ein Handle für das Fenster im Registerkartenformat (`CMFCTabCtrl`), die die untergeordneten MDI-Fensters eingefügt wurde.|Ignoriert.|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|Gesendet, um ein übergeordnetes Element von `CDockablePane` klickt der Benutzer die **schließen** Schaltfläche in der Titelleiste der Steuerleiste.|Nicht verwendet.|Ein Zeiger auf einen andockbaren Bereich, der auf dem der Benutzer geklickt hat die **schließen** Schaltfläche.|TRUE, wenn ein Bereich kann nicht geschlossen werden; andernfalls "false".|  
|AFX_WM_ON_RENAME_TAB|Das dem übergeordneten Fenster im Registerkartenformat gesendet, nachdem der Benutzer eine bearbeitbare Registerkarte umbenannt.|Der nullbasierte Index der Registerkarte für umbenannt werden soll.|[out] Ein Zeiger auf eine Zeichenfolge, die den Namen der neuen Registerkarte enthält.|Ungleich NULL, wenn die Anwendung diese Nachricht verarbeitet; Das Framework wird den Aufruf von unterdrückt `CMFCBaseTabCtrl::SetTabLabel`.  Wenn 0 (null), klicken Sie dann zurückgegeben wird `CMFCBaseTabCtrl::SetTabLabel` vom Framework aufgerufen wird.|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|Auf den übergeordneten Frame gesendet, wenn Benutzer die Anpassung startet. Verarbeiten Sie diese Meldung, wenn Sie Ihre eigenen Anpassungsdialogfelds anzeigen möchten.|Nicht verwendet.|Ein Zeiger auf das Menübandsteuerelement angepasst werden.|Ungleich NULL, wenn die Anwendung diese Nachricht verarbeitet, und zeigt ein eigenes Dialogfeld Anpassen. Wenn die Anwendung auf 0 (null) zurückgibt, wird das Framework die integrierten Anpassung-Dialogfeld angezeigt.|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_POSTSETPREVIEWFRAME|Gesendet, um dem Hauptframe informieren, dass der Benutzer den Seitenansichtmodus geändert|TRUE gibt an, dass der Seitenansicht-Modus festgelegt ist. FALSE gibt an, dass diese Seitenansicht-Modus deaktiviert ist.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_PROPERTY_CHANGED|An den Besitzer von dem Eigenschaftenraster-Steuerelement gesendet (`CMFCPropertyGridCtrl`) Wenn der Benutzer den Wert der ausgewählten Eigenschaft ändert.|Die Steuerelement-ID der Eigenschaftenliste.|Ein Zeiger auf die Eigenschaft (`CMFCPropertyGridProperty`), die sich geändert.|Nicht verwendet.|  
|AFX_WM_RESETCONTEXTMENU|An das Hauptrahmenfenster gesendet, wenn der Benutzer im Kontextmenü während der Anpassung zurücksetzt.|Die Ressourcen-ID des Kontextmenüs.|Ein Zeiger auf den aktuellen Kontextmenü, `CMFCPopupMenu`.|Nicht verwendet.|  
|AFX_WM_RESETKEYBOARD|Das Framework sendet diese Nachricht an das Hauptrahmenfenster, wenn der Benutzer alle Zugriffstasten während der Anpassung zurücksetzt.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETMENU|Das Framework sendet diese Nachricht an den Menü-Besitzer (ein Rahmenfenster) Wenn der Benutzer ein Frame-Anwendungsmenü zurücksetzt, während der Anpassung|Die Menü-Ressourcen-ID.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETPROMPT|Das Framework sendet diese Nachricht, wenn die Benutzer wird eine Symbolleiste, über die Symbolleiste das Dialogfeld Anpassen. Der standardmäßige Handler zeigt ein Meldungsfeld mit der Frage, ob der Benutzer die Symbolleiste zurücksetzen möchte.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETTOOLBAR|Ein `CMFCToolBar` Object sendet diese Nachricht, wenn eine Symbolleiste, also von seinem ursprünglichen Zustand aus den Ressourcen geladen wiederhergestellt wird. Diese Meldung, Schaltflächen der Symbolleiste erneut einzufügen, deren Klassen abgeleitet werden, verarbeiten `CMFCToolbarButton`. Weitere Informationen finden Sie unter `CMFCToolbarComboBoxButton`.|Die Ressourcen-ID, einer Symbolleiste, dessen Zustand wiederhergestellt wurde.|Nicht verwendet.|0 (null).|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton` Object sendet diese Nachricht an den Besitzer, klickt der Benutzer eine normale Menüschaltfläche. Jedes Mal, mit denen Sie für diese Meldung verarbeiten `CMFCToolbarMenuButton` um ein Popupmenü anzuzeigen, wenn der Benutzer eine Schaltfläche klickt.|Die Befehls-ID einer Schaltfläche, die die Nachricht sendet.|Die Bildschirmkoordinaten des Cursors. Das niederwertige Wort gibt die X-Koordinate. Das höherwertige Wort gibt die y-Koordinate.|Nicht verwendet.|  
|AFX_WM_TOOLBARMENU|An das Hauptrahmenfenster gesendet, wenn der Benutzer die rechte Schaltfläche der Maus loslässt, während der Mauszeiger in den Client oder nicht-Clientbereich eines Bereichs ist.|Nicht verwendet.|Die Bildschirmkoordinaten des Mauszeigers. Das niederwertige Wort gibt die X-Koordinate. Das höherwertige Wort gibt die y-Koordinate.|NULL, wenn die Anwendung diese Nachricht verarbeitet; andernfalls, ungleich NULL.|  
|AFX_WM_UPDATETOOLTIPS|Gesendet an alle Besitzer von QuickInfo ein, um anzugeben, dass die QuickInfo-Steuerelemente neu erstellt werden sollen.|Der Typ des Steuerelements, das diese Nachricht verarbeiten soll. Siehe Tabelle weiter unten in diesem Thema eine Liste der möglichen Werte.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog` sendet diese Nachricht an den übergeordneten Rahmen, klickt der Benutzer die **Hilfe** Schaltfläche oder den Hilfemodus eingibt, indem Sie auf die **Hilfe** Titelleisten-Schaltfläche oder die F1-Taste.|Nicht verwendet.|Ein Zeiger auf die Instanz von `CMFCWindowsManagerDialog`.|Nicht verwendet.|  
  
 Die folgende Tabelle zeigt die Werte für das niedrige Word der der *lParam* Parameters der Methode AFX_WM_HSCROLL:  
  
|||  
|-|-|  
|Wert|Bedeutung|  
|SB_ENDSCROLL|Der Benutzer beendet den Bildlauf.|  
|SB_LEFT|Der Benutzer einen Bildlauf auf der linken oberen Ecke.|  
|SB_RIGHT|Der Benutzer einen Bildlauf nach rechts unten.|  
|SB_LINELEFT|Der Benutzer einen Bildlauf nach links, um eine Einheit.|  
|SB_LINERIGHT|Der Benutzer scrollt, rechts, um eine Einheit.|  
|SB_PAGELEFT|Der Benutzer einen Bildlauf nach links durch die Breite des Fensters.|  
|SB_PAGERIGHT|Der Benutzer scrollt nach rechts durch die Breite des Fensters.|  
|SB_THUMBPOSITION|Der Benutzer hat das Bildlauffeld (Ziehpunkt) ziehen und Loslassen der Maustaste. Das höherwertige Wort gibt die Position des Bildlauffelds am Ende des Ziehvorgangs an.|  
|SB_THUMBTRACK|Der Benutzer wird die bildlaufbox. Die AFX_WM_ON_HSCROLL-Nachricht wird mit diesem Wert wiederholt gesendet werden, bis der Benutzer die Maustaste loslässt. Das höherwertige Wort gibt an, der die Position, die das Bildlauffeld gezogen wurde.|  
  
> [!NOTE]
>  Das höherwertige Wort von der *lParam* Parameter gibt die aktuelle Position des Bildlauffelds an, wenn das niederwertige Wort SB_THUMBPOSITION oder SB_THUMBTRACK ist; andernfalls wird dieses Wort nicht verwendet wird.  
  
 Die folgende Tabelle enthält die Werte für die Kennzeichen für die *lParam* -Parameter der Nachricht AFX_WM_UPDATETOOLTIPS:  
  
|||  
|-|-|  
|Flag|Wert|  
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|  
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|  
|AFX_TOOLTIP_TYPE_TAB|0x0004|  
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|  
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|  
|AFX_TOOLTIP_TYPE_EDIT|0x0020|  
|AFX_TOOLTIP_TYPE_BUTTON|0 x 0040|  
|AFX_TOOLTIP_TYPE_TOOLBOX|0 x 0080|  
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
