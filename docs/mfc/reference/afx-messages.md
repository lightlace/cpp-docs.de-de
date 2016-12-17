---
title: "AFX-Meldungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "SB_LINELEFT"
  - "SB_THUMBTRACK"
  - "AFX_TOOLTIP_TYPE_EDIT"
  - "AFX_WM_ON_HSCROLL"
  - "SB_PAGERIGHT"
  - "AFX_WM_RESETPROMPT"
  - "AFX_WM_CHANGE_RIBBON_CATEGORY"
  - "AFX_TOOLTIP_TYPE_MINIFRAME"
  - "AFX_WM_CUSTOMIZETOOLBAR"
  - "AFX_WM_CHANGE_ACTIVE_TAB"
  - "AFX_WM_ACCGETOBJECT"
  - "AFX_WM_TOOLBARMENU"
  - "AFX_TOOLTIP_TYPE_DOCKBAR"
  - "AFX_WM_CUSTOMIZEHELP"
  - "AFX_WM_ON_GET_TAB_TOOLTIP"
  - "AFX_WM_ON_RIBBON_CUSTOMIZE"
  - "AFX_WM_ON_DRAGCOMPLETE"
  - "AFX_WM_RESETTOOLBAR"
  - "AFX_WM_ON_MOVETOTABGROUP"
  - "AFX_WM_CHECKEMPTYMINIFRAME"
  - "AFX_WM_GETDOCUMENTCOLORS"
  - "SB_RIGHT"
  - "AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU"
  - "AFX_WM_ACCGETSTATE"
  - "SB_PAGELEFT"
  - "SB_ENDSCROLL"
  - "AFX_WM_ON_CANCELTABMOVE"
  - "AFX_TOOLTIP_TYPE_TAB"
  - "AFX_WM_WINDOW_HELP"
  - "AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM"
  - "AFX_WM_SHOWREGULARMENU"
  - "AFX_TOOLTIP_TYPE_TOOLBAR"
  - "AFX_WM_CHANGE_CURRENT_FOLDER"
  - "AFX_WM_UPDATETOOLTIPS"
  - "AFX_WM_ON_MOVE_TAB"
  - "AFX_WM_CHANGING_ACTIVE_TAB"
  - "AFX_WM_RESETMENU"
  - "AFX_WM_GETDRAGBOUNDS"
  - "AFX_WM_RESETCONTEXTMENU"
  - "AFX_TOOLTIP_TYPE_BUTTON"
  - "AFX_WM_ON_CLOSEPOPUPWINDOW"
  - "AFX_TOOLTIP_TYPE_TOOLBOX"
  - "AFX_WM_CHANGEVISUALMANAGER"
  - "SB_LINERIGHT"
  - "AFX_WM_ON_RENAME_TAB"
  - "AFX_TOOLTIP_TYPE_DEFAULT"
  - "AFX_WM_ON_TABGROUPMOUSEMOVE"
  - "SB_LEFT"
  - "AFX_WM_DELETETOOLBAR"
  - "AFX_WM_PROPERTY_CHANGED"
  - "AFX_TOOLTIP_TYPE_ALL"
  - "AFX_WM_ACCHITTEST"
  - "AFX_WM_ON_AFTER_SHELL_COMMAND"
  - "AFX_WM_ON_PRESS_CLOSE_BUTTON"
  - "AFX_WM_RESETKEYBOARD"
  - "AFX_WM_ON_MOVETABCOMPLETE"
  - "AFX_WM_CREATETOOLBAR"
  - "SB_THUMBPOSITION"
  - "AFX_WM_POSTSETPREVIEWFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX-Meldungen"
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 24
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# AFX-Meldungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Meldungen werden in MFC verwendet.  
  
## Meldungen  
 Die folgende Tabelle zeigt Meldungen auf, die in der MFC\-Bibliothek verwendet werden:  
  
||||||  
|-|-|-|-|-|  
|Meldung|**Beschreibung**|\[in\] `wParam`|`lParam` \(alle Parameter sind \[in\] wenn nicht anders festgelegt.\)|Rückgabewert|  
|AFX\_WM\_ACCGETOBJECT|Nicht verwendet.|Nicht verwendet.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX\_WM\_ACCGETSTATE|Wird für Barrierefreiheitsunterstützung.  Senden Sie diese Meldung an `CMFCPopupMenu` oder `CMFCRibbonPanelMenu`, um den Zustand des aktuellen Elements abzurufen.|Index des Elements, der eine Menüschaltfläche oder ein Trennzeichen sein.|Nicht verwendet.|Der Zustand des Elements.  Es ist \-1, wenn der Index ungültig ist, 0, wenn die Menütaste keine Specialattribute hat.  Andernfalls handelt es sich um eine Kombination der folgenden Flags:<br /><br /> TBBS\_DISABLED \- Element ist deaktiviert<br /><br /> TBBS\_CHECKED \- Element ist aktiviert<br /><br /> TBBS\_BUTTON \- das Element ist ein Standardpushbutton<br /><br /> TBBS\_PRESSED \- Schaltfläche ist aktiviert<br /><br /> TBBS\_INDETERMINATE \- nicht definierter Zustand<br /><br /> TBBS\_SEPARATOR \)anstatt auf eine Menüschaltfläche, bildet dieses Element eine Trennung zwischen anderen Menüelemente|  
|AFX\_WM\_CHANGE\_ACTIVE\_TAB|Das Framework sendet diese Meldung in der Größe veränderbaren Steuerleistensteuerelement.  Verarbeiten Sie diese Meldung, Benachrichtigungen `CMFCTabCtrl`\-Objekten zu empfangen, wenn ein Benutzer eine aktive Registerkarte ändert.|Der Index einer Registerkarte.|Nicht verwendet.|Wert ungleich 0.|  
|AFX\_WM\_CHANGE\_CURRENT\_FOLDER|Das Framework sendet diese Meldung an das übergeordnete Element von `CMFCShellListCtrl`, wenn der Benutzer den aktuellen Ordner geändert hat.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX\_WM\_CHANGEVISUALMANAGER|Das Framework sendet diese Meldung für alle Rahmenfenstern, wenn der Benutzer den aktuellen visuellen Manager ändert.  Als Reaktion auf diese Meldung rechnet ein Rahmenfenster ihren Bereich nach und passt weitere Parameter nach Bedarf.  Sie können die AFX\_WM\_CHANGEVISUALMANAGER\-Meldung in Ihrer Anwendung verarbeiten, wenn Sie über dieses Ereignis benachrichtigt werden müssen.  Sie müssen den Handler \(`OnChangeVisualManager`\) aufrufen dass die interne Verarbeitung des Frameworks dieses Ereignisses stattfindet.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX\_WM\_CHANGING\_ACTIVE\_TAB|Gesendet übergeordnete Element von `CMFCTabCtrl`\-Objekt.  Verarbeiten Sie diese Nachricht, wenn Sie Benachrichtigungen von `CMFCTabCtrl`\-Objekte erhalten möchten, wenn ein Benutzer eine Registerkarte.|Der Index der Registerkarte, die aktiviert ist.|Nicht verwendet.|Wert ungleich 0.|  
|AFX\_WM\_CHECKEMPTYMINIFRAME|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX\_WM\_CREATETOOLBAR|Gesendet von `CMFCToolBarsListPropertyPage`, wenn ein Benutzer eine neue Symbolleiste während des Anpassungsprozesses erstellt.  Sie können diese Meldung verarbeiten, um ein Objekt CMFCToolBar\-abgeleitetes angepasster zu instanziieren.  Wenn Sie diese Meldung verarbeiten und eigene Symbolleiste erstellen, können Sie den Aufruf an den Standardhandler weg.|Nicht verwendet.|Ein Zeiger auf eine Zeichenfolge, die den Namen der Symbolleiste enthält.|Ein Zeiger auf die neu erstellten Symbolleiste.  NULL gibt an, dass die Symbolleistenerstellung abgebrochen wurde.|  
|AFX\_WM\_CUSTOMIZEHELP|Gesendet das Hauptrahmenfenster vom Anpassungseigenschaftenblatt `CMFCToolbarCustomize``Dialog`, wenn der Benutzer die Schaltfläche **Hilfe** oder F1 drückt.|Gibt der aktiven Seite des Anpassungseigenschaftenblattes an.|Ein Zeiger auf ein Objekt `CMFCToolbarCustomize``Dialog`.|0|  
|AFX\_WM\_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize` `Dialog` sendet diese Meldung, um die übergeordnete Frame zu benachrichtigen, dass der Benutzer eine neue Symbolleiste erstellt.|`TRUE`, wenn Anpassung gestartet wird, `FALSE`, wenn Anpassung beendet wird.|Nicht verwendet.|0|  
|AFX\_WM\_DELETETOOLBAR|Gesendet das Hauptrahmenfenster, wenn der Benutzer im Begriff ist, eine Symbolleiste im Anpassungsmodus zu löschen.<br /><br /> Verarbeiten Sie diese Meldung, um zusätzliche Aktionen ausführen, wenn ein Benutzer eine Symbolleiste im Anpassungsmodus löscht.  Sie sollten den Standardhandler \(`OnToolbarDelete`\) aufrufen, der die Symbolleiste löscht.  Der Standardhandler gibt einen Wert zurück, der angibt, dass es möglich ist, die Symbolleiste zu löschen.|Nicht verwendet.|Zeiger zu einem zu löschenden `CMFCToolBar`\-Objekt.|Wert ungleich 0 \(null\), wenn die Symbolleiste nicht gelöscht werden kann; 0 andernfalls.|  
|AFX\_WM\_GETDOCUMENTCOLORS|`CMFCColorMenuButton` sendet diese Meldung in das Hauptrahmenfenster, um die Dokumentfarben abzurufen.|Nicht verwendet.|\[in, out\] Zeiger auf ein `CList<COLORREF, COLORREF>`\-Objekt.|0|  
|AFX\_WM\_GETDRAGBOUNDS|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX\_WM\_HIGHLIGHT\_RIBBON\_LIST\_ITEM|Gesendet das Hauptrahmenfenster, wenn ein Benutzer ein Menübandlistenelement hervorhebt.|Index des ausgewählten Elements|Ein Zeiger auf `CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX\_WM\_ON\_AFTER\_SHELL\_COMMAND|Gesendet einem übergeordneten Element von `CMFCShellListCtrl` oder `CMFCShellTreeCtrl`\-Steuerelemente, wenn ein Benutzer beendet, ein Shellbefehl auszuführen.|Die ID des Befehls, den der Benutzer ausführen|Nicht verwendet.|Wenn die Anwendungsprozesse diese Meldung, er keinen zurückgeben.|  
|AFX\_WM\_ON\_BEFORE\_SHOW\_RIBBON\_ITEM\_MENU|Das Framework sendet diese Meldung übergeordnete Element des Menübands, bevor das Popupmenü angezeigt.  Sie können diese Meldung verarbeiten und Popupmenüs jederzeit ändern.|Nicht verwendet.|Ein Zeiger auf `CMFCBaseRibbonElement`|Nicht verwendet.|  
|AFX\_WM\_ON\_CANCELTABMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.||  
|AFX\_WM\_ON\_CHANGE\_RIBBON\_CATEGORY|Das Framework sendet diese Meldung zum Hauptframes, wenn der Benutzer die aktuelle Menüband\-Steuerelement\-Kategorie ändert.|Nicht verwendet.|Ein Zeiger auf `CMFCRibbonBar`, dessen Kategorie geändert hat.|Nicht verwendet.|  
|AFX\_WM\_ON\_CLOSEPOPUPWINDOW|Das Framework sendet diese Meldung, um den Besitzer zu `CMFCDesktopAlertWnd` zu benachrichtigen, den das Fenster wird, geschlossen werden.|Nicht verwendet.|Ein Zeiger auf `CMFCDesktopAlertWnd`\-Objekt.|Nicht verwendet.|  
|AFX\_WM\_ON\_DRAGCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX\_WM\_ON\_GET\_TAB\_TOOLTIP|Gesendet das Hauptrahmenfenster, wenn ein Registerkartenfenster im Begriff ist, eine QuickInfo für eine Registerkarte angezeigt, wenn benutzerdefinierte QuickInfos aktiviert werden.|Nicht verwendet.|Ein Zeiger auf eine Struktur. `CMFCTabToolTipInfo`|Nicht verwendet.|  
|AFX\_WM\_ON\_HSCROLL|Gesendet in der Größe veränderbaren Steuerleistensteuerelement.  Verarbeiten Sie diese Meldung, Benachrichtigungen `CMFCTabCtrl`\-Objekten zu empfangen, wenn ein Bildlaufereignis in der des in Registerform horizontalen Bildlaufleiste Widgets auftritt.|Das Wort niederwertige gibt ein Bildlaufleistenwert an, der der Bildlaufanforderung des Benutzers angibt.  Weitere Informationen finden Sie in der Tabelle weiter unten in diesem Thema.|Nicht verwendet.|Wert ungleich 0.|  
|AFX\_WM\_ON\_MOVE\_TAB|Gesendet übergeordnete Element eines Fensters im Registerkartenformat, wenn ein Benutzer eine Registerkarte an eine neue Position zieht.|Der nullbasierte Index der Registerkarte in seiner ursprünglichen Position.|\[out\] der nullbasierte Index der Registerkarte in der neuen Position.|0|  
|AFX\_WM\_ON\_MOVETABCOMPLETE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX\_WM\_ON\_MOVETOTABGROUP|Gesendet das Hauptrahmenfenster, wenn ein Benutzer ein untergeordnetes MDI\-Fenster von einer mit als Registerkarten Gruppe in eine andere verschoben wird.|Ein Handle dem Fenster im Registerkartenformat \(`CMFCTabCtrl`\) aus dem das untergeordnete MDI\-Fenster entfernt wurde.|\[out\] a\-Handle dem Fenster im Registerkartenformat \(`CMFCTabCtrl`\) in dem das untergeordnete MDI\-Fenster eingefügt wurde.|Sie wird ignoriert.|  
|AFX\_WM\_ON\_PRESS\_CLOSE\_BUTTON|Gesendet einem übergeordneten Element von `CDockablePane`, wenn Benutzer auf die Schaltfläche **Schließen** auf Beschriftung der Steuerleiste klickt.|Nicht verwendet.|Ein Zeiger auf einen andockbaren Fenster, auf dem der Benutzer auf die Schaltfläche **Schließen** geklickt hat.|`TRUE`, wenn kein Bereich nicht geschlossen werden kann; FALSE andernfalls.|  
|AFX\_WM\_ON\_RENAME\_TAB|Gesendet übergeordnete Element des Fensters im Registerkartenformat nach dem Benutzer umbenannt eine bearbeitbare Registerkarte.|Der nullbasierte Index der umbenannten Registerkarte.|\[out\] Ein Zeiger auf eine Zeichenfolge, die den neuen Registerkartennamen enthält.|Wert ungleich 0 \(null\) beim Anwendungsprozesse diese Meldung; das Framework unterdrückt den Aufruf von `CMFCBaseTabCtrl::SetTabLabel`.  Wenn Null zurückgegeben wird, wird `CMFCBaseTabCtrl::SetTabLabel` vom Framework aufgerufen.|  
|AFX\_WM\_ON\_RIBBON\_CUSTOMIZE|Gesendet zu übergeordneten Frame, wenn Benutzer Anpassung startet.  Verarbeiten Sie diese Nachricht, wenn Sie Ihr eigenes Anpassungsdialogfeld anzeigen möchten.|Nicht verwendet.|Ein Zeiger auf angepasst werden Menüband\-Steuerelement.|Wert ungleich 0 \(null\) beim Anwendungsprozesse diese Meldung und Anzeigen sein eigenes Anpassungsdialogfeld.  Wenn die Anwendung null zurückgibt, zeigt das Framework integrierte Anpassungsdialogfeld an.|  
|AFX\_WM\_ON\_TABGROUPMOUSEMOVE|Nur für interne Verwendung.|Nicht zutreffend.|Nicht zutreffend.|Nicht zutreffend.|  
|AFX\_WM\_POSTSETPREVIEWFRAME|Gesendet, um des Hauptframes zu benachrichtigen, dass der Benutzer die Seitenansicht geändert|`TRUE` gibt an, dass der Seitenansicht festgelegt wird.  `FALSE` gibt an, dass Seitenansicht deaktiviert ist.|Nicht verwendet.|Nicht verwendet.|  
|AFX\_WM\_PROPERTY\_CHANGED|Gesendet zum Besitzer des Eigenschaftenraster\-steuerelements \(`CMFCPropertyGridCtrl`\) Wenn der Benutzer den Wert der ausgewählten Eigenschaft ändert.|Die Steuerelement\-ID der Liste.|Ein Zeiger auf die Eigenschaft `CMFCProp`\(`ertyGridProperty`\) die geändert wurde.|Nicht verwendet.|  
|AFX\_WM\_RESETCONTEXTMENU|Gesendet das Hauptrahmenfenster, wenn der Benutzer das Kontextmenü für die Anpassung.|Die Ressourcen\-ID des Kontextmenüs.|Ein Zeiger auf das aktuelle Kontextmenü, `CMFCPopupMenu`.|Nicht verwendet.|  
|AFX\_WM\_RESETKEYBOARD|Das Framework sendet diese Meldung in das Hauptrahmenfenster, wenn der Benutzer alle Zugriffstasten während der Anpassung.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX\_WM\_RESETMENU|Das Framework sendet diese Meldung im Menübesitzer \(ein Rahmenfenster\) Wenn der Benutzer ein Anwendungsframemenü während der Anpassung zurücksetzt|Die ID Menüressource|Nicht verwendet.|Nicht verwendet.|  
|AFX\_WM\_RESETPROMPT|Das Framework sendet diese Nachricht, wenn der Benutzer eine Symbolleiste der Symbolleiste anpassen Dialogfeld.  Der Standardhandler zeigt ein Meldungsfeld an, das bewirkt, dass der Benutzer die Symbolleiste ausführen möchte.|Nicht verwendet.|Nicht verwendet.|Nicht verwendet.|  
|AFX\_WM\_RESETTOOLBAR|Ein `CMFCToolBar`\-Objekt sendet diese Nachricht, wenn eine Symbolleiste in ihrem ursprünglichen Zustand. h wiederhergestellt wird geladen von Ressourcen.  Verarbeiten Sie diese Meldung, um Symbolleisten\-Schaltflächen wiedereinzufügen, deren Klassen von `CMFCToolbarButton` abgeleitet werden.  Weitere Informationen finden Sie unter `CMFCToolbarComboBoxButton`.|Die Ressourcen\-ID einer Symbolleiste, deren Zustand wiederhergestellt wurde.|Nicht verwendet.|0|  
|AFX\_WM\_SHOWREGULARMENU|`CMFCToolbarMenuButton`\-Objekt sendet diese Meldung zu seinem Besitzer, wenn der Benutzer auf eine Menüschaltfläche reguläre klickt.  Verarbeiten Sie diese Meldung jedes Mal, wenn Sie `CMFCToolbarMenuButton` verwenden, um ein Popupmenü angezeigt, wenn der Benutzer auf eine Schaltfläche klickt.|Die Befehls\-ID einer Schaltfläche, die die Meldung sendet.|Bildschirmkoordinaten des Cursors.  Das Wort niederwertige gibt der x\-Koordinate an.  Das Wort höherwertige gibt der y\-Koordinate an.|Nicht verwendet.|  
|AFX\_WM\_TOOLBARMENU|Gesendet das Hauptrahmenfenster, wenn der Benutzer die rechte Schaltfläche einer Maus freigibt, während der Mauszeiger im Client oder im Nicht\-Clientbereich eines Bereichs ist.|Nicht verwendet.|Bildschirmkoordinaten des Mauszeigers.  Das Wort niederwertige gibt der x\-Koordinate an.  Das Wort höherwertige gibt der y\-Koordinate an.|Null wenn die Anwendungsprozesse diese Meldung; andernfalls Wert ungleich 0.|  
|AFX\_WM\_UPDATETOOLTIPS|Gesendet zu allen QuickInfobesitzern, um anzugeben, dass ihre QuickInfokontrollen neu erstellt werden sollen.|Der Typ von Steuerelement, die diese Meldung verarbeiten soll.  Siehe die Tabelle weiter unten in diesem Thema für eine Liste möglicher Werte.|Nicht verwendet.|Nicht verwendet.|  
|AFX\_WM\_WINDOW\_HELP|`CMFCWindowsManagerDialog` sendet diese Meldung für die übergeordneten Frame, wenn der Benutzer auf die Schaltfläche **Hilfe** klickt, oder gibt den Hilfemodus ein, indem die **Hilfe** Untertiteln oder die F1\-TASTE klickt.|Nicht verwendet.|Ein Zeiger auf die Instanz von `CMFCWindowsManagerDialog`.|Nicht verwendet.|  
  
 In der folgenden Tabelle werden die Werte für das Wort niederwertige des Parameters `lParam` der AFX\_WM\_HSCROLL\-Methode an:  
  
|||  
|-|-|  
|Wert|Bedeutung|  
|SB\_ENDSCROLL|Der Benutzer beendet den Bildlauf.|  
|SB\_LEFT|Die oben links Benutzerbildläufe zu.|  
|SB\_RIGHT|Die Benutzerbildläufe zum rechts.|  
|SB\_LINELEFT|Der Benutzer führt links von einer Einheit durch.|  
|SB\_LINERIGHT|Die Benutzerbildläufe berichtigen durch eine Einheit.|  
|SB\_PAGELEFT|Der Benutzer führt links über die Breite des Fensters durch.|  
|SB\_PAGERIGHT|Die Benutzerbildläufe berichtigen über die Breite des Fensters.|  
|SB\_THUMBPOSITION|Der Benutzer verfügt das Bildlauffeld \(Ziehpunkt\) gezogen und die Maustaste losgelassen.  Das Wort höherwertige gibt die Position des Bildlauffelds am Ende des Ziehvorgangs an.|  
|SB\_THUMBTRACK|Der Benutzer beginnt das Bildlauffeld.  Die AFX\_WM\_ON\_HSCROLL\-Meldung wiederholt mit diesem Wert übermittelt, bis der Benutzer die Maustaste loslässt.  Das Wort höherwertige gibt die Position an, zu der das Bildlauffeld gezogen wurde.|  
  
> [!NOTE]
>  Das Wort höherwertige des `lParam`\-Parameters gibt der aktuellen Position des Bildlauffelds an, wenn das SB\_THUMBPOSITION niederwertige Wort oder SB\_THUMBTRACK ist; Andernfalls wird das Wort nicht verwendet.  
  
 Die folgende Tabelle zeigt die Flagwerte für den Parameter der `lParam` AFX\_WM\_UPDATETOOLTIPS\-Meldung auf:  
  
|||  
|-|-|  
|Flag|Wert|  
|AFX\_TOOLTIP\_TYPE\_DEFAULT|0x0001|  
|AFX\_TOOLTIP\_TYPE\_TOOLBAR|0x0002|  
|AFX\_TOOLTIP\_TYPE\_TAB|0x0004|  
|AFX\_TOOLTIP\_TYPE\_MINIFRAME|0x0008|  
|AFX\_TOOLTIP\_TYPE\_DOCKBAR|0x0010|  
|AFX\_TOOLTIP\_TYPE\_EDIT|0x0020|  
|AFX\_TOOLTIP\_TYPE\_BUTTON|0x0040|  
|AFX\_TOOLTIP\_TYPE\_TOOLBOX|0x0080|  
|AFX\_TOOLTIP\_TYPE\_ALL|0xFFFF|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)