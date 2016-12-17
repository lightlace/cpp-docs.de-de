---
title: "CWnd-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWnd-Klasse"
  - "window objects [C++]"
  - "windows [C++]"
ms.assetid: 49a832ee-bc34-4126-88b3-bc1d9974f6c4
caps.latest.revision: 27
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# CWnd-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Basisfunktionalität aller Fensterklassen der Microsoft Foundation Class\-Bibliothek bereit.  
  
## Syntax  
  
```  
class CWnd : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWnd::CWnd](../Topic/CWnd::CWnd.md)|Erstellt ein `CWnd`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWnd::accDoDefaultAction](../Topic/CWnd::accDoDefaultAction.md)|Wird durch das Framework aufgerufen, um die Standardaktion des Objekts auszuführen.|  
|[CWnd::accHitTest](../Topic/CWnd::accHitTest.md)|Wird durch das Framework aufgerufen, um das untergeordnete Element oder untergeordnete Objekt an einem bestimmten Punkt auf dem Bildschirm abzurufen.|  
|[CWnd::accLocation](../Topic/CWnd::accLocation.md)|Wird durch das Framework aufgerufen, um die aktuelle Bildschirmposition des angegebenen Objekts abzurufen.|  
|[CWnd::accNavigate](../Topic/CWnd::accNavigate.md)|Wird durch das Framework aufgerufen, um zu einem anderen Benutzer\-Schnittstellenelement innerhalb eines Containers zu gelangen und wenn möglich, das Objekt abzurufen.|  
|[CWnd::accSelect](../Topic/CWnd::accSelect.md)|Wird durch das Framework aufgerufen, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben.|  
|[CWnd::AnimateWindow](../Topic/CWnd::AnimateWindow.md)|Animiert das zugeordnete Fensterobjekt.|  
|[CWnd::ArrangeIconicWindows](../Topic/CWnd::ArrangeIconicWindows.md)|Ordnet alle minimierten untergeordneten Fenster \(Symbole\).|  
|[CWnd::Attach](../Topic/CWnd::Attach.md)|Fügt ein Windows\-Handle zu einem `CWnd`\-Objekt hinzu.|  
|[CWnd::BeginModalState](../Topic/CWnd::BeginModalState.md)|Rufen Sie diese Memberfunktion auf, um ein Framefenster modal zu machen.|  
|[CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md)|Bereit `CWnd` für die Zeichnung vor.|  
|[CWnd::BindDefaultProperty](../Topic/CWnd::BindDefaultProperty.md)|Bindet die standardmäßige einfache gebundene Eigenschaft des aufrufenden Objekts gemäß der Markierung in der Typenbibliothek an einen Cursor, der mit dem Datenquellen\-Steuerelement verknüpft ist.|  
|[CWnd::BindProperty](../Topic/CWnd::BindProperty.md)|Bindet eine cursorgebundene Eigenschaft auf einem datengebundenen Steuerelement mit einem Datenquellen\-Steuerelement und registriert diese Beziehung mit dem MFC\-Bindungs\-Manager.|  
|[CWnd::BringWindowToTop](../Topic/CWnd::BringWindowToTop.md)|Bringt `CWnd` nach oben im Stapel überlappender Fenster.|  
|[CWnd::CalcWindowRect](../Topic/CWnd::CalcWindowRect.md)|Wird aufgerufen, um das Fensterrechtecke aus dem Clientrechteck zu berechnen.|  
|[CWnd::CancelToolTips](../Topic/CWnd::CancelToolTips.md)|Deaktiviert das QuickInfo\-Steuerelement.|  
|[CWnd::CenterWindow](../Topic/CWnd::CenterWindow.md)|Zentriert ein Fenster relativ zu dessen übergeordnetem Element.|  
|[CWnd::ChangeClipboardChain](../Topic/CWnd::ChangeClipboardChain.md)|Entfernt `CWnd` aus der Kette der Zwischenablageansichten.|  
|[CWnd::CheckDlgButton](../Topic/CWnd::CheckDlgButton.md)|Setzt ein Häkchen neben einem Schaltflächensteuerelement oder entfernt ein Häkchen aus einem Schaltflächensteuerelement.|  
|[CWnd::CheckRadioButton](../Topic/CWnd::CheckRadioButton.md)|Überprüft das angegebene Optionsfeld und entfernt das Häkchen aus allen anderen Optionsfeldern in der angegebenen Gruppe der Schaltflächen.|  
|[CWnd::ChildWindowFromPoint](../Topic/CWnd::ChildWindowFromPoint.md)|Ermittelt welches der untergeordneten Fenster ggf. den angegebenen Punkt enthält.|  
|[CWnd::ClientToScreen](../Topic/CWnd::ClientToScreen.md)|Konvertiert die Clientkoordinaten eines bestimmten Punkts oder Rechtecks auf der Anzeige zu Bildschirmkoordinaten.|  
|[CWnd::CloseWindow](../Topic/CWnd::CloseWindow.md)|Minimiert das Fenster.|  
|[CWnd::ContinueModal](../Topic/CWnd::ContinueModal.md)|Setzt den modalen Status eines Fensters fort.|  
|[CWnd::Create](../Topic/CWnd::Create.md)|Erstellt und initialisiert das untergeordnete Fenster, das mit dem `CWnd`\-Objekt verknüpft ist.|  
|[CWnd::CreateAccessibleProxy](../Topic/CWnd::CreateAccessibleProxy.md)|Erstellt einen Active Accessibility\-Proxy für das angegebene Objekt.|  
|[CWnd::CreateCaret](../Topic/CWnd::CreateCaret.md)|Erstellt eine neue Form für den Systemzeiger und ruft die Inhaberschaft des Caretzeichens ab.|  
|[CWnd::CreateControl](../Topic/CWnd::CreateControl.md)|Erstellt ein ActiveX\-Steuerelement, das in einem MFC\-Programm durch ein `CWnd`\-Objekt dargestellt wird.|  
|[CWnd::CreateEx](../Topic/CWnd::CreateEx.md)|Erstellt ein überlapptes, Popup\- oder untergeordnetes Fenster von Windows und fügt es an ein `CWnd`\-Objekt an.|  
|[CWnd::CreateGrayCaret](../Topic/CWnd::CreateGrayCaret.md)|Erstellt einen grauen Block für den Systemzeiger und ruft die Inhaberschaft des Caretzeichens ab.|  
|[CWnd::CreateSolidCaret](../Topic/CWnd::CreateSolidCaret.md)|Erstellt einen durchgezogenen Block für den Systemzeiger und ruft die Inhaberschaft des Caretzeichens ab.|  
|[CWnd::DeleteTempMap](../Topic/CWnd::DeleteTempMap.md)|Wird automatisch durch den `CWinApp`\-Leerlaufzeithandler aufgerufen, wobei durch `FromHandle` erstellte temporäre `CWnd`\-Objekte gelöscht werden.|  
|[CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md)|Löscht das angefügte Windows\-Fenster.|  
|[CWnd::Detach](../Topic/CWnd::Detach.md)|Trennt ein Windows\-Handle von einem `CWnd`\-Objekt und gibt das Handle zurück.|  
|[CWnd::DlgDirList](../Topic/CWnd::DlgDirList.md)|Füllt ein Listenfeld mit einer Datei\- oder Verzeichnisauflistung auf.|  
|[CWnd::DlgDirListComboBox](../Topic/CWnd::DlgDirListComboBox.md)|Füllt das Listenfeld eines Kombinationsfelds mit einer Datei\- oder Verzeichnisauflistung auf.|  
|[CWnd::DlgDirSelect](../Topic/CWnd::DlgDirSelect.md)|Ruft die aktuelle Auswahl aus einem Listenfeld ab.|  
|[CWnd::DlgDirSelectComboBox](../Topic/CWnd::DlgDirSelectComboBox.md)|Ruft die neueste Auswahl aus dem Listenfeld von einem Kombinationsfeld ab.|  
|[CWnd::DragAcceptFiles](../Topic/CWnd::DragAcceptFiles.md)|Gibt an, dass das Fenster gezogene Dateien akzeptiert.|  
|[CWnd::DragDetect](../Topic/CWnd::DragDetect.md)|Erfasst die Maus und zeichnet ihre Bewegung auf, bis der Benutzer die linke Maustaste loslässt, die ESC\-Taste drückt oder die Maus so bewegt, dass sie sich außerhalb des Ziehrechtecks um den angegebenen Punkt herum befindet.|  
|[CWnd::DrawAnimatedRects](../Topic/CWnd::DrawAnimatedRects.md)|Zeichnet ein Drahtrahmenrechteck und animiert es, um das Öffnen eines Symbols oder das Minimieren bzw. Maximieren eines Fensters anzudeuten.|  
|[CWnd::DrawCaption](../Topic/CWnd::DrawCaption.md)|Zeichnet eine Beschriftung.|  
|[CWnd::DrawMenuBar](../Topic/CWnd::DrawMenuBar.md)|Zeichnet die Menüleiste neu.|  
|[CWnd::EnableActiveAccessibility](../Topic/CWnd::EnableActiveAccessibility.md)|Aktiviert benutzerdefinierte `Active Accessibility`\-Funktionen.|  
|[CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md)|Ermöglicht, dass die Position und Größe von untergeordneten Fenstern automatisch angepasst werden können, wenn der Benutzer die Größe des Fensters ändert.|  
|[CWnd::EnableD2DSupport](../Topic/CWnd::EnableD2DSupport.md)|Aktiviert oder deaktiviert die Fensterunterstützung für `D2D`.  Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|  
|[CWnd::EnableScrollBar](../Topic/CWnd::EnableScrollBar.md)|Aktiviert oder deaktiviert einen oder beide Pfeile auf einer Scrollleiste.|  
|[CWnd::EnableScrollBarCtrl](../Topic/CWnd::EnableScrollBarCtrl.md)|Aktiviert oder deaktiviert ein gleichgeordnetes Scrollleisten\-Steuerelement.|  
|[CWnd::EnableToolTips](../Topic/CWnd::EnableToolTips.md)|Aktiviert das QuickInfo\-Steuerelement.|  
|[CWnd::EnableTrackingToolTips](../Topic/CWnd::EnableTrackingToolTips.md)|Aktiviert das QuickInfo\-Steuerelement im Überwachungsmodus.|  
|[CWnd::EnableWindow](../Topic/CWnd::EnableWindow.md)|Aktiviert oder deaktiviert die Maus\- und Tastatureingaben.|  
|[CWnd::EndModalLoop](../Topic/CWnd::EndModalLoop.md)|Beendet den modalen Status eines Fensters.|  
|[CWnd::EndModalState](../Topic/CWnd::EndModalState.md)|Rufen Sie diese Memberfunktion auf, um ein Framefenster von einem modalen in einen Status ohne Modus zu ändern.|  
|[CWnd::EndPaint](../Topic/CWnd::EndPaint.md)|Markiert das Ende der Zeichnung.|  
|[CWnd::ExecuteDlgInit](../Topic/CWnd::ExecuteDlgInit.md)|Initiiert eine Dialogfeldressource.|  
|[CWnd::FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md)|Ruft den Titel oder Text ab, der mit einem Steuerelement in einem Dialogfeld verknüpft ist.|  
|[CWnd::FindWindow](../Topic/CWnd::FindWindow.md)|Gibt das Handle für das Fenster zurück, das anhand seines Fensternamens und seiner Fensterklasse bestimmt wird.|  
|[CWnd::FindWindowEx](../Topic/CWnd::FindWindowEx.md)|Gibt das Handle für das Fenster zurück, das anhand seines Fensternamens und seiner Fensterklasse bestimmt wird.|  
|[CWnd::FlashWindow](../Topic/CWnd::FlashWindow.md)|Bringt das Fenster einmal zum Blinken.|  
|[CWnd::FlashWindowEx](../Topic/CWnd::FlashWindowEx.md)|Bringt das Fenster mit zusätzlicher Funktionalität zum Blinken.|  
|[CWnd::FromHandle](../Topic/CWnd::FromHandle.md)|Gibt einen Zeigt zu einem `CWnd`\-Objekt zurück, wenn ein Handle zu einem Fenster vorhanden ist.   Wenn ein `CWnd`\-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CWnd`\-Objekt erstellt und angefügt.|  
|[CWnd::FromHandlePermanent](../Topic/CWnd::FromHandlePermanent.md)|Gibt einen Zeigt zu einem `CWnd`\-Objekt zurück, wenn ein Handle zu einem Fenster vorhanden ist.   Wenn ein `CWnd`\-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CWnd`\-Objekt erstellt und angefügt.|  
|[CWnd::get\_accChild](../Topic/CWnd::get_accChild.md)|Wird durch das Framework aufgerufen, um die Adresse einer `IDispatch`\-Schnittstelle für das angegebene, untergeordnete Element abzurufen.|  
|[CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md)|Wird durch das Framework aufgerufen, um die Zahl der untergeordneten Elemente abzurufen, die zu diesem Objekt gehören.|  
|[CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md)|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die Standardaktion des Objekts beschreibt.|  
|[CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md)|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt.|  
|[CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md)|Wird durch das Framework aufgerufen, um das Objekt abzurufen, das den Tastaturfokus hat.|  
|[CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md)|Wird durch das Framework aufgerufen, um die **Hilfe**\-Eigenschaftszeichenfolge eines Objekts abzurufen.|  
|[CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md)|Wird durch das Framework aufgerufen, um den vollständigen Pfad der `WinHelp`\-Datei abzurufen, die mit dem angegebenen Objekt verbunden ist und dem Bezeichner des passenden Themas innerhalb dieser Datei.|  
|[CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md)|Wird durch das Framework aufgerufen, um die Tastenkombination oder Zugriffstaste des angegebenen Objekts abzurufen.|  
|[CWnd::get\_accName](../Topic/CWnd::get_accName.md)|Wird durch das Framework aufgerufen, um den Namen des angegebenen Objekts abzurufen.|  
|[CWnd::get\_accParent](../Topic/CWnd::get_accParent.md)|Wird durch das Framework aufgerufen, um die `IDispatch`\-Schnittstelle des übergeordneten Elements des Objekts abzurufen.|  
|[CWnd::get\_accRole](../Topic/CWnd::get_accRole.md)|Wird durch das Framework aufgerufen, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreiben.|  
|[CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md)|Wird durch das Framework aufgerufen, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen.|  
|[CWnd::get\_accState](../Topic/CWnd::get_accState.md)|Wird durch das Framework aufgerufen, um den aktuellen Status des angegebenen Objekts abzurufen.|  
|[CWnd::get\_accValue](../Topic/CWnd::get_accValue.md)|Wird durch das Framework aufgerufen, um den Wert des angegebenen Objekts abzurufen.|  
|[CWnd::GetActiveWindow](../Topic/CWnd::GetActiveWindow.md)|Ruft das aktive Fenster ab.|  
|[CWnd::GetAncestor](../Topic/CWnd::GetAncestor.md)|Ruft das Vorgängerfensterobjekt des angegebenen Fensters ab.|  
|[CWnd::GetCapture](../Topic/CWnd::GetCapture.md)|Ruft das von der Maus erfasste `CWnd` ab.|  
|[CWnd::GetCaretPos](../Topic/CWnd::GetCaretPos.md)|Ruft die Clientkoordinaten der aktuellen Position des Caretzeichens ab.|  
|[CWnd::GetCheckedRadioButton](../Topic/CWnd::GetCheckedRadioButton.md)|Gibt die ID des derzeit aktivierten Optionsfelds in einer Gruppe von Optionsfeldern zurück.|  
|[CWnd::GetClientRect](../Topic/CWnd::GetClientRect.md)|Ruft die Abmessungen des `CWnd`\-Clientbereichs ab.|  
|[CWnd::GetClipboardOwner](../Topic/CWnd::GetClipboardOwner.md)|Ruft einen Zeiger zum aktuellen Inhaber der Zwischenablage ab.|  
|[CWnd::GetClipboardViewer](../Topic/CWnd::GetClipboardViewer.md)|Ruft einen Zeiger zum ersten Fenster in einer Kette von Zwischenablageansichten ab.|  
|[CWnd::GetControlUnknown](../Topic/CWnd::GetControlUnknown.md)|Ruft einen Zeiger zu einem unbekannten ActiveX\-Steuerelement ab.|  
|[CWnd::GetDC](../Topic/CWnd::GetDC.md)|Ruft einen Anzeigekontext für den Clientbereich ab.|  
|[CWnd::GetDCEx](../Topic/CWnd::GetDCEx.md)|Ruft einen Anzeigekontext für den Clientbereich ab und aktiviert Clipping beim Zeichnen.|  
|[CWnd::GetDCRenderTarget](../Topic/CWnd::GetDCRenderTarget.md)|Ruft das Renderziel des Geräts Gerätekontext \(DC\) für das `CWnd`\-Fenster ab.|  
|[CWnd::GetDescendantWindow](../Topic/CWnd::GetDescendantWindow.md)|Sucht alle Nachfolgerfenster und gibt das Fenster mit der angegebenen ID zurück.|  
|[CWnd::GetDesktopWindow](../Topic/CWnd::GetDesktopWindow.md)|Ruft das Windows\-Desktopfenster ab.|  
|[CWnd::GetDlgCtrlID](../Topic/CWnd::GetDlgCtrlID.md)|Wenn es sich bei `CWnd` um ein untergeordnetes Fenster handelt, wird durch den Aufruf dieser Funktion der zugehörige ID\-Wert zurückgegeben.|  
|[CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md)|Ruft das Steuerelement mit der angegebenen ID aus dem angegebenen Dialogfeld ab.|  
|[CWnd::GetDlgItemInt](../Topic/CWnd::GetDlgItemInt.md)|Übersetzt den Text eines Steuerelements im angegebenen Dialogfeld in einen Ganzzahlenwert.|  
|[CWnd::GetDlgItemText](../Topic/CWnd::GetDlgItemText.md)|Ruft die Beschriftung oder den Text ab, die bzw. der mit einem Steuerelement verknüpft ist.|  
|[CWnd::GetDSCCursor](../Topic/CWnd::GetDSCCursor.md)|Ruft einen Zeiger zum zugrunde liegenden Cursor eines Datenquellen\-Steuerelements ab, der durch die Eigenschaften „DataSource“, „UserName“, „Password“ und „SQL“ definiert ist.|  
|[CWnd::GetDynamicLayout](../Topic/CWnd::GetDynamicLayout.md)|Ruft einen Zeiger zum dynamischen Layout\-Manager\-Objekt ab.|  
|[CWnd::GetExStyle](../Topic/CWnd::GetExStyle.md)|Gibt den erweiterten Stil des Fensters zurück.|  
|[CWnd::GetFocus](../Topic/CWnd::GetFocus.md)|Ruft `CWnd` ab, das derzeit über den Eingabefokus verfügt.|  
|[CWnd::GetFont](../Topic/CWnd::GetFont.md)|Ruft die aktuelle Schriftart ab.|  
|[CWnd::GetForegroundWindow](../Topic/CWnd::GetForegroundWindow.md)|Gibt einen Zeiger zum Vordergrundfenster \(das Fenster auf oberster Ebene, mit dem der Benutzer aktuell arbeitet\) zurück.|  
|[CWnd::GetIcon](../Topic/CWnd::GetIcon.md)|Ruft das Handle für ein Symbol ab.|  
|[CWnd::GetLastActivePopup](../Topic/CWnd::GetLastActivePopup.md)|Bestimmt, welches `CWnd` gehörige Popupfenster zuletzt aktiv war.|  
|[CWnd::GetLayeredWindowAttributes](../Topic/CWnd::GetLayeredWindowAttributes.md)|Ruft die Deckkraft\- und Transparenzfarbenschlüssel eines überlappenden Fensters ab.|  
|[CWnd::GetMenu](../Topic/CWnd::GetMenu.md)|Ruft einen Zeiger zum angegebenen Menü ab.|  
|[CWnd::GetNextDlgGroupItem](../Topic/CWnd::GetNextDlgGroupItem.md)|Sucht nach dem nächsten \(oder vorherigen\) Steuerelement in einer Steuerelementgruppe.|  
|[CWnd::GetNextDlgTabItem](../Topic/CWnd::GetNextDlgTabItem.md)|Ruft das erste Steuerelement mit dem Stil [WS\_TABSTOP](../../mfc/reference/window-styles.md) ab, das auf das angegebene Steuerelement folgt \(oder dem vorhergeht\).|  
|[CWnd::GetNextWindow](../Topic/CWnd::GetNextWindow.md)|Gibt das nächste \(oder vorherige\) Fenster in der Liste des Fenster\-Managers zurück.|  
|[CWnd::GetOleControlSite](../Topic/CWnd::GetOleControlSite.md)|Ruft die benutzerdefinierte Site für das angegebene ActiveX\-Steuerelement ab.|  
|[CWnd::GetOpenClipboardWindow](../Topic/CWnd::GetOpenClipboardWindow.md)|Ruft einen Zeiger zum Fenster ab, bei dem die Zwischenablage aktuell geöffnet ist.|  
|[CWnd::GetOwner](../Topic/CWnd::GetOwner.md)|Rift einen Zeiger zum Inhaber von `CWnd` ab.|  
|[CWnd::GetParent](../Topic/CWnd::GetParent.md)|Ruft das übergeordnete Fenster von `CWnd` \(sofern vorhanden\) ab.|  
|[CWnd::GetParentFrame](../Topic/CWnd::GetParentFrame.md)|Ruft das übergeordnete Framefenster des `CWnd`\-Objekts ab.|  
|[CWnd::GetParentOwner](../Topic/CWnd::GetParentOwner.md)|Gibt einen Zeiger zum übergeordneten Fenster eines untergeordneten Fensters zurück.|  
|[CWnd::GetProperty](../Topic/CWnd::GetProperty.md)|Ruft eine ActiveX\-Steuerelementeigenschaft ab.|  
|[CWnd::GetRenderTarget](../Topic/CWnd::GetRenderTarget.md)|Ruft ein Renderziel ab, das mit diesem Fenster verknüpft ist.|  
|[CWnd::GetSafeHwnd](../Topic/CWnd::GetSafeHwnd.md)|Gibt `m_hWnd` oder `NULL` zurück, wenn der `this`\-Zeiger `NULL` ist.|  
|[CWnd::GetSafeOwner](../Topic/CWnd::GetSafeOwner.md)|Ruft den sicheren Inhaber für das angegebene Fenster ab.|  
|[CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md)|Gibt ein gleichgeordnetes Scrollleistensteuerelement zurück.|  
|[CWnd::GetScrollBarInfo](../Topic/CWnd::GetScrollBarInfo.md)|Ruft Informationen über die angegebene Bildlaufleiste ab.|  
|[CWnd::GetScrollInfo](../Topic/CWnd::GetScrollInfo.md)|Ruft die Informationen ab, die von der `SCROLLINFO`\-Struktur über eine Scrollleiste verwaltet werden.|  
|[CWnd::GetScrollLimit](../Topic/CWnd::GetScrollLimit.md)|Ruft den Grenzwert der Scrollleiste ab.|  
|[CWnd::GetScrollPos](../Topic/CWnd::GetScrollPos.md)|Ruft die aktuelle Position eines Scrollfelds ab.|  
|[CWnd::GetScrollRange](../Topic/CWnd::GetScrollRange.md)|Kopiert die aktuellen minimalen und maximalen Positionen der Scrollleiste für eine bestimmte Scrollleiste.|  
|[CWnd::GetStyle](../Topic/CWnd::GetStyle.md)|Gibt den aktuellen Fensterstil zurück.|  
|[CWnd::GetSystemMenu](../Topic/CWnd::GetSystemMenu.md)|Ermöglicht der Anwendung, auf das Steuerelementmenü zuzugreifen, um Kopier\- und Änderungsvorgänge vorzunehmen.|  
|[CWnd::GetTitleBarInfo](../Topic/CWnd::GetTitleBarInfo.md)|Ruft Informationen über die angegebene Titelleiste ab.|  
|[CWnd::GetTopLevelFrame](../Topic/CWnd::GetTopLevelFrame.md)|Ruft das Framefenster auf oberster Ebene des Fensters ab.|  
|[CWnd::GetTopLevelOwner](../Topic/CWnd::GetTopLevelOwner.md)|Ruft das Fenster auf der obersten Ebene ab.|  
|[CWnd::GetTopLevelParent](../Topic/CWnd::GetTopLevelParent.md)|Ruft das übergeordnete Element auf oberster Ebene des Fensters ab.|  
|[CWnd::GetTopWindow](../Topic/CWnd::GetTopWindow.md)|Gibt das erste untergeordnete Element zurück, das zu `CWnd` gehört.|  
|[CWnd::GetUpdateRect](../Topic/CWnd::GetUpdateRect.md)|Ruft die Koordinaten des kleines Rechtecks ab, das die `CWnd`\-Aktualisierungsregion komplett umschließt.|  
|[CWnd::GetUpdateRgn](../Topic/CWnd::GetUpdateRgn.md)|Ruft die `CWnd`\-Aktualisierungsregion ab.|  
|[CWnd::GetWindow](../Topic/CWnd::GetWindow.md)|Gibt das Fenster mit der angegebenen Beziehung zu diesem Fenster zurück.|  
|[CWnd::GetWindowContextHelpId](../Topic/CWnd::GetWindowContextHelpId.md)|Ruft den Hilfekontextbezeichner ab.|  
|[CWnd::GetWindowDC](../Topic/CWnd::GetWindowDC.md)|Ruft den Anzeigekontext für das gesamte Fenster, einschließlich Titelleiste, Menüs und Scrollleisten, ab.|  
|[CWnd::GetWindowedChildCount](../Topic/CWnd::GetWindowedChildCount.md)|Gibt die Anzahl der zugehörigen untergeordneten Fenster zurück.|  
|[CWnd::GetWindowInfo](../Topic/CWnd::GetWindowInfo.md)|Gibt Informationen über das Fenster zurück.|  
|[CWnd::GetWindowlessChildCount](../Topic/CWnd::GetWindowlessChildCount.md)|Gibt die Anzahl der zugehörigen untergeordneten Fenster ohne Fenster zurück.|  
|[CWnd::GetWindowPlacement](../Topic/CWnd::GetWindowPlacement.md)|Ruft den Anzeigestatus und die normalen \(wiederhergestellt\), minimierten und maximierten Positionen eines Fensters ab.|  
|[CWnd::GetWindowRect](../Topic/CWnd::GetWindowRect.md)|Ruft die Bildschirmkoordinaten von `CWnd` ab.|  
|[CWnd::GetWindowRgn](../Topic/CWnd::GetWindowRgn.md)|Ruft eine Kopie der Fensterregion eines Fensters ab.|  
|[CWnd::GetWindowText](../Topic/CWnd::GetWindowText.md)|Gibt den Fenstertext oder Beschriftungstitel \(sofern vorhanden\) zurück.|  
|[CWnd::GetWindowTextLength](../Topic/CWnd::GetWindowTextLength.md)|Gibt die Länge des Texts oder Beschriftungstitels des Fensters zurück.|  
|[CWnd::HideCaret](../Topic/CWnd::HideCaret.md)|Blendet das Caretzeichen aus, indem es auf dem Anzeigebildschirm entfernt wird.|  
|[CWnd::HiliteMenuItem](../Topic/CWnd::HiliteMenuItem.md)|Hebt die Hervorhebung eines Menüelements auf oberster Ebene \(Menüleiste\) hervor oder entfernt sie.|  
|[CWnd::HtmlHelp](../Topic/CWnd::HtmlHelp.md)|Wird aufgerufen, um die HTMLHelp\-Anwendung zu initiieren.|  
|[CWnd::Invalidate](../Topic/CWnd::Invalidate.md)|Macht den gesamten Clientbereich ungültig.|  
|[CWnd::InvalidateRect](../Topic/CWnd::InvalidateRect.md)|Macht den Clientbereich im angegebenen Rechteck ungültig, indem dieses Rechteck zur aktuellen Aktualisierungsregion hinzugefügt wird.|  
|[CWnd::InvalidateRgn](../Topic/CWnd::InvalidateRgn.md)|Macht den Clientbereich in der angegebenen Region ungültig, indem diese Region zur aktuellen Aktualisierungsregion hinzugefügt wird.|  
|[CWnd::InvokeHelper](../Topic/CWnd::InvokeHelper.md)|Ruft eine ActiveX\-Steuerelementmethode oder \-Eigenschaft ab.|  
|[CWnd::IsChild](../Topic/CWnd::IsChild.md)|Gibt an, ob `CWnd` ein untergeordnetes Fenster oder ein weiterer direkter Nachfolger des angegebenen Fensters ist.|  
|[CWnd::IsD2DSupportEnabled](../Topic/CWnd::IsD2DSupportEnabled.md)|Bestimmt, ob die `D2D`\-Unterstützung aktiviert ist.|  
|[CWnd::IsDialogMessage](../Topic/CWnd::IsDialogMessage.md)|Bestimmt, ob die angegebene Meldung für das Dialogfeld ohne Modus vorgesehen ist, und wenn dies der Fall ist, erfolgt die entsprechende Verarbeitung.|  
|[CWnd::IsDlgButtonChecked](../Topic/CWnd::IsDlgButtonChecked.md)|Bestimmt, ob ein Schaltflächensteuerelement aktiviert ist.|  
|[CWnd::IsDynamicLayoutEnabled](../Topic/CWnd::IsDynamicLayoutEnabled.md)|Bestimmt, ob das dynamische Layout in diesem Fenster aktiviert ist.  Wenn das dynamische Layout aktiviert ist, können sich die Position und die Größe der untergeordneten Fenster ändern, wenn der Benutzer die Größe des übergeordneten Fensters ändert.|  
|[CWnd::IsIconic](../Topic/CWnd::IsIconic.md)|Bestimmt, ob `CWnd` minimiert \(Symbol\) ist.|  
|[CWnd::IsTouchWindow](../Topic/CWnd::IsTouchWindow.md)|Gibt an, ob `CWnd` über die Fingereingabeunterstützung verfügt.|  
|[CWnd::IsWindowEnabled](../Topic/CWnd::IsWindowEnabled.md)|Bestimmt, ob das Fenster für die Maus\- und Tastatureingabe aktiviert ist.|  
|[CWnd::IsWindowVisible](../Topic/CWnd::IsWindowVisible.md)|Bestimmt, ob das Fenster sichtbar ist.|  
|[CWnd::IsZoomed](../Topic/CWnd::IsZoomed.md)|Bestimmt, ob `CWnd` maximiert ist.|  
|[CWnd::KillTimer](../Topic/CWnd::KillTimer.md)|Beendet einen Systemzeitgeber.|  
|[CWnd::LockWindowUpdate](../Topic/CWnd::LockWindowUpdate.md)|Deaktiviert oder aktiviert die Zeichnung im angegebenen Fenster erneut.|  
|[CWnd::MapWindowPoints](../Topic/CWnd::MapWindowPoints.md)|Konvertiert \(Zuordnung\) einen Satz von Punkten aus dem Koordinatenbereich von `CWnd` zum Koordinatenbereich des anderen Fensters.|  
|[CWnd::MessageBox](../Topic/CWnd::MessageBox.md)|Erstellt und zeigt ein Fenster an, das eine über die Anwendung bereitgestellte Meldung und Beschriftung aufweist.|  
|[CWnd::ModifyStyle](../Topic/CWnd::ModifyStyle.md)|Ändert den aktuellen Fensterstil.|  
|[CWnd::ModifyStyleEx](../Topic/CWnd::ModifyStyleEx.md)|Ändert den erweiterten Stil des Fensters.|  
|[CWnd::MoveWindow](../Topic/CWnd::MoveWindow.md)|Ändert die Position und die Abmessungen von `CWnd`.|  
|[CWnd::NotifyWinEvent](../Topic/CWnd::NotifyWinEvent.md)|Signalisiert dem System, dass ein vordefiniertes Ereignis aufgetreten ist.|  
|[CWnd::OnAmbientProperty](../Topic/CWnd::OnAmbientProperty.md)|Implementieren Sie die Ambient\-Eigenschaftswerte.|  
|[CWnd::OnDrawIconicThumbnailOrLivePreview](../Topic/CWnd::OnDrawIconicThumbnailOrLivePreview.md)|Wird durch das Framework aufgerufen, wenn es eine auf der Windows 7\-Registerkartenminiaturansicht oder auf dem Client für die Anwendungsvorschau anzuzeigende Bitmap abrufen muss.|  
|[CWnd::OnHelp](../Topic/CWnd::OnHelp.md)|Verarbeitet die F1\-Hilfe in der Anwendung \(unter Verwendung des aktuellen Kontexts\).|  
|[CWnd::OnHelpFinder](../Topic/CWnd::OnHelpFinder.md)|Verarbeitet die Befehle `ID_HELP_FINDER` und `ID_DEFAULT_HELP`.|  
|[CWnd::OnHelpIndex](../Topic/CWnd::OnHelpIndex.md)|Verarbeitet den Befehl `ID_HELP_INDEX` und stellt ein standardmäßiges Hilfethema bereit.|  
|[CWnd::OnHelpUsing](../Topic/CWnd::OnHelpUsing.md)|Verarbeitet den Befehl `ID_HELP_USING`.|  
|[CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md)|Legt fest, ob sich ein Punkt im umgebenden Rechteck des angegebenen Tools befindet und fragt Informationen über das Tool ab.|  
|[CWnd::OpenClipboard](../Topic/CWnd::OpenClipboard.md)|Öffnet die Zwischenablage.  Andere Anwendungen können die Zwischenablage erst ändern, nachdem die Windows\-Funktion [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) aufgerufen wurde.|  
|[CWnd::PaintWindowlessControls](../Topic/CWnd::PaintWindowlessControls.md)|Zeichnet fensterlose Steuerelemente auf dem Steuerelementcontainer.|  
|[CWnd::PostMessage](../Topic/CWnd::PostMessage.md)|Platziert eine Nachricht in der Anwendungswarteschlange, nimmt dann eine Rückgabe vor, ohne darauf zu warten, dass das Fenster die Nachricht verarbeitet.|  
|[CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md)|Wird vor der Erstellung des an diesem `CWnd`\-Objekt angefügten Windows\-Fensters aufgerufen.|  
|[CWnd::PreSubclassWindow](../Topic/CWnd::PreSubclassWindow.md)|Ermöglicht, dass andere erforderliche Unterklassen erstellt werden, bevor [SubclassWindow](../Topic/CWnd::SubclassWindow.md) aufgerufen wird.|  
|[CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)|Wird durch `CWinApp` verwendet, um Fenstermeldungen zu filtern, bevor sie an die Windows\-Funktionen `TranslateMessage` und `DispatchMessage` gesendet werden.|  
|[CWnd::Print](../Topic/CWnd::Print.md)|Zeichnet das aktuelle Fenster in den angegebenen Gerätekontext.|  
|[CWnd::PrintClient](../Topic/CWnd::PrintClient.md)|Zeichnet alle Fenster in den angegebenen Gerätekontext \(für gewöhnlich einen Druckergerätkontext\).|  
|[CWnd::PrintWindow](../Topic/CWnd::PrintWindow.md)|Kopiert ein visuelles Fenster in den angegebenen Gerätekontext, für gewöhnlich handelt es sich dabei um einen Druckerdomänencontroller.|  
|[CWnd::RedrawWindow](../Topic/CWnd::RedrawWindow.md)|Aktualisiert das angegebene Rechteck bzw. die Region im Clientbereich.|  
|[CWnd::RegisterTouchWindow](../Topic/CWnd::RegisterTouchWindow.md)|Registrieren Sie das Fenster für die Windows\-Fingereingabe, oder heben Sie die Registrierung auf.|  
|[CWnd::ReleaseDC](../Topic/CWnd::ReleaseDC.md)|Gibt Client\- und Fenstergerätkontexte für die Verwendung durch andere Anwendungen frei.|  
|[CWnd::RepositionBars](../Topic/CWnd::RepositionBars.md)|Ordnet die Steuerleisten im Clientbereich neu an.|  
|[CWnd::RunModalLoop](../Topic/CWnd::RunModalLoop.md)|Ruft Meldungen für ein Fenster, das sich im modalen Status befindet, ab, übersetzt oder sendet sie.|  
|[CWnd::ScreenToClient](../Topic/CWnd::ScreenToClient.md)|Konvertiert die Bildschirmkoordinaten eines bestimmten Punkts oder Rechtecks auf der Anzeige zu Clientkoordinaten.|  
|[CWnd::ScrollWindow](../Topic/CWnd::ScrollWindow.md)|Scrollt durch Inhalte im Clientbereich.|  
|[CWnd::ScrollWindowEx](../Topic/CWnd::ScrollWindowEx.md)|Scrollt durch Inhalte im Clientbereich.  Ähnelt `ScrollWindow`, weist jedoch zusätzliche Features auf.|  
|[CWnd::SendChildNotifyLastMsg](../Topic/CWnd::SendChildNotifyLastMsg.md)|Stellt einem untergeordneten Fenster über das übergeordnete Fenster eine Benachrichtigungsmeldung bereit, sodass das untergeordnete Fenster eine Aufgabe verarbeiten kann.|  
|[CWnd::SendDlgItemMessage](../Topic/CWnd::SendDlgItemMessage.md)|Sendet eine Nachricht an das angegebene Steuerelement.|  
|[CWnd::SendMessage](../Topic/CWnd::SendMessage.md)|Sendet eine Nachricht an das `CWnd`\-Objekt und gibt erst etwas zurück, nachdem die Meldung verarbeitet wurde.|  
|[CWnd::SendMessageToDescendants](../Topic/CWnd::SendMessageToDescendants.md)|Sendet eine Nachricht an alle Nachfolgefenster des Fensters.|  
|[CWnd::SendNotifyMessage](../Topic/CWnd::SendNotifyMessage.md)|Sendet die angegebene Meldung an das Fenster und gibt schnellstmöglich etwas zurück, und zwar in Abhängigkeit davon, ob der aufrufende Thread das Fenster erstellt hat.|  
|[CWnd::SetActiveWindow](../Topic/CWnd::SetActiveWindow.md)|Aktiviert das Fenster.|  
|[CWnd::SetCapture](../Topic/CWnd::SetCapture.md)|Sorgt dafür, dass alle nachfolgenden Mauseingaben an `CWnd` gesendet werden.|  
|[CWnd::SetCaretPos](../Topic/CWnd::SetCaretPos.md)|Verschiebt das Caretzeichen an die angegebene Position.|  
|[CWnd::SetClipboardViewer](../Topic/CWnd::SetClipboardViewer.md)|Fügt `CWnd` zur Fensterkette hinzu, die benachrichtigt werden, sobald sich die Inhalte der Zwischenablage ändern.|  
|[CWnd::SetDlgCtrlID](../Topic/CWnd::SetDlgCtrlID.md)|Legt die Fenster\- oder Steuerelement\-ID für das Fenster \(hierbei kann es sich um beliebige untergeordnete Fenster und nicht nur um ein Steuerelement in einem Dialogfeld handeln\) fest.|  
|[CWnd::SetDlgItemInt](../Topic/CWnd::SetDlgItemInt.md)|Legt den Text eines Steuerelements auf die Zeichenfolge fest, die einen Ganzzahlwert darstellt.|  
|[CWnd::SetDlgItemText](../Topic/CWnd::SetDlgItemText.md)|Legt die Beschriftung oder den Text eines Steuerelements im angegebenen Dialogfeld fest.|  
|[CWnd::SetFocus](../Topic/CWnd::SetFocus.md)|Beansprucht den Eingabefokus.|  
|[CWnd::SetFont](../Topic/CWnd::SetFont.md)|Legt die aktuelle Schriftart fest.|  
|[CWnd::SetForegroundWindow](../Topic/CWnd::SetForegroundWindow.md)|Versetzt den Thread, durch den das Fenster erstellt wurde, in den Vordergrund und aktiviert das Fenster.|  
|[CWnd::SetIcon](../Topic/CWnd::SetIcon.md)|Legt das Handle auf ein bestimmtes Symbol fest.|  
|[CWnd::SetLayeredWindowAttributes](../Topic/CWnd::SetLayeredWindowAttributes.md)|Legt die Deckkraft\- und Transparenzfarbenschlüssel eines überlappenden Fensters fest.|  
|[CWnd::SetMenu](../Topic/CWnd::SetMenu.md)|Legt das Menü auf das angegebene Menü fest.|  
|[CWnd::SetOwner](../Topic/CWnd::SetOwner.md)|Ändert den Inhaber von`CWnd`.|  
|[CWnd::SetParent](../Topic/CWnd::SetParent.md)|Ändert das übergeordnete Fenster.|  
|[CWnd::SetProperty](../Topic/CWnd::SetProperty.md)|Legt eine ActiveX\-Steuerelementeigenschaft fest.|  
|[CWnd::SetRedraw](../Topic/CWnd::SetRedraw.md)|Ermöglicht, dass Änderungen in `CWnd` neu gezeichnet werden oder verhindert, dass Änderungen neu gezeichnet werden.|  
|[CWnd::SetScrollInfo](../Topic/CWnd::SetScrollInfo.md)|Legt die Informationen über die Bildlaufleiste fest.|  
|[CWnd::SetScrollPos](../Topic/CWnd::SetScrollPos.md)|Legt die aktuelle Position eines Scrollfelds fest und zeichnet \(sofern angegeben\) die Scrollleiste neu, um die neue Position zu berücksichtigen.|  
|[CWnd::SetScrollRange](../Topic/CWnd::SetScrollRange.md)|Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.|  
|[CWnd::SetTimer](../Topic/CWnd::SetTimer.md)|Installiert einen Systemzeitgeber, der eine [WM\_TIMER](../Topic/CWnd::OnTimer.md)\-Meldung sendet, wenn die Auslösung erfolgt.|  
|[CWnd::SetWindowContextHelpId](../Topic/CWnd::SetWindowContextHelpId.md)|Legt den Hilfekontextbezeichner fest.|  
|[CWnd::SetWindowPlacement](../Topic/CWnd::SetWindowPlacement.md)|Legt den Anzeigestatus und die normalen \(wiederhergestellt\), minimierten und maximierten Positionen für ein Fenster fest.|  
|[CWnd::SetWindowPos](../Topic/CWnd::SetWindowPos.md)|Ändert die Größe, Position und Reihenfolge von untergeordneten, Popup\- und Fenstern auf oberster Ebene.|  
|[CWnd::SetWindowRgn](../Topic/CWnd::SetWindowRgn.md)|Legt die Region eines Fensters fest.|  
|[CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)|Legt den Fenstertext oder Beschriftungstitel \(sofern vorhanden\) auf den angegebenen Text fest.|  
|[CWnd::ShowCaret](../Topic/CWnd::ShowCaret.md)|Zeigt das Caretzeichen auf der Anzeige an der aktuellen Position des Caretzeichens.  Sobald die Anzeige erfolgt, blinkt das Caretzeichen automatisch auf.|  
|[CWnd::ShowOwnedPopups](../Topic/CWnd::ShowOwnedPopups.md)|Zeigt alle Popupfenster an, die dem Fenster gehören, oder blendet sie aus.|  
|[CWnd::ShowScrollBar](../Topic/CWnd::ShowScrollBar.md)|Zeigt eine Scrollleiste an oder blendet sie aus.|  
|[CWnd::ShowWindow](../Topic/CWnd::ShowWindow.md)|Zeigt das Fenster an oder blendet es aus.|  
|[CWnd::SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md)|Fügt ein Windows\-Steuerelement an ein `CWnd`\-Objekt an und initiiert das Weiterleiten von Nachrichten über die Nachrichtenzuordnung von `CWnd`.|  
|[CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md)|Fügt ein Fenster an ein `CWnd`\-Objekt an und initiiert das Weiterleiten von Nachrichten über die Nachrichtenzuordnung von `CWnd`.|  
|[CWnd::UnlockWindowUpdate](../Topic/CWnd::UnlockWindowUpdate.md)|Entsperrt ein Fenster, das mit `CWnd::LockWindowUpdate` gesperrt wurde.|  
|[CWnd::UnsubclassWindow](../Topic/CWnd::UnsubclassWindow.md)|Trennt ein Fenster von einem `CWnd` \-Objekt.|  
|[CWnd::UpdateData](../Topic/CWnd::UpdateData.md)|Initialisiert Daten von einem Dialogfeld oder ruft sie ab.|  
|[CWnd::UpdateDialogControls](../Topic/CWnd::UpdateDialogControls.md)|Wird aufgerufen, um den Status der Dialogfelder und von anderen Steuerelementen zu aktualisieren.|  
|[CWnd::UpdateLayeredWindow](../Topic/CWnd::UpdateLayeredWindow.md)|Aktualisiert die Position, Größe, Form, Inhalte und Lichtdurchlässigkeit eines überlappenden Fensters.|  
|[CWnd::UpdateWindow](../Topic/CWnd::UpdateWindow.md)|Aktualisiert den Clientbereich.|  
|[CWnd::ValidateRect](../Topic/CWnd::ValidateRect.md)|Überprüft den Clientbereich in einem angegebenen Rechteck durch das Entfernen des Rechtecks aus der aktuellen Aktualisierungsregion.|  
|[CWnd::ValidateRgn](../Topic/CWnd::ValidateRgn.md)|Überprüft den Clientbereich in einer angegebenen Region durch das Entfernen der Region aus der aktuellen Aktualisierungsregion.|  
|[CWnd::WindowFromPoint](../Topic/CWnd::WindowFromPoint.md)|Bestimmt das Fenster, das den angegebenen Punkt enthält.|  
|[CWnd::WinHelp](../Topic/CWnd::WinHelp.md)|Wird aufgerufen, um die WinHelp\-Anwendung zu initiieren.|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWnd::Default](../Topic/CWnd::Default.md)|Ruft die standardmäßige Fensterprozedur auf, die eine standardmäßige Verarbeitung für Fenstermeldungen bereitstellt, die von einer Anwendung nicht verarbeitet werden.|  
|[CWnd::DefWindowProc](../Topic/CWnd::DefWindowProc.md)|Ruft die standardmäßige Fensterprozedur auf, die eine standardmäßige Verarbeitung für Fenstermeldungen bereitstellt, die von einer Anwendung nicht verarbeitet werden.|  
|[CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)|Für den Dialogfeld\-Datenaustausch und die \-überprüfung.  Wird von `UpdateData` aufgerufen.|  
|[CWnd::GetCurrentMessage](../Topic/CWnd::GetCurrentMessage.md)|Gibt einen Zeiger zur Nachricht zurück, die durch dieses Fenster zurzeit verarbeitet wird.  Sollte nur in einer `On`*Message*\-Nachrichtenhandler\-Memberfunktion aufgerufen werden.|  
|[CWnd::InitDynamicLayout](../Topic/CWnd::InitDynamicLayout.md)|Wird durch das Framework aufgerufen, um das dynamische Layout für das Fenster zu initialisieren.|  
|[CWnd::LoadDynamicLayoutResource](../Topic/CWnd::LoadDynamicLayoutResource.md)|Lädt dynamische Layoutinformationen aus der Ressourcendatei.|  
|[CWnd::OnActivate](../Topic/CWnd::OnActivate.md)|Wird aufgerufen, wenn `CWnd` aktiviert bzw. deaktiviert wird.|  
|[CWnd::OnActivateApp](../Topic/CWnd::OnActivateApp.md)|Wird aufgerufen, wenn die Anwendung aktiviert oder deaktiviert wird.|  
|[CWnd::OnAppCommand](../Topic/CWnd::OnAppCommand.md)|Wird aufgerufen, wenn der Benutzer ein Anwendungsbefehlereignis generiert.|  
|[CWnd::OnAskCbFormatName](../Topic/CWnd::OnAskCbFormatName.md)|Wird durch eine Zwischenablageansichtsanwendung aufgerufen, wenn der Zwischenablageinhaber die Zwischenablageinhalte anzeigt.|  
|[CWnd::OnCancelMode](../Topic/CWnd::OnCancelMode.md)|Wird aufgerufen, um zu ermöglichen, dass `CWnd` interne Modi wie die Mauserfassung abbricht.|  
|[CWnd::OnCaptureChanged](../Topic/CWnd::OnCaptureChanged.md)|Sendet eine Nachricht an das Fenster, dem die Mauserfassung entzogen wird.|  
|[CWnd::OnChangeCbChain](../Topic/CWnd::OnChangeCbChain.md)|Gibt eine Benachrichtigung darüber aus, dass ein angegebenes Fenster aus der Kette entfernt wird.|  
|[CWnd::OnChangeUIState](../Topic/CWnd::OnChangeUIState.md)|Wird aufgerufen, wenn der Benutzeroberflächenstatus \(UI\) geändert werden sollte.|  
|[CWnd::OnChar](../Topic/CWnd::OnChar.md)|Wird aufgerufen, wenn eine Tastatureingabe in ein systemfremdes Zeichen übersetzt wird.|  
|[CWnd::OnCharToItem](../Topic/CWnd::OnCharToItem.md)|Wird durch ein untergeordnetes Listenfeld mit dem Stil [LBS\_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) als Antwort auf eine [WM\_CHAR](../Topic/CWnd::OnChar.md)\-Meldung aufgerufen.|  
|[CWnd::OnChildActivate](../Topic/CWnd::OnChildActivate.md)|Wird für untergeordnete MDI\-Fenster \(Multiple Document Interface, Schnittstelle für mehrere Dokumente\) aufgerufen, sobald sich die Größe oder Position von `CWnd` ändert oder `CWnd` aktiviert wird.|  
|[CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md)|Wird durch ein übergeordnetes Fenster aufgerufen, um einem Benachrichtigungssteuerelement zu ermöglichen, auf eine Steuerelementbenachrichtigung zu antworten.|  
|[CWnd::OnClipboardUpdate](../Topic/CWnd::OnClipboardUpdate.md)|Wird aufgerufen, wenn die Inhalte der Zwischenablage geändert wurden.|  
|[CWnd::OnClose](../Topic/CWnd::OnClose.md)|Wird als ein Signal aufgerufen, dass `CWnd` geschlossen werden sollte.|  
|[CWnd::OnColorizationColorChanged](../Topic/CWnd::OnColorizationColorChanged.md)|Wird aufgerufen, wenn sich die Renderrichtlinie des Nicht\-Clientbereichs geändert hat.|  
|[CWnd::OnCommand](../Topic/CWnd::OnCommand.md)|Wird aufgerufen, wenn der Benutzer einen Befehl auswählt.|  
|[CWnd::OnCompacting](../Topic/CWnd::OnCompacting.md)|Wird aufgerufen, wenn Windows erkennt, dass der Arbeitsspeicher des Systems niedrig ist.|  
|[CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)|Wird aufgerufen, um die relative Position eines neuen Elements in einem untergeordneten sortierten vom Besitzer gezeichneten Kombinationsfeld oder Listenfeld zu ermitteln.|  
|[CWnd::OnCompositionChanged](../Topic/CWnd::OnCompositionChanged.md)|Wird für alle Fenster auf oberster Ebene aufgerufen, wenn die Desktopfenster\-Manager\-Komposition aktiviert oder deaktiviert wird.|  
|[CWnd::OnContextMenu](../Topic/CWnd::OnContextMenu.md)|Wird aufgerufen, wenn der Benutzer mit die rechten Maustaste in das Fenster klickt.|  
|[CWnd::OnCopyData](../Topic/CWnd::OnCopyData.md)|Kopiert Daten aus einer Anwendung in eine andere.|  
|[CWnd::OnCreate](../Topic/CWnd::OnCreate.md)|Wird im Rahmen einer Fenstererstellung aufgerufen.|  
|[CWnd::OnCtlColor](../Topic/CWnd::OnCtlColor.md)|Wird aufgerufen, wenn `CWnd` das übergeordnete Element eines Steuerelements ist, wenn das Steuerelement gezeichnet wird.|  
|[CWnd::OnDeadChar](../Topic/CWnd::OnDeadChar.md)|Wird aufgerufen, wenn eine Tastatureingabe in ein systemfremdes, funktionsloses Zeichen \(beispielsweise Akzentzeichen\) übersetzt wird.|  
|[CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)|Wird aufgerufen, wenn ein vom Besitzer gezeichnetes Listen\- oder Kombinationsfeld zerstört wird oder wenn Elemente aus dem Steuerelement entfernt werden.|  
|[CWnd::OnDestroy](../Topic/CWnd::OnDestroy.md)|Wird aufgerufen, wenn `CWnd` zerstört wird.|  
|[CWnd::OnDestroyClipboard](../Topic/CWnd::OnDestroyClipboard.md)|Wird aufgerufen, wenn die Zwischenablage über einen Aufruf zur Windows\-Funktion [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) geleert wird.|  
|[CWnd::OnDeviceChange](../Topic/CWnd::OnDeviceChange.md)|Benachrichtigt eine Anwendung oder einen Gerätetreiber über eine Änderung an der Hardwarekonfiguration eines Geräts oder des Computers.|  
|[CWnd::OnDevModeChange](../Topic/CWnd::OnDevModeChange.md)|Wird für alle Fenster auf oberster Ebene aufgerufen, wenn der Benutzer die Gerätemoduseinstellungen ändert.|  
|[CWnd::OnDrawClipboard](../Topic/CWnd::OnDrawClipboard.md)|Wird aufgerufen, wenn sich der Inhalt der Zwischenablage ändert.|  
|[CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)|Wird aufgerufen, wenn ein visueller Aspekt eines vom Besitzer gezeichneten untergeordneten Schaltflächensteuerelements, Kombinationsfeldsteuerelements, Listenfeldsteuerelements oder Menüs gezeichnet werden muss.|  
|[CWnd::OnDropFiles](../Topic/CWnd::OnDropFiles.md)|Wird aufgerufen, wenn der Benutzer die linke Maustaste über einem Fenster loslässt, das sich selbst als der Empfänger von abgelegten Dateien registriert hat.|  
|[CWnd::OnEnable](../Topic/CWnd::OnEnable.md)|Wird aufgerufen, wenn `CWnd` aktiviert oder deaktiviert ist.|  
|[CWnd::OnEndSession](../Topic/CWnd::OnEndSession.md)|Wird aufgerufen, wenn die Sitzung beendet wird.|  
|[CWnd::OnEnterIdle](../Topic/CWnd::OnEnterIdle.md)|Wird aufgerufen, um die Hauptfensterprozedur einer Anwendung darüber zu informieren, dass ein modales Dialogfeld oder ein Menü in den Leerlaufstatus übergeht.|  
|[CWnd::OnEnterMenuLoop](../Topic/CWnd::OnEnterMenuLoop.md)|Wird aufgerufen, wenn eine modale Menüschleife eingegangen wurde.|  
|[CWnd::OnEnterSizeMove](../Topic/CWnd::OnEnterSizeMove.md)|Wird aufgerufen, nachdem das betroffene Fenster eine Verschiebungs\- oder modale Größenanpassungsschleife eingeht.|  
|[CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md)|Wird aufgerufen, wenn der Fensterhintergrund gelöscht werden muss.|  
|[CWnd::OnExitMenuLoop](../Topic/CWnd::OnExitMenuLoop.md)|Wird aufgerufen, wenn eine modale Menüschleife beendet wurde.|  
|[CWnd::OnExitSizeMove](../Topic/CWnd::OnExitSizeMove.md)|Wird aufgerufen, nachdem das betroffene Fenster eine Verschiebungs\- oder modale Größenanpassungsschleife beendet.|  
|[CWnd::OnFontChange](../Topic/CWnd::OnFontChange.md)|Wird aufgerufen, wenn sich der Pool der Schriftartressourcen ändert.|  
|[CWnd::OnGetDlgCode](../Topic/CWnd::OnGetDlgCode.md)|Wird für ein Steuerelement aufgerufen, sodass das Steuerelement die Eingabe für die PFEILTASTE und TAB\-TASTE selbst verarbeiten kann.|  
|[CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)|Wird aufgerufen, sobald Windows über die maximierte Position oder Dimensionen oder die minimale oder maximale Nachverfolgungsgröße informiert werden muss.|  
|[CWnd::OnHelpInfo](../Topic/CWnd::OnHelpInfo.md)|Wird durch das Framework aufgerufen, wenn der Benutzer die F1\-TASTE drückt.|  
|[CWnd::OnHotKey](../Topic/CWnd::OnHotKey.md)|Wird aufgerufen, wenn der Benutzer eine systemübergreifende Abkürzungstaste drückt.|  
|[CWnd::OnHScroll](../Topic/CWnd::OnHScroll.md)|Wird aufgerufen, wenn der Benutzer auf die horizontale Scrollleiste von `CWnd` klickt.|  
|[CWnd::OnHScrollClipboard](../Topic/CWnd::OnHScrollClipboard.md)|Wird aufgerufen, wenn ein Zwischenablageinhaber das Zwischenablagebild scrollen, den entsprechenden Abschnitt ungültig machen und die Scrollleistenwerte aktualisieren sollte.|  
|[CWnd::OnIconEraseBkgnd](../Topic/CWnd::OnIconEraseBkgnd.md)|Wird aufgerufen, wenn `CWnd` minimiert \(Symbol\) ist und der Hintergrund des Symbols vor dem Zeichnen des Symbols aufgefüllt werden muss.|  
|[CWnd::OnInitMenu](../Topic/CWnd::OnInitMenu.md)|Wird aufgerufen, wenn ein Menü aktiv wird.|  
|[CWnd::OnInitMenuPopup](../Topic/CWnd::OnInitMenuPopup.md)|Wird aufgerufen, wenn ein Popupmenü aktiv wird.|  
|[CWnd::OnInputDeviceChange](../Topic/CWnd::OnInputDeviceChange.md)|Wird aufgerufen, wenn dem System ein E\/A\-Gerät hinzugefügt oder aus dem System entfernt wird.|  
|[CWnd::OnInputLangChange](../Topic/CWnd::OnInputLangChange.md)|Wird aufgerufen, nachdem sich die Eingabesprache einer Anwendung geändert hat.|  
|[CWnd::OnInputLangChangeRequest](../Topic/CWnd::OnInputLangChangeRequest.md)|Wird aufgerufen, wenn der Benutzer eine neue Eingabesprache auswählt.|  
|[CWnd::OnKeyDown](../Topic/CWnd::OnKeyDown.md)|Wird aufgerufen, wenn eine systemfremde Taste gedrückt wird.|  
|[CWnd::OnKeyUp](../Topic/CWnd::OnKeyUp.md)|Wird aufgerufen, wenn eine systemfremde Taste losgelassen wird.|  
|[CWnd::OnKillFocus](../Topic/CWnd::OnKillFocus.md)|Wird sofort aufgerufen, bevor `CWnd` den Eingabefokus verliert.|  
|[CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer mit der linken Maustaste doppelklickt.|  
|[CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md)|Wird aufgerufen, wenn der Benutzer die linke Maustaste drückt.|  
|[CWnd::OnLButtonUp](../Topic/CWnd::OnLButtonUp.md)|Wird aufgerufen, wenn der Benutzer die linke Maustaste loslässt.|  
|[CWnd::OnMButtonDblClk](../Topic/CWnd::OnMButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer mit der mittleren Maustaste doppelklickt.|  
|[CWnd::OnMButtonDown](../Topic/CWnd::OnMButtonDown.md)|Wird aufgerufen, wenn der Benutzer auf die mittlere Maustaste drückt.|  
|[CWnd::OnMButtonUp](../Topic/CWnd::OnMButtonUp.md)|Wird aufgerufen, wenn der Benutzer die mittlere Maustaste loslässt.|  
|[CWnd::OnMDIActivate](../Topic/CWnd::OnMDIActivate.md)|Wird aufgerufen, wenn ein untergeordnetes MDI\-Fenster aktiviert oder deaktiviert wird.|  
|[CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)|Wird für ein vom Besitzer gezeichnetes untergeordnetes Kombinationsfeld, Listenfeld oder Menüelement aufgerufen, wenn das Steuerelement erstellt wird.  `CWnd` informiert Windows über die Abmessungen des Steuerelements.|  
|[CWnd::OnMenuChar](../Topic/CWnd::OnMenuChar.md)|Wird aufgerufen, wenn der Benutzer auf ein mnemonisches Menüzeichen  drückt, das nicht mit den vordefinierten mnemonischen Zeichen im aktuellen Menü übereinstimmt.|  
|[CWnd::OnMenuDrag](../Topic/CWnd::OnMenuDrag.md)|Wird aufgerufen, wenn der Benutzer beginnt, ein Menüelement zu ziehen.|  
|[CWnd::OnMenuGetObject](../Topic/CWnd::OnMenuGetObject.md)|Wird aufgerufen, wenn der Mauszeiger in ein Menüelement geführt oder aus der Mitte des Elements zur Ober\- oder Unterseite des Elements bewegt wird.|  
|[CWnd::OnMenuRButtonUp](../Topic/CWnd::OnMenuRButtonUp.md)|Wird aufgerufen, wenn die rechte Maustaste losgelassen wird und sich der Cursor dabei über einem Menüelement befindet.|  
|[CWnd::OnMenuSelect](../Topic/CWnd::OnMenuSelect.md)|Wird aufgerufen, wenn der Benutzer ein Menüelement auswählt.|  
|[CWnd::OnMouseActivate](../Topic/CWnd::OnMouseActivate.md)|Wird aufgerufen, wenn sich der Cursor in einem inaktiven Fenster befindet und der Benutzer eine Maustaste drückt.|  
|[CWnd::OnMouseHover](../Topic/CWnd::OnMouseHover.md)|Wird aufgerufen, wenn der Cursor für eine gewisse in einem vorherigen Aufruf für [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) angegebene Zeit auf den Clientbereich eines Fensters zeigt.|  
|[CWnd::OnMouseHWheel](../Topic/CWnd::OnMouseHWheel.md)|Wird aufgerufen, wenn das aktuelle Fenster durch den Desktopfenster\-Manager zusammengesetzt wird und dieses Fenster maximiert ist.|  
|[CWnd::OnMouseLeave](../Topic/CWnd::OnMouseLeave.md)|Wird aufgerufen, wenn der Cursor den Clientbereich des in einem vorherigen Aufruf von [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) angegebenen Fensters verlässt.|  
|[CWnd::OnMouseMove](../Topic/CWnd::OnMouseMove.md)|Wird aufgerufen, wenn der Mauszeiger bewegt wird.|  
|[CWnd::OnMouseWheel](../Topic/CWnd::OnMouseWheel.md)|Wird aufgerufen, wenn ein Benutzer das Mausrad dreht.  Verwendet die Windows NT 4.0\-Nachrichtenverarbeitung.|  
|[CWnd::OnMove](../Topic/CWnd::OnMove.md)|Wird aufgerufen, nachdem die Position von `CWnd` geändert wurde.|  
|[CWnd::OnMoving](../Topic/CWnd::OnMoving.md)|Gibt an, dass ein Benutzer ein `CWnd`\-Objekt verschiebt.|  
|[CWnd::OnNcActivate](../Topic/CWnd::OnNcActivate.md)|Wird aufgerufen, wenn der clientfremde Bereich geändert werden muss, um einen aktiven oder inaktiven Status anzugeben.|  
|[CWnd::OnNcCalcSize](../Topic/CWnd::OnNcCalcSize.md)|Wird aufgerufen, wenn die Größe und Position des Clientbereichs berechnet werden müssen.|  
|[CWnd::OnNcCreate](../Topic/CWnd::OnNcCreate.md)|Wird vor [OnCreate](../Topic/CWnd::OnCreate.md) aufgerufen, wenn der clientfremde Bereich erstellt wird.|  
|[CWnd::OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)|Wird aufgerufen, wenn der clientfremde Bereich zerstört wird.|  
|[CWnd::OnNcHitTest](../Topic/CWnd::OnNcHitTest.md)|Wird durch Windows aufgerufen, sobald die Maus bewegt wird, wenn `CWnd` den Cursor enthält oder die Mauseingabe mit `SetCapture` erfasst hat.|  
|[CWnd::OnNcLButtonDblClk](../Topic/CWnd::OnNcLButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer mit der linken Maustaste doppelklickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcLButtonDown](../Topic/CWnd::OnNcLButtonDown.md)|Wird aufgerufen, wenn der Benutzer die linke Maustaste drückt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcLButtonUp](../Topic/CWnd::OnNcLButtonUp.md)|Wird aufgerufen, wenn der Benutzer die linke Maustaste loslässt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMButtonDblClk](../Topic/CWnd::OnNcMButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer mit der mittleren Maustaste doppelklickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMButtonDown](../Topic/CWnd::OnNcMButtonDown.md)|Wird aufgerufen, wenn der Benutzer die mittlere Maustaste drückt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMButtonUp](../Topic/CWnd::OnNcMButtonUp.md)|Wird aufgerufen, wenn der Benutzer die mittlere Maustaste loslässt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMouseHover](../Topic/CWnd::OnNcMouseHover.md)|Wird aufgerufen, wenn der Cursor für eine gewisse in einem vorherigen Aufruf für [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) angegebene Zeit auf den clientfremden Bereich eines Fensters zeigt.|  
|[CWnd::OnNcMouseLeave](../Topic/CWnd::OnNcMouseLeave.md)|Das Framework ruft diese Memberfunktion auf, wenn der Cursor den clientfremden Bereich des in einem vorherigen Aufruf für [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) angegebenen Fensters verlässt.|  
|[CWnd::OnNcMouseMove](../Topic/CWnd::OnNcMouseMove.md)|Wird aufgerufen, wenn der Cursor innerhalb eines clientfremden Bereichs von `CWnd` bewegt wird.|  
|[CWnd::OnNcPaint](../Topic/CWnd::OnNcPaint.md)|Wird aufgerufen, wenn für den clientfremden Bereich eine Zeichnung erforderlich ist.|  
|[CWnd::OnNcRButtonDblClk](../Topic/CWnd::OnNcRButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste doppelklickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcRButtonDown](../Topic/CWnd::OnNcRButtonDown.md)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste klickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcRButtonUp](../Topic/CWnd::OnNcRButtonUp.md)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste klickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcRenderingChanged](../Topic/CWnd::OnNcRenderingChanged.md)|Wird aufgerufen, wenn sich die Renderrichtlinie des Nicht\-Clientbereichs geändert hat.|  
|[CWnd::OnNcXButtonDblClk](../Topic/CWnd::OnNcXButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 doppelklickt, während sich der Cursor im clientfremden Bereich eines Fensters befindet.|  
|[CWnd::OnNcXButtonDown](../Topic/CWnd::OnNcXButtonDown.md)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 der Maus drückt, während sich der Cursor im clientfremden Bereich eines Fensters befindet.|  
|[CWnd::OnNcXButtonUp](../Topic/CWnd::OnNcXButtonUp.md)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 der Maus loslässt, während sich der Cursor im clientfremden Bereich eines Fensters befindet.|  
|[CWnd::OnNextMenu](../Topic/CWnd::OnNextMenu.md)|Wird aufgerufen, wenn der NACH\-RECHTS\- oder NACH\-LINKS\-PFEIL verwendet wird, um zwischen der Menüleiste und dem Systemmenü zu wechseln.|  
|[CWnd::OnNotify](../Topic/CWnd::OnNotify.md)|Wird durch das Framework aufgerufen, um ein übergeordnetes Fenster darüber zu informieren, dass ein Ereignis in einem seiner Steuerelemente aufgetreten ist oder dass das Steuerelement Informationen benötigt.|  
|[CWnd::OnNotifyFormat](../Topic/CWnd::OnNotifyFormat.md)|Wird aufgerufen, um zu bestimmen, ob das aktuelle Fenster ANSI\- oder Unicode\-Strukturen in der WM\_NOTIFY\-Benachrichtigung akzeptiert.|  
|[CWnd::OnPaint](../Topic/CWnd::OnPaint.md)|Wird aufgerufen, um eine Teilmenge des Fensters neu zu zeichnen.|  
|[CWnd::OnPaintClipboard](../Topic/CWnd::OnPaintClipboard.md)|Wird aufgerufen, wenn der Clientbereich der Zwischenablagenansicht neu gezeichnet werden muss.|  
|[CWnd::OnPaletteChanged](../Topic/CWnd::OnPaletteChanged.md)|Wird aufgerufen, um Fenstern zu erlauben, die eine Farbpalette verwenden, ihre logischen Paletten zu realisieren und ihre Clientbereiche zu aktualisieren.|  
|[CWnd::OnPaletteIsChanging](../Topic/CWnd::OnPaletteIsChanging.md)|Informiert andere Anwendungen, wenn eine Anwendung ihre logische Palette realisiert.|  
|[CWnd::OnParentNotify](../Topic/CWnd::OnParentNotify.md)|Wird aufgerufen, wenn ein untergeordnetes Fenster erstellt oder zerstört wird oder wenn der Benutzer eine Maustaste drückt, während sich der Cursor über einem untergeordneten Fenster befindet.|  
|[CWnd::OnPowerBroadcast](../Topic/CWnd::OnPowerBroadcast.md)|Wird aufgerufen, wenn ein Energieverwaltungsereignis auftritt.|  
|[CWnd::OnQueryDragIcon](../Topic/CWnd::OnQueryDragIcon.md)|Wird aufgerufen, wenn ein minimiertes `CWnd` \(Symbol\) durch den Benutzer gezogen wird.|  
|[CWnd::OnQueryEndSession](../Topic/CWnd::OnQueryEndSession.md)|Wird aufgerufen, wenn der Benutzer entscheidet, die Windows\-Sitzung zu beenden.|  
|[CWnd::OnQueryNewPalette](../Topic/CWnd::OnQueryNewPalette.md)|Informiert `CWnd` darüber, dass es den Eingabefokus empfängt.|  
|[CWnd::OnQueryOpen](../Topic/CWnd::OnQueryOpen.md)|Wird aufgerufen, wenn `CWnd` ein Symbol ist und der Benutzer das Öffnen des Symbols anfordert.|  
|[CWnd::OnQueryUIState](../Topic/CWnd::OnQueryUIState.md)|Wird aufgerufen, um den Benutzeroberflächenstatus \(UI\) für ein Fenster abzurufen.|  
|[CWnd::OnRawInput](../Topic/CWnd::OnRawInput.md)|Wird aufgerufen, wenn das aktuelle Fenster nicht formatierte Daten erhält.|  
|[CWnd::OnRButtonDblClk](../Topic/CWnd::OnRButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste doppelklickt.|  
|[CWnd::OnRButtonDown](../Topic/CWnd::OnRButtonDown.md)|Wird aufgerufen, wenn der Benutzer die rechte Maustaste drückt.|  
|[CWnd::OnRButtonUp](../Topic/CWnd::OnRButtonUp.md)|Wird aufgerufen, wenn der Benutzer die rechte Maustaste loslässt.|  
|[CWnd::OnRenderAllFormats](../Topic/CWnd::OnRenderAllFormats.md)|Wird aufgerufen, wenn die Inhaberanwendung zerstört wird und ihre gesamten Formate rendern muss.|  
|[CWnd::OnRenderFormat](../Topic/CWnd::OnRenderFormat.md)|Wird für den Zwischenablageinhaber aufgerufen, wenn ein bestimmtes Format mit verzögertem Rendering gerendert werden muss.|  
|[CWnd::OnSessionChange](../Topic/CWnd::OnSessionChange.md)|Wird aufgerufen, um eine Anwendung über eine Änderung im Sitzungsstatus zu informieren.|  
|[CWnd::OnSetCursor](../Topic/CWnd::OnSetCursor.md)|Wird aufgerufen, wenn die Mauseingabe nicht erfasst wird und die Maus eine Bewegung des Cursors in einem Fenster verursacht.|  
|[CWnd::OnSetFocus](../Topic/CWnd::OnSetFocus.md)|Wird aufgerufen, nachdem `CWnd` den Eingabefokus erhält.|  
|[CWnd::OnSettingChange](../Topic/CWnd::OnSettingChange.md)|Wird aufgerufen, wenn die `SystemParametersInfo`\-Win32\-Funktion eine systemübergreifende Einstellung ändert.|  
|[CWnd::OnShowWindow](../Topic/CWnd::OnShowWindow.md)|Wird aufgerufen, wenn `CWnd` ausgeblendet oder angezeigt wird.|  
|[CWnd::OnSize](../Topic/CWnd::OnSize.md)|Wird aufgerufen, nachdem die Größe von `CWnd` geändert wurde.|  
|[CWnd::OnSizeClipboard](../Topic/CWnd::OnSizeClipboard.md)|Wird aufgerufen, wenn sich die Größe des Clientbereichs des Zwischenablageanzeigefensters geändert hat.|  
|[CWnd::OnSizing](../Topic/CWnd::OnSizing.md)|Gibt an, dass der Benutzer die Größe des Rechtecks ändert.|  
|[CWnd::OnSpoolerStatus](../Topic/CWnd::OnSpoolerStatus.md)|Wird vom Druck\-Manager aufgerufen, sobald der Druck\-Manager\-Warteschlange ein Auftrag hinzugefügt wird bzw. einer aus ihr entfernt wird.|  
|[CWnd::OnStyleChanged](../Topic/CWnd::OnStyleChanged.md)|Gibt an, dass die Windows\-Funktion [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) mindestens einen Stil des Fensters geändert hat.|  
|[CWnd::OnStyleChanging](../Topic/CWnd::OnStyleChanging.md)|Gibt an, dass die Windows\-Funktion [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) mindestens einen Stil des Fensters ändert.|  
|[CWnd::OnSysChar](../Topic/CWnd::OnSysChar.md)|Wird aufgerufen, wenn eine Tastatureingabe in ein Systemzeichen übersetzt wird.|  
|[CWnd::OnSysColorChange](../Topic/CWnd::OnSysColorChange.md)|Wird für alle Fenster auf oberster Ebene aufgerufen, wenn in der Systemfarbeneinstellung eine Änderung vorgenommen wird.|  
|[CWnd::OnSysCommand](../Topic/CWnd::OnSysCommand.md)|Wird aufgerufen, wenn der Benutzer einen Befehl aus dem Steuerelementmenü auswählt oder wenn der Benutzer die Schaltfläche „Maximieren“ oder „Minimieren“ auswählt.|  
|[CWnd::OnSysDeadChar](../Topic/CWnd::OnSysDeadChar.md)|Wird aufgerufen, wenn eine Tastatureingabe in ein funktionsloses Systemzeichen \(beispielsweise Akzentzeichen\) übersetzt wird.|  
|[CWnd::OnSysKeyDown](../Topic/CWnd::OnSysKeyDown.md)|Wird aufgerufen, wenn der Benutzer die ALT\-TASTE gedrückt hält und dann eine andere Taste drückt.|  
|[CWnd::OnSysKeyUp](../Topic/CWnd::OnSysKeyUp.md)|Wird aufgerufen, wenn der Benutzer eine Taste loslässt, die gedrückt wurde, während die ALT\-TASTE gedrückt gehalten wurde.|  
|[CWnd::OnTCard](../Topic/CWnd::OnTCard.md)|Wird aufgerufen, wenn der Benutzer auf eine bearbeitbare Schaltfläche drückt|  
|[CWnd::OnTimeChange](../Topic/CWnd::OnTimeChange.md)|Wird für alle Fenster auf oberster Ebene aufgerufen, nachdem die Systemzeit geändert wurde.|  
|[CWnd::OnTimer](../Topic/CWnd::OnTimer.md)|Wird nach jedem in [SetTimer](../Topic/CWnd::SetTimer.md) angegebenen Intervall aufgerufen.|  
|[CWnd::OnTouchInput](../Topic/CWnd::OnTouchInput.md)|Verarbeitet die einzelne Eingabe aus Windows Touch.|  
|[CWnd::OnTouchInputs](../Topic/CWnd::OnTouchInputs.md)|Verarbeitet Eingaben aus Windows Touch.|  
|[CWnd::OnUniChar](../Topic/CWnd::OnUniChar.md)|Wird aufgerufen, wenn eine Taste gedrückt wird.  Das aktuelle Fenster hat demnach den Tastaturfokus, und eine [WM\_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280)\-Meldung wird durch die Funktion [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) übersetzt.|  
|[CWnd::OnUnInitMenuPopup](../Topic/CWnd::OnUnInitMenuPopup.md)|Wird aufgerufen, wenn eine Dropdownmenü oder \-untermenü zerstört wurde.|  
|[CWnd::OnUpdateUIState](../Topic/CWnd::OnUpdateUIState.md)|Wird aufgerufen, um den Benutzeroberflächenstatus für das angegebene Fenster und alle zugehörigen untergeordneten Fenster zu ändern.|  
|[CWnd::OnUserChanged](../Topic/CWnd::OnUserChanged.md)|Wird aufgerufen, nachdem sich der Benutzer an\- oder abgemeldet hat.|  
|[CWnd::OnVKeyToItem](../Topic/CWnd::OnVKeyToItem.md)|Wird als Antwort auf die [WM\_KEYDOWN](../Topic/CWnd::OnKeyDown.md)\-Meldung durch ein `CWnd` gehöriges Listenfeld aufgerufen.|  
|[CWnd::OnVScroll](../Topic/CWnd::OnVScroll.md)|Wird aufgerufen, wenn der Benutzer auf die vertikale Scrollleiste des Fensters klickt.|  
|[CWnd::OnVScrollClipboard](../Topic/CWnd::OnVScrollClipboard.md)|Wird aufgerufen, wenn der Inhaber das Zwischenablagebild scrollen, den entsprechenden Abschnitt ungültig machen und die Scrollleistenwerte aktualisieren sollte.|  
|[CWnd::OnWindowPosChanged](../Topic/CWnd::OnWindowPosChanged.md)|Wird aufgerufen, wenn sich die Größe, Position oder Z\-Reihenfolge infolge eines Aufrufs für [SetWindowPos](../Topic/CWnd::SetWindowPos.md) oder einer anderen Fensterverwaltungsfunktion geändert hat.|  
|[CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)|Wird aufgerufen, wenn sich die Größe, Position oder Z\-Reihenfolge infolge eines Aufrufs für [SetWindowPos](../Topic/CWnd::SetWindowPos.md) oder einer anderen Fensterverwaltungsfunktion ändert.|  
|[CWnd::OnWinIniChange](../Topic/CWnd::OnWinIniChange.md)|Wird für alle Fenster auf oberster Ebene aufgerufen, nachdem die Windows\-Initialisierungsdatei \(WIN.INI\) geändert wird.|  
|[CWnd::OnWndMsg](../Topic/CWnd::OnWndMsg.md)|Gibt an, ob eine Fenstermeldung verarbeitet wurde.|  
|[CWnd::OnXButtonDblClk](../Topic/CWnd::OnXButtonDblClk.md)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 doppelklickt, während sich der Cursor im Clientbereich eines Fensters befindet.|  
|[CWnd::OnXButtonDown](../Topic/CWnd::OnXButtonDown.md)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 drückt, während sich der Cursor im Clientbereich eines Fensters befindet.|  
|[CWnd::OnXButtonUp](../Topic/CWnd::OnXButtonUp.md)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 loslässt, während sich der Cursor im Clientbereich eines Fensters befindet.|  
|[CWnd::PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)|Diese virtuelle Funktion wird durch die standardmäßige [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)\-Funktion aufgerufen, nachdem das Fenster zerstört wurde.|  
|[CWnd::ReflectChildNotify](../Topic/CWnd::ReflectChildNotify.md)|Hilfsfunktion, die eine Meldung an ihre Quelle weitergibt.|  
|[CWnd::ReflectLastMsg](../Topic/CWnd::ReflectLastMsg.md)|Gibt die letzte Meldung zum untergeordneten Fenster weiter.|  
|[CWnd::ResizeDynamicLayout](../Topic/CWnd::ResizeDynamicLayout.md)|Wird durch das Framework aufgerufen, wenn sich die Fenstergröße ändert, um das Layout der untergeordneten Fenster anzupassen, wenn das dynamische Layout für das Fenster aktiviert ist.|  
|[CWnd::WindowProc](../Topic/CWnd::WindowProc.md)|Stellt eine Fensterprozedur für `CWnd` bereit.  Der Standard versendet Meldungen über die Meldungszuordnung.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWnd::operator HWND](../Topic/CWnd::operator%20HWND.md)|Nehmen Sie einen Aufruf vor, um ein Handle zu einem Fenster zu erhalten.|  
|[CWnd::operator \!\=](../Topic/CWnd::operator%20!=.md)|Ermittelt, ob ein Fenster nicht dem Fenster entspricht, dessen Handle [m\_hWnd](../Topic/CWnd::m_hWnd.md) ist.|  
|[CWnd::operator \=\=](../Topic/CWnd::operator%20==.md)|Ermittelt, ob ein Fenster dem Fenster entspricht, dessen Handle [m\_hWnd](../Topic/CWnd::m_hWnd.md) ist.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWnd::m\_hWnd](../Topic/CWnd::m_hWnd.md)|Gibt das an `CWnd` angefügte `HWND` an.|  
  
## Hinweise  
 Ein `CWnd`\-Objekt unterscheidet sich von einem Windows\-Fenster, aber beide sind jedoch eng miteinander verknüpft.  Ein `CWnd`\-Objekt wird durch den `CWnd`\-Konstruktor und \-Dekonstruktor erstellt oder zerstört.  Beim Windows\-Fenster handelt es sich wiederum um eine für Windows interne Datenstruktur, die über die Memberfunktion **Create** erstellt und mithilfe des virtuellen Destruktors `CWnd` zerstört wird.  Die Funktion [DestroyWindow](../Topic/CWnd::DestroyWindow.md) zerstört das Windows\-Fenster, ohne das Objekt zu zerstören.  
  
 Die `CWnd`\-Klasse und der Meldungszuordnungsmechanismus blenden die Funktion **WndProc** aus.  Eingehende Windows\-Benachrichtigungsmeldungen werden automatisch über die Meldungszuordnung an die entsprechenden **On***Message* `CWnd`\-Memberfunktionen umgeleitet.  Sie überschreiben eine **On***Message*\-Memberfunktion, um eine bestimmte Meldung des Members in Ihren abgeleiteten Klassen zu verarbeiten.  
  
 Mithilfe der `CWnd`\-Klasse können Sie auch ein untergeordnetes Windows\-Fenster für Ihre Anwendung erstellen.  Leiten Sie eine Klasse aus `CWnd` ab, fügen Sie dann der abgeleiteten Klasse Membervariablen hinzu, um für Ihre Anwendung spezifische Daten zu speichern.  Implementieren Sie Meldungshandler\-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Ein untergeordnetes Fenster wird in zwei Schritten erstellt.  Rufen Sie zunächst den Konstruktor `CWnd` zum Erstellen des `CWnd`\-Objekts auf. Rufen Sie anschließend die Memberfunktion [Create](../Topic/CWnd::Create.md) auf, um das untergeordnete Fenster zu erstellen und es an das `CWnd`\-Objekt anzufügen.  
  
 Wenn der Benutzer Ihr untergeordnetes Fenster beendet, zerstören Sie das Objekt `CWnd`, oder rufen Sie die Memberfunktion `DestroyWindow` auf, um das Fenster zu entfernen und dessen Datenstrukturen zu zerstören.  
  
 In der Microsoft Foundation Class\-Bibliothek werden weitere Klassen aus `CWnd` abgeleitet, um bestimmte Fenstertypen bereitzustellen.  Viele der Klassen, einschließlich [CFrameWnd](../../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md), [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md), [CView](../../mfc/reference/cview-class.md) und [CDialog](../../mfc/reference/cdialog-class.md), sind für die weitere Ableitung ausgelegt.  Die aus `CWnd` abgeleiteten Steuerelementklassen wie [CButton](../../mfc/reference/cbutton-class.md) können direkt oder für die weitere Ableitung von Klassen verwendet werden.  
  
 Weitere Informationen über die Verwendung von `CWnd` finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md) und [Fensterobjekte](../../mfc/window-objects.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWnd`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)