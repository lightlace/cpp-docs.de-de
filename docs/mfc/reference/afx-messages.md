---
title: AFX-Meldungen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- AFX messages
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: f9e63f47a8df69b52a6a12688e84602981d20dae
ms.openlocfilehash: 345c84e763d82cd8d13fc842dc57c49f133e39f0
ms.lasthandoff: 03/21/2017

---
# <a name="afx-messages"></a>AFX-Meldungen
Diese Nachrichten werden in MFC verwendet.  
  
## <a name="messages"></a>Meldungen  
 Die folgende Tabelle enthält die Nachrichten, die in der MFC-Bibliothek verwendet werden:  
  
||||||  
|-|-|-|-|-|  
|Meldung|Beschreibung|[in] `wParam`|`lParam`(Alle Parameter sind [in], sofern nicht anders angegeben.)|Rückgabewert|  
|AFX_WM_ACCGETOBJECT|Nicht verwendet.|Nicht verwendet.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ACCGETSTATE|Für die Unterstützung von Eingabehilfen verwendet. Senden Sie diese Nachricht an `CMFCPopupMenu` oder `CMFCRibbonPanelMenu` beim Abrufen des Status des aktuellen Elements.|Der Index des Elements, das eine Schaltfläche oder ein Trennzeichen werden konnte.|Nicht verwendet.|Das Element€™ s-Zustand. Es ist 1, wenn der Index ungültig ist, ist 0, wenn die Schaltfläche keine besonderen Attribute hat. Andernfalls ist es eine Kombination der folgenden Flags:<br /><br /> TBBS_DISABLED Â € ist "Element deaktiviert<br /><br /> TBBS_CHECKED Â €"Element ist aktiviert<br /><br /> TBBS_BUTTON â €"das Element ist eine standard-Schaltfläche<br /><br /> TBBS_PRESSED "Â €Schaltfläche gedrückt wird<br /><br /> TBBS_INDETERMINATE Â €"undefined Zustand<br /><br /> TBBS_SEPARATOR - anstelle einer Menüschaltfläche, dieses Element Formen Trennung zwischen anderen Menüelementen|  
|AFX_WM_CHANGE_ACTIVE_TAB|Das Framework sendet diese Nachricht an das Steuerelement in der Größe veränderbaren Steuerelements. Diese Meldung zum Empfangen von Nachrichten aus dem Verarbeiten `CMFCTabCtrl` Objekte, wenn ein Benutzer eine aktive Registerkarte ändert.|Der Index einer Registerkarte.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_CHANGE_CURRENT_FOLDER|Das Framework sendet diese Nachricht an das übergeordnete Element des `CMFCShellListCtrl` Wenn der Benutzer den aktuellen Ordner geändert hat.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_CHANGEVISUALMANAGER|Das Framework sendet diese Nachricht an alle Rahmenfenster, wenn der Benutzer den aktuellen Visual Manager ändert. Reaktion auf diese Meldung ein Rahmenfenster mit seinem Bereich berechnet und andere Parameter passt, je nach Bedarf. Wenn Sie dieses Ereignis informiert werden müssen, können Sie die AFX_WM_CHANGEVISUALMANAGER-Nachricht in Ihrer Anwendung verarbeiten. Müssen Sie die Basisklassenhandler aufrufen (`OnChangeVisualManager`) um sicherzustellen, dass das Framework interne's Verarbeitung dieses Ereignisses stattfindet.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_CHANGING_ACTIVE_TAB|Gesendet, um das übergeordnete Element des `CMFCTabCtrl` Objekt.  Diese Meldung verarbeiten, wenn Sie Benachrichtigungen erhalten möchten `CMFCTabCtrl` Objekte, wenn ein Benutzer eine Registerkarte zurücksetzt.|Der Index der Registerkarte, die aktiviert wird.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_CHECKEMPTYMINIFRAME|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_CREATETOOLBAR|Gesendet von `CMFCToolBarsListPropertyPage` Wenn ein Benutzer eine neue Symbolleiste während des Anpassungsvorgangs erstellt. Sie können diese Nachricht ein benutzerdefiniertes CMFCToolBar abgeleitetes Objekt instanziieren verarbeiten. Wenn Sie diese Meldung verarbeiten und erstellen eine eigene Symbolleiste, lassen Sie den Aufruf an den Standardhandler.|Nicht verwendet.|Ein Zeiger auf eine Zeichenfolge, die den Namen der Symbolleiste enthält.|Ein Zeiger auf die neu erstellte Symbolleiste. NULL gibt an, dass die Symbolleiste Erstellung abgebrochen wurde.|  
|AFX_WM_CUSTOMIZEHELP|Gesendet an das Hauptrahmenfenster aus dem Eigenschaftenblatt Anpassung `CMFCToolbarCustomize``Dialog` Wenn der Benutzer drückt die **Hilfe** Schaltfläche oder die F1-Taste.|Gibt die aktive Seite der Eigenschaftenseite für die Anpassung an.|Ein Zeiger auf ein `CMFCToolbarCustomize``Dialog` Objekt.|0 (null).|  
|AFX_WM_CUSTOMIZETOOLBAR|Der `CMFCToolbarCustomize``Dialog` sendet diese Nachricht an dem übergeordneten Frame zu benachrichtigen, dass der Benutzer eine neue Symbolleiste erstellt.|`TRUE`Beginn der Anpassung `FALSE` Wenn Anpassung abgeschlossen ist.|Nicht verwendet.|0 (null).|  
|AFX_WM_DELETETOOLBAR|An das Hauptrahmenfenster gesendet, wenn der Benutzer zu eine Symbolleiste in den Anpassungsmodus zu löschen.<br /><br /> Zusätzliche Aktionen ausführen, wenn ein Benutzer eine Symbolleiste im Anpassungsmodus löscht diese Nachricht zu verarbeiten. Sie sollten auch die Standard-Handler aufrufen (`OnToolbarDelete`), die Symbolleiste gelöscht. Der standardmäßige Handler gibt einen Wert, der angibt, ob es möglich ist, löschen Sie die Symbolleiste zurück.|Nicht verwendet.|Zeiger auf ein `CMFCToolBar` Objekt, das gelöscht werden.|Wert ungleich NULL, wenn eine Symbolleiste kann nicht gelöscht werden; andernfalls 0.|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`sendet diese Nachricht an das Hauptrahmenfenster, um die Farben abzurufen.|Nicht verwendet.|[in, out] Zeiger auf ein `CList<COLORREF, COLORREF>` Objekt.|0 (null).|  
|AFX_WM_GETDRAGBOUNDS|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|An das Hauptrahmenfenster gesendet, wenn ein Benutzer ein Menübandelement hervorhebt.|Index des markierten Elements|Ein Zeiger auf`CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|Gesendet an ein übergeordnetes Element des `CMFCShellListCtrl` oder `CMFCShellTreeCtrl` steuert, wenn ein Benutzer beendet einen Shellbefehl ausführen.|Die ID des Befehls, die der Benutzer ausgeführt.|Nicht verwendet.|Wenn die Anwendung diese Nachricht verarbeitet, muss er&0; (null) zurückgeben.|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Das Framework sendet diese Nachricht auf dem Menüband übergeordnete, bevor Sie im Popupmenü angezeigt. Sie können diese Meldung verarbeiten und Popupmenüs jederzeit ändern.|Nicht verwendet.|Ein Zeiger auf`CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX_WM_ON_CANCELTABMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Das Framework sendet diese Nachricht an den Hauptframe, wenn der Benutzer die aktive Menübandsteuerelement Kategorie ändert.|Nicht verwendet.|Ein Zeiger auf die `CMFCRibbonBar` , deren Kategorie geändert hat.|Nicht verwendet.|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|Das Framework sendet diese Nachricht benachrichtigt den Besitzer des `CMFCDesktopAlertWnd` , dass das Fenster geschlossen werden.|Nicht verwendet.|Ein Zeiger auf `CMFCDesktopAlertWnd` Objekt.|Nicht verwendet.|  
|AFX_WM_ON_DRAGCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ON_GET_TAB_TOOLTIP|An das Hauptrahmenfenster gesendet, wenn eine im Registerkartenfenster wird eine QuickInfo für eine Registerkarte angezeigt, wenn QuickInfos aktiviert sind.|Nicht verwendet.|Ein Zeiger auf eine `CMFCTabToolTipInfo` Struktur.|Nicht verwendet.|  
|AFX_WM_ON_HSCROLL|Gesendet, um das Steuerelement in der Größe veränderbaren Steuerelements. Diese Meldung zum Empfangen von Nachrichten aus dem Verarbeiten `CMFCTabCtrl` ein Scroll-Ereignis tritt in der horizontalen Bildlaufleiste im Registerkartenformat Widget-Objekten.|Das niederwertige Wort gibt an, dass ein Scroll-Leiste-Wert, der den Benutzer angibt Anforderung Bildlauf des.  Weitere Informationen finden Sie in der Tabelle weiter unten in diesem Thema.|Nicht verwendet.|Ungleich NULL ist.|  
|AFX_WM_ON_MOVE_TAB|An das übergeordnete Element von einem Fenster im Registerkartenformat gesendet, wenn ein Benutzer eine Registerkarte auf eine neue Position zieht.|Der nullbasierte Index der Registerkarte in der ursprünglichen Position.|[out] Der nullbasierte Index der Registerkarte in die neue Position.|0 (null).|  
|AFX_WM_ON_MOVETABCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_ON_MOVETOTABGROUP|An das Hauptrahmenfenster gesendet, wenn ein Benutzer ein untergeordnetes MDI-Fenster aus einer Gruppe im Registerkartenformat zu einem anderen verschoben.|Ein Handle für das Fenster im Registerkartenformat (`CMFCTabCtrl`) aus dem das untergeordnete MDI-Fenster entfernt wurde.|[out] Ein Handle für das Fenster im Registerkartenformat (`CMFCTabCtrl`), die die untergeordneten MDI-Fensters eingefügt wurde.|Ignoriert.|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|Gesendet, um ein übergeordnetes Element des `CDockablePane` Wenn der Benutzer klickt auf die **schließen** Schaltfläche in der Titelleiste der Steuerleiste.|Nicht verwendet.|Ein Zeiger auf einen andockbaren Bereich, auf dem der Benutzer geklickt hat, die **schließen** Schaltfläche.|`TRUE`Wenn ein Bereich kann nicht geschlossen werden; andernfalls FALSE.|  
|AFX_WM_ON_RENAME_TAB|Das dem übergeordneten Fenster im Registerkartenformat gesendet, nachdem der Benutzer eine bearbeitbare Registerkarte umbenannt.|Der nullbasierte Index der Registerkarte umbenannt.|[out] Ein Zeiger auf eine Zeichenfolge, die Namen der neuen Registerkarte enthält.|Wert ungleich NULL, wenn die Anwendung diese Nachricht verarbeitet; Das Framework wird unterdrückt den Aufruf von `CMFCBaseTabCtrl::SetTabLabel`.  Wenn&0; (null) zurückgegeben wird, wird `CMFCBaseTabCtrl::SetTabLabel` wird vom Framework aufgerufen wird.|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|An den übergeordneten Frame gesendet, wenn Benutzer die Anpassung startet. Verarbeiten Sie diese Meldung, wenn Sie ein eigenes Dialogfeld Anpassung anzeigen möchten.|Nicht verwendet.|Ein Zeiger auf die Menüband-Steuerelements angepasst werden.|Wert ungleich NULL, wenn die Anwendung diese Nachricht verarbeitet und ein eigenes Dialogfeld Anpassung angezeigt. Wenn die Anwendung auf&0; (null) zurückgibt, wird das Framework die integrierte-Dialogfeld angezeigt.|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX_WM_POSTSETPREVIEWFRAME|Gesendet, um dem Hauptframe informieren, dass der Benutzer den Seitenansichtmodus geändert|`TRUE`Gibt an, dass die Seitenansicht festgelegt ist. `FALSE`Gibt an, dass diese Seitenansichtsmodus ausgeschaltet ist.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_PROPERTY_CHANGED|Der Besitzer des dem Eigenschaftenraster-Steuerelement gesendet (`CMFCPropertyGridCtrl`) Wenn der Benutzer den Wert der ausgewählten Eigenschaft ändert.|Die Steuerelement-ID der Eigenschaftenliste.|Ein Zeiger auf die-Eigenschaft (`CMFCProp``ertyGridProperty`), die sich geändert.|Nicht verwendet.|  
|AFX_WM_RESETCONTEXTMENU|An das Hauptrahmenfenster gesendet, wenn der Benutzer im Kontextmenü während der Anpassung zurückgesetzt.|Die Ressourcen-ID des Kontextmenüs.|Ein Zeiger auf den aktuellen Kontextmenü `CMFCPopupMenu`.|Nicht verwendet.|  
|AFX_WM_RESETKEYBOARD|Das Framework sendet diese Nachricht an das Hauptrahmenfenster, wenn der Benutzer alle Zugriffstasten während der Anpassung zurückgesetzt.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETMENU|Das Framework sendet diese Nachricht an den Besitzer Menü (Rahmenfenster) Wenn der Benutzer ein Frame Anwendungsmenü während der Anpassung zurückgesetzt|Der Menü-Ressourcen-ID.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETPROMPT|Das Framework sendet diese Nachricht, wenn die Benutzer wird eine Symbolleiste, über die Symbolleiste im Dialogfeld Anpassen. Der standardmäßige Handler zeigt ein Meldungsfeld mit der Frage, ob der Benutzer möchte die Symbolleiste zurückgesetzt.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_RESETTOOLBAR|Ein `CMFCToolBar` Objekt sendet diese Nachricht, wenn eine Symbolleiste aus den Ressourcen geladen, also von seinem ursprünglichen Zustand wiederhergestellt wird. Verarbeiten Sie diese Nachricht, um Symbolleisten-Schaltflächen stecken, deren Klassen abgeleitet sind `CMFCToolbarButton`. Weitere Informationen finden Sie unter `CMFCToolbarComboBoxButton`.|Die Ressourcen-ID einer Symbolleiste, deren Zustand wiederhergestellt wurde.|Nicht verwendet.|0 (null).|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`Objekt sendet diese Nachricht auf den Besitzer, wenn der Benutzer eine normale Schaltfläche klickt. Diese Meldung jedes Mal, mit denen Sie verarbeiten `CMFCToolbarMenuButton` um ein Popupmenü anzuzeigen, wenn der Benutzer auf eine Schaltfläche klickt.|Die Befehls-ID einer Schaltfläche, die die Nachricht sendet.|Die Bildschirmkoordinaten des Cursors. Das niederwertige Wort gibt die X-Koordinate. Das höherwertige Wort gibt die y-Koordinate.|Nicht verwendet.|  
|AFX_WM_TOOLBARMENU|An das Hauptrahmenfenster gesendet, wenn der Benutzer die Rechte Taste Mausklick loslässt, während der Mauszeiger in den Client- oder nicht-Clientbereich eines Bereichs befindet.|Nicht verwendet.|Die Bildschirmkoordinaten des Mauszeigers. Das niederwertige Wort gibt die X-Koordinate. Das höherwertige Wort gibt die y-Koordinate.|NULL, wenn die Anwendung diese Nachricht verarbeitet; andernfalls, einen Wert ungleich NULL.|  
|AFX_WM_UPDATETOOLTIPS|Gesendet an alle Besitzer der QuickInfo ein, um anzugeben, dass die QuickInfo-Steuerelemente neu erstellt werden soll.|Der Typ des Steuerelements, das diese Nachricht verarbeitet werden soll. Siehe die Tabelle weiter unten in diesem Thema eine Liste der möglichen Werte.|Nicht verwendet.|Nicht verwendet.|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`sendet diese Nachricht an den übergeordneten Rahmen, klickt der Benutzer die **Hilfe** klicken, oder den Hilfemodus eingibt, indem Sie auf die **Hilfe** Titelleistenschaltfläche oder die F1-Taste.|Nicht verwendet.|Ein Zeiger auf die Instanz von `CMFCWindowsManagerDialog`.|Nicht verwendet.|  
  
 Die folgende Tabelle zeigt die Werte für das niedrige Word des der `lParam` -Parameter der Methode AFX_WM_HSCROLL:  
  
|||  
|-|-|  
|Wert|Bedeutung|  
|SB_ENDSCROLL|Der Benutzer beendet die Bildlaufleiste.|  
|SB_LEFT|Der Benutzer einen Bildlauf auf der linken oberen Ecke.|  
|SB_RIGHT|Der Benutzer einen Bildlauf nach rechts unten.|  
|SB_LINELEFT|Der Benutzer einen Bildlauf nach links, um eine Einheit.|  
|SB_LINERIGHT|Der Benutzer einen Bildlauf nach rechts, eine Einheit.|  
|SB_PAGELEFT|Der Benutzer einen Bildlauf nach links durch die Breite des Fensters.|  
|SB_PAGERIGHT|Der Benutzer führt einen Bildlauf rechts von der Breite des Fensters.|  
|SB_THUMBPOSITION|Der Benutzer hat das Bildlauffeld (Ziehpunkt) gezogen und Loslassen der Maustaste. Das höherwertige Wort gibt die Position des Bildlauffelds am Ende des Ziehvorgangs an.|  
|SB_THUMBTRACK|Der Benutzer wird das Bildlauffeld gezogen wird. Die AFX_WM_ON_HSCROLL-Nachricht wird mit diesem Wert wiederholt gesendet, bis der Benutzer die Maustaste loslässt. Das höherwertige Wort gibt die Position auf der Bildlauffeld gezogen wurde.|  
  
> [!NOTE]
>  Das höherwertige Wort von der `lParam` Parameter gibt die aktuelle Position des Bildlauffelds an, wenn das niederwertige Wort SB_THUMBPOSITION oder SB_THUMBTRACK ist; andernfalls wird dieses Wort nicht verwendet.  
  
 Die folgende Tabelle enthält die Werte für die Kennzeichen für die `lParam` -Parameter der Meldung AFX_WM_UPDATETOOLTIPS:  
  
|||  
|-|-|  
|Flag|Wert|  
|AFX_TOOLTIP_TYPE_DEFAULT|0 x&0001;|  
|AFX_TOOLTIP_TYPE_TOOLBAR|0 x&0002;|  
|AFX_TOOLTIP_TYPE_TAB|0 x&0004;|  
|AFX_TOOLTIP_TYPE_MINIFRAME|0 x&0008;|  
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|  
|AFX_TOOLTIP_TYPE_EDIT|0x0020|  
|AFX_TOOLTIP_TYPE_BUTTON|0 x&0040;|  
|AFX_TOOLTIP_TYPE_TOOLBOX|0 x&0080;|  
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

