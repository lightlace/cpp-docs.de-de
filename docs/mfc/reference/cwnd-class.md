---
title: CWnd-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- windows [C++]
- window objects [C++]
- CWnd class
ms.assetid: 49a832ee-bc34-4126-88b3-bc1d9974f6c4
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ab9007e512f5af43bdace06796fb8487ffebc8e6
ms.lasthandoff: 02/24/2017

---
# <a name="cwnd-class"></a>CWnd-Klasse
Stellt die Basisfunktionalität aller Fensterklassen der Microsoft Foundation Class-Bibliothek bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWnd : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWnd::CWnd](#cwnd)|Erstellt ein `CWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWnd::accDoDefaultAction](#accdodefaultaction)|Wird durch das Framework aufgerufen, um die Standardaktion des Objekts auszuführen.|  
|[CWnd::accHitTest](#acchittest)|Wird durch das Framework aufgerufen, um das untergeordnete Element oder untergeordnete Objekt an einem bestimmten Punkt auf dem Bildschirm abzurufen.|  
|[CWnd::accLocation](#acclocation)|Wird durch das Framework aufgerufen, um die aktuelle Bildschirmposition des angegebenen Objekts abzurufen.|  
|[CWnd::accNavigate](#accnavigate)|Wird durch das Framework aufgerufen, um zu einem anderen Benutzer-Schnittstellenelement innerhalb eines Containers zu gelangen und wenn möglich, das Objekt abzurufen.|  
|[CWnd::accSelect](#accselect)|Wird durch das Framework aufgerufen, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben.|  
|[CWnd::AnimateWindow](#animatewindow)|Animiert das zugeordnete Fensterobjekt.|  
|[CWnd::ArrangeIconicWindows](#arrangeiconicwindows)|Ordnet alle minimierten untergeordneten Fenster (Symbole).|  
|[CWnd::Attach](#attach)|Fügt ein Windows-Handle zu einem `CWnd`-Objekt hinzu.|  
|[CWnd::BeginModalState](#beginmodalstate)|Rufen Sie diese Memberfunktion auf, um ein Framefenster modal zu machen.|  
|[CWnd::BeginPaint](#beginpaint)|Bereit `CWnd` für die Zeichnung vor.|  
|[CWnd::BindDefaultProperty](#binddefaultproperty)|Bindet die standardmäßige einfache gebundene Eigenschaft des aufrufenden Objekts gemäß der Markierung in der Typenbibliothek an einen Cursor, der mit dem Datenquellen-Steuerelement verknüpft ist.|  
|[CWnd:: BindProperty](#bindproperty)|Bindet eine cursorgebundene Eigenschaft auf einem datengebundenen Steuerelement mit einem Datenquellen-Steuerelement und registriert diese Beziehung mit dem MFC-Bindungs-Manager.|  
|[CWnd::BringWindowToTop](#bringwindowtotop)|Bringt `CWnd` nach oben im Stapel überlappender Fenster.|  
|[CWnd::CalcWindowRect](#calcwindowrect)|Wird aufgerufen, um das Fensterrechtecke aus dem Clientrechteck zu berechnen.|  
|[CWnd::CancelToolTips](#canceltooltips)|Deaktiviert das QuickInfo-Steuerelement.|  
|[CWnd::CenterWindow](#centerwindow)|Zentriert ein Fenster relativ zu dessen übergeordnetem Element.|  
|[CWnd::ChangeClipboardChain](#changeclipboardchain)|Entfernt `CWnd` aus der Kette der Zwischenablageansichten.|  
|[CWnd::CheckDlgButton](#checkdlgbutton)|Setzt ein Häkchen neben einem Schaltflächensteuerelement oder entfernt ein Häkchen aus einem Schaltflächensteuerelement.|  
|[CWnd::CheckRadioButton](#checkradiobutton)|Überprüft das angegebene Optionsfeld und entfernt das Häkchen aus allen anderen Optionsfeldern in der angegebenen Gruppe der Schaltflächen.|  
|[CWnd::ChildWindowFromPoint](#childwindowfrompoint)|Ermittelt welches der untergeordneten Fenster ggf. den angegebenen Punkt enthält.|  
|[CWnd::ClientToScreen](#clienttoscreen)|Konvertiert die Clientkoordinaten eines bestimmten Punkts oder Rechtecks auf der Anzeige zu Bildschirmkoordinaten.|  
|[CWnd::CloseWindow](#closewindow)|Minimiert das Fenster.|  
|[CWnd::ContinueModal](#continuemodal)|Setzt den modalen Status eines Fensters fort.|  
|[CWnd:: Create](#create)|Erstellt und initialisiert das untergeordnete Fenster, das mit dem `CWnd`-Objekt verknüpft ist.|  
|[CWnd::CreateAccessibleProxy](#createaccessibleproxy)|Erstellt einen Active Accessibility-Proxy für das angegebene Objekt.|  
|[CWnd::CreateCaret](#createcaret)|Erstellt eine neue Form für den Systemzeiger und ruft die Inhaberschaft des Caretzeichens ab.|  
|[CWnd:: CreateControl](#createcontrol)|Erstellt ein ActiveX-Steuerelement, das in einem MFC-Programm durch ein `CWnd`-Objekt dargestellt wird.|  
|[CWnd::CreateEx](#createex)|Erstellt ein überlapptes, Popup- oder untergeordnetes Fenster von Windows und fügt es an ein `CWnd`-Objekt an.|  
|[CWnd::CreateGrayCaret](#creategraycaret)|Erstellt einen grauen Block für den Systemzeiger und ruft die Inhaberschaft des Caretzeichens ab.|  
|[CWnd::CreateSolidCaret](#createsolidcaret)|Erstellt einen durchgezogenen Block für den Systemzeiger und ruft die Inhaberschaft des Caretzeichens ab.|  
|[CWnd::DeleteTempMap](#deletetempmap)|Wird automatisch durch den `CWinApp`-Leerlaufzeithandler aufgerufen, wobei durch `FromHandle` erstellte temporäre `CWnd`-Objekte gelöscht werden.|  
|[CWnd:: DestroyWindow](#destroywindow)|Zerstört das angefügte Windows-Fenster.|  
|[CWnd::Detach](#detach)|Trennt ein Windows-Handle von einem `CWnd`-Objekt und gibt das Handle zurück.|  
|[CWnd::DlgDirList](#dlgdirlist)|Füllt ein Listenfeld mit einer Datei- oder Verzeichnisauflistung auf.|  
|[CWnd::DlgDirListComboBox](#dlgdirlistcombobox)|Füllt das Listenfeld eines Kombinationsfelds mit einer Datei- oder Verzeichnisauflistung auf.|  
|[CWnd::DlgDirSelect](#dlgdirselect)|Ruft die aktuelle Auswahl aus einem Listenfeld ab.|  
|[CWnd::DlgDirSelectComboBox](#dlgdirselectcombobox)|Ruft die neueste Auswahl aus dem Listenfeld von einem Kombinationsfeld ab.|  
|[CWnd::DragAcceptFiles](#dragacceptfiles)|Gibt an, dass das Fenster gezogene Dateien akzeptiert.|  
|[CWnd::DragDetect](#dragdetect)|Erfasst die Maus und zeichnet ihre Bewegung auf, bis der Benutzer die linke Maustaste loslässt, die ESC-Taste drückt oder die Maus so bewegt, dass sie sich außerhalb des Ziehrechtecks um den angegebenen Punkt herum befindet.|  
|[CWnd::DrawAnimatedRects](#drawanimatedrects)|Zeichnet ein Drahtrahmenrechteck und animiert es, um das Öffnen eines Symbols oder das Minimieren bzw. Maximieren eines Fensters anzudeuten.|  
|[CWnd::DrawCaption](#drawcaption)|Zeichnet eine Beschriftung.|  
|[CWnd::DrawMenuBar](#drawmenubar)|Zeichnet die Menüleiste neu.|  
|[CWnd::EnableActiveAccessibility](#enableactiveaccessibility)|Aktiviert benutzerdefinierte `Active Accessibility`-Funktionen.|  
|[CWnd::EnableDynamicLayout](#enabledynamiclayout)|Ermöglicht, dass die Position und Größe von untergeordneten Fenstern automatisch angepasst werden können, wenn der Benutzer die Größe des Fensters ändert.|  
|[CWnd::EnableD2DSupport](#enabled2dsupport)|Aktiviert oder deaktiviert die Fensterunterstützung für `D2D`. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|  
|[CWnd::EnableScrollBar](#enablescrollbar)|Aktiviert oder deaktiviert einen oder beide Pfeile auf einer Scrollleiste.|  
|[CWnd::EnableScrollBarCtrl](#enablescrollbarctrl)|Aktiviert oder deaktiviert ein gleichgeordnetes Scrollleisten-Steuerelement.|  
|[CWnd:: EnableToolTips](#enabletooltips)|Aktiviert das QuickInfo-Steuerelement.|  
|[CWnd::EnableTrackingToolTips](#enabletrackingtooltips)|Aktiviert das QuickInfo-Steuerelement im Überwachungsmodus.|  
|[CWnd::EnableWindow](#enablewindow)|Aktiviert oder deaktiviert die Maus- und Tastatureingaben.|  
|[CWnd::EndModalLoop](#endmodalloop)|Beendet den modalen Status eines Fensters.|  
|[CWnd::EndModalState](#endmodalstate)|Rufen Sie diese Memberfunktion auf, um ein Framefenster von einem modalen in einen Status ohne Modus zu ändern.|  
|[CWnd::EndPaint](#endpaint)|Markiert das Ende der Zeichnung.|  
|[CWnd::ExecuteDlgInit](#executedlginit)|Initiiert eine Dialogfeldressource.|  
|[CWnd:: FilterToolTipMessage](#filtertooltipmessage)|Ruft den Titel oder Text ab, der mit einem Steuerelement in einem Dialogfeld verknüpft ist.|  
|[CWnd::FindWindow](#findwindow)|Gibt das Handle für das Fenster zurück, das anhand seines Fensternamens und seiner Fensterklasse bestimmt wird.|  
|[CWnd::FindWindowEx](#findwindowex)|Gibt das Handle für das Fenster zurück, das anhand seines Fensternamens und seiner Fensterklasse bestimmt wird.|  
|[CWnd::FlashWindow](#flashwindow)|Bringt das Fenster einmal zum Blinken.|  
|[CWnd::FlashWindowEx](#flashwindowex)|Bringt das Fenster mit zusätzlicher Funktionalität zum Blinken.|  
|[CWnd:: FromHandle](#fromhandle)|Gibt einen Zeigt zu einem `CWnd`-Objekt zurück, wenn ein Handle zu einem Fenster vorhanden ist.  Wenn ein `CWnd`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CWnd`-Objekt erstellt und angefügt.|  
|[CWnd::FromHandlePermanent](#fromhandlepermanent)|Gibt einen Zeigt zu einem `CWnd`-Objekt zurück, wenn ein Handle zu einem Fenster vorhanden ist.  Wenn ein `CWnd`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CWnd`-Objekt erstellt und angefügt.|  
|[CWnd::get_accChild](#get_accchild)|Wird durch das Framework aufgerufen, um die Adresse einer `IDispatch`-Schnittstelle für das angegebene, untergeordnete Element abzurufen.|  
|[CWnd::get_accChildCount](#get_accchildcount)|Wird durch das Framework aufgerufen, um die Zahl der untergeordneten Elemente abzurufen, die zu diesem Objekt gehören.|  
|[CWnd::get_accDefaultAction](#get_accdefaultaction)|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die Standardaktion des Objekts beschreibt.|  
|[CWnd::get_accDescription](#get_accdescription)|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt.|  
|[CWnd::get_accFocus](#get_accfocus)|Wird durch das Framework aufgerufen, um das Objekt abzurufen, das den Tastaturfokus hat.|  
|[CWnd::get_accHelp](#get_acchelp)|Zum Abrufen eines Objekts aufgerufen **Hilfe** Eigenschaftenzeichenfolge.|  
|[CWnd::get_accHelpTopic](#get_acchelptopic)|Wird durch das Framework aufgerufen, um den vollständigen Pfad der `WinHelp`-Datei abzurufen, die mit dem angegebenen Objekt verbunden ist und dem Bezeichner des passenden Themas innerhalb dieser Datei.|  
|[CWnd::get_accKeyboardShortcut](#get_acckeyboardshortcut)|Wird durch das Framework aufgerufen, um die Tastenkombination oder Zugriffstaste des angegebenen Objekts abzurufen.|  
|[CWnd::get_accName](#get_accname)|Wird durch das Framework aufgerufen, um den Namen des angegebenen Objekts abzurufen.|  
|[CWnd::get_accParent](#get_accparent)|Wird durch das Framework aufgerufen, um die `IDispatch`-Schnittstelle des übergeordneten Elements des Objekts abzurufen.|  
|[CWnd::get_accRole](#get_accrole)|Wird durch das Framework aufgerufen, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreiben.|  
|[CWnd::get_accSelection](#get_accselection)|Wird durch das Framework aufgerufen, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen.|  
|[CWnd::get_accState](#get_accstate)|Wird durch das Framework aufgerufen, um den aktuellen Status des angegebenen Objekts abzurufen.|  
|[CWnd::get_accValue](#get_accvalue)|Wird durch das Framework aufgerufen, um den Wert des angegebenen Objekts abzurufen.|  
|[CWnd::GetActiveWindow](#getactivewindow)|Ruft das aktive Fenster ab.|  
|[CWnd::GetAncestor](#getancestor)|Ruft das Vorgängerfensterobjekt des angegebenen Fensters ab.|  
|[CWnd::GetCapture](#getcapture)|Ruft das von der Maus erfasste `CWnd` ab.|  
|[CWnd::GetCaretPos](#getcaretpos)|Ruft die Clientkoordinaten der aktuellen Position des Caretzeichens ab.|  
|[CWnd::GetCheckedRadioButton](#getcheckedradiobutton)|Gibt die ID des derzeit aktivierten Optionsfelds in einer Gruppe von Optionsfeldern zurück.|  
|[GetClientRect](#getclientrect)|Ruft die Abmessungen des `CWnd`-Clientbereichs ab.|  
|[CWnd::GetClipboardOwner](#getclipboardowner)|Ruft einen Zeiger zum aktuellen Inhaber der Zwischenablage ab.|  
|[CWnd::GetClipboardViewer](#getclipboardviewer)|Ruft einen Zeiger zum ersten Fenster in einer Kette von Zwischenablageansichten ab.|  
|[CWnd::GetControlUnknown](#getcontrolunknown)|Ruft einen Zeiger zu einem unbekannten ActiveX-Steuerelement ab.|  
|[CWnd::GetDC](#getdc)|Ruft einen Anzeigekontext für den Clientbereich ab.|  
|[CWnd::GetDCEx](#getdcex)|Ruft einen Anzeigekontext für den Clientbereich ab und aktiviert Clipping beim Zeichnen.|  
|[CWnd::GetDCRenderTarget](#getdcrendertarget)|Ruft das Renderziel des Geräts Gerätekontext (DC) für das `CWnd`-Fenster ab.|  
|[CWnd::GetDescendantWindow](#getdescendantwindow)|Sucht alle Nachfolgerfenster und gibt das Fenster mit der angegebenen ID zurück.|  
|[CWnd::GetDesktopWindow](#getdesktopwindow)|Ruft das Windows-Desktopfenster ab.|  
|[CWnd::GetDlgCtrlID](#getdlgctrlid)|Wenn es sich bei `CWnd` um ein untergeordnetes Fenster handelt, wird durch den Aufruf dieser Funktion der zugehörige ID-Wert zurückgegeben.|  
|[GetDlgItem](#getdlgitem)|Ruft das Steuerelement mit der angegebenen ID aus dem angegebenen Dialogfeld ab.|  
|[CWnd::GetDlgItemInt](#getdlgitemint)|Übersetzt den Text eines Steuerelements im angegebenen Dialogfeld in einen Ganzzahlenwert.|  
|[CWnd::GetDlgItemText](#getdlgitemtext)|Ruft die Beschriftung oder den Text ab, die bzw. der mit einem Steuerelement verknüpft ist.|  
|[CWnd::GetDSCCursor](#getdsccursor)|Ruft einen Zeiger zum zugrunde liegenden Cursor eines Datenquellen-Steuerelements ab, der durch die Eigenschaften „DataSource“, „UserName“, „Password“ und „SQL“ definiert ist.|  
|[CWnd::GetDynamicLayout](#getdynamiclayout)|Ruft einen Zeiger zum dynamischen Layout-Manager-Objekt ab.|  
|[CWnd::GetExStyle](#getexstyle)|Gibt den erweiterten Stil des Fensters zurück.|  
|[CWnd::GetFocus](#getfocus)|Ruft `CWnd` ab, das derzeit über den Eingabefokus verfügt.|  
|[CWnd::GetFont](#getfont)|Ruft die aktuelle Schriftart ab.|  
|[CWnd::GetForegroundWindow](#getforegroundwindow)|Gibt einen Zeiger zum Vordergrundfenster (das Fenster auf oberster Ebene, mit dem der Benutzer aktuell arbeitet) zurück.|  
|[CWnd::GetIcon](#geticon)|Ruft das Handle für ein Symbol ab.|  
|[CWnd::GetLastActivePopup](#getlastactivepopup)|Bestimmt, welches `CWnd` gehörige Popupfenster zuletzt aktiv war.|  
|[CWnd::GetLayeredWindowAttributes](#getlayeredwindowattributes)|Ruft die Deckkraft- und Transparenzfarbenschlüssel eines überlappenden Fensters ab.|  
|[CWnd::GetMenu](#getmenu)|Ruft einen Zeiger zum angegebenen Menü ab.|  
|[CWnd::GetNextDlgGroupItem](#getnextdlggroupitem)|Sucht nach dem nächsten (oder vorherigen) Steuerelement in einer Steuerelementgruppe.|  
|[CWnd::GetNextDlgTabItem](#getnextdlgtabitem)|Ruft das erste Steuerelement mit der [WS_TABSTOP](window-styles.md) Format, das das angegebene Steuerelement folgt (oder vorangestellt).|  
|[CWnd::GetNextWindow](#getnextwindow)|Gibt das nächste (oder vorherige) Fenster in der Liste des Fenster-Managers zurück.|  
|[CWnd::GetOleControlSite](#getolecontrolsite)|Ruft die benutzerdefinierte Site für das angegebene ActiveX-Steuerelement ab.|  
|[CWnd::GetOpenClipboardWindow](#getopenclipboardwindow)|Ruft einen Zeiger zum Fenster ab, bei dem die Zwischenablage aktuell geöffnet ist.|  
|[CWnd::GetOwner](#getowner)|Rift einen Zeiger zum Inhaber von `CWnd` ab.|  
|[CWnd::GetParent](#getparent)|Ruft das übergeordnete Fenster von `CWnd` (sofern vorhanden) ab.|  
|[CWnd::GetParentFrame](#getparentframe)|Ruft das übergeordnete Framefenster des `CWnd`-Objekts ab.|  
|[CWnd::GetParentOwner](#getparentowner)|Gibt einen Zeiger zum übergeordneten Fenster eines untergeordneten Fensters zurück.|  
|[CWnd::GetProperty](#getproperty)|Ruft eine ActiveX-Steuerelementeigenschaft ab.|  
|[CWnd::GetRenderTarget](#getrendertarget)|Ruft ein Renderziel ab, das mit diesem Fenster verknüpft ist.|  
|[CWnd::GetSafeHwnd](#getsafehwnd)|Gibt `m_hWnd` oder `NULL` zurück, wenn der `this`-Zeiger `NULL` ist.|  
|[CWnd::GetSafeOwner](#getsafeowner)|Ruft den sicheren Inhaber für das angegebene Fenster ab.|  
|[CWnd:: Getscrollbarctrl](#getscrollbarctrl)|Gibt ein gleichgeordnetes Scrollleistensteuerelement zurück.|  
|[CWnd::GetScrollBarInfo](#getscrollbarinfo)|Ruft Informationen über die angegebene Bildlaufleiste ab.|  
|[CWnd::GetScrollInfo](#getscrollinfo)|Ruft die Informationen ab, die von der `SCROLLINFO`-Struktur über eine Scrollleiste verwaltet werden.|  
|[CWnd::GetScrollLimit](#getscrolllimit)|Ruft den Grenzwert der Scrollleiste ab.|  
|[CWnd::GetScrollPos](#getscrollpos)|Ruft die aktuelle Position eines Scrollfelds ab.|  
|[CWnd::GetScrollRange](#getscrollrange)|Kopiert die aktuellen minimalen und maximalen Positionen der Scrollleiste für eine bestimmte Scrollleiste.|  
|[CWnd::GetStyle](#getstyle)|Gibt den aktuellen Fensterstil zurück.|  
|[CWnd::GetSystemMenu](#getsystemmenu)|Ermöglicht der Anwendung, auf das Steuerelementmenü zuzugreifen, um Kopier- und Änderungsvorgänge vorzunehmen.|  
|[CWnd::GetTitleBarInfo](#gettitlebarinfo)|Ruft Informationen über die angegebene Titelleiste ab.|  
|[CWnd::GetTopLevelFrame](#gettoplevelframe)|Ruft das Framefenster auf oberster Ebene des Fensters ab.|  
|[CWnd::GetTopLevelOwner](#gettoplevelowner)|Ruft das Fenster auf der obersten Ebene ab.|  
|[CWnd::GetTopLevelParent](#gettoplevelparent)|Ruft das übergeordnete Element auf oberster Ebene des Fensters ab.|  
|[CWnd::GetTopWindow](#gettopwindow)|Gibt das erste untergeordnete Element zurück, das zu `CWnd` gehört.|  
|[CWnd::GetUpdateRect](#getupdaterect)|Ruft die Koordinaten des kleines Rechtecks ab, das die `CWnd`-Aktualisierungsregion komplett umschließt.|  
|[CWnd::GetUpdateRgn](#getupdatergn)|Ruft die `CWnd`-Aktualisierungsregion ab.|  
|[CWnd::GetWindow](#getwindow)|Gibt das Fenster mit der angegebenen Beziehung zu diesem Fenster zurück.|  
|[CWnd::GetWindowContextHelpId](#getwindowcontexthelpid)|Ruft den Hilfekontextbezeichner ab.|  
|[CWnd::GetWindowDC](#getwindowdc)|Ruft den Anzeigekontext für das gesamte Fenster, einschließlich Titelleiste, Menüs und Scrollleisten, ab.|  
|[CWnd::GetWindowedChildCount](#getwindowedchildcount)|Gibt die Anzahl der zugehörigen untergeordneten Fenster zurück.|  
|[CWnd::GetWindowInfo](#getwindowinfo)|Gibt Informationen über das Fenster zurück.|  
|[CWnd::GetWindowlessChildCount](#getwindowlesschildcount)|Gibt die Anzahl der zugehörigen untergeordneten Fenster ohne Fenster zurück.|  
|[CWnd::GetWindowPlacement](#getwindowplacement)|Ruft den Anzeigestatus und die normalen (wiederhergestellt), minimierten und maximierten Positionen eines Fensters ab.|  
|[CWnd::GetWindowRect](#getwindowrect)|Ruft die Bildschirmkoordinaten von `CWnd` ab.|  
|[CWnd::GetWindowRgn](#getwindowrgn)|Ruft eine Kopie der Fensterregion eines Fensters ab.|  
|[CWnd::GetWindowText](#getwindowtext)|Gibt den Fenstertext oder Beschriftungstitel (sofern vorhanden) zurück.|  
|[CWnd::GetWindowTextLength](#getwindowtextlength)|Gibt die Länge des Texts oder Beschriftungstitels des Fensters zurück.|  
|[CWnd::HideCaret](#hidecaret)|Blendet das Caretzeichen aus, indem es auf dem Anzeigebildschirm entfernt wird.|  
|[CWnd::HiliteMenuItem](#hilitemenuitem)|Hebt die Hervorhebung eines Menüelements auf oberster Ebene (Menüleiste) hervor oder entfernt sie.|  
|[CWnd::HtmlHelp](#htmlhelp)|Wird aufgerufen, um die HTMLHelp-Anwendung zu initiieren.|  
|[CWnd::Invalidate](#invalidate)|Macht den gesamten Clientbereich ungültig.|  
|[CWnd::InvalidateRect](#invalidaterect)|Macht den Clientbereich im angegebenen Rechteck ungültig, indem dieses Rechteck zur aktuellen Aktualisierungsregion hinzugefügt wird.|  
|[CWnd::InvalidateRgn](#invalidatergn)|Macht den Clientbereich in der angegebenen Region ungültig, indem diese Region zur aktuellen Aktualisierungsregion hinzugefügt wird.|  
|[CWnd::InvokeHelper](#invokehelper)|Ruft eine ActiveX-Steuerelementmethode oder -Eigenschaft ab.|  
|[CWnd::IsChild](#ischild)|Gibt an, ob `CWnd` ein untergeordnetes Fenster oder ein weiterer direkter Nachfolger des angegebenen Fensters ist.|  
|[CWnd::IsD2DSupportEnabled](#isd2dsupportenabled)|Bestimmt, ob die `D2D`-Unterstützung aktiviert ist.|  
|[CWnd::IsDialogMessage](#isdialogmessage)|Bestimmt, ob die angegebene Meldung für das Dialogfeld ohne Modus vorgesehen ist, und wenn dies der Fall ist, erfolgt die entsprechende Verarbeitung.|  
|[CWnd::IsDlgButtonChecked](#isdlgbuttonchecked)|Bestimmt, ob ein Schaltflächensteuerelement aktiviert ist.|  
|[CWnd::IsDynamicLayoutEnabled](#isdynamiclayoutenabled)|Bestimmt, ob das dynamische Layout in diesem Fenster aktiviert ist. Wenn das dynamische Layout aktiviert ist, können sich die Position und die Größe der untergeordneten Fenster ändern, wenn der Benutzer die Größe des übergeordneten Fensters ändert.|  
|[CWnd::IsIconic](#isiconic)|Bestimmt, ob `CWnd` minimiert (Symbol) ist.|  
|[CWnd::IsTouchWindow](#istouchwindow)|Gibt an, ob `CWnd` über die Fingereingabeunterstützung verfügt.|  
|[CWnd::IsWindowEnabled](#iswindowenabled)|Bestimmt, ob das Fenster für die Maus- und Tastatureingabe aktiviert ist.|  
|[CWnd::IsWindowVisible](#iswindowvisible)|Bestimmt, ob das Fenster sichtbar ist.|  
|[CWnd::IsZoomed](#iszoomed)|Bestimmt, ob `CWnd` maximiert ist.|  
|[CWnd::KillTimer](#killtimer)|Beendet einen Systemzeitgeber.|  
|[CWnd::LockWindowUpdate](#lockwindowupdate)|Deaktiviert oder aktiviert die Zeichnung im angegebenen Fenster erneut.|  
|[CWnd::MapWindowPoints](#mapwindowpoints)|Konvertiert (Zuordnung) einen Satz von Punkten aus dem Koordinatenbereich von `CWnd` zum Koordinatenbereich des anderen Fensters.|  
|[CWnd::MessageBox](#messagebox)|Erstellt und zeigt ein Fenster an, das eine über die Anwendung bereitgestellte Meldung und Beschriftung aufweist.|  
|[CWnd::ModifyStyle](#modifystyle)|Ändert den aktuellen Fensterstil.|  
|[CWnd::ModifyStyleEx](#modifystyleex)|Ändert den erweiterten Stil des Fensters.|  
|[CWnd::MoveWindow](#movewindow)|Ändert die Position und die Abmessungen von `CWnd`.|  
|[CWnd::NotifyWinEvent](#notifywinevent)|Signalisiert dem System, dass ein vordefiniertes Ereignis aufgetreten ist.|  
|[CWnd::OnAmbientProperty](#onambientproperty)|Implementieren Sie die Ambient-Eigenschaftswerte.|  
|[CWnd::OnDrawIconicThumbnailOrLivePreview](#ondrawiconicthumbnailorlivepreview)|Wird durch das Framework aufgerufen, wenn es eine auf der Windows 7-Registerkartenminiaturansicht oder auf dem Client für die Anwendungsvorschau anzuzeigende Bitmap abrufen muss.|  
|[CWnd::OnHelp](#onhelp)|Verarbeitet die F1-Hilfe in der Anwendung (unter Verwendung des aktuellen Kontexts).|  
|[CWnd::OnHelpFinder](#onhelpfinder)|Verarbeitet die Befehle `ID_HELP_FINDER` und `ID_DEFAULT_HELP`.|  
|[CWnd::OnHelpIndex](#onhelpindex)|Verarbeitet den Befehl `ID_HELP_INDEX` und stellt ein standardmäßiges Hilfethema bereit.|  
|[CWnd::OnHelpUsing](#onhelpusing)|Verarbeitet den Befehl `ID_HELP_USING`.|  
|[CWnd::OnToolHitTest](#ontoolhittest)|Legt fest, ob sich ein Punkt im umgebenden Rechteck des angegebenen Tools befindet und fragt Informationen über das Tool ab.|  
|[CWnd::OpenClipboard](#openclipboard)|Öffnet die Zwischenablage. Andere Programme werden nicht in der Lage, ändern die Zwischenablage bis Windows [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) -Funktion aufgerufen wird.|  
|[CWnd::PaintWindowlessControls](#paintwindowlesscontrols)|Zeichnet fensterlose Steuerelemente auf dem Steuerelementcontainer.|  
|[CWnd::PostMessage](#postmessage)|Platziert eine Nachricht in der Anwendungswarteschlange, nimmt dann eine Rückgabe vor, ohne darauf zu warten, dass das Fenster die Nachricht verarbeitet.|  
|[CWnd::PreCreateWindow](#precreatewindow)|Wird vor der Erstellung des an diesem `CWnd`-Objekt angefügten Windows-Fensters aufgerufen.|  
|[CWnd::PreSubclassWindow](#presubclasswindow)|Ermöglicht anderen erforderlichen Unterklassen vor der [SubclassWindow](#subclasswindow) aufgerufen wird.|  
|[CWnd:: PreTranslateMessage](#pretranslatemessage)|Wird durch `CWinApp` verwendet, um Fenstermeldungen zu filtern, bevor sie an die Windows-Funktionen `TranslateMessage` und `DispatchMessage` gesendet werden.|  
|[CWnd::Print](#print)|Zeichnet das aktuelle Fenster in den angegebenen Gerätekontext.|  
|[CWnd::PrintClient](#printclient)|Zeichnet alle Fenster in den angegebenen Gerätekontext (für gewöhnlich einen Druckergerätkontext).|  
|[CWnd::PrintWindow](#printwindow)|Kopiert ein visuelles Fenster in den angegebenen Gerätekontext, für gewöhnlich handelt es sich dabei um einen Druckerdomänencontroller.|  
|[CWnd::RedrawWindow](#redrawwindow)|Aktualisiert das angegebene Rechteck bzw. die Region im Clientbereich.|  
|[CWnd::RegisterTouchWindow](#registertouchwindow)|Registrieren Sie das Fenster für die Windows-Fingereingabe, oder heben Sie die Registrierung auf.|  
|[CWnd::ReleaseDC](#releasedc)|Gibt Client- und Fenstergerätkontexte für die Verwendung durch andere Anwendungen frei.|  
|[CWnd::RepositionBars](#repositionbars)|Ordnet die Steuerleisten im Clientbereich neu an.|  
|[CWnd::RunModalLoop](#runmodalloop)|Ruft Meldungen für ein Fenster, das sich im modalen Status befindet, ab, übersetzt oder sendet sie.|  
|[CWnd::ScreenToClient](#screentoclient)|Konvertiert die Bildschirmkoordinaten eines bestimmten Punkts oder Rechtecks auf der Anzeige zu Clientkoordinaten.|  
|[CWnd::ScrollWindow](#scrollwindow)|Scrollt durch Inhalte im Clientbereich.|  
|[CWnd::ScrollWindowEx](#scrollwindowex)|Scrollt durch Inhalte im Clientbereich. Ähnelt `ScrollWindow`, weist jedoch zusätzliche Features auf.|  
|[CWnd::SendChildNotifyLastMsg](#sendchildnotifylastmsg)|Stellt einem untergeordneten Fenster über das übergeordnete Fenster eine Benachrichtigungsmeldung bereit, sodass das untergeordnete Fenster eine Aufgabe verarbeiten kann.|  
|[CWnd::SendDlgItemMessage](#senddlgitemmessage)|Sendet eine Nachricht an das angegebene Steuerelement.|  
|[Funktion CWnd:: SendMessage](#sendmessage)|Sendet eine Nachricht an das `CWnd`-Objekt und gibt erst etwas zurück, nachdem die Meldung verarbeitet wurde.|  
|[Wm_idleupdatecmdui](#sendmessagetodescendants)|Sendet eine Nachricht an alle Nachfolgefenster des Fensters.|  
|[CWnd::SendNotifyMessage](#sendnotifymessage)|Sendet die angegebene Meldung an das Fenster und gibt schnellstmöglich etwas zurück, und zwar in Abhängigkeit davon, ob der aufrufende Thread das Fenster erstellt hat.|  
|[CWnd::SetActiveWindow](#setactivewindow)|Aktiviert das Fenster.|  
|[CWnd::SetCapture](#setcapture)|Sorgt dafür, dass alle nachfolgenden Mauseingaben an `CWnd` gesendet werden.|  
|[CWnd::SetCaretPos](#setcaretpos)|Verschiebt das Caretzeichen an die angegebene Position.|  
|[CWnd::SetClipboardViewer](#setclipboardviewer)|Fügt `CWnd` zur Fensterkette hinzu, die benachrichtigt werden, sobald sich die Inhalte der Zwischenablage ändern.|  
|[CWnd::SetDlgCtrlID](#setdlgctrlid)|Legt die Fenster- oder Steuerelement-ID für das Fenster (hierbei kann es sich um beliebige untergeordnete Fenster und nicht nur um ein Steuerelement in einem Dialogfeld handeln) fest.|  
|[CWnd::SetDlgItemInt](#setdlgitemint)|Legt den Text eines Steuerelements auf die Zeichenfolge fest, die einen Ganzzahlwert darstellt.|  
|[CWnd::SetDlgItemText](#setdlgitemtext)|Legt die Beschriftung oder den Text eines Steuerelements im angegebenen Dialogfeld fest.|  
|[CWnd::SetFocus](#setfocus)|Beansprucht den Eingabefokus.|  
|[CWnd::SetFont](#setfont)|Legt die aktuelle Schriftart fest.|  
|[CWnd::SetForegroundWindow](#setforegroundwindow)|Versetzt den Thread, durch den das Fenster erstellt wurde, in den Vordergrund und aktiviert das Fenster.|  
|[CWnd::SetIcon](#seticon)|Legt das Handle auf ein bestimmtes Symbol fest.|  
|[CWnd::SetLayeredWindowAttributes](#setlayeredwindowattributes)|Legt die Deckkraft- und Transparenzfarbenschlüssel eines überlappenden Fensters fest.|  
|[CWnd::SetMenu](#setmenu)|Legt das Menü auf das angegebene Menü fest.|  
|[CWnd::SetOwner](#setowner)|Ändert den Inhaber von`CWnd`.|  
|[CWnd::SetParent](#setparent)|Ändert das übergeordnete Fenster.|  
|[CWnd::SetProperty](#setproperty)|Legt eine ActiveX-Steuerelementeigenschaft fest.|  
|[CWnd::SetRedraw](#setredraw)|Ermöglicht, dass Änderungen in `CWnd` neu gezeichnet werden oder verhindert, dass Änderungen neu gezeichnet werden.|  
|[CWnd::SetScrollInfo](#setscrollinfo)|Legt die Informationen über die Bildlaufleiste fest.|  
|[CWnd::SetScrollPos](#setscrollpos)|Legt die aktuelle Position eines Scrollfelds fest und zeichnet (sofern angegeben) die Scrollleiste neu, um die neue Position zu berücksichtigen.|  
|[CWnd::SetScrollRange](#setscrollrange)|Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.|  
|[CWnd::SetTimer](#settimer)|Installiert einen Systemzeitgeber, die sendet eine [WM_TIMER](#ontimer) Meldung auslösen.|  
|[CWnd::SetWindowContextHelpId](#setwindowcontexthelpid)|Legt den Hilfekontextbezeichner fest.|  
|[CWnd::SetWindowPlacement](#setwindowplacement)|Legt den Anzeigestatus und die normalen (wiederhergestellt), minimierten und maximierten Positionen für ein Fenster fest.|  
|[CWnd:: SetWindowPos](#setwindowpos)|Ändert die Größe, Position und Reihenfolge von untergeordneten, Popup- und Fenstern auf oberster Ebene.|  
|[CWnd::SetWindowRgn](#setwindowrgn)|Legt die Region eines Fensters fest.|  
|[CWnd::SetWindowText](#setwindowtext)|Legt den Fenstertext oder Beschriftungstitel (sofern vorhanden) auf den angegebenen Text fest.|  
|[CWnd::ShowCaret](#showcaret)|Zeigt das Caretzeichen auf der Anzeige an der aktuellen Position des Caretzeichens. Sobald die Anzeige erfolgt, blinkt das Caretzeichen automatisch auf.|  
|[CWnd::ShowOwnedPopups](#showownedpopups)|Zeigt alle Popupfenster an, die dem Fenster gehören, oder blendet sie aus.|  
|[CWnd::ShowScrollBar](#showscrollbar)|Zeigt eine Scrollleiste an oder blendet sie aus.|  
|[ShowWindow](#showwindow)|Zeigt das Fenster an oder blendet es aus.|  
|[CWnd::SubclassDlgItem](#subclassdlgitem)|Fügt ein Windows-Steuerelement an ein `CWnd`-Objekt an und initiiert das Weiterleiten von Nachrichten über die Nachrichtenzuordnung von `CWnd`.|  
|[CWnd:: SubclassWindow](#subclasswindow)|Fügt ein Fenster an ein `CWnd`-Objekt an und initiiert das Weiterleiten von Nachrichten über die Nachrichtenzuordnung von `CWnd`.|  
|[CWnd::UnlockWindowUpdate](#unlockwindowupdate)|Entsperrt ein Fenster, das mit `CWnd::LockWindowUpdate` gesperrt wurde.|  
|[CWnd::UnsubclassWindow](#unsubclasswindow)|Löst ein Fenster von einem `CWnd` Objekt|  
|[CWnd::UpdateData](#updatedata)|Initialisiert Daten von einem Dialogfeld oder ruft sie ab.|  
|[CWnd::UpdateDialogControls](#updatedialogcontrols)|Wird aufgerufen, um den Status der Dialogfelder und von anderen Steuerelementen zu aktualisieren.|  
|[CWnd::UpdateLayeredWindow](#updatelayeredwindow)|Aktualisiert die Position, Größe, Form, Inhalte und Lichtdurchlässigkeit eines überlappenden Fensters.|  
|[CWnd::UpdateWindow](#updatewindow)|Aktualisiert den Clientbereich.|  
|[CWnd::ValidateRect](#validaterect)|Überprüft den Clientbereich in einem angegebenen Rechteck durch das Entfernen des Rechtecks aus der aktuellen Aktualisierungsregion.|  
|[CWnd::ValidateRgn](#validatergn)|Überprüft den Clientbereich in einer angegebenen Region durch das Entfernen der Region aus der aktuellen Aktualisierungsregion.|  
|[CWnd::WindowFromPoint](#windowfrompoint)|Bestimmt das Fenster, das den angegebenen Punkt enthält.|  
|[CWnd::WinHelp](#winhelp)|Wird aufgerufen, um die WinHelp-Anwendung zu initiieren.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWnd::Default](#default)|Ruft die standardmäßige Fensterprozedur auf, die eine standardmäßige Verarbeitung für Fenstermeldungen bereitstellt, die von einer Anwendung nicht verarbeitet werden.|  
|[CWnd::DefWindowProc](#defwindowproc)|Ruft die standardmäßige Fensterprozedur auf, die eine standardmäßige Verarbeitung für Fenstermeldungen bereitstellt, die von einer Anwendung nicht verarbeitet werden.|  
|[Ddx_managedcontrol](#dodataexchange)|Für den Dialogfeld-Datenaustausch und die -validierung. Wird von `UpdateData` aufgerufen.|  
|[CWnd::GetCurrentMessage](#getcurrentmessage)|Gibt einen Zeiger zur Nachricht zurück, die durch dieses Fenster zurzeit verarbeitet wird. Sollte nur aufgerufen werden, wenn einer `On` *Nachricht* Meldungshandler-Memberfunktion.|  
|[CWnd::InitDynamicLayout](#initdynamiclayout)|Wird durch das Framework aufgerufen, um das dynamische Layout für das Fenster zu initialisieren.|  
|[CWnd::LoadDynamicLayoutResource](#loaddynamiclayoutresource)|Lädt dynamische Layoutinformationen aus der Ressourcendatei.|  
|[CWnd::OnActivate](#onactivate)|Wird aufgerufen, wenn `CWnd` aktiviert bzw. deaktiviert wird.|  
|[CWnd::OnActivateApp](#onactivateapp)|Wird aufgerufen, wenn die Anwendung aktiviert oder deaktiviert wird.|  
|[CWnd::OnAppCommand](#onappcommand)|Wird aufgerufen, wenn der Benutzer ein Anwendungsbefehlereignis generiert.|  
|[CWnd::OnAskCbFormatName](#onaskcbformatname)|Wird durch eine Zwischenablageansichtsanwendung aufgerufen, wenn der Zwischenablageinhaber die Zwischenablageinhalte anzeigt.|  
|[CWnd::OnCancelMode](#oncancelmode)|Wird aufgerufen, um zu ermöglichen, dass `CWnd` interne Modi wie die Mauserfassung abbricht.|  
|[CWnd::OnCaptureChanged](#oncapturechanged)|Sendet eine Nachricht an das Fenster, dem die Mauserfassung entzogen wird.|  
|[CWnd::OnChangeCbChain](#onchangecbchain)|Gibt eine Benachrichtigung darüber aus, dass ein angegebenes Fenster aus der Kette entfernt wird.|  
|[CWnd::OnChangeUIState](#onchangeuistate)|Wird aufgerufen, wenn der Benutzeroberflächenstatus (UI) geändert werden sollte.|  
|[CWnd::OnChar](#onchar)|Wird aufgerufen, wenn eine Tastatureingabe in ein systemfremdes Zeichen übersetzt wird.|  
|[CWnd::OnCharToItem](#onchartoitem)|Aufgerufen durch ein untergeordnetes Listenfeld mit den [LBS_WANTKEYBOARDINPUT](list-box-styles.md) Stil als Antwort auf eine [WM_CHAR](#onchar) Nachricht.|  
|[CWnd::OnChildActivate](#onchildactivate)|Wird für untergeordnete MDI-Fenster (Multiple Document Interface, Schnittstelle für mehrere Dokumente) aufgerufen, sobald sich die Größe oder Position von `CWnd` ändert oder `CWnd` aktiviert wird.|  
|[CWnd:: OnChildNotify](#onchildnotify)|Wird durch ein übergeordnetes Fenster aufgerufen, um einem Benachrichtigungssteuerelement zu ermöglichen, auf eine Steuerelementbenachrichtigung zu antworten.|  
|[CWnd::OnClipboardUpdate](#onclipboardupdate)|Wird aufgerufen, wenn die Inhalte der Zwischenablage geändert wurden.|  
|[CWnd::OnClose](#onclose)|Wird als ein Signal aufgerufen, dass `CWnd` geschlossen werden sollte.|  
|[CWnd::OnColorizationColorChanged](#oncolorizationcolorchanged)|Wird aufgerufen, wenn sich die Renderrichtlinie des Nicht-Clientbereichs geändert hat.|  
|[Memberfunktion CWnd:: OnCommand](#oncommand)|Wird aufgerufen, wenn der Benutzer einen Befehl auswählt.|  
|[CWnd::OnCompacting](#oncompacting)|Wird aufgerufen, wenn Windows erkennt, dass der Arbeitsspeicher des Systems niedrig ist.|  
|[CWnd::OnCompareItem](#oncompareitem)|Wird aufgerufen, um die relative Position eines neuen Elements in einem untergeordneten sortierten vom Besitzer gezeichneten Kombinationsfeld oder Listenfeld zu ermitteln.|  
|[CWnd::OnCompositionChanged](#oncompositionchanged)|Wird für alle Fenster auf oberster Ebene aufgerufen, wenn die Desktopfenster-Manager-Komposition aktiviert oder deaktiviert wird.|  
|[CWnd::OnContextMenu](#oncontextmenu)|Wird aufgerufen, wenn der Benutzer mit die rechten Maustaste in das Fenster klickt.|  
|[CWnd::OnCopyData](#oncopydata)|Kopiert Daten aus einer Anwendung in eine andere.|  
|[CWnd::OnCreate](#oncreate)|Wird im Rahmen einer Fenstererstellung aufgerufen.|  
|[CWnd::OnCtlColor](#onctlcolor)|Wird aufgerufen, wenn `CWnd` das übergeordnete Element eines Steuerelements ist, wenn das Steuerelement gezeichnet wird.|  
|[CWnd::OnDeadChar](#ondeadchar)|Wird aufgerufen, wenn eine Tastatureingabe in ein systemfremdes, funktionsloses Zeichen (beispielsweise Akzentzeichen) übersetzt wird. |  
|[CWnd::OnDeleteItem](#ondeleteitem)|Wird aufgerufen, wenn ein vom Besitzer gezeichnetes Listen- oder Kombinationsfeld zerstört wird oder wenn Elemente aus dem Steuerelement entfernt werden.|  
|[CWnd::OnDestroy](#ondestroy)|Wird aufgerufen, wenn `CWnd` zerstört wird.|  
|[CWnd::OnDestroyClipboard](#ondestroyclipboard)|Wird aufgerufen, wenn die Zwischenablage, durch einen Aufruf von Windows geleert wird [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Funktion.|  
|[CWnd::OnDeviceChange](#ondevicechange)|Benachrichtigt eine Anwendung oder einen Gerätetreiber über eine Änderung an der Hardwarekonfiguration eines Geräts oder des Computers.|  
|[CWnd::OnDevModeChange](#ondevmodechange)|Wird für alle Fenster auf oberster Ebene aufgerufen, wenn der Benutzer die Gerätemoduseinstellungen ändert.|  
|[CWnd::OnDrawClipboard](#ondrawclipboard)|Wird aufgerufen, wenn sich der Inhalt der Zwischenablage ändert.|  
|[CWnd::OnDrawItem](#ondrawitem)|Wird aufgerufen, wenn ein visueller Aspekt eines vom Besitzer gezeichneten untergeordneten Schaltflächensteuerelements, Kombinationsfeldsteuerelements, Listenfeldsteuerelements oder Menüs gezeichnet werden muss.|  
|[CWnd::OnDropFiles](#ondropfiles)|Wird aufgerufen, wenn der Benutzer die linke Maustaste über einem Fenster loslässt, das sich selbst als der Empfänger von abgelegten Dateien registriert hat.|  
|[CWnd::OnEnable](#onenable)|Wird aufgerufen, wenn `CWnd` aktiviert oder deaktiviert ist.|  
|[CWnd::OnEndSession](#onendsession)|Wird aufgerufen, wenn die Sitzung beendet wird.|  
|[CWnd::OnEnterIdle](#onenteridle)|Wird aufgerufen, um die Hauptfensterprozedur einer Anwendung darüber zu informieren, dass ein modales Dialogfeld oder ein Menü in den Leerlaufstatus übergeht.|  
|[CWnd::OnEnterMenuLoop](#onentermenuloop)|Wird aufgerufen, wenn eine modale Menüschleife eingegangen wurde.|  
|[CWnd::OnEnterSizeMove](#onentersizemove)|Wird aufgerufen, nachdem das betroffene Fenster eine Verschiebungs- oder modale Größenanpassungsschleife eingeht.|  
|[CWnd::OnEraseBkgnd](#onerasebkgnd)|Wird aufgerufen, wenn der Fensterhintergrund gelöscht werden muss.|  
|[CWnd::OnExitMenuLoop](#onexitmenuloop)|Wird aufgerufen, wenn eine modale Menüschleife beendet wurde.|  
|[CWnd::OnExitSizeMove](#onexitsizemove)|Wird aufgerufen, nachdem das betroffene Fenster eine Verschiebungs- oder modale Größenanpassungsschleife beendet.|  
|[CWnd::OnFontChange](#onfontchange)|Wird aufgerufen, wenn sich der Pool der Schriftartressourcen ändert.|  
|[CWnd::OnGetDlgCode](#ongetdlgcode)|Wird für ein Steuerelement aufgerufen, sodass das Steuerelement die Eingabe für die PFEILTASTE und TAB-TASTE selbst verarbeiten kann.|  
|[CWnd::OnGetMinMaxInfo](#ongetminmaxinfo)|Wird aufgerufen, sobald Windows über die maximierte Position oder Dimensionen oder die minimale oder maximale Nachverfolgungsgröße informiert werden muss.|  
|[CWnd::OnHelpInfo](#onhelpinfo)|Wird durch das Framework aufgerufen, wenn der Benutzer die F1-TASTE drückt.|  
|[CWnd::OnHotKey](#onhotkey)|Wird aufgerufen, wenn der Benutzer eine systemübergreifende Abkürzungstaste drückt.|  
|[CWnd::OnHScroll](#onhscroll)|Wird aufgerufen, wenn der Benutzer auf die horizontale Scrollleiste von `CWnd` klickt.|  
|[CWnd::OnHScrollClipboard](#onhscrollclipboard)|Wird aufgerufen, wenn ein Zwischenablageinhaber das Zwischenablagebild scrollen, den entsprechenden Abschnitt ungültig machen und die Scrollleistenwerte aktualisieren sollte.|  
|[CWnd::OnIconEraseBkgnd](#oniconerasebkgnd)|Wird aufgerufen, wenn `CWnd` minimiert (Symbol) ist und der Hintergrund des Symbols vor dem Zeichnen des Symbols aufgefüllt werden muss.|  
|[CWnd::OnInitMenu](#oninitmenu)|Wird aufgerufen, wenn ein Menü aktiv wird.|  
|[CWnd::OnInitMenuPopup](#oninitmenupopup)|Wird aufgerufen, wenn ein Popupmenü aktiv wird.|  
|[CWnd::OnInputDeviceChange](#oninputdevicechange)|Wird aufgerufen, wenn dem System ein E/A-Gerät hinzugefügt oder aus dem System entfernt wird.|  
|[CWnd::OnInputLangChange](#oninputlangchange)|Wird aufgerufen, nachdem sich die Eingabesprache einer Anwendung geändert hat.|  
|[CWnd::OnInputLangChangeRequest](#oninputlangchangerequest)|Wird aufgerufen, wenn der Benutzer eine neue Eingabesprache auswählt.|  
|[CWnd::OnKeyDown](#onkeydown)|Wird aufgerufen, wenn eine systemfremde Taste gedrückt wird.|  
|[CWnd::OnKeyUp](#onkeyup)|Wird aufgerufen, wenn eine systemfremde Taste losgelassen wird.|  
|[CWnd::OnKillFocus](#onkillfocus)|Wird sofort aufgerufen, bevor `CWnd` den Eingabefokus verliert.|  
|[CWnd::OnLButtonDblClk](#onlbuttondblclk)|Wird aufgerufen, wenn der Benutzer mit der linken Maustaste doppelklickt.|  
|[CWnd::OnLButtonDown](#onlbuttondown)|Wird aufgerufen, wenn der Benutzer die linke Maustaste drückt.|  
|[CWnd::OnLButtonUp](#onlbuttonup)|Wird aufgerufen, wenn der Benutzer die linke Maustaste loslässt.|  
|[CWnd::OnMButtonDblClk](#onmbuttondblclk)|Wird aufgerufen, wenn der Benutzer mit der mittleren Maustaste doppelklickt.|  
|[CWnd::OnMButtonDown](#onmbuttondown)|Wird aufgerufen, wenn der Benutzer auf die mittlere Maustaste drückt.|  
|[CWnd::OnMButtonUp](#onmbuttonup)|Wird aufgerufen, wenn der Benutzer die mittlere Maustaste loslässt.|  
|[CWnd::OnMDIActivate](#onmdiactivate)|Wird aufgerufen, wenn ein untergeordnetes MDI-Fenster aktiviert oder deaktiviert wird.|  
|[CWnd::OnMeasureItem](#onmeasureitem)|Wird für ein vom Besitzer gezeichnetes untergeordnetes Kombinationsfeld, Listenfeld oder Menüelement aufgerufen, wenn das Steuerelement erstellt wird. `CWnd` informiert Windows über die Abmessungen des Steuerelements.|  
|[CWnd::OnMenuChar](#onmenuchar)|Wird aufgerufen, wenn der Benutzer auf ein mnemonisches Menüzeichen  drückt, das nicht mit den vordefinierten mnemonischen Zeichen im aktuellen Menü übereinstimmt.|  
|[CWnd::OnMenuDrag](#onmenudrag)|Wird aufgerufen, wenn der Benutzer beginnt, ein Menüelement zu ziehen.|  
|[CWnd::OnMenuGetObject](#onmenugetobject)|Wird aufgerufen, wenn der Mauszeiger in ein Menüelement geführt oder aus der Mitte des Elements zur Ober- oder Unterseite des Elements bewegt wird.|  
|[CWnd::OnMenuRButtonUp](#onmenurbuttonup)|Wird aufgerufen, wenn die rechte Maustaste losgelassen wird und sich der Cursor dabei über einem Menüelement befindet.|  
|[CWnd::OnMenuSelect](#onmenuselect)|Wird aufgerufen, wenn der Benutzer ein Menüelement auswählt.|  
|[CWnd::OnMouseActivate](#onmouseactivate)|Wird aufgerufen, wenn sich der Cursor in einem inaktiven Fenster befindet und der Benutzer eine Maustaste drückt.|  
|[CWnd::OnMouseHover](#onmousehover)|Wird aufgerufen, wenn der Cursor für die Zeitspanne, die in einem vorherigen Aufruf über den Clientbereich des Fensters bewegt wird [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnMouseHWheel](#onmousehwheel)|Wird aufgerufen, wenn das aktuelle Fenster durch den Desktopfenster-Manager zusammengesetzt wird und dieses Fenster maximiert ist.|  
|[CWnd::OnMouseLeave](#onmouseleave)|Wird aufgerufen, wenn der Cursor den Clientbereich des angegebenen Fensters in einem vorherigen Aufruf von verlässt [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnMouseMove](#onmousemove)|Wird aufgerufen, wenn der Mauszeiger bewegt wird.|  
|[CWnd::OnMouseWheel](#onmousewheel)|Wird aufgerufen, wenn ein Benutzer das Mausrad dreht. Verwendet die Windows NT 4.0-Nachrichtenverarbeitung.|  
|[CWnd::OnMove](#onmove)|Wird aufgerufen, nachdem die Position von `CWnd` geändert wurde.|  
|[CWnd::OnMoving](#onmoving)|Gibt an, dass ein Benutzer ein `CWnd`-Objekt verschiebt.|  
|[CWnd::OnNcActivate](#onncactivate)|Wird aufgerufen, wenn der clientfremde Bereich geändert werden muss, um einen aktiven oder inaktiven Status anzugeben.|  
|[CWnd::OnNcCalcSize](#onnccalcsize)|Wird aufgerufen, wenn die Größe und Position des Clientbereichs berechnet werden müssen.|  
|[CWnd::OnNcCreate](#onnccreate)|Wird vor aufgerufen [OnCreate](#oncreate) Wenn der nicht-Clientbereich erstellt wird.|  
|[CWnd::OnNcDestroy](#onncdestroy)|Wird aufgerufen, wenn der clientfremde Bereich zerstört wird.|  
|[CWnd::OnNcHitTest](#onnchittest)|Wird durch Windows aufgerufen, sobald die Maus bewegt wird, wenn `CWnd` den Cursor enthält oder die Mauseingabe mit `SetCapture` erfasst hat.|  
|[CWnd::OnNcLButtonDblClk](#onnclbuttondblclk)|Wird aufgerufen, wenn der Benutzer mit der linken Maustaste doppelklickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcLButtonDown](#onnclbuttondown)|Wird aufgerufen, wenn der Benutzer die linke Maustaste drückt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcLButtonUp](#onnclbuttonup)|Wird aufgerufen, wenn der Benutzer die linke Maustaste loslässt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMButtonDblClk](#onncmbuttondblclk)|Wird aufgerufen, wenn der Benutzer mit der mittleren Maustaste doppelklickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMButtonDown](#onncmbuttondown)|Wird aufgerufen, wenn der Benutzer die mittlere Maustaste drückt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMButtonUp](#onncmbuttonup)|Wird aufgerufen, wenn der Benutzer die mittlere Maustaste loslässt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcMouseHover](#onncmousehover)|Wird aufgerufen, wenn der Cursor für die Zeitspanne, die in einem vorherigen Aufruf von nicht-Clientbereich des Fensters bewegt wird [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnNcMouseLeave](#onncmouseleave)|Das Framework ruft diese Memberfunktion auf, wenn der Cursor den nicht-Clientbereich des Fensters in einem vorherigen Aufruf von angegebenen verlässt [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnNcMouseMove](#onncmousemove)|Wird aufgerufen, wenn der Cursor innerhalb eines clientfremden Bereichs von `CWnd` bewegt wird.|  
|[CWnd::OnNcPaint](#onncpaint)|Wird aufgerufen, wenn für den clientfremden Bereich eine Zeichnung erforderlich ist.|  
|[CWnd::OnNcRButtonDblClk](#onncrbuttondblclk)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste doppelklickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcRButtonDown](#onncrbuttondown)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste klickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcRButtonUp](#onncrbuttonup)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste klickt, während sich der Cursor in einem clientfremden Bereich von `CWnd` befindet.|  
|[CWnd::OnNcRenderingChanged](#onncrenderingchanged)|Wird aufgerufen, wenn sich die Renderrichtlinie des Nicht-Clientbereichs geändert hat.|  
|[CWnd::OnNcXButtonDblClk](#onncxbuttondblclk)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 doppelklickt, während sich der Cursor im clientfremden Bereich eines Fensters befindet.|  
|[CWnd::OnNcXButtonDown](#onncxbuttondown)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 der Maus drückt, während sich der Cursor im clientfremden Bereich eines Fensters befindet.|  
|[CWnd::OnNcXButtonUp](#onncxbuttonup)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 der Maus loslässt, während sich der Cursor im clientfremden Bereich eines Fensters befindet.|  
|[CWnd::OnNextMenu](#onnextmenu)|Wird aufgerufen, wenn der NACH-RECHTS- oder NACH-LINKS-PFEIL verwendet wird, um zwischen der Menüleiste und dem Systemmenü zu wechseln.|  
|[CWnd::OnNotify](#onnotify)|Wird durch das Framework aufgerufen, um ein übergeordnetes Fenster darüber zu informieren, dass ein Ereignis in einem seiner Steuerelemente aufgetreten ist oder dass das Steuerelement Informationen benötigt.|  
|[CWnd::OnNotifyFormat](#onnotifyformat)|Wird aufgerufen, um zu bestimmen, ob das aktuelle Fenster ANSI- oder Unicode-Strukturen in der WM_NOTIFY-Benachrichtigung akzeptiert.|  
|[CWnd::OnPaint](#onpaint)|Wird aufgerufen, um eine Teilmenge des Fensters neu zu zeichnen.|  
|[CWnd::OnPaintClipboard](#onpaintclipboard)|Wird aufgerufen, wenn der Clientbereich der Zwischenablagenansicht neu gezeichnet werden muss.|  
|[CWnd::OnPaletteChanged](#onpalettechanged)|Wird aufgerufen, um Fenstern zu erlauben, die eine Farbpalette verwenden, ihre logischen Paletten zu realisieren und ihre Clientbereiche zu aktualisieren. |  
|[CWnd::OnPaletteIsChanging](#onpaletteischanging)|Informiert andere Anwendungen, wenn eine Anwendung ihre logische Palette realisiert.|  
|[Memberfunktion CWnd:: OnParentNotify](#onparentnotify)|Wird aufgerufen, wenn ein untergeordnetes Fenster erstellt oder zerstört wird oder wenn der Benutzer eine Maustaste drückt, während sich der Cursor über einem untergeordneten Fenster befindet.|  
|[CWnd:: Onpowerbroadcast](#onpowerbroadcast)|Wird aufgerufen, wenn ein Energieverwaltungsereignis auftritt.|  
|[CWnd::OnQueryDragIcon](#onquerydragicon)|Wird aufgerufen, wenn ein minimiertes `CWnd` (Symbol) durch den Benutzer gezogen wird.|  
|[CWnd::OnQueryEndSession](#onqueryendsession)|Wird aufgerufen, wenn der Benutzer entscheidet, die Windows-Sitzung zu beenden.|  
|[CWnd::OnQueryNewPalette](#onquerynewpalette)|Informiert `CWnd` darüber, dass es den Eingabefokus empfängt.|  
|[CWnd::OnQueryOpen](#onqueryopen)|Wird aufgerufen, wenn `CWnd` ein Symbol ist und der Benutzer das Öffnen des Symbols anfordert.|  
|[CWnd::OnQueryUIState](#onqueryuistate)|Wird aufgerufen, um den Benutzeroberflächenstatus (UI) für ein Fenster abzurufen.|  
|[CWnd::OnRawInput](#onrawinput)|Wird aufgerufen, wenn das aktuelle Fenster nicht formatierte Daten erhält.|  
|[CWnd::OnRButtonDblClk](#onrbuttondblclk)|Wird aufgerufen, wenn der Benutzer mit der rechten Maustaste doppelklickt.|  
|[CWnd::OnRButtonDown](#onrbuttondown)|Wird aufgerufen, wenn der Benutzer die rechte Maustaste drückt.|  
|[CWnd::OnRButtonUp](#onrbuttonup)|Wird aufgerufen, wenn der Benutzer die rechte Maustaste loslässt.|  
|[CWnd::OnRenderAllFormats](#onrenderallformats)|Wird aufgerufen, wenn die Inhaberanwendung zerstört wird und ihre gesamten Formate rendern muss.|  
|[CWnd::OnRenderFormat](#onrenderformat)|Wird für den Zwischenablageinhaber aufgerufen, wenn ein bestimmtes Format mit verzögertem Rendering gerendert werden muss.|  
|[CWnd::OnSessionChange](#onsessionchange)|Wird aufgerufen, um eine Anwendung über eine Änderung im Sitzungsstatus zu informieren.|  
|[CWnd::OnSetCursor](#onsetcursor)|Wird aufgerufen, wenn die Mauseingabe nicht erfasst wird und die Maus eine Bewegung des Cursors in einem Fenster verursacht.|  
|[CWnd::OnSetFocus](#onsetfocus)|Wird aufgerufen, nachdem `CWnd` den Eingabefokus erhält.|  
|[CWnd::OnSettingChange](#onsettingchange)|Wird aufgerufen, wenn die `SystemParametersInfo`-Win32-Funktion eine systemübergreifende Einstellung ändert.|  
|[CWnd::OnShowWindow](#onshowwindow)|Wird aufgerufen, wenn `CWnd` ausgeblendet oder angezeigt wird.|  
|[CWnd::OnSize](#onsize)|Wird aufgerufen, nachdem die Größe von `CWnd` geändert wurde.|  
|[CWnd::OnSizeClipboard](#onsizeclipboard)|Wird aufgerufen, wenn sich die Größe des Clientbereichs des Zwischenablageanzeigefensters geändert hat.|  
|[CWnd::OnSizing](#onsizing)|Gibt an, dass der Benutzer die Größe des Rechtecks ändert.|  
|[CWnd::OnSpoolerStatus](#onspoolerstatus)|Wird vom Druck-Manager aufgerufen, sobald der Druck-Manager-Warteschlange ein Auftrag hinzugefügt wird bzw. einer aus ihr entfernt wird.|  
|[CWnd::OnStyleChanged](#onstylechanged)|Gibt an, dass die [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows-Funktion wurde geändert, eine oder mehrere der Stile für das Fenster.|  
|[CWnd::OnStyleChanging](#onstylechanging)|Gibt an, dass die [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows-Funktion eine oder mehrere der Stile des Fensters geändert wird.|  
|[CWnd::OnSysChar](#onsyschar)|Wird aufgerufen, wenn eine Tastatureingabe in ein Systemzeichen übersetzt wird.|  
|[CWnd::OnSysColorChange](#onsyscolorchange)|Wird für alle Fenster auf oberster Ebene aufgerufen, wenn in der Systemfarbeneinstellung eine Änderung vorgenommen wird.|  
|[CWnd::OnSysCommand](#onsyscommand)|Wird aufgerufen, wenn der Benutzer einen Befehl aus dem Steuerelementmenü auswählt oder wenn der Benutzer die Schaltfläche „Maximieren“ oder „Minimieren“ auswählt.|  
|[CWnd::OnSysDeadChar](#onsysdeadchar)|Wird aufgerufen, wenn eine Tastatureingabe in ein funktionsloses Systemzeichen (beispielsweise Akzentzeichen) übersetzt wird. |  
|[CWnd::OnSysKeyDown](#onsyskeydown)|Wird aufgerufen, wenn der Benutzer die ALT-TASTE gedrückt hält und dann eine andere Taste drückt.|  
|[CWnd::OnSysKeyUp](#onsyskeyup)|Wird aufgerufen, wenn der Benutzer eine Taste loslässt, die gedrückt wurde, während die ALT-TASTE gedrückt gehalten wurde.|  
|[CWnd::OnTCard](#ontcard)|Wird aufgerufen, wenn der Benutzer auf eine bearbeitbare Schaltfläche drückt |  
|[CWnd::OnTimeChange](#ontimechange)|Wird für alle Fenster auf oberster Ebene aufgerufen, nachdem die Systemzeit geändert wurde.|  
|[CWnd::OnTimer](#ontimer)|Nach jedem im angegebenen Intervall aufgerufen [SetTimer](#settimer).|  
|[CWnd::OnTouchInput](#ontouchinput)|Verarbeitet die einzelne Eingabe aus Windows Touch.|  
|[CWnd::OnTouchInputs](#ontouchinputs)|Verarbeitet Eingaben aus Windows Touch.|  
|[CWnd::OnUniChar](#onunichar)|Wird aufgerufen, wenn eine Taste gedrückt wird. D. h. das aktuelle Fenster den Tastaturfokus hat und ein [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) Nachricht übersetzt, von der [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) Funktion.|  
|[CWnd::OnUnInitMenuPopup](#onuninitmenupopup)|Wird aufgerufen, wenn eine Dropdownmenü oder -untermenü zerstört wurde.|  
|[CWnd::OnUpdateUIState](#onupdateuistate)|Wird aufgerufen, um den Benutzeroberflächenstatus für das angegebene Fenster und alle zugehörigen untergeordneten Fenster zu ändern.|  
|[CWnd::OnUserChanged](#onuserchanged)|Wird aufgerufen, nachdem sich der Benutzer an- oder abgemeldet hat.|  
|[CWnd::OnVKeyToItem](#onvkeytoitem)|Aufgerufen, die für ein Listenfeld, das im Besitz von `CWnd` als Antwort auf eine [WM_KEYDOWN](#onkeydown) Nachricht.|  
|[CWnd::OnVScroll](#onvscroll)|Wird aufgerufen, wenn der Benutzer auf die vertikale Scrollleiste des Fensters klickt.|  
|[CWnd::OnVScrollClipboard](#onvscrollclipboard)|Wird aufgerufen, wenn der Inhaber das Zwischenablagebild scrollen, den entsprechenden Abschnitt ungültig machen und die Scrollleistenwerte aktualisieren sollte.|  
|[CWnd::OnWindowPosChanged](#onwindowposchanged)|Wird aufgerufen, wenn die Größe, Position oder Z-Reihenfolge nach einem Aufruf von geänderten [SetWindowPos](#setwindowpos) oder einem anderen Fenster-Management-Funktion.|  
|[CWnd::OnWindowPosChanging](#onwindowposchanging)|Wird aufgerufen, wenn die Größe, Position oder Z-Reihenfolge zu ändern ist aufgrund eines Aufrufs von [SetWindowPos](#setwindowpos) oder einem anderen Fenster-Management-Funktion.|  
|[CWnd::OnWinIniChange](#onwininichange)|Wird für alle Fenster auf oberster Ebene aufgerufen, nachdem die Windows-Initialisierungsdatei (WIN.INI) geändert wird.|  
|[CWnd::OnWndMsg](#onwndmsg)|Gibt an, ob eine Fenstermeldung verarbeitet wurde.|  
|[CWnd::OnXButtonDblClk](#onxbuttondblclk)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 doppelklickt, während sich der Cursor im Clientbereich eines Fensters befindet.|  
|[CWnd::OnXButtonDown](#onxbuttondown)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 drückt, während sich der Cursor im Clientbereich eines Fensters befindet.|  
|[CWnd::OnXButtonUp](#onxbuttonup)|Wird aufgerufen, wenn der Benutzer XBUTTON1 oder XBUTTON2 loslässt, während sich der Cursor im Clientbereich eines Fensters befindet.|  
|[CWnd::PostNcDestroy](#postncdestroy)|Diese virtuellen Funktion wird aufgerufen, die standardmäßig [OnNcDestroy](#onncdestroy) funktionieren, nachdem das Fenster zerstört wurde.|  
|[CWnd::ReflectChildNotify](#reflectchildnotify)|Hilfsfunktion, die eine Meldung an ihre Quelle weitergibt.|  
|[CWnd::ReflectLastMsg](#reflectlastmsg)|Gibt die letzte Meldung zum untergeordneten Fenster weiter.|  
|[CWnd::ResizeDynamicLayout](#resizedynamiclayout)|Wird durch das Framework aufgerufen, wenn sich die Fenstergröße ändert, um das Layout der untergeordneten Fenster anzupassen, wenn das dynamische Layout für das Fenster aktiviert ist.|  
|[CWnd::WindowProc](#windowproc)|Stellt eine Fensterprozedur für `CWnd` bereit. Der Standard versendet Meldungen über die Meldungszuordnung.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWnd::operator HWND](#operator_hwnd)|Nehmen Sie einen Aufruf vor, um ein Handle zu einem Fenster zu erhalten.|  
|[CWnd::operator! =](#operator_neq)|Bestimmt, ob ein Fenster, dessen Handle ist, nicht identisch mit dem Fenster ist [M_hWnd](#m_hwnd).|  
|[CWnd::operator ==](#operator_eq_eq)|Bestimmt, ob ein Fenster des Fensters identisch ist, dessen Handle ist [M_hWnd](#m_hwnd).|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWnd::m_hWnd](#m_hwnd)|Gibt das an `CWnd` angefügte `HWND` an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CWnd`-Objekt unterscheidet sich von einem Windows-Fenster, aber beide sind jedoch eng miteinander verknüpft. Ein `CWnd`-Objekt wird durch den `CWnd`-Konstruktor und -Dekonstruktor erstellt oder zerstört. Das Windows-Fenster auf der anderen Seite ist eine Datenstruktur, die interne Windows durch die erstellte ein **erstellen** -Memberfunktion und zerstört wird, indem die `CWnd` virtuellen Destruktor. Die [DestroyWindow](#destroywindow) Funktion zerstört das Windows-Fenster, ohne das Objekt zu zerstören.  
  
 Die `CWnd` -Klasse und der Meldung-Map-Mechanismus Ausblenden der **WndProc** Funktion. Eingehende Windows-Benachrichtigung über die Message-Karte, um die richtige automatisch weitergeleitet **auf***Nachricht* `CWnd` Memberfunktionen. Sie Überschreiben einer **auf***Nachricht* -Memberfunktion eines Mitglieds bestimmte Nachrichten in Ihrer abgeleiteten Klassen zu behandeln.  
  
 Mithilfe der `CWnd`-Klasse können Sie auch ein untergeordnetes Windows-Fenster für Ihre Anwendung erstellen. Leiten Sie eine Klasse aus `CWnd` ab, fügen Sie dann der abgeleiteten Klasse Membervariablen hinzu, um für Ihre Anwendung spezifische Daten zu speichern. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Ein untergeordnetes Fenster wird in zwei Schritten erstellt. Zuerst rufen Sie den Konstruktor `CWnd` erstellt die `CWnd` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion, die das untergeordnete Fenster erstellen und Anfügen an die `CWnd` Objekt.  
  
 Wenn der Benutzer Ihr untergeordnetes Fenster beendet, zerstören Sie das Objekt `CWnd`, oder rufen Sie die Memberfunktion `DestroyWindow` auf, um das Fenster zu entfernen und dessen Datenstrukturen zu zerstören.  
  
 In der Microsoft Foundation Class-Bibliothek werden weitere Klassen aus `CWnd` abgeleitet, um bestimmte Fenstertypen bereitzustellen. Viele dieser Klassen, einschließlich [CFrameWnd](../../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md), [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md), [CView](../../mfc/reference/cview-class.md), und [CDialog](../../mfc/reference/cdialog-class.md), eignen sich für weitere Ableitung. Von abgeleiteten Steuerelementklassen `CWnd`, wie z. B. [CButton](../../mfc/reference/cbutton-class.md), direkt verwendet werden können, oder für weitere Ableitung von Klassen verwendet werden kann.  
  
 Weitere Informationen zur Verwendung von `CWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md) und [Fensterobjekten](../../mfc/window-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-nameaccdodefaultactiona--cwndaccdodefaultaction"></a><a name="accdodefaultaction"></a>CWnd::accDoDefaultAction  
 Wird durch das Framework aufgerufen, um die Standardaktion des Objekts auszuführen.  
  
```  
virtual HRESULT accDoDefaultAction(VARIANT varChild);
```  
  
### <a name="parameters"></a>Parameter  
 `varChild`  
 Gibt an, ob die Standardaktion, die aufgerufen werden, die des Objekts oder eines Objekts untergeordneten Elemente. Dieser Parameter kann entweder CHILDID_SELF (um die Standardaktion des Objekts ausführen) oder untergeordnete ID (, führen Sie die Standardaktion eines Objekts untergeordnete Elemente) sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg, eine COM-Fehlercode zurück. Finden Sie unter **Rückgabewerte** in [IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) unterstützen.  
  
 Überschreiben Sie diese Funktion in Ihrer `CWnd`-abgeleitete Klasse, die zum Ausführen der Standardaktion des Objekts. Weitere Informationen finden Sie unter [IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameacchittesta--cwndacchittest"></a><a name="acchittest"></a>CWnd::accHitTest  
 Wird durch das Framework aufgerufen, um das untergeordnete Element oder untergeordnete Objekt an einem bestimmten Punkt auf dem Bildschirm abzurufen.  
  
```  
virtual HRESULT accHitTest(
    long xLeft,  
    long yTop,  
    VARIANT* pvarChild);
```  
  
### <a name="parameters"></a>Parameter  
 `xLeft`  
 X-Koordinate des Punkts auf Treffer zu überprüfenden getestet (in Einheiten des Bildschirms).  
  
 `yTop`  
 Y-Koordinate des Punkts auf Treffer zu überprüfenden getestet (in Einheiten des Bildschirms).  
  
 `pvarChild`  
 Informationen zur Identifizierung des Objekts am angegebenen Punkt empfängt `xLeft` und `yTop`. Finden Sie unter *PvarID* in [IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg, eine COM-Fehlercode zurück. Finden Sie unter **Rückgabewerte** in **IAccessible::accHitTest** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) unterstützen.  
  
 Überschreiben Sie diese Funktion in Ihrer `CWnd`-abgeleiteten Klasse Elemente der Benutzeroberfläche (mit Ausnahme des fensterlose ActiveX-Steuerelemente, die MFC behandelt) Nonwindowed haben.  
  
 Weitere Informationen finden Sie unter [IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameacclocationa--cwndacclocation"></a><a name="acclocation"></a>CWnd::accLocation  
 Wird durch das Framework aufgerufen, um die aktuelle Bildschirmposition des angegebenen Objekts abzurufen.  
  
```  
virtual HRESULT accLocation(
    long* pxLeft,  
    long* pyTop,  
    long* pcxWidth,  
    long* pcyHeight,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>Parameter  
 *pxLeft*  
 Empfängt die X-Koordinate des Objekts oberen linken Ecke (in Einheiten des Bildschirms).  
  
 *pyTop*  
 Empfängt die y-Koordinate des Objekts oberen linken Ecke (in Einheiten des Bildschirms).  
  
 *pcxWidth*  
 Erhält die Breite des Objekts (in Einheiten des Bildschirms).  
  
 *pcyHeight*  
 Empfängt die Höhe des Objekts (in Einheiten des Bildschirms).  
  
 `varChild`  
 Gibt an, ob die Position abgerufen werden sollen, die das Objekt oder einem der untergeordneten Elemente des Objekts ist. Dieser Parameter kann CHILDID_SELF (um erhalten Informationen über das Objekt) oder eine untergeordnete ID (um erhalten Informationen über das Objekt untergeordneten Element).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg, eine COM-Fehlercode zurück. Finden Sie unter **Rückgabewerte** in **IAccessible::accLocation** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion in Ihrer `CWnd`-abgeleiteten Klasse Elemente der Benutzeroberfläche (mit Ausnahme des fensterlose ActiveX-Steuerelemente, die MFC behandelt) Nonwindowed haben.  
  
 Weitere Informationen finden Sie unter **IAccessible::accLocation** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameaccnavigatea--cwndaccnavigate"></a><a name="accnavigate"></a>CWnd::accNavigate  
 Wird durch das Framework aufgerufen, um zu einem anderen Benutzer-Schnittstellenelement innerhalb eines Containers zu gelangen und wenn möglich, das Objekt abzurufen.  
  
```  
virtual HRESULT accNavigate(
    long navDir,  
    VARIANT varStart,  
    VARIANT* pvarEndUpAt);
```  
  
### <a name="parameters"></a>Parameter  
 `navDir`  
 Gibt die Richtung zu navigieren. Finden Sie unter `navDir` in [IAccessible:: accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `varStart`  
 Gibt das Objekt ab. Finden Sie unter `varStart` in **IAccessible:: accNavigate** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *pvarEndUpAt*  
 Informationen über das Benutzeroberflächenobjekt Ziel empfängt. Finden Sie unter *PvarEnd* in **IAccessible:: accNavigate** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg, eine COM-Fehlercode zurück. Finden Sie unter **Rückgabewerte** in **IAccessible:: accNavigate** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) unterstützen.  
  
 Überschreiben Sie diese Funktion in Ihrer `CWnd`-abgeleiteten Klasse Elemente der Benutzeroberfläche (mit Ausnahme des fensterlose ActiveX-Steuerelemente, die MFC behandelt) Nonwindowed haben.  
  
 Weitere Informationen finden Sie unter [IAccessible:: accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameaccselecta--cwndaccselect"></a><a name="accselect"></a>CWnd::accSelect  
 Wird durch das Framework aufgerufen, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben.  
  
```  
virtual HRESULT accSelect(
    long flagsSelect,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>Parameter  
 `flagsSelect`  
 Gibt an, wie die aktuelle Auswahl oder den Fokus zu ändern. Finden Sie unter `flagsSelect` in [IAccessible:: accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `varChild`  
 Gibt das Objekt ausgewählt werden. Dieser Parameter kann entweder CHILDID_SELF (um das Objekt selbst auszuwählen) oder untergeordnete ID (, wählen Sie eines der untergeordneten Elemente des Objekts) sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg, eine COM-Fehlercode zurück. Finden Sie unter **Rückgabewerte** in **IAccessible:: accSelect** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) unterstützen.  
  
 Überschreiben Sie diese Funktion in Ihrer `CWnd`-abgeleiteten Klasse Elemente der Benutzeroberfläche (mit Ausnahme des fensterlose ActiveX-Steuerelemente, die MFC behandelt) Nonwindowed haben.  
  
 Weitere Informationen finden Sie unter [IAccessible:: accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameanimatewindowa--cwndanimatewindow"></a><a name="animatewindow"></a>CWnd::AnimateWindow  
 Erzeugt Spezialeffekte beim ein- oder Ausblenden von Windows.  
  
```  
BOOL AnimateWindow(
    DWORD dwTime,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTime*  
 Gibt an, wie lange es dauert, um die Wiedergabe der Animation in Millisekunden. In der Regel nimmt eine Animation 200 Millisekunden wiedergegeben.  
  
 `dwFlags`  
 Gibt den Typ der Animation an. Eine vollständige Liste der möglichen Werte finden Sie unter [AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669).  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namearrangeiconicwindowsa--cwndarrangeiconicwindows"></a><a name="arrangeiconicwindows"></a>CWnd::ArrangeIconicWindows  
 Ordnet alle minimierten untergeordneten Fenster (Symbole).  
  
```  
UINT ArrangeIconicWindows();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe einer Zeile von Symbolen, wenn die Funktion erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ordnet auch Symbole für das desktop-Fenster, das den gesamten Bildschirm abdeckt. Die [GetDesktopWindow](#getdesktopwindow) Member-Funktion ruft einen Zeiger auf den desktop Window-Objekt.  
  
 Aufrufen, um iconic untergeordnete MDI-Fenster in einer MDI-Clientfenster anzuordnen, [CMDIFrameWnd::MDIIconArrange](../../mfc/reference/cmdiframewnd-class.md#mdiiconarrange).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#66;](../../mfc/reference/codesnippet/cpp/cwnd-class_1.cpp)]  
  
##  <a name="a-nameattacha--cwndattach"></a><a name="attach"></a>CWnd::Attach  
 Fügt eine Windows-Fenster an ein `CWnd` Objekt.  
  
```  
BOOL Attach(HWND hWndNew);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndNew`  
 Gibt ein Handle für ein Windows-Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht das Anfügen und trennen verwenden, um das MDI-Clientfenster zuordnen.  
  
 [!code-cpp[NVC_MFCWindowing&#67;](../../mfc/reference/codesnippet/cpp/cwnd-class_2.h)]  
  
 [!code-cpp[NVC_MFCWindowing&#68;](../../mfc/reference/codesnippet/cpp/cwnd-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#69;](../../mfc/reference/codesnippet/cpp/cwnd-class_4.cpp)]  
  
##  <a name="a-namebeginmodalstatea--cwndbeginmodalstate"></a><a name="beginmodalstate"></a>CWnd::BeginModalState  
 Rufen Sie diese Memberfunktion auf, um ein Framefenster modal zu machen.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="a-namebeginpainta--cwndbeginpaint"></a><a name="beginpaint"></a>CWnd::BeginPaint  
 Bereitet `CWnd` für Zeichen- und füllt eine `PAINTSTRUCT` Datenstruktur mit Informationen über das Zeichnen.  
  
```  
CDC* BeginPaint(LPPAINTSTRUCT lpPaint);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPaint`  
 Verweist auf die [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) -Struktur, zeichnen Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Identifiziert den Gerätekontext für `CWnd`. Der Zeiger kann temporär sein und sollte nicht Gegenstand gespeichert werden [EndPaint](#endpaint).  
  
### <a name="remarks"></a>Hinweise  
 Die Paint-Struktur enthält eine RECT-Datenstruktur, die das kleinste Rechteck vollständig umschließt die Update-Region und ein Flag, das angibt, ob der Hintergrund gelöscht wurde.  
  
 Der Aktualisierungsbereich wird festgelegt, indem die [Invalidate](#invalidate), [InvalidateRect](#invalidaterect), oder [InvalidateRgn](#invalidatergn) Memberfunktionen und vom System nach Größe, verschiebt, erstellt, führt einen Bildlauf oder führt keine anderen Vorgänge, die den Client-Bereich auswirkt. Wenn der Aktualisierungsbereich zum Löschen, markiert ist `BeginPaint` sendet ein [WM_ONERASEBKGND](#onerasebkgnd) Nachricht.  
  
 Rufen Sie nicht die `BeginPaint` Memberfunktion außer als Antwort auf eine [WM_PAINT](#onpaint) Nachricht. Jeder Aufruf von der `BeginPaint` Memberfunktion benötigen Sie einen entsprechenden Aufruf von der [EndPaint](#endpaint) Member-Funktion. Wenn die Einfügemarke im Bereich gezeichnet werden soll, wird die `BeginPaint` Memberfunktion Blendet automatisch die Einfügemarke, um zu verhindern, dass es gelöscht wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#70;](../../mfc/reference/codesnippet/cpp/cwnd-class_5.cpp)]  
  
##  <a name="a-namebinddefaultpropertya--cwndbinddefaultproperty"></a><a name="binddefaultproperty"></a>CWnd::BindDefaultProperty  
 Bindet das aufrufende Objekt einfach gebundenen Standardeigenschaft (z. B. ein Bearbeitungssteuerelement), als in der Typbibliothek markiert auf den zugrunde liegenden Cursor, der von der Datenquelle, Benutzername, Kennwort und SQL-Eigenschaften des Datenquellen-Steuerelements definiert wird.  
  
```  
void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Gibt die DISPID einer Eigenschaft auf einem datengebundenen Steuerelement, die an ein Datenquellen-Steuerelement gebunden werden soll.  
  
 `vtProp`  
 Gibt den Typ der Eigenschaft, die gebunden werden, z. B. `VT_BSTR`, **VT_VARIANT**und so weiter.  
  
 `szFieldName`  
 Gibt den Namen der Spalte im Cursor zur Verfügung gestellt, von dem Datenquellen-Steuerelement, zu dem die Eigenschaft gebunden wird.  
  
 `pDSCWnd`  
 Verweist auf das Fenster Hosts die Datenquellen-Steuerelements an die Eigenschaft gebunden wird. Rufen Sie `GetDlgItem` mit der Ressourcen-ID des Hostfensters die DCS dieser Zeiger abgerufen.  
  
### <a name="remarks"></a>Hinweise  
 Das `CWnd` Objekt, auf dem Sie diese Funktion aufrufen, muss ein datengebundenes Steuerelement.  
  
### <a name="example"></a>Beispiel  
 `BindDefaultProperty`kann im folgenden Kontext verwendet werden:  
  
 [!code-cpp[NVC_MFC_AxDataBinding&#1;](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&#2;](../../mfc/reference/codesnippet/cpp/cwnd-class_7.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&3;](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="a-namebindpropertya--cwndbindproperty"></a><a name="bindproperty"></a>CWnd:: BindProperty  
 Eine Cursor gebundene Eigenschaft auf einem datengebundenen Steuerelement (z. B. ein Rastersteuerelement) an ein Datenquellen-Steuerelement gebunden, und die Beziehung mit dem MFC-Bindung-Manager registriert.  
  
```  
void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispId*  
 Gibt die DISPID einer Eigenschaft auf einem datengebundenen Steuerelement, die an ein Datenquellen-Steuerelement gebunden werden soll.  
  
 `pWndDSC`  
 Verweist auf das Fenster Hosts die Datenquellen-Steuerelements an die Eigenschaft gebunden wird. Rufen Sie `GetDlgItem` mit der Ressourcen-ID des Hostfensters die DCS dieser Zeiger abgerufen.  
  
### <a name="remarks"></a>Hinweise  
 Das `CWnd` Objekt, auf dem Sie diese Funktion aufrufen, muss ein datengebundenes Steuerelement.  
  
### <a name="example"></a>Beispiel  
 `BindProperty`kann im folgenden Kontext verwendet werden:  
  
 [!code-cpp[NVC_MFC_AxDataBinding&#1;](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&4;](../../mfc/reference/codesnippet/cpp/cwnd-class_9.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding&3;](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="a-namebringwindowtotopa--cwndbringwindowtotop"></a><a name="bringwindowtotop"></a>CWnd::BringWindowToTop  
 Bringt `CWnd` nach oben im Stapel überlappender Fenster.  
  
```  
void BringWindowToTop();
```  
  
### <a name="remarks"></a>Hinweise  
 Darüber hinaus aktiviert `BringWindowToTop` Popupfenster, Fenster der obersten Ebene und untergeordnete MDI-Fenster. Die Memberfunktion `BringWindowToTop` sollte dazu verwendet werden, um jedes Fenster aufzudecken, das von irgendeinem überlappenden Fenster teilweise oder vollständig verdeckt ist.  
  
 Diese Funktion ruft nur die Win32 [BringWindowToTop](http://msdn.microsoft.com/library/windows/desktop/ms632673\(v=vs.85\).aspx) Funktion. Rufen Sie die [SetWindowPos](#setwindowpos) Funktion, um die Position eines Fensters in der Z-Reihenfolge zu ändern. Die `BringWindowToTop`-Funktion ändert nicht den Fensterstil, um daraus ein Fenster oberster Ebene zu machen. Weitere Informationen finden Sie unter [Was ist der Unterschied zwischen HWND_TOP and HWND_TOPMOST](http://blogs.msdn.com/b/oldnewthing/archive/2005/11/21/495246.aspx)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#71;](../../mfc/reference/codesnippet/cpp/cwnd-class_10.cpp)]  
  
##  <a name="a-namecalcwindowrecta--cwndcalcwindowrect"></a><a name="calcwindowrect"></a>CWnd::CalcWindowRect  
 Berechnet das Fenster Rechteck mit dem angegebenen Clientrechtecks enthalten kann.  
  
```  
virtual void CalcWindowRect(
    LPRECT lpClientRect,  
    UINT nAdjustType = adjustBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `lpClientRect`  
 Ein Zeiger auf eine Rectangle-Struktur. Bei der Eingabe enthält diese Struktur das Clientrechteck. Nach dem Beenden der Methode enthält dieser Struktur Fenster Rechteck mit der angegebenen Clientrechtecks enthalten kann.  
  
 [in] `nAdjustType`  
 Verwenden Sie `CWnd::adjustBorder` Fensterkoordinaten ohne berechnet die `WS_EX_CLIENTEDGE` formatieren; verwenden Sie andernfalls `CWnd::adjustOutside`.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe des Rechtecks berechneten Fenster umfasst nicht den Platz für eine Menüleiste.  
  
 Weitere verwendungseinschränkungen, finden Sie unter [AdjustWindowRectEx](http://msdn.microsoft.com/library/windows/desktop/ms632667).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#72;](../../mfc/reference/codesnippet/cpp/cwnd-class_11.cpp)]  
  
##  <a name="a-namecanceltooltipsa--cwndcanceltooltips"></a><a name="canceltooltips"></a>CWnd::CancelToolTips  
 Rufen Sie diese Memberfunktion, um eine QuickInfo auf dem Bildschirm zu entfernen, wenn derzeit eine QuickInfo angezeigt wird.  
  
```  
static void PASCAL CancelToolTips(BOOL bKeys = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *bKeys*  
 **True,** QuickInfos Abbrechen, wenn eine Taste gedrückt, und legen Sie den Text der Statusleiste auf; wird ansonsten **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Verwenden diese Memberfunktion hat keine Auswirkung auf QuickInfos im Code verwaltet. Diese Einstellung betrifft nur des QuickInfo-Steuerelements verwaltet [CWnd:: EnableToolTips](#enabletooltips).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#73;](../../mfc/reference/codesnippet/cpp/cwnd-class_12.cpp)]  
  
##  <a name="a-namecenterwindowa--cwndcenterwindow"></a><a name="centerwindow"></a>CWnd::CenterWindow  
 Zentriert ein Fenster relativ zu dessen übergeordnetem Element.  
  
```  
void CenterWindow(CWnd* pAlternateOwner = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pAlternateOwner`  
 Zeiger auf eine andere Fenster relativ zu dem er kann zentriert (andere als das übergeordnete Fenster).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel aufgerufen [CDialog::](../../mfc/reference/cdialog-class.md#oninitdialog) Center Dialogfelder relativ zum Hauptfenster der Anwendung. In der Standardeinstellung zentriert die Funktion untergeordnete Fenster relativ zu ihrer übergeordneten Fenster und Popupfenster relativ zu deren Besitzer. Wenn das Popup-Fenster nicht gehört, ist er relativ zum Bildschirm zentriert. So zentrieren Sie ein Fenster relativ zu einem bestimmten Fenster wird nicht der Besitzer oder die übergeordneten der `pAlternateOwner` Parameter kann auf ein gültiges Fenster festgelegt werden. Um relativ zum Bildschirm zentrieren zu erzwingen, übergeben Sie den Rückgabewert von [CWnd::GetDesktopWindow](#getdesktopwindow) als `pAlternateOwner`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#74;](../../mfc/reference/codesnippet/cpp/cwnd-class_13.cpp)]  
  
##  <a name="a-namechangeclipboardchaina--cwndchangeclipboardchain"></a><a name="changeclipboardchain"></a>CWnd::ChangeClipboardChain  
 Entfernt `CWnd` aus der Kette der Zwischenablage-Viewer und führt anhand des Fensters `hWndNext` Nachfolger der `CWnd` Vorgänger in der Kette.  
  
```  
BOOL ChangeClipboardChain(HWND hWndNext);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndNext`  
 Identifiziert das Fenster, das folgt `CWnd` in der Zwischenablage Kette.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namecheckdlgbuttona--cwndcheckdlgbutton"></a><a name="checkdlgbutton"></a>CWnd::CheckDlgButton  
 Aktiviert (ein Häkchen neben stellen) oder deaktiviert (entfernt ein Häkchen von) eine Schaltfläche oder ändert den Zustand einer drei-Status-Schaltfläche.  
  
```  
void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDButton`  
 Gibt die Schaltfläche geändert werden.  
  
 `nCheck`  
 Gibt die auszuführende Aktion an. Wenn `nCheck` ungleich NULL ist, wird der `CheckDlgButton` Member-Funktion setzt ein Häkchen neben der Schaltfläche; Wenn 0, wird das Kontrollkästchen deaktiviert. Drei-Status-Schaltflächen Wenn `nCheck` gleich 2 ist, den Zustand der Schaltfläche unbestimmt ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `CheckDlgButton` -Funktion sendet eine [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989) Nachricht an die angegebene Schaltfläche.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#75;](../../mfc/reference/codesnippet/cpp/cwnd-class_14.cpp)]  
  
##  <a name="a-namecheckradiobuttona--cwndcheckradiobutton"></a><a name="checkradiobutton"></a>CWnd::CheckRadioButton  
 Wählt (Fügt ein Häkchen) in einer Gruppe eine bestimmte Optionsfeld und löscht (entfernt einen Kontrollkästchen) alle anderen Optionsfelder in der Gruppe.  
  
```  
void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDFirstButton`  
 Gibt den ganzzahligen Bezeichner der das erste Optionsfeld in der Gruppe.  
  
 `nIDLastButton`  
 Gibt den ganzzahligen Bezeichner des letzten Optionsfelds in der Gruppe.  
  
 `nIDCheckButton`  
 Gibt den ganzzahligen Bezeichner des Optionsfelds überprüft werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die `CheckRadioButton` -Funktion sendet eine [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989) Nachricht an das angegebene Optionsfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#76;](../../mfc/reference/codesnippet/cpp/cwnd-class_15.cpp)]  
  
##  <a name="a-namechildwindowfrompointa--cwndchildwindowfrompoint"></a><a name="childwindowfrompoint"></a>CWnd::ChildWindowFromPoint  
 Bestimmt, die ggf. die untergeordneten Fenster zur `CWnd` den angegebenen Punkt enthält.  
  
```  
CWnd* ChildWindowFromPoint(POINT point) const;  
  
CWnd* ChildWindowFromPoint(
    POINT point,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Gibt die Clientkoordinaten des Punkts getestet werden soll.  
  
 *nFlags*  
 Gibt an, welche untergeordneten Fenstern zu überspringen. Dieser Parameter kann eine Kombination der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**CWP_ALL**|Lassen Sie keine untergeordneten Fenster|  
|**CWP_SKIPINVISIBLE**|Fahren Sie nicht sichtbare untergeordnete Fenster|  
|**CWP_SKIPDISABLED**|Überspringen Sie deaktivierte untergeordnete Fenster|  
|**CWP_SKIPTRANSPARENT**|Überspringen Sie transparente untergeordnete Fenster|  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das untergeordnete Fenster, das den Punkt enthält. Es ist **NULL** , wenn der angegebene Punkt außerhalb des Clientbereichs liegt. Wenn der Punkt im Clientbereich ist, aber nicht in einem beliebigen untergeordneten Fenster enthalten ist `CWnd` wird zurückgegeben.  
  
 Diese Memberfunktion gibt eine ausgeblendete oder deaktivierte untergeordnete Fenster zurück, die den angegebenen Punkt enthält.  
  
 Mehrere Fenster kann den angegebenen Punkt enthalten. Diese Funktion gibt jedoch nur die `CWnd`* des ersten Fensters gefunden, die den Punkt enthält.  
  
 Die `CWnd`* zurückgegeben wird, kann temporär sein und sollte nicht zur späteren Verwendung gespeichert werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#77;](../../mfc/reference/codesnippet/cpp/cwnd-class_16.cpp)]  
  
##  <a name="a-nameclienttoscreena--cwndclienttoscreen"></a><a name="clienttoscreen"></a>CWnd::ClientToScreen  
 Konvertiert die Clientkoordinaten eines bestimmten Punkts oder Rechtecks auf der Anzeige zu Bildschirmkoordinaten.  
  
```  
void ClientToScreen(LPPOINT lpPoint) const;  void ClientToScreen(LPRECT lpRect) const;  ```  
  
### Parameters  
 `lpPoint`  
 Points to a [POINT structure](../../mfc/reference/point-structure1.md) or `CPoint` object that contains the client coordinates to be converted.  
  
 `lpRect`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) or `CRect` object that contains the client coordinates to be converted.  
  
### Remarks  
 The `ClientToScreen` member function uses the client coordinates in the **POINT** or `RECT` structure or the `CPoint` or `CRect` object pointed to by `lpPoint` or `lpRect` to compute new screen coordinates; it then replaces the coordinates in the structure with the new coordinates. The new screen coordinates are relative to the upper-left corner of the system display.  
  
 The `ClientToScreen` member function assumes that the given point or rectangle is in client coordinates.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#78](../../mfc/reference/codesnippet/cpp/cwnd-class_17.cpp)]  
  
##  <a name="closewindow"></a>  CWnd::CloseWindow  
 Minimizes the window.  
  
```  
void CloseWindow();
```  
  
### Remarks  
 This member function emulates the functionality of the function [CloseWindow](http://msdn.microsoft.com/library/windows/desktop/ms632678), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="continuemodal"></a>  CWnd::ContinueModal  
 This member function is called by [RunModalLoop](#runmodalloop) to determine when the modal state should be exited.  
  
```  
virtuelle BOOL ContinueModal();
```  
  
### Return Value  
 Nonzero if modal loop is to be continued; 0 when [EndModalLoop](#endmodalloop) is called.  
  
### Remarks  
 By default, it returns non-zero until `EndModalLoop` is called.  
  
##  <a name="create"></a>  CWnd::Create  
 Creates the specified child window and attaches it to the [CWnd](../../mfc/reference/cwnd-class.md) object.  
  
```  
virtuelle BOOL erstellen (LPCTSTR "lpszclassname",  
    LPCTSTR LpszWindowName,  
    DWORD-dwStyle  
    Const RECT & Rect,  
    CWnd* pParentWnd "," UINT nID "angegeben ist und* pContext = NULL);
```  
  
### Parameters  
 [in] `lpszClassName`  
 Pointer to a null-terminated string that contains the name of a registered system window class; or the name of a predefined system window class.  
  
 [in] `lpszWindowName`  
 Pointer to a null-terminated string that contains the window display name; otherwise `NULL` for no window display name.  
  
 [in] `dwStyle`  
 Bitwise combination (OR) of [window styles](../../mfc/reference/window-styles.md). The `WS_POPUP` option is not a valid style.  
  
 [in] `rect`  
 The size and location of the window relative to the top-left corner of the parent window.  
  
 [in] `pParentWnd`  
 Pointer to the parent window.  
  
 [in] `nID`  
 ID of the window.  
  
 [in] `pContext`  
 Pointer to a [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) structure that is used to customize the document-view architecture for the application.  
  
### Return Value  
 `TRUE` if the method was successful; otherwise `FALSE`.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of its `CREATESTRUCT` parameter to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 Use the [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) function to register window classes. User defined window classes are available in the module where they are registered.  
  
 The [CWnd::OnCreate](#oncreate) method is called before the `Create` method returns, and before the window becomes visible.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#79](../../mfc/reference/codesnippet/cpp/cwnd-class_18.cpp)]  
  
##  <a name="createaccessibleproxy"></a>  CWnd::CreateAccessibleProxy  
 Creates an Active Accessibility proxy for the specified object.  
  
```  
virtuelle HRESULT CreateAccessibleProxy (wParam WPARAM-Parameter  
    LPARAM lParam  
    LRESULT* pResult);
```  
  
### Parameters  
 `wParam`  
 Identifies the object accessed by the Active Accessibility proxy. Can be one of the following values  
  
|Value|Meaning|  
|-----------|-------------|  
|**OBJID_CLIENT**|Refers to the window's client area.|  
  
 `lParam`  
 Provides additional message-dependent information.  
  
 `pResult`  
 A pointer to an **LRESULT** that stores the result code.  
  
### Remarks  
 Creates an Active Accessibility proxy for the specified object.  
  
##  <a name="createcaret"></a>  CWnd::CreateCaret  
 Creates a new shape for the system caret and claims ownership of the caret.  
  
```  
void CreateCaret (CBitmap * pBitmap);
```  
  
### Parameters  
 `pBitmap`  
 Identifies the bitmap that defines the caret shape.  
  
### Remarks  
 The bitmap must have previously been created by the [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap) member function, the [CreateDIBitmap](http://msdn.microsoft.com/library/windows/desktop/dd183491) Windows function, or the [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap) member function.  
  
 `CreateCaret` automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#80](../../mfc/reference/codesnippet/cpp/cwnd-class_19.cpp)]  
  
##  <a name="createcontrol"></a>  CWnd::CreateControl  
 Use this member function to create an ActiveX control that will be represented in the MFC program by a `CWnd` object.  
  
```  
BOOL CreateControl (LPCTSTR PszClass,  
    LPCTSTR PszWindowName,  
    DWORD-dwStyle  
    const RECT & Rechteck,  
    CWnd* pParentWnd, UINT nID CFile* pPersist = NULL  
    BOOL bStorage = FALSE  
    BSTR-BstrLicKey = NULL);

 
BOOL CreateControl (REFCLSID clsid  
    LPCTSTR PszWindowName,  
    DWORD-dwStyle  
    const RECT & Rechteck,  
    CWnd* pParentWnd, UINT nID CFile* pPersist = NULL  
    BOOL bStorage = FALSE  
    BSTR-BstrLicKey = NULL);

 
BOOL CreateControl (REFCLSID clsid  
    LPCTSTR PszWindowName,  
    DWORD-dwStyle  
    const Punkt* ppt, const Größe* Psize,  
    CWnd* pParentWnd, UINT nID CFile* pPersist = NULL  
    BOOL bStorage = FALSE  
    BSTR-BstrLicKey = NULL);
```  
  
### Parameters  
 *pszClass*  
 This string may contain the OLE "short name" (ProgID) for the class, e.g., "CIRC3.Circ3Ctrl.1". The name needs to match the same name registered by the control. Alternatively, the string may contain the string form of a **CLSID**, contained in braces, e.g., "{9DBAFCCF-592F-101B-85CE-00608CEC297B}". In either case, `CreateControl` converts the string to the corresponding class ID.  
  
 *pszWindowName*  
 A pointer to the text to be displayed in the control. Sets the value of the control's Caption or Text property (if any). If **NULL**, the control's Caption or Text property is not changed.  
  
 `dwStyle`  
 Windows styles. The available styles are listed under Remarks.  
  
 `rect`  
 Specifies the control's size and position. It can be either a [CRect](../../atl-mfc-shared/reference/crect-class.md) object or a [RECT structure](../../mfc/reference/rect-structure1.md).  
  
 `ppt`  
 Points to a [POINT structure](../../mfc/reference/point-structure1.md) or `CPoint` object that contains the upper left corner of the control.  
  
 `pSize`  
 Points to a [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure or `CSize` object that contains the control's size  
  
 `pParentWnd`  
 Specifies the control's parent window. It must not be **NULL**.  
  
 `nID`  
 Specifies the control's ID.  
  
 `pPersist`  
 A pointer to a [CFile](../../mfc/reference/cfile-class.md) containing the persistent state for the control. The default value is **NULL**, indicating that the control initializes itself without restoring its state from any persistent storage. If not **NULL**, it should be a pointer to a `CFile`-derived object which contains the control's persistent data, in the form of either a stream or a storage. This data could have been saved in a previous activation of the client. The `CFile` can contain other data, but must have its read-write pointer set to the first byte of persistent data at the time of the call to `CreateControl`.  
  
 `bStorage`  
 Indicates whether the data in `pPersist` should be interpreted as IStorage or IStream data. If the data in `pPersist` is a storage, `bStorage` should be **TRUE**. If the data in `pPersist` is a stream, `bStorage` should be **FALSE**. The default value is **FALSE**.  
  
 *bstrLicKe*y  
 Optional license key data. This data is needed only for creating controls that require a run-time license key. If the control supports licensing, you must provide a license key for the creation of the control to succeed. The default value is **NULL**.  
  
 `clsid`  
 The unique class ID of the control.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 `CreateControl` is a direct analog of the [CWnd::Create](#create) function, which creates the window for a `CWnd`. `CreateControl` creates an ActiveX control instead of an ordinary window.  
  
 Only a subset of the Windows `dwStyle` flags are supported for `CreateControl`:  
  
- **WS_VISIBLE** Creates a window that is initially visible. Required if you want the control to be visible immediately, like ordinary windows.  
  
- **WS_DISABLED** Creates a window that is initially disabled. A disabled window cannot receive input from the user. Can be set if the control has an Enabled property.  
  
- `WS_BORDER` Creates a window with a thin-line border. Can be set if control has a BorderStyle property.  
  
- **WS_GROUP** Specifies the first control of a group of controls. The user can change the keyboard focus from one control in the group to the next by using the direction keys. All controls defined with the **WS_GROUP** style after the first control belong to the same group. The next control with the **WS_GROUP** style ends the group and starts the next group.  
  
- **WS_TABSTOP** Specifies a control that can receive the keyboard focus when the user presses the TAB key. Pressing the TAB key changes the keyboard focus to the next control of the **WS_TABSTOP** style.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#81](../../mfc/reference/codesnippet/cpp/cwnd-class_20.h)]  
  
##  <a name="createex"></a>  CWnd::CreateEx  
 Creates the specified window and attaches it to the `CWnd` object.  
  
```  
virtuelle BOOL CreateEx (DWORD DwExStyle,  
    LPCTSTR "lpszclassname",  
    LPCTSTR LpszWindowName,  
    DWORD-dwStyle  
    Int x  
    Int-y  
    Int-nWidth  
    Int-nHeight  
    HWND-hWndParent  
    HMENU-nIDorHMenu  
    LPVOID LpParam = NULL);

 
virtuelle BOOL CreateEx (DWORD DwExStyle,  
    LPCTSTR "lpszclassname",  
    LPCTSTR LpszWindowName,  
    DWORD-dwStyle  
    const RECT & Rechteck,  
    CWnd * pParentWnd,  
    UINT nID  
    LPVOID LpParam = NULL);
```  
  
### Parameters  
 `dwExStyle`  
 Bitwise combination (OR) of [extended window styles](../../mfc/reference/extended-window-styles.md); otherwise `NULL` for the default extended window style.  
  
 `lpszClassName`  
 Pointer to a null-terminated string that contains the name of a registered system window class; or the name of a predefined system window class.  
  
 `lpszWindowName`  
 Pointer to a null-terminated string that contains the window display name; otherwise `NULL` for no window display name.  
  
 `dwStyle`  
 Bitwise combination (OR) of [window styles](../../mfc/reference/window-styles.md); otherwise `NULL` for the default window style.  
  
 `x`  
 The initial horizontal distance of the window from the left side of the screen or the parent window.  
  
 `y`  
 The initial vertical distance of the window from the top of the screen or the parent window.  
  
 `nWidth`  
 The width, in pixels, of the window.  
  
 `nHeight`  
 The height, in pixels, of the window.  
  
 `hwndParent`  
 For a child window, the handle to the parent window; otherwise, the handle of the owner window if the window has an owner.  
  
 `nIDorHMenu`  
 For a child window, the window ID; otherwise, the ID of a menu for the window.  
  
 `lpParam`  
 Pointer to user data that is passed to the [CWnd::OnCreate](#oncreate) method in the `lpCreateParams` field.  
  
 `rect`  
 The size and location of the window relative to the screen or the parent window.  
  
 `pParentWnd`  
 For a child window, pointer to the parent window; otherwise, pointer to the owner window if the window has an owner.  
  
 `nID`  
 For a child window, the window ID; otherwise, the ID of a menu for the window.  
  
### Return Value  
 `TRUE` if the method was successful; otherwise `FALSE`.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of its `CREATESTRUCT` parameter to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 The default extended window style is `WS_EX_LEFT`. The default window style is `WS_OVERLAPPED`.  
  
 Use the [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) function to register window classes. User defined window classes are available in the module where they are registered.  
  
 Dimensions for child windows are relative to the top-left corner of the client area of the parent window. Dimensions for top-level windows are relative to the top-left corner of the screen.  
  
 The [CWnd::OnCreate](#oncreate) method is called before the `CreateEx` method returns, and before the window becomes visible.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#82](../../mfc/reference/codesnippet/cpp/cwnd-class_21.cpp)]  
  
##  <a name="creategraycaret"></a>  CWnd::CreateGrayCaret  
 Creates a gray rectangle for the system caret and claims ownership of the caret.  
  
```  
void CreateGrayCaret (Int nWidth,  
    Int nHeight);
```  
  
### Parameters  
 `nWidth`  
 Specifies the width of the caret (in logical units). If this parameter is 0, the width is set to the system-defined window-border width.  
  
 `nHeight`  
 Specifies the height of the caret (in logical units). If this parameter is 0, the height is set to the system-defined window-border height.  
  
### Remarks  
 The caret shape can be a line or a block.  
  
 The parameters `nWidth` and `nHeight` specify the caret's width and height (in logical units); the exact width and height (in pixels) depend on the mapping mode.  
  
 The system's window-border width or height can be retrieved by the [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function with the **SM_CXBORDER** and **SM_CYBORDER** indexes. Using the window-border width or height ensures that the caret will be visible on a high-resolution display.  
  
 The `CreateGrayCaret` member function automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#83](../../mfc/reference/codesnippet/cpp/cwnd-class_22.cpp)]  
  
##  <a name="createsolidcaret"></a>  CWnd::CreateSolidCaret  
 Creates a solid rectangle for the system caret and claims ownership of the caret.  
  
```  
void CreateSolidCaret (Int nWidth,  
    Int nHeight);
```  
  
### Parameters  
 `nWidth`  
 Specifies the width of the caret (in logical units). If this parameter is 0, the width is set to the system-defined window-border width.  
  
 `nHeight`  
 Specifies the height of the caret (in logical units). If this parameter is 0, the height is set to the system-defined window-border height.  
  
### Remarks  
 The caret shape can be a line or block.  
  
 The parameters `nWidth` and `nHeight` specify the caret's width and height (in logical units); the exact width and height (in pixels) depend on the mapping mode.  
  
 The system's window-border width or height can be retrieved by the [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function with the **SM_CXBORDER** and **SM_CYBORDER** indexes. Using the window-border width or height ensures that the caret will be visible on a high-resolution display.  
  
 The `CreateSolidCaret` member function automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#84](../../mfc/reference/codesnippet/cpp/cwnd-class_23.cpp)]  
  
##  <a name="cwnd"></a>  CWnd::CWnd  
 Constructs a `CWnd` object.  
  
```  
CWnd();
```  
  
### Remarks  
 The Windows window is not created and attached until the [CreateEx](#createex) or [Create](#create) member function is called.  
  
##  <a name="default"></a>  CWnd::Default  
 Calls the default window procedure.  
  
```  
Default() LRESULT;
```  
  
### Return Value  
 Depends on the message sent.  
  
### Remarks  
 The default window procedure provides default processing for any window message that an application does not process. This member function ensures that every message is processed.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#85](../../mfc/reference/codesnippet/cpp/cwnd-class_24.cpp)]  
  
##  <a name="defwindowproc"></a>  CWnd::DefWindowProc  
 Calls the default window procedure, which provides default processing for any window message that an application does not process.  
  
```  
virtuelle LRESULT DefWindowProc (UINT-Nachricht,  
    WPARAM wParam-Parameter  
    LPARAM lParam);
```  
  
### Parameters  
 `message`  
 Specifies the Windows message to be processed.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
### Return Value  
 Depends on the message sent.  
  
### Remarks  
 This member function ensures that every message is processed. It should be called with the same parameters as those received by the window procedure.  
  
##  <a name="deletetempmap"></a>  CWnd::DeleteTempMap  
 Called automatically by the idle time handler of the `CWinApp` object.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### Remarks  
 Deletes any temporary `CWnd` objects created by the `FromHandle` member function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#86](../../mfc/reference/codesnippet/cpp/cwnd-class_25.cpp)]  
  
##  <a name="destroywindow"></a>  CWnd::DestroyWindow  
 Destroys the Windows window attached to the `CWnd` object.  
  
```  
virtuelle BOOL DestroyWindow();
```  
  
### Return Value  
 Nonzero if the window is destroyed; otherwise 0.  
  
### Remarks  
 The `DestroyWindow` member function sends appropriate messages to the window to deactivate it and remove the input focus. It also destroys the window's menu, flushes the application queue, destroys outstanding timers, removes Clipboard ownership, and breaks the Clipboard-viewer chain if `CWnd` is at the top of the viewer chain. It sends [WM_DESTROY](#ondestroy) and [WM_NCDESTROY](#onncdestroy) messages to the window. It does not destroy the `CWnd` object.  
  
 `DestroyWindow` is a place holder for performing cleanup. Because `DestroyWindow` is a virtual function, it is shown in any `CWnd`-derived class in Class View. But even if you override this function in your `CWnd`-derived class, `DestroyWindow` is not necessarily called. If `DestroyWindow` is not called in the MFC code, then you have to explicitly call it in your own code if you want it to be called.  
  
 Assume, for example, you have overridden `DestroyWindow` in a `CView`-derived class. Since MFC source code does not call `DestroyWindow` in any of its `CFrameWnd`-derived classes, your overridden `DestroyWindow` will not be called unless you call it explicitly.  
  
 If the window is the parent of any windows, these child windows are automatically destroyed when the parent window is destroyed. The `DestroyWindow` member function destroys child windows first and then the window itself.  
  
 The `DestroyWindow` member function also destroys modeless dialog boxes created by [CDialog::Create](../../mfc/reference/cdialog-class.md#create).  
  
 If the `CWnd` being destroyed is a child window and does not have the [WS_EX_NOPARENTNOTIFY](../../mfc/reference/extended-window-styles.md) style set, then the [WM_PARENTNOTIFY ](https://msdn.microsoft.com/library/ms632638.aspx)       message is sent to the parent.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#87](../../mfc/reference/codesnippet/cpp/cwnd-class_26.cpp)]  
  
##  <a name="detach"></a>  CWnd::Detach  
 Detaches a Windows handle from a `CWnd` object and returns the handle.  
  
```  
HWND Detach();
```  
  
### Return Value  
 A `HWND` to the Windows object.  
  
### Example  
  See the example for [CWnd::Attach](#attach).  
  
##  <a name="dlgdirlist"></a>  CWnd::DlgDirList  
 Fills a list box with a file or directory listing.  
  
```  
Int DlgDirList (LPTSTR LpPathSpec,  
    Int-nIDListBox  
    Int-nIDStaticPath  
    UINT-nFileType);
```  
  
### Parameters  
 `lpPathSpec`  
 Points to a null-terminated string that contains the path or filename. `DlgDirList` modifies this string, which should be long enough to contain the modifications. For more information, see the following "Remarks" section.  
  
 `nIDListBox`  
 Specifies the identifier of a list box. If `nIDListBox` is 0, `DlgDirList` assumes that no list box exists and does not attempt to fill one.  
  
 `nIDStaticPath`  
 Specifies the identifier of the static-text control used to display the current drive and directory. If `nIDStaticPath` is 0, `DlgDirList` assumes that no such text control is present.  
  
 `nFileType`  
 Specifies the attributes of the files to be displayed. It can be any combination of the following values:  
  
- **DDL_READWRITE** Read-write data files with no additional attributes.  
  
- **DDL_READONLY** Read-only files.  
  
- **DDL_HIDDEN** Hidden files.  
  
- **DDL_SYSTEM** System files.  
  
- **DDL_DIRECTORY** Directories.  
  
- **DDL_ARCHIVE** Archives.  
  
- **DDL_POSTMSGS LB_DIR** flag. If the **LB_DIR** flag is set, Windows places the messages generated by `DlgDirList` in the application's queue; otherwise, they are sent directly to the dialog-box procedure.  
  
- **DDL_DRIVES** Drives. If the **DDL_DRIVES** flag is set, the **DDL_EXCLUSIVE** flag is set automatically. Therefore, to create a directory listing that includes drives and files, you must call `DlgDirList` twice: once with the **DDL_DRIVES** flag set and once with the flags for the rest of the list.  
  
- **DDL_EXCLUSIVE** Exclusive bit. If the exclusive bit is set, only files of the specified type are listed; otherwise normal files and files of the specified type are listed.  
  
### Return Value  
 Nonzero if the function is successful; otherwise 0.  
  
### Remarks  
 `DlgDirList` sends [LB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb761325) and [LB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775185) messages to the list box. It fills the list box specified by `nIDListBox` with the names of all files that match the path given by `lpPathSpec`.  
  
 The `lpPathSpec` parameter has the following form:  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 In this example, `drive` is a drive letter, `directory` is a valid directory name, and *filename* is a valid filename that must contain at least one wildcard. The wildcards are a question mark ( ****), which means match any character, and an asterisk ( **\***), meaning match any number of characters.  
  
 If you specify a 0-length string for `lpPathSpec`, or if you specify only a directory name but do not include any file specification, the string will be changed to "*.\*".  
  
 If `lpPathSpec` includes a drive and/or directory name, the current drive and directory are changed to the designated drive and directory before the list box is filled. The text control identified by `nIDStaticPath` is also updated with the new drive and/or directory name.  
  
 After the list box is filled, `lpPathSpec` is updated by removing the drive and/or directory portion of the path.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#88](../../mfc/reference/codesnippet/cpp/cwnd-class_27.cpp)]  
  
##  <a name="dlgdirlistcombobox"></a>  CWnd::DlgDirListComboBox  
 Fills the list box of a combo box with a file or directory listing.  
  
```  
Int DlgDirListComboBox (LPTSTR LpPathSpec,  
    Int-nIDComboBox  
    Int-nIDStaticPath  
    UINT-nFileType);
```  
  
### Parameters  
 `lpPathSpec`  
 Points to a null-terminated string that contains the path or filename. `DlgDirListComboBox` modifies this string, so this data should not be in the form of a string literal. See the following "Remarks" section.  
  
 `nIDComboBox`  
 Specifies the identifier of a combo box in a dialog box. If `nIDComboBox` is 0, `DlgDirListComboBox` assumes that no combo box exists and does not attempt to fill one.  
  
 `nIDStaticPath`  
 Specifies the identifier of the static-text control used to display the current drive and directory. If `nIDStaticPath` is 0, `DlgDirListComboBox` assumes that no such text control is present.  
  
 `nFileType`  
 Specifies DOS file attributes of the files to be displayed. It can be any combination of the following values:  
  
- **DDL_READWRITE** Read-write data files with no additional attributes.  
  
- **DDL_READONLY** Read-only files.  
  
- **DDL_HIDDEN** Hidden files.  
  
- **DDL_SYSTEM** System files.  
  
- **DDL_DIRECTORY** Directories.  
  
- **DDL_ARCHIVE** Archives.  
  
- **DDL_POSTMSGS CB_DIR** flag. If the **CB_DIR** flag is set, Windows places the messages generated by `DlgDirListComboBox` in the application's queue; otherwise, they are sent directly to the dialog-box procedure.  
  
- **DDL_DRIVES** Drives. If the **DDL_DRIVES** flag is set, the **DDL_EXCLUSIVE** flag is set automatically. Therefore, to create a directory listing that includes drives and files, you must call `DlgDirListComboBox` twice: once with the **DDL_DRIVES** flag set and once with the flags for the rest of the list.  
  
- **DDL_EXCLUSIVE** Exclusive bit. If the exclusive bit is set, only files of the specified type are listed; otherwise normal files and files of the specified type are listed.  
  
### Return Value  
 Specifies the outcome of the function. It is nonzero if a listing was made, even an empty listing. A 0 return value implies that the input string did not contain a valid search path.  
  
### Remarks  
 `DlgDirListComboBox` sends [CB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb775878) and [CB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775832) messages to the combo box. It fills the list box of the combo box specified by `nIDComboBox` with the names of all files that match the path given by `lpPathSpec`.  
  
 The `lpPathSpec` parameter has the following form:  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 In this example, `drive` is a drive letter, `directory` is a valid directory name, and *filename* is a valid filename that must contain at least one wildcard. The wildcards are a question mark ( ****), which means match any character, and an asterisk ( **\***), which means match any number of characters.  
  
 If you specify a zero-length string for `lpPathSpec`, the current directory will be used and `lpPathSpec` will not be modified. If you specify only a directory name but do not include any file specification, the string will be changed to "*".  
  
 If `lpPathSpec` includes a drive and/or directory name, the current drive and directory are changed to the designated drive and directory before the list box is filled. The text control identified by `nIDStaticPath` is also updated with the new drive and/or directory name.  
  
 After the combo-box list box is filled, `lpPathSpec` is updated by removing the drive and/or directory portion of the path.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#89](../../mfc/reference/codesnippet/cpp/cwnd-class_28.cpp)]  
  
##  <a name="dlgdirselect"></a>  CWnd::DlgDirSelect  
 Retrieves the current selection from a list box.  
  
```  
BOOL DlgDirSelect (LPTSTR LpString,  
    Int nIDListBox);
```  
  
### Parameters  
 `lpString`  
 Points to a buffer that is to receive the current selection in the list box.  
  
 `nIDListBox`  
 Specifies the integer ID of a list box in the dialog box.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 It assumes that the list box has been filled by the [DlgDirList](#dlgdirlist) member function and that the selection is a drive letter, a file, or a directory name.  
  
 The `DlgDirSelect` member function copies the selection to the buffer given by `lpString`. If there is no selection, `lpString` does not change.  
  
 `DlgDirSelect` sends [LB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775197) and [LB_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761313) messages to the list box.  
  
 It does not allow more than one filename to be returned from a list box. The list box must not be a multiple-selection list box.  
  
##  <a name="dlgdirselectcombobox"></a>  CWnd::DlgDirSelectComboBox  
 Retrieves the current selection from the list box of a combo box.  
  
```  
BOOL DlgDirSelectComboBox (LPTSTR LpString,  
    Int nIDComboBox);
```  
  
### Parameters  
 `lpString`  
 Points to a buffer that is to receive the selected path.  
  
 `nIDComboBox`  
 Specifies the integer ID of the combo box in the dialog box.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 It assumes that the list box has been filled by the [DlgDirListComboBox](#dlgdirlistcombobox) member function and that the selection is a drive letter, a file, or a directory name.  
  
 The `DlgDirSelectComboBox` member function copies the selection to the specified buffer. If there is no selection, the contents of the buffer are not changed.  
  
 `DlgDirSelectComboBox` sends [CB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775845) and [CB_GETLBTEXT](http://msdn.microsoft.com/library/windows/desktop/bb775862) messages to the combo box.  
  
 It does not allow more than one filename to be returned from a combo box.  
  
##  <a name="dodataexchange"></a>  CWnd::DoDataExchange  
 Called by the framework to exchange and validate dialog data.  
  
```  
virtuelle void DoDataExchange (CDataExchange * pDX);
```  
  
### Parameters  
 `pDX`  
 A pointer to a `CDataExchange` object.  
  
### Remarks  
 Never call this function directly. It is called by the [UpdateData](#updatedata) member function. Call `UpdateData` to initialize a dialog box's controls or retrieve data from a dialog box.  
  
 When you derive an application-specific dialog class from [CDialog](../../mfc/reference/cdialog-class.md), you need to override this member function if you wish to utilize the framework's automatic data exchange and validation. The Add Variable wizard will write an overridden version of this member function for you containing the desired "data map" of dialog data exchange (DDX) and validation (DDV) global function calls.  
  
 To automatically generate an overridden version of this member function, first create a dialog resource with the dialog editor, then derive an application-specific dialog class. Then use the Add Variable wizard to associate variables, data, and validation ranges with various controls in the new dialog box. The wizard then writes the overridden `DoDataExchange`, which contains a data map. The following is an example DDX/DDV code block generated by the Add Variable wizard:  
  
 [!code-cpp[NVC_MFCWindowing#90](../../mfc/reference/codesnippet/cpp/cwnd-class_29.cpp)]  
  
 The `DoDataExchange` overridden member function must precede the macro statements in your source file.  
  
 For more information on dialog data exchange and validation, see [Displaying and Manipulating Data in a Form](../../data/odbc/displaying-and-manipulating-data-in-a-form.md) and [Dialog Data Exchange and Validation](../../mfc/dialog-data-exchange-and-validation.md). For a description of the DDX_ and DDV_ macros generated by the Add Variable wizard, see [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md).  
  
##  <a name="dragacceptfiles"></a>  CWnd::DragAcceptFiles  
 Call this member function from within a window, using a `CWnd` pointer, in your application's [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) function to indicate that the window accepts dropped files from the Windows File Manager or File Explorer.  
  
```  
void DragAcceptFiles (BOOL bAccept = TRUE);
```  
  
### Parameters  
 *BAccept*  
 Flag that indicates whether dragged files are accepted.  
  
### Remarks  
 Only the window that calls `DragAcceptFiles` with the `bAccept` parameter set to **TRUE** has identified itself as able to process the Windows message `WM_DROPFILES`. For example, in an MDI application, if the `CMDIFrameWnd` window pointer is used in the `DragAcceptFiles` function call, only the `CMDIFrameWnd` window gets the `WM_DROPFILES` message. This message is not sent to all open `CMDIChildWnd` windows. For a `CMDIChildWnd` window to receive this message, you must call `DragAcceptFiles` with the `CMDIChildWnd` window pointer.  
  
 To discontinue receiving dragged files, call the member function with `bAccept` set to **FALSE**.  
  
##  <a name="dragdetect"></a>  CWnd::DragDetect  
 Captures the mouse and tracks its movement until the user releases the left button, presses the ESC key, or moves the mouse outside the drag rectangle around the specified point.  
  
```  
BOOL DragDetect(POINT pt) const;  
```  
  
### Parameters  
 `pt`  
 Initial position of the mouse, in screen coordinates. The function determines the coordinates of the drag rectangle by using this point.  
  
### Return Value  
 If the user moved the mouse outside of the drag rectangle while holding down the left button , the return value is nonzero.  
  
 If the user did not move the mouse outside of the drag rectangle while holding down the left button , the return value is zero.  
  
### Remarks  
 This member function emulates the functionality of the function [DragDetect](http://msdn.microsoft.com/library/windows/desktop/ms646256), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawanimatedrects"></a>  CWnd::DrawAnimatedRects  
 Draws a wire-frame rectangle and animates it to indicate the opening of an icon or the minimizing or maximizing of a window.  
  
```  
BOOL DrawAnimatedRects (Int IdAni,  
    CONST-RECT* LprcFrom, CONST RECT* LprcTo);
```  
  
### Parameters  
 *idAni*  
 Specifies the type of animation. If you specify **IDANI_CAPTION**, the window caption will animate from the position specified by `lprcFrom` to the position specified by `lprcTo`. The effect is similar to minimizing or maximizing a window.  
  
 `lprcFrom`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure specifying the location and size of the icon or minimized window.  
  
 `lprcTo`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure specifying the location and size of the restored window  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [DrawAnimatedRects](http://msdn.microsoft.com/library/windows/desktop/dd162475), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawcaption"></a>  CWnd::DrawCaption  
 Draws a window caption.  
  
```  
BOOL DrawCaption (CDC * pDC,  
    LPCRECT-lprc  
    UINT-uFlags);
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context. The function draws the window caption into this device context.  
  
 `lprc`  
 A pointer to a RECT structure that specifies the bounding rectangle for the window caption.  
  
 `uFlags`  
 Specifies drawing options. For a complete list of values, see [DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawmenubar"></a>  CWnd::DrawMenuBar  
 Redraws the menu bar.  
  
```  
void DrawMenuBar();
```  
  
### Remarks  
 If a menu bar is changed after Windows has created the window, call this function to draw the changed menu bar.  
  
### Example  
  See the example for [CWnd::GetMenu](#getmenu).  
  
##  <a name="enableactiveaccessibility"></a>  CWnd::EnableActiveAccessibility  
 Enables user-defined Active Accessibility functions.  
  
```  
void EnableActiveAccessibility();
```  
  
### Remarks  
 MFC's default Active Accessibility support is sufficient for standard windows and controls, including ActiveX controls; however, if your `CWnd`-derived class contains nonwindowed user interface elements, MFC has no way of knowing about them. In that case, you must override the appropriate [Active Accessibility member functions](http://msdn.microsoft.com/en-us/68af04ac-4eb9-4b7d-b33f-c45512097a74) in your class, and you must call **EnableActiveAccessibility** in the class's constructor.  
  
##  <a name="enabledynamiclayout"></a>  CWnd::EnableDynamicLayout  
 Enables or disables the dynamic layout manager. When dynamic layout is enabled, the position and size of child windows can adjust dynamically when the user resizes the window.  
  
```  
void EnableDynamicLayout (BOOL bAktivieren = TRUE);
```  
  
### Parameters  
 `bEnable`  
 TRUE to enable dynamic layout; FALSE to disable dynamic layout.  
  
### Remarks  
 If you want to enable dynamic layout, you have to do more than just call this method. You also have to provide dynamic layout information which species how the controls in the window respond to size changes. You can specify this information in the resource editor, or programmatically, for each control. See [Dynamic Layout](../../mfc/dynamic-layout.md).  
  
##  <a name="enabled2dsupport"></a>  CWnd::EnableD2DSupport  
 Enables or disables window D2D support. Call this method before the main window is initialized.  
  
```  
void EnableD2DSupport (BOOL bAktivieren = TRUE:  
    BOOL bUseDCRenderTarget = FALSE);
```  
  
### Parameters  
 `bEnable`  
 Specifies whether to turn on, or off D2D support.  
  
 `bUseDCRenderTarget`  
 Species whether to use the Device Context (DC) render target, CDCRenderTarget. If FALSE, CHwndRenderTarget is used.  
  
##  <a name="enablescrollbar"></a>  CWnd::EnableScrollBar  
 Enables or disables one or both arrows of a scroll bar.  
  
```  
BOOL EnableScrollBar (Int nSBFlags,  
    UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### Parameters  
 *nSBFlags*  
 Specifies the scroll-bar type. Can have one of the following values:  
  
- **SB_BOTH** Enables or disables the arrows of the horizontal and vertical scroll bars associated with the window.  
  
- **SB_HORZ** Enables or disables the arrows of the horizontal scroll bar associated with the window.  
  
- **SB_VERT** Enables or disables the arrows of the vertical scroll bar associated with the window.  
  
 `nArrowFlags`  
 Specifies whether the scroll-bar arrows are enabled or disabled and which arrows are enabled or disabled. Can have one of the following values:  
  
- **ESB_ENABLE_BOTH** Enables both arrows of a scroll bar (default).  
  
- **ESB_DISABLE_LTUP** Disables the left arrow of a horizontal scroll bar or the up arrow of a vertical scroll bar.  
  
- **ESB_DISABLE_RTDN** Disables the right arrow of a horizontal scroll bar or the down arrow of a vertical scroll bar.  
  
- **ESB_DISABLE_BOTH** Disables both arrows of a scroll bar.  
  
### Return Value  
 Nonzero if the arrows are enabled or disabled as specified. Otherwise it is 0, which indicates that the arrows are already in the requested state or that an error occurred.  
  
##  <a name="enablescrollbarctrl"></a>  CWnd::EnableScrollBarCtrl  
 Enables or disables the scroll bar for this window.  
  
```  
void EnableScrollBarCtrl (Int nBar,  
    BOOL bAktivieren = TRUE);
```  
  
### Parameters  
 `nBar`  
 The scroll-bar identifier.  
  
 `bEnable`  
 Specifies whether the scroll bar is to be enabled or disabled.  
  
### Remarks  
 If the window has a sibling scroll-bar control, that scroll bar is used; otherwise the window's own scroll bar is used.  
  
##  <a name="enabletooltips"></a>  CWnd::EnableToolTips  
 Enables tool tips for the given window.  
  
```  
BOOL EnableToolTips(BOOL bEnable = TRUE);
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the tool tip control is enabled or disabled. **TRUE** enables the control; **FALSE** disables the control.  
  
### Return Value  
 **TRUE** if tool tips are enabled; otherwise **FALSE**.  
  
### Remarks  
 Override [OnToolHitTest](#ontoolhittest) to provide the [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) struct or structs for the window.  
  
> [!NOTE]
>  Some windows, such as [CToolBar](../../mfc/reference/ctoolbar-class.md), provide a built-in implementation of [OnToolHitTest](#ontoolhittest).  
  
 See [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information on this structure.  
  
 Simply calling `EnableToolTips` is not enough to display tool tips for your child controls unless the parent window is derived from `CFrameWnd`. This is because `CFrameWnd` provides a default handler for the **TTN_NEEDTEXT** notification. If your parent window is not derived from `CFrameWnd`, that is, if it is a dialog box or a form view, tool tips for your child controls will not display correctly unless you provide a handler for the **TTN_NEEDTEXT** tool tip notification. See [Tool Tips](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 The default tool tips provided for your windows by `EnableToolTips` do not have text associated with them. To retrieve text for the tool tip to display, the **TTN_NEEDTEXT** notification is sent to the tool tip control's parent window just before the tool tip window is displayed. If there is no handler for this message to assign some value to the `pszText` member of the **TOOLTIPTEXT** structure, there will be no text displayed for the tool tip.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#91](../../mfc/reference/codesnippet/cpp/cwnd-class_30.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#92](../../mfc/reference/codesnippet/cpp/cwnd-class_31.cpp)]  
  
##  <a name="enabletrackingtooltips"></a>  CWnd::EnableTrackingToolTips  
 Enables or disables tracking tooltips.  
  
```  
BOOL EnableTrackingToolTips(BOOL bEnable = TRUE);
```  
  
### Parameters  
 `bEnable`  
 Specifies whether tracking tool tips are enabled or disabled. If this parameter is **TRUE**, the tracking tool tips will be enabled. If this parameter is **FALSE**, the tracking tool tips will be disabled.  
  
### Return Value  
 Indicates the state before the `EnableWindow` member function was called. The return value is nonzero if the window was previously disabled. The return value is 0 if the window was previously enabled or an error occurred.  
  
### Remarks  
 Tracking tool tips are tool tip windows that you can dynamically position on the screen. By rapidly updating the position, the tool tip window appears to move smoothly, or "track." This functionality can be useful if you need tool tip text to follow the position of the pointer as it moves.  
  
##  <a name="enablewindow"></a>  CWnd::EnableWindow  
 Enables or disables mouse and keyboard input.  
  
```  
BOOL EnableWindow(BOOL bEnable = TRUE);
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the given window is to be enabled or disabled. If this parameter is **TRUE**, the window will be enabled. If this parameter is **FALSE**, the window will be disabled.  
  
### Return Value  
 Indicates the state before the `EnableWindow` member function was called. The return value is nonzero if the window was previously disabled. The return value is 0 if the window was previously enabled or an error occurred.  
  
### Remarks  
 When input is disabled, input such as mouse clicks and keystrokes is ignored. When input is enabled, the window processes all input.  
  
 If the enabled state is changing, the [WM_ENABLE](#onenable) message is sent before this function returns.  
  
 If disabled, all child windows are implicitly disabled, although they are not sent `WM_ENABLE` messages.  
  
 A window must be enabled before it can be activated. For example, if an application is displaying a modeless dialog box and has disabled its main window, the main window must be enabled before the dialog box is destroyed. Otherwise, another window will get the input focus and be activated. If a child window is disabled, it is ignored when Windows tries to determine which window should get mouse messages.  
  
 By default, a window is enabled when it is created. An application can specify the **WS_DISABLED** style in the [Create](#create) or [CreateEx](#createex) member function to create a window that is initially disabled. After a window has been created, an application can also use the `EnableWindow` member function to enable or disable the window.  
  
 An application can use this function to enable or disable a control in a dialog box. A disabled control cannot receive the input focus, nor can a user access it.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#93](../../mfc/reference/codesnippet/cpp/cwnd-class_32.cpp)]  
  
##  <a name="endmodalloop"></a>  CWnd::EndModalLoop  
 Terminates a call to `RunModalLoop`.  
  
```  
virtuelle void EndModalLoop (Int %nergebnis);
```  
  
### Parameters  
 `nResult`  
 Contains the value to be returned to the caller of [RunModalLoop](#runmodalloop).  
  
### Remarks  
 The `nResult` parameter is propagated to the return value from `RunModalLoop`.  
  
##  <a name="endmodalstate"></a>  CWnd::EndModalState  
 Call this member function to change a frame window from modal to modeless.  
  
```  
virtuelle void EndModalState();
```  
  
##  <a name="endpaint"></a>  CWnd::EndPaint  
 Marks the end of painting in the given window.  
  
```  
void EndPaint (LPPAINTSTRUCT LpPaint);
```  
  
### Parameters  
 `lpPaint`  
 Points to a [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) structure that contains the painting information retrieved by the [BeginPaint](#beginpaint) member function.  
  
### Remarks  
 The `EndPaint` member function is required for each call to the `BeginPaint` member function, but only after painting is complete.  
  
 If the caret was hidden by the `BeginPaint` member function, `EndPaint` restores the caret to the screen.  
  
### Example  
  See the example for [CWnd::BeginPaint](#beginpaint).  
  
##  <a name="executedlginit"></a>  CWnd::ExecuteDlgInit  
 Initiates a dialog resource.  
  
```  
BOOL ExecuteDlgInit(LPCTSTR lpszResourceName);  
BOOL ExecuteDlgInit(LPVOID lpResource);
```  
  
### Parameters  
 `lpszResourceName`  
 A pointer to a null-terminated string specifying the name of the resource.  
  
 `lpResource`  
 A pointer to a resource.  
  
### Return Value  
 **TRUE** if a dialog resource is executed; otherwise **FALSE**.  
  
### Remarks  
 `ExecuteDlgInit` will use resources bound to the executing module, or resources from other sources. To accomplish this, `ExecuteDlgInit` finds a resource handle by calling `AfxFindResourceHandle`. If your MFC application does not use the shared DLL (MFCx0[U][D].DLL), **AfxFindResourceHandle** calls [AfxGetResourceHandle](http://msdn.microsoft.com/library/d0eff6c4-f566-471a-96b7-a5a70a751a92), which returns the current resource handle for the executable. If your MFC application that uses MFCx0[U][D].DLL, `AfxFindResourceHandle` traverses the **CDynLinkLibrary** object list of shared and extension DLLs looking for the correct resource handle.  
  
##  <a name="filtertooltipmessage"></a>  CWnd::FilterToolTipMessage  
 Called by the framework to display tool tip messages.  
  
```  
void FilterToolTipMessage (MSG * pMsg);
```  
  
### Parameters  
 `pMsg`  
 A pointer to the tool tip message.  
  
### Remarks  
 In most MFC applications this method is called by the framework from [PreTranslateMessage](#pretranslatemessage) and [EnableToolTips](#enabletooltips), and you do not need to call it yourself.  
  
 However, in certain applications, for example some ActiveX controls, these methods might not be invoked by the framework, and you will need to call FilterToolTipMessage yourself. For more information, see [Methods of Creating Tool Tips](../../mfc/methods-of-creating-tool-tips.md).  
  
##  <a name="findwindow"></a>  CWnd::FindWindow  
 Returns the top-level `CWnd` whose window class is given by `lpszClassName` and whose window name, or title, is given by `lpszWindowName`.  
  
```  
statische CWnd * PASCAL FindWindow (LPCTSTR "lpszclassname",  
    LPCTSTR LpszWindowName);
```  
  
### Parameters  
 `lpszClassName`  
 Points to a null-terminated string that specifies the window's class name (a **WNDCLASS** structure). If `lpClassName` is **NULL**, all class names match.  
  
 `lpszWindowName`  
 Points to a null-terminated string that specifies the window name (the window's title). If `lpWindowName` is **NULL**, all window names match.  
  
### Return Value  
 Identifies the window that has the specified class name and window name. It is **NULL** if no such window is found.  
  
 The `CWnd`* may be temporary and should not be stored for later use.  
  
### Remarks  
 This function does not search child windows.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#94](../../mfc/reference/codesnippet/cpp/cwnd-class_33.cpp)]  
  
##  <a name="findwindowex"></a>  CWnd::FindWindowEx  
 Retrieves the window object whose class name and window name match the specified strings.  
  
```  
statische CWnd * "FindWindowEx" (HWND HwndParent,  
    HWND-hwndChildAfter  
    LPCTSTR LpszClass,  
    LPCTSTR LpszWindow);
```  
  
### Parameters  
 *hwndParent*  
 Handle to the parent window whose child windows are to be searched.  
  
 *hwndChildAfter*  
 Handle to a child window. The search begins with the next child window in the Z order. The child window must be a direct child window of *hwndParent*, not just a descendant window.  
  
 `lpszClass`  
 Pointer to a null-terminated string that specifies the class name or a class atom created by a previous call to the [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586) or [RegisterClassEx](http://msdn.microsoft.com/library/windows/desktop/ms633587).  
  
 *lpszWindow*  
 Pointer to a null-terminated string that specifies the window name (the window's title). If this parameter is **NULL**, all window names match.  
  
### Return Value  
 If the function succeeds, the return value is a pointer to the window object having the specified class and window names. If the function fails, the return value is **NULL**.  
  
### Remarks  
 This member function emulates the functionality of the function [FindWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms633500), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="flashwindow"></a>  CWnd::FlashWindow  
 Flashes the given window once.  
  
```  
BOOL FlashWindow(BOOL bInvert);
```  
  
### Parameters  
 `bInvert`  
 Specifies whether the `CWnd` is to be flashed or returned to its original state. The `CWnd` is flashed from one state to the other if `bInvert` is **TRUE**. If `bInvert` is **FALSE**, the window is returned to its original state (either active or inactive).  
  
### Return Value  
 Nonzero if the window was active before the call to the `FlashWindow` member function; otherwise 0.  
  
### Remarks  
 For successive flashing, create a system timer and repeatedly call `FlashWindow`. Flashing the `CWnd` means changing the appearance of its title bar as if the `CWnd` were changing from inactive to active status, or vice versa. (An inactive title bar changes to an active title bar; an active title bar changes to an inactive title bar.)  
  
 Typically, a window is flashed to inform the user that it requires attention but that it does not currently have the input focus.  
  
 The `bInvert` parameter should be **FALSE** only when the window is getting the input focus and will no longer be flashing; it should be **TRUE** on successive calls while waiting to get the input focus.  
  
 This function always returns nonzero for minimized windows. If the window is minimized, `FlashWindow` will simply flash the window's icon; `bInvert` is ignored for minimized windows.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#95](../../mfc/reference/codesnippet/cpp/cwnd-class_34.cpp)]  
  
##  <a name="flashwindowex"></a>  CWnd::FlashWindowEx  
 Flashes the given window.  
  
```  
BOOL FlashWindowEx (DWORD DwFlags,  
    UINT-uCount  
    DWORD-DwTimeout);
```  
  
### Parameters  
 `dwFlags`  
 Specifies the flash status. For a complete list of values, see the [FLASHWINFO](http://msdn.microsoft.com/library/windows/desktop/ms679348) structure.  
  
 `uCount`  
 Specifies the number of times to flash the window.  
  
 `dwTimeout`  
 Specifies the rate, in milliseconds, at which the window will be flashed. If `dwTimeout` is zero, the function uses the default cursor blink rate.  
  
### Return Value  
 The return value specifies the window's state before the call to the `FlashWindowEx` function. If the window caption was drawn as active before the call, the return value is nonzero. Otherwise, the return value is zero.  
  
### Remarks  
 This method emulates the functionality of the function [FlashWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms679347), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="fromhandle"></a>  CWnd::FromHandle  
 Returns a pointer to a `CWnd` object when given a handle to a window. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached.  
  
```  
statische CWnd * PASCAL FromHandle(HWND hWnd);
```  
  
### Parameters  
 `hWnd`  
 An `HWND` of a Windows window.  
  
### Return Value  
 Returns a pointer to a `CWnd` object when given a handle to a window. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached.  
  
 The pointer may be temporary and should not be stored for later use.  
  
##  <a name="fromhandlepermanent"></a>  CWnd::FromHandlePermanent  
 Returns a pointer to a `CWnd` object when given a handle to a window.  
  
```  
statische CWnd * PASCAL FromHandlePermanent(HWND hWnd);
```  
  
### Parameters  
 `hWnd`  
 An `HWND` of a Windows window.  
  
### Return Value  
 A pointer to a `CWnd` object.  
  
### Remarks  
 If a `CWnd` object is not attached to the handle, **NULL** is returned.  
  
 This function, unlike [FromHandle](#fromhandle), does not create temporary objects.  
  
##  <a name="get_accchild"></a>  CWnd::get_accChild  
 Called by the framework to retrieve the address of an `IDispatch` interface for the specified child.  
  
```  
virtuelle HRESULT Get_accChild (Variante VarChild,  
    IDispatch** PpdispChild);
```  
  
### Parameters  
 `varChild`  
 Identifies the child whose `IDispatch` interface is to be retrieved.  
  
 *ppdispChild*  
 Receives the address of the child object's `IDispatch` interface.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accchildcount"></a>  CWnd::get_accChildCount  
 Called by the framework to retrieve the number of children belonging to this object.  
  
```  
virtuelle HRESULT Get_accChildCount (Long * PcountChildren);
```  
  
### Parameters  
 *pcountChildren*  
 Receives the number of children.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles). Call the base class version and then add the nonwindowed child elements.  
  
 For more information, see [IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accdefaultaction"></a>  CWnd::get_accDefaultAction  
 Called by the framework to retrieve a string that describes the object's default action.  
  
```  
virtuelle HRESULT Get_accDefaultAction (Variante VarChild,  
    BSTR* PszDefaultAction);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the default action to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszDefaultAction*  
 Address of a `BSTR` that receives a localized string describing the default action for the specified object, or NULL if this object has no default action.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to describe your object's default action.  
  
 For more information, see [IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accdescription"></a>  CWnd::get_accDescription  
 Called by framework to retrieve a string that describes the visual appearance of the specified object.  
  
```  
virtuelle HRESULT Get_accDescription (Variante VarChild,  
    BSTR* PszDescription);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the description to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszDescription`  
 Address of a `BSTR` that receives a localized string describing the specified object, or NULL if no description is available for this object.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to describe your object. Call the base class version and add your description.  
  
 For more information, see [IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accfocus"></a>  CWnd::get_accFocus  
 Called by the framework to retrieve the object that has the keyboard focus.  
  
```  
virtuelle HRESULT Get_accFocus (VARIANT * PvarChild);
```  
  
### Parameters  
 `pvarChild`  
 Receives information about the object that has the focus. See *pvarID* in [IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accFocus** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acchelp"></a>  CWnd::get_accHelp  
 Called by the framework to retrieve an object's **Help** property string.  
  
```  
virtuelle HRESULT Get_accHelp (VarChild Variante,  
    BSTR* PszHelp);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the help information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszHelp*  
 Address of a `BSTR` that receives the localized string containing the help information for the specified object, or NULL if no help information is available.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to provide help text for your object.  
  
 For more information, see [IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acchelptopic"></a>  CWnd::get_accHelpTopic  
 Called by the framework to retrieve the full path of the **WinHelp** file associated with the specified object and the identifier of the appropriate topic within that file.  
  
```  
virtuelle HRESULT Get_accHelpTopic (BSTR* PszHelpFile VarChild Variante, lange* PidTopic);
```  
  
### Parameters  
 `pszHelpFile`  
 Address of a `BSTR` that receives the full path of the `WinHelp` file associated with the specified object, if any.  
  
 `varChild`  
 Specifies whether the Help topic to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain a Help topic for the object) or a child ID (to obtain a Help topic for one of the object's child elements).  
  
 `pidTopic`  
 Identifies the Help file topic associated with the specified object. See `pidTopic` in [IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accHelpTopic** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to provide help information about your object.  
  
 For more information, see [IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acckeyboardshortcut"></a>  CWnd::get_accKeyboardShortcut  
 Called by the framework to retrieve the specified object's shortcut key or access key.  
  
```  
virtuelle HRESULT Get_accKeyboardShortcut (VarChild Variante,  
    BSTR* PszKeyboardShortcut);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the keyboard shortcut to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszKeyboardShortcut*  
 Address of a `BSTR` that receives a localized string identifying the keyboard shortcut, or NULL if no keyboard shortcut is associated with the specified object.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to identify the keyboard shortcut for your object.  
  
 For more information, see [IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accname"></a>  CWnd::get_accName  
 Called by the framework to retrieve the name of the specified object.  
  
```  
virtuelle HRESULT Get_accName (VarChild Variante,  
    BSTR* PszName);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the name to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszName`  
 Address of a `BSTR` that receives a string containing the specified object's name.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to return the name of your object.  
  
 For more information, see [IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accparent"></a>  CWnd::get_accParent  
 Called by the framework to retrieve the `IDispatch` interface of the object's parent.  
  
```  
virtuelle HRESULT Get_accParent (IDispatch ** PpdispParent);
```  
  
### Parameters  
 *ppdispParent*  
 Receives the address of the parent object's `IDispatch` interface. The variable is set to NULL if no parent exists, or if the child cannot access its parent.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 In most cases you don't have to override this function.  
  
 For more information, see [IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accrole"></a>  CWnd::get_accRole  
 Called by the framework to retrieve information that describes the role of the specified object.  
  
```  
virtuelle HRESULT Get_accRole (Variante VarChild,  
    Variant* PvarRole);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the role information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pvarRole`  
 Receives the role information. See `pvarRole` in [IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accRole** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accselection"></a>  CWnd::get_accSelection  
 Called by the framework to retrieve the selected children of this object.  
  
```  
virtuelle HRESULT Get_accSelection (VARIANT * PvarChildren);
```  
  
### Parameters  
 `pvarChildren`  
 Receives information about which children are selected. See `pvarChildren` in [IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accSelection** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accstate"></a>  CWnd::get_accState  
 Called by the framework to retrieve the current state of the specified object.  
  
```  
virtuelle HRESULT Get_accState (Variante VarChild,  
    Variant* PvarState);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the state information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pvarState`  
 Receives information about the object's state. See `pvarState` in [IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accState** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accvalue"></a>  CWnd::get_accValue  
 Called by the framework to retrieve the value of the specified object.  
  
```  
virtuelle HRESULT Get_accValue (Variante VarChild,  
    BSTR* PszValue);
```  
  
### Parameters  
 `varChild`  
 Specifies whether the value information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszValue`  
 Address of the `BSTR` that receives a localized string containing the object's current value.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getactivewindow"></a>  CWnd::GetActiveWindow  
 Retrieves a pointer to the active window.  
  
```  
statische CWnd * PASCAL GetActiveWindow();
```  
  
### Return Value  
 The active window or **NULL** if no window was active at the time of the call. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The active window is either the window that has the current input focus or the window explicitly made active by the [SetActiveWindow](#setactivewindow) member function.  
  
##  <a name="getancestor"></a>  CWnd::GetAncestor  
 Retrieves the ancestor window object of the specified window.  
  
```  
CWnd * const GetAncestor(UINT gaFlags);  
```  
  
### Parameters  
 *gaFlags*  
 Specifies the ancestor to be retrieved. For a complete list of possible values, see [GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502).  
  
### Return Value  
 If the function succeeds, the return value is a pointer to the ancestor window object. If the function fails, the return value is **NULL**.  
  
### Remarks  
 This member function emulates the functionality of the function [GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcapture"></a>  CWnd::GetCapture  
 Retrieves the window that has the mouse capture.  
  
```  
statische CWnd * PASCAL GetCapture();
```  
  
### Return Value  
 Identifies the window that has the mouse capture. It is **NULL** if no window has the mouse capture.  
  
 The return value may be temporary and should not be stored for later use.  
  
### Remarks  
 Only one window has the mouse capture at any given time. A window receives the mouse capture when the [SetCapture](#setcapture) member function is called. This window receives mouse input whether or not the cursor is within its borders.  
  
##  <a name="getcaretpos"></a>  CWnd::GetCaretPos  
 Retrieves the client coordinates of the caret's current position and returns them as a `CPoint`.  
  
```  
statische CPoint PASCAL GetCaretPos();
```  
  
### Return Value  
 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object containing the coordinates of the caret's position.  
  
### Remarks  
 The caret position is given in the client coordinates of the `CWnd` window.  
  
##  <a name="getcheckedradiobutton"></a>  CWnd::GetCheckedRadioButton  
 Retrieves the ID of the currently checked radio button in the specified group.  
  
```  
Int GetCheckedRadioButton (Int nIDFirstButton,  
    Int nIDLastButton);
```  
  
### Parameters  
 `nIDFirstButton`  
 Specifies the integer identifier of the first radio button in the group.  
  
 `nIDLastButton`  
 Specifies the integer identifier of the last radio button in the group.  
  
### Return Value  
 ID of the checked radio button, or 0 if none is selected.  
  
##  <a name="getclientrect"></a>  CWnd::GetClientRect  
 Copies the client coordinates of the `CWnd` client area into the structure pointed to by `lpRect`.  
  
```  
void GetClientRect (LPRECT LpRect) const;  
```  
  
### Parameters  
 `lpRect`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) or a `CRect` object to receive the client coordinates. The **left** and **top** members will be 0. The **right** and **bottom** members will contain the width and height of the window.  
  
### Remarks  
 The client coordinates specify the upper-left and lower-right corners of the client area. Since client coordinates are relative to the upper-left corners of the `CWnd` client area, the coordinates of the upper-left corner are (0,0).  
  
### Example  
  See the example for [CWnd::IsIconic](#isiconic).  
  
##  <a name="getclipboardowner"></a>  CWnd::GetClipboardOwner  
 Retrieves the current owner of the Clipboard.  
  
```  
statische CWnd * PASCAL GetClipboardOwner();
```  
  
### Return Value  
 Identifies the window that owns the Clipboard if the function is successful. Otherwise, it is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The Clipboard can still contain data even if it is not currently owned.  
  
##  <a name="getclipboardviewer"></a>  CWnd::GetClipboardViewer  
 Retrieves the first window in the Clipboard-viewer chain.  
  
```  
statische CWnd * PASCAL GetClipboardViewer();
```  
  
### Return Value  
 Identifies the window currently responsible for displaying the Clipboard if successful; otherwise **NULL** (for example, if there is no viewer).  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
##  <a name="getcontrolunknown"></a>  CWnd::GetControlUnknown  
 Call this member function to retrieve a pointer to an unknown OLE control.  
  
```  
LPUNKNOWN GetControlUnknown();
```  
  
### Return Value  
 A pointer to the [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) interface of the OLE control represented by this `CWnd` object. If this object does not represent an OLE control, the return value is **NULL**.  
  
### Remarks  
 You should not release this **IUnknown** pointer. Typically, you would use to obtain a specific interface of the control.  
  
 The interface pointer returned by **GetControlUnknown** is not reference-counted. Do not call [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) on the pointer unless you have previously called [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) on it.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#96](../../mfc/reference/codesnippet/cpp/cwnd-class_35.cpp)]  
  
##  <a name="getcurrentmessage"></a>  CWnd::GetCurrentMessage  
 Returns a pointer to the message this window is currently processing. Should only be called when in an **On***Message* message-handler member function.  
  
```  
static const MSG * PASCAL GetCurrentMessage();
```  
  
### Return Value  
 Returns a pointer to the [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message the window is currently processing. Should only be called when in an **On***Message* handler.  
  
### Example  
  See the example for [CMDIFrameWnd::MDICascade](../../mfc/reference/cmdiframewnd-class.md#mdicascade).  
  
##  <a name="getdc"></a>  CWnd::GetDC  
 Retrieves a pointer to a common, class, or private device context for the client area depending on the class style specified for the `CWnd`.  
  
```  
CDC * GetDC();
```  
  
### Return Value  
 Identifies the device context for the `CWnd` client area if successful; otherwise, the return value is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 For common device contexts, `GetDC` assigns default attributes to the context each time it is retrieved. For class and private contexts, `GetDC` leaves the previously assigned attributes unchanged. The device context can be used in subsequent graphics device interface (GDI) functions to draw in the client area.  
  
 Unless the device context belongs to a window class, the [ReleaseDC](#releasedc) member function must be called to release the context after painting.  
  
 A device context belonging to the `CWnd` class is returned by the `GetDC` member function if **CS_CLASSDC**, **CS_OWNDC**, or **CS_PARENTDC** was specified as a style in the **WNDCLASS** structure when the class was registered.  
  
##  <a name="getdcex"></a>  CWnd::GetDCEx  
 Retrieves the handle of a device context for the `CWnd` window.  
  
```  
CDC* GetDCEx (CRgn* PrgnClip,  
    DWORD-Flags)
```  
  
### Parameters  
 `prgnClip`  
 Identifies a clipping region that may be combined with the visible region of the client window.  
  
 `flags`  
 Can have one of the following preset values:  
  
- **DCX_CACHE** Returns a device context from the cache rather than the **OWNDC** or **CLASSDC** window. Overrides **CS_OWNDC** and **CS_CLASSDC**.  
  
- **DCX_CLIPCHILDREN** Excludes the visible regions of all child windows below the `CWnd` window.  
  
- **DCX_CLIPSIBLINGS** Excludes the visible regions of all sibling windows above the `CWnd` window.  
  
- **DCX_EXCLUDERGN** Excludes the clipping region identified by `prgnClip` from the visible region of the returned device context.  
  
- **DCX_INTERSECTRGN** Intersects the clipping region identified by `prgnClip` within the visible region of the returned device context.  
  
- **DCX_LOCKWINDOWUPDATE** Allows drawing even if there is a `LockWindowUpdate` call in effect that would otherwise exclude this window. This value is used for drawing during tracking.  
  
- **DCX_PARENTCLIP** Uses the visible region of the parent window and ignores the parent window's **WS_CLIPCHILDREN** and **WS_PARENTDC** style bits. This value sets the device context's origin to the upper-left corner of the `CWnd` window.  
  
- **DCX_WINDOW** Returns a device context that corresponds to the window rectangle rather than the client rectangle.  
  
### Return Value  
 The device context for the specified window if the function is successful; otherwise **NULL**.  
  
### Remarks  
 The device context can be used in subsequent GDI functions to draw in the client area.  
  
 This function, which is an extension to the [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) function, gives an application more control over how and whether a device context for a window is clipped.  
  
 Unless the device context belongs to a window class, the [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) function must be called to release the context after drawing. Since only five common device contexts are available at any given time, failure to release a device context can prevent other applications from gaining access to a device context.  
  
 To obtain a cached device context, an application must specify [DCX_CACHE](http://msdn.microsoft.com/library/windows/desktop/dd144873). If **DCX_CACHE** is not specified and the window is neither **CS_OWNDC** nor [CS_CLASSDC](http://msdn.microsoft.com/library/windows/desktop/ms633576), this function returns **NULL**.  
  
 A device context with special characteristics is returned by the [GetDCEx](http://msdn.microsoft.com/library/windows/desktop/dd144873) function if the **CS_CLASSDC**, [CS_OWNDC](http://msdn.microsoft.com/library/windows/desktop/ms633576), or [CS_PARENTDC](http://msdn.microsoft.com/library/windows/desktop/ms633576) style was specified in the [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure when the class was registered.  
  
 For more information about these characteristics, see the description of the **WNDCLASS** structure in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdcrendertarget"></a>  CWnd::GetDCRenderTarget  
 Retrieves the device context (DC) render target for the `CWnd` window.  
  
```  
CDCRenderTarget * GetDCRenderTarget();
```  
  
### Return Value  
 The device context render target for the specified window if the function is successful; otherwise **NULL**.  
  
### Remarks  
  
##  <a name="getdescendantwindow"></a>  CWnd::GetDescendantWindow  
 Call this member function to find the descendant window specified by the given ID.  
  
```  
CWnd * GetDescendantWindow (Int nID  
    BOOL bOnlyPerm = FALSE) const;  
```  
  
### Parameters  
 `nID`  
 Specifies the identifier of the control or child window to be retrieved.  
  
 `bOnlyPerm`  
 Specifies whether the window to be returned can be temporary. If **TRUE**, only a permanent window can be returned; if **FALSE,** the function can return a temporary window. For more information on temporary windows see [Technical Note 3](../../mfc/tn003-mapping-of-windows-handles-to-objects.md).  
  
### Return Value  
 A pointer to a `CWnd` object, or **NULL** if no child window is found.  
  
### Remarks  
 This member function searches the entire tree of child windows, not only the windows that are immediate children.  
  
##  <a name="getdesktopwindow"></a>  CWnd::GetDesktopWindow  
 Returns the Windows desktop window.  
  
```  
statische CWnd * PASCAL GetDesktopWindow();
```  
  
### Return Value  
 Identifies the Windows desktop window. This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The desktop window covers the entire screen and is the area on top of which all icons and other windows are painted.  
  
##  <a name="getdlgctrlid"></a>  CWnd::GetDlgCtrlID  
 Returns the window or control ID value for any child window, not only that of a control in a dialog box.  
  
```  
GetDlgCtrlID() const Int.  
```  
  
### Return Value  
 The numeric identifier of the `CWnd` child window if the function is successful; otherwise 0.  
  
### Remarks  
 Since top-level windows do not have an ID value, the return value of this function is invalid if the `CWnd` is a top-level window.  
  
### Example  
  See the example for [CWnd::OnCtlColor](#onctlcolor).  
  
##  <a name="getdlgitem"></a>  CWnd::GetDlgItem  
 Retrieves a pointer to the specified control or child window in a dialog box or other window.  
  
```  
CWnd * const GetDlgItem(int nID);  
  
void GetDlgItem (Int nID  
    HWND* PhWnd) const;  
```  
  
### Parameters  
 `nID`  
 Specifies the identifier of the control or child window to be retrieved.  
  
 `phWnd`  
 A pointer to a child window.  
  
### Return Value  
 A pointer to the given control or child window. If no control with the integer ID given by the `nID` parameter exists, the value is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The pointer returned is usually cast to the type of control identified by `nID`.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#97](../../mfc/reference/codesnippet/cpp/cwnd-class_36.cpp)]  
  
##  <a name="getdlgitemint"></a>  CWnd::GetDlgItemInt  
 Retrieves the text of the control identified by `nID`.  
  
```  
"Uint" GetDlgItemInt (Int nID  
    BOOL * LpTrans = NULL  
    BOOL bSigned = TRUE) const;  
```  
  
### Parameters  
 `nID`  
 Specifies the integer identifier of the dialog-box control to be translated.  
  
 `lpTrans`  
 Points to the Boolean variable that is to receive the translated flag.  
  
 `bSigned`  
 Specifies whether the value to be retrieved is signed.  
  
### Return Value  
 Specifies the translated value of the dialog-box item text. Since 0 is a valid return value, `lpTrans` must be used to detect errors. If a signed return value is desired, cast it as an `int` type.  
  
 The function returns 0 if the translated number is greater than INT_MAX (for signed numbers) or UINT_MAX (for unsigned).  
  
 When errors occur, such as encountering nonnumeric characters and exceeding the above maximum, `GetDlgItemInt` copies 0 to the location pointed to by `lpTrans`. If there are no errors, `lpTrans` receives a nonzero value. If `lpTrans` is **NULL**, `GetDlgItemInt` does not warn about errors.  
  
### Remarks  
 It translates the text of the specified control in the given dialog box into an integer value by stripping any extra spaces at the beginning of the text and converting decimal digits. It stops the translation when it reaches the end of the text or encounters any nonnumeric character.  
  
 If `bSigned` is **TRUE**, `GetDlgItemInt` checks for a minus sign (–) at the beginning of the text and translates the text into a signed number. Otherwise, it creates an unsigned value.  
  
 It sends a [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627) message to the control.  
  
##  <a name="getdlgitemtext"></a>  CWnd::GetDlgItemText  
 Call this member function to retrieve the title or text associated with a control in a dialog box.  
  
```  
Int GetDlgItemText (Int nID  
    LPTSTR LpStr,  
    Int nMaxCount) const;  
  
Int GetDlgItemText (Int nID  
    CString- & rString) const;  
```  
  
### Parameters  
 `nID`  
 Specifies the integer identifier of the control whose title is to be retrieved.  
  
 `lpStr`  
 Points to the buffer to receive the control's title or text.  
  
 `nMaxCount`  
 Specifies the maximum length (in characters) of the string to be copied to `lpStr`. If the string is longer than `nMaxCount`, it is truncated.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### Return Value  
 Specifies the actual number of characters copied to the buffer, not including the terminating null character. The value is 0 if no text is copied.  
  
### Remarks  
 The `GetDlgItemText` member function copies the text to the location pointed to by `lpStr` and returns a count of the number of bytes it copies.  
  
##  <a name="getdsccursor"></a>  CWnd::GetDSCCursor  
 Call this member function to retrieve a pointer to the underlying cursor that is defined by the DataSource, UserName, Password, and SQL properties of the data-source control.  
  
```  
IUnknown * GetDSCCursor();
```  
  
### Return Value  
 A pointer to a cursor that is defined by a data-source control. MFC takes care of calling `AddRef` for the pointer.  
  
### Remarks  
 Use the returned pointer to set the ICursor property of a complex data-bound control, such as the data-bound grid control. A data-source control will not become active until the first bound control requests its cursor. This can happen either explicitly by a call to `GetDSCCursor` or implicitly by the MFC binding manager. In either case, you can force a data-source control to become active by calling `GetDSCCursor` and then calling **Release** on the returned pointer to **IUnknown**. Activation will cause the data-source control to attempt to connect to the underlying data source. The returned pointer might be used in the following context:  
  
### Example  
 [!code-cpp[NVC_MFC_AxDataBinding#1](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#5](../../mfc/reference/codesnippet/cpp/cwnd-class_37.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#3](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="getdynamiclayout"></a>  CWnd::GetDynamicLayout  
 Retrieves a pointer to the dynamic layout manager object.  
  
```  
CMFCDynamicLayout * GetDynamicLayout();
```  
  
### Return Value  
 A pointer to the dynamic layout manager object, or NULL if dynamic layout is not enabled.  
  
### Remarks  
 The window object owns and manages the lifetime of the returned pointer, so it should only be used to access the object; do not delete the pointer or store the pointer permanently.  
  
##  <a name="getexstyle"></a>  CWnd::GetExStyle  
 Returns the window's extended style.  
  
```  
DWORD GetExStyle() const;  
```  
  
### Return Value  
 The window's extended style. For more information about the extended window styles used in MFC, see [Extended Window Styles](../../mfc/reference/extended-window-styles.md).  
  
##  <a name="getfocus"></a>  CWnd::GetFocus  
 Retrieves a pointer to the `CWnd` that currently has the input focus.  
  
```  
statische CWnd * PASCAL GetFocus();
```  
  
### Return Value  
 A pointer to the window that has the current focus, or **NULL** if there is no focus window.  
  
 The pointer may be temporary and should not be stored for later use.  
  
##  <a name="getfont"></a>  CWnd::GetFont  
 Sends the `WM_GETFONT` message to the window to retrieve the current font.  
  
```  
CFont * const GetFont();  
```  
  
### Return Value  
 Pointer to a [CFont](../../mfc/reference/cfont-class.md) object that is attached to the current font for the window.  
  
### Remarks  
 This method has no effect unless the window processes the `WM_GETFONT` message. Many MFC classes that derive from `CWnd` process this message because they are attached to a predefined window class that includes a message handler for the `WM_GETFONT` message. To use this method, classes that you derive from `CWnd` must define a method handler for the `WM_GETFONT` message.  
  
##  <a name="getforegroundwindow"></a>  CWnd::GetForegroundWindow  
 Returns a pointer to the foreground window (the window with which the user is currently working).  
  
```  
statische CWnd * PASCAL GetForegroundWindow();
```  
  
### Return Value  
 A pointer to the foreground window. This may be a temporary `CWnd` object.  
  
### Remarks  
 The foreground window applies only to top-level windows (frame windows or dialog boxes).  
  
##  <a name="geticon"></a>  CWnd::GetIcon  
 Call this member function to get the handle to either a big (32x32) or the handle to a small (16x16) icon, as indicated by `bBigIcon`.  
  
```  
HICON GetIcon(BOOL bBigIcon) const;  
```  
  
### Parameters  
 `bBigIcon`  
 Specifies a 32 pixel by 32 pixel icon if **TRUE**; specifies a 16 pixel by 16 pixel icon if **FALSE**.  
  
### Return Value  
 A handle to an icon. If unsuccessful, returns **NULL**.  
  
##  <a name="getlastactivepopup"></a>  CWnd::GetLastActivePopup  
 Determines which pop-up window owned by `CWnd` was most recently active.  
  
```  
CWnd * const GetLastActivePopup();  
```  
  
### Return Value  
 Identifies the most recently active pop-up window. The return value will be the window itself if any of the following conditions are met:  
  
-   The window itself was most recently active.  
  
-   The window does not own any pop-up windows.  
  
-   The window is not a top-level window or is owned by another window.  
  
 The pointer may be temporary and should not be stored for later use.  
  
### Example  
  See the example for [CWnd::FindWindow](#findwindow).  
  
##  <a name="getlayeredwindowattributes"></a>  CWnd::GetLayeredWindowAttributes  
 Retrieves the opacity and transparency color key of a layered window.  
  
```  
BOOL GetLayeredWindowAttributes (COLORREF* PcrKey BYTE* PbAlpha,  
    DWORD* PdwFlags) const;  
```  
  
### Parameters  
 *pcrKey*  
 Pointer to a **COLORREF** value that receives the transparency color key to be used when composing the layered window. All pixels painted by the window in this color will be transparent. This can be **NULL** if the argument is not needed.  
  
 `pbAlpha`  
 Pointer to a **BYTE** that receives the Alpha value used to describe the opacity of the layered window. When the variable referred to by `pbAlpha` is 0, the window is completely transparent. When the variable referred to by `pbAlpha` is 255, the window is opaque. This can be **NULL** if the argument is not needed.  
  
 *pdwFlags*  
 Pointer to a `DWORD` that receives a layering flag. This can be **NULL** if the argument is not needed. For a complete list of possible values, see [GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmenu"></a>  CWnd::GetMenu  
 Retrieves a pointer to the menu for this window.  
  
```  
CMenu * const GetMenu();  
```  
  
### Return Value  
 Identifies the menu. The value is **NULL** if `CWnd` has no menu. The return value is undefined if `CWnd` is a child window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 This function should not be used for child windows because they do not have a menu.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#98](../../mfc/reference/codesnippet/cpp/cwnd-class_38.cpp)]  
  
##  <a name="getmenubarinfo"></a>  CWnd::GetMenuBarInfo  
 Retrieves information about the specified menu bar.  
  
```  
BOOL GetMenuBarInfo (LONG IdObject,  
    LANGE idItem  
    PMENUBARINFO Pmbi) const;  
```  
  
### Parameters  
 `idObject`  
 Specifies the menu object. For a list of possible values, see [GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833).  
  
 `idItem`  
 Specifies the item for which to retrieve information. If this parameter is zero, the function retrieves information about the menu itself. If this parameter is 1, the function retrieves information about the first item on the menu, and so on.  
  
 *pmbi*  
 Pointer to a [MENUBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms647564) structure that receives the information.  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnextdlggroupitem"></a>  CWnd::GetNextDlgGroupItem  
 Searches for the previous or next control within a group of controls in a dialog box.  
  
```  
CWnd* GetNextDlgGroupItem (CWnd* pWndCtl,  
    BOOL bVorherige = FALSE) const;  
  
COleControlSiteOrWnd* GetNextDlgGroupItem (COleControlSiteOrWnd* pCurSiteOrWnd = NULL) const;  
```  
  
### Parameters  
 `pWndCtl`  
 Identifies the control to be used as the starting point for the search.  
  
 `bPrevious`  
 Specifies how the function is to search the group of controls in the dialog box. If **TRUE**, the function searches for the previous control in the group; if **FALSE**, it searches for the next control in the group.  
  
 `pCurSiteOrWnd`  
 Identifies the **COleControlSiteOrWnd** control. For more information about `COleControlSiteOrWnd`, see **Remarks**.  
  
### Return Value  
 Pointer to the previous or next control in the group if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 A group of controls begins with a control that was created with the [WS_GROUP](../../mfc/reference/window-styles.md) style and ends with the last control that was not created with the **WS_GROUP** style.  
  
 By default, the `GetNextDlgGroupItem` member function returns a pointer to the next control in the group. If `pWndCtl` identifies the first control in the group and `bPrevious` is **TRUE**, `GetNextDlgGroupItem` returns a pointer to the last control in the group.  
  
> [!NOTE]
>  Because MFC supports windowless ActiveX controls, standard ActiveX controls, and windows, referring to a control by only an HWND no longer suffices. The `COleControlSiteOrWnd` object includes information that identifies the object as a windowed ActiveX control, a windowless ActiveX control, or a window, as follows:  
  
|Control or window type|Identifying information|  
|----------------------------|-----------------------------|  
|Windowed ActiveX control|Contains an HWND and associates a [COleControlSite](../../mfc/reference/colecontrolsite-class.md) object with it. The `m_hWnd` member of `COleControlSiteOrWnd` is set to the HWND of the control, and the **m_pSite** member points to the control's `COleControlSite`.|  
|Windowless ActiveX control|Contains no `HWND`. The **m_pSite** member of `COleControlSiteOrWnd` points to the control's `COleControlSite`, and the **m_hWnd** member is **NULL**.|  
|Standard window|Contains just an `HWND`. The `m_hWnd` member of `COleControlSiteOrWnd` is set to the `HWND` of the window, and the **m_pSite** member is **NULL**.|  
  
##  <a name="getnextdlgtabitem"></a>  CWnd::GetNextDlgTabItem  
 Retrieves a pointer to the first control that was created with the [WS_TABSTOP](window-styles.md) style and that precedes or follows the specified control.  
  
```  
CWnd* GetNextDlgTabItem (CWnd* pWndCtl,  
    BOOL bVorherige = FALSE) const;  
  
COleControlSiteOrWnd* GetNextDlgTabItem (COleControlSiteOrWnd* pCurSiteOrWnd,  
    BOOL bVorherige) const;  
```  
  
### Parameters  
 `pWndCtl`  
 Identifies the control to be used as the starting point for the search.  
  
 `pCurSiteOrWnd`  
 Identifies the **COleControlSiteOrWnd** control. For more information about `COleControlSiteOrWnd`, see [CWnd::GetNextDlgGroupItem](#getnextdlggroupitem).  
  
 `bPrevious`  
 Specifies how the function is to search the dialog box. If **TRUE**, the function searches for the previous control in the dialog box; if **FALSE**, it searches for the next control.  
  
### Return Value  
 Pointer to the previous or next control that has the **WS_TABSTOP** style, if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
 For more information about `COleControlSiteOrWnd`, see [CWnd::GetNextDlgGroupItem](#getnextdlggroupitem).  
  
##  <a name="getnextwindow"></a>  CWnd::GetNextWindow  
 Searches for the next (or previous) window in the window manager's list.  
  
```  
CWnd * const GetNextWindow(UINT nFlag = GW_HWNDNEXT);  
```  
  
### Parameters  
 `nFlag`  
 Specifies whether the function returns a pointer to the next window or the previous window. It can be either **GW_HWNDNEXT**, which returns the window that follows the `CWnd` object on the window manager's list, or **GW_HWNDPREV**, which returns the previous window on the window manager's list.  
  
### Return Value  
 Identifies the next (or the previous) window in the window manager's list if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The window manager's list contains entries for all top-level windows, their associated child windows, and the child windows of any child windows.  
  
 If `CWnd` is a top-level window, the function searches for the next (or previous) top-level window; if `CWnd` is a child window, the function searches for the next (or previous) child window.  
  
##  <a name="getolecontrolsite"></a>  CWnd::GetOleControlSite  
 Retrieves the custom site for the specified ActiveX control.  
  
```  
COleControlSite * const GetOleControlSite(UINT idControl);  
```  
  
### Parameters  
 `idControl`  
 The ID of the ActiveX control.  
  
##  <a name="getopenclipboardwindow"></a>  CWnd::GetOpenClipboardWindow  
 Retrieves the handle of the window that currently has the Clipboard open.  
  
```  
statische CWnd * PASCAL GetOpenClipboardWindow();
```  
  
### Return Value  
 The handle of the window that currently has the Clipboard open if the function is successful; otherwise **NULL**.  
  
##  <a name="getowner"></a>  CWnd::GetOwner  
 Retrieves a pointer to the owner of the window.  
  
```  
CWnd * const GetOwner();  
```  
  
### Return Value  
 A pointer to a `CWnd` object.  
  
### Remarks  
 If the window has no owner, then a pointer to the parent window object is returned by default. Note that the relationship between the owner and the owned differs from the parent-child aspect in several important aspects. For example, a window with a parent is confined to its parent window's client area. Owned windows can be drawn at any location on the desktop.  
  
 The ownership concept of this function is different from the ownership concept of [GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515).  
  
##  <a name="getparent"></a>  CWnd::GetParent  
 Call this function to get a pointer to a child window's parent window (if any).  
  
```  
CWnd * const GetParent();  
```  
  
### Return Value  
 See the Return Values section in [GetParent](http://msdn.microsoft.com/library/windows/desktop/ms633510) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 The `GetParent` function returns a pointer to the immediate parent (if it exists). In contrast, the [GetParentOwner](#getparentowner) function returns a pointer to the most immediate parent or owner window that is not a child window (does not have the **WS_CHILD** style). If you have a child window within a child window `GetParent` and `GetParentOwner` return different results.  
  
##  <a name="getparentframe"></a>  CWnd::GetParentFrame  
 Call this member function to retrieve the parent frame window.  
  
```  
CFrameWnd * const GetParentFrame();  
```  
  
### Return Value  
 A pointer to a frame window if successful; otherwise **NULL**.  
  
### Remarks  
 The member function searches up the parent chain until a [CFrameWnd](../../mfc/reference/cframewnd-class.md) (or derived class) object is found.  
  
##  <a name="getparentowner"></a>  CWnd::GetParentOwner  
 Call this member function to get a pointer to a child window's parent window or owner window.  
  
```  
CWnd * const GetParentOwner();  
```  
  
### Return Value  
 A pointer to a `CWnd` object. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `GetParentOwner` returns a pointer to the most immediate parent or owner window that is not a child window (does not have the **WS_CHILD** style). The current owner window can be set with [SetOwner](#setowner). By default, the parent of a window is its owner.  
  
 In contrast, the [GetParent](#getparent) function returns a pointer to the immediate parent, whether it is a child window or not. If you have a child window within a child window `GetParent` and `GetParentOwner` return different results.  
  
##  <a name="getproperty"></a>  CWnd::GetProperty  
 Call this member function to get the ActiveX control property specified by `dwDispID`.  
  
```  
void GetProperty (DISPID DwDispID,  
    VARTYPE-vtProp  
    Void * PvProp) const;  
```  
  
### Parameters  
 `dwDispID`  
 Identifies the property to be retrieved.  
  
 `vtProp`  
 Specifies the type of the property to be retrieved. For possible values, see the Remarks section for [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvProp`  
 Address of the variable that will that will receive the property value. It must match the type specified by `vtProp`.  
  
### Remarks  
 **GetProperty** returns the value through `pvProp`.  
  
> [!NOTE]
>  This function should be called only on a `CWnd` object that represents an ActiveX control.  
  
 For more information about using this member function with ActiveX Control Containers, see the article [ActiveX Control Containers: Programming ActiveX Controls in an ActiveX Control Container](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="getrendertarget"></a>  CWnd::GetRenderTarget  
 Gets a render target that is associated with this window.  
  
```  
CHwndRenderTarget * GetRenderTarget();
```  
  
### Return Value  
 Pointer to the render target or NULL.  
  
##  <a name="getsafehwnd"></a>  CWnd::GetSafeHwnd  
 Returns `m_hWnd`, or **NULL** if the **this** pointer is **NULL**.  
  
```  
HWND GetSafeHwnd() const;  
```  
  
### Return Value  
 Returns the window handle for a window. Returns **NULL** if the `CWnd` is not attached to a window or if it is used with a **NULL CWnd** pointer.  
  
### Example  
  See the example for [CWnd::SubclassWindow](#subclasswindow).  
  
##  <a name="getsafeowner"></a>  CWnd::GetSafeOwner  
 Call this member function to retrieve the owner window that should be used for dialog boxes or other modal windows.  
  
```  
statische CWnd* GetSafeOwner (CWnd* pParent = NULL  
    HWND* pWndTop = NULL);
```  
  
### Parameters  
 `pParent`  
 A pointer to a parent `CWnd` window. May be **NULL**.  
  
 *pWndTop*  
 A pointer to the window that is currently on top. May be **NULL**.  
  
### Return Value  
 A pointer to the safe owner for the given window.  
  
### Remarks  
 The safe owner is the first non-child parent window of `pParent`. If `pParent` is **NULL**, the thread's main window (retrieved via [AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd)) is used to find an owner.  
  
> [!NOTE]
>  The framework itself uses this function to determine the correct owner window for dialog boxes and property sheets where the owner is not specified.  
  
##  <a name="getscrollbarctrl"></a>  CWnd::GetScrollBarCtrl  
 Call this member function to obtain a pointer to the specified sibling scroll bar or splitter window.  
  
```  
virtuelle CScrollBar * GetScrollBarCtrl(int nBar) const;  
```  
  
### Parameters  
 `nBar`  
 Specifies the type of scroll bar. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
### Return Value  
 A sibling scroll-bar control, or **NULL** if none.  
  
### Remarks  
 This member function does not operate on scroll bars created when the **WS_HSCROLL** or **WS_VSCROLL** bits are set during the creation of a window. The `CWnd` implementation of this function simply returns **NULL**. Derived classes, such as `CView`, implement the described functionality.  
  
##  <a name="getscrollbarinfo"></a>  CWnd::GetScrollBarInfo  
 Retrieves information about the specified scroll bar.  
  
```  
BOOL GetScrollBarInfo (LONG IdObject,  
    PSCROLLBARINFO Psbi) const;  
```  
  
### Parameters  
 `idObject`  
 Specifies the menu object. For a list of possible values, see [GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581).  
  
 *psbi*  
 Pointer to a [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) structure that receives the information.  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getscrollinfo"></a>  CWnd::GetScrollInfo  
 Call this member function to retrieve the information that the `SCROLLINFO` structure maintains about a scroll bar.  
  
```  
BOOL GetScrollInfo (nBar Int,  
    LPSCROLLINFO-lpScrollInfo  
    UINT nMask = SIF_ALL);
```  
  
### Parameters  
 `nBar`  
 Specifies whether the scroll bar is a control or part of a window's nonclient area. If it is part of the nonclient area, `nBar` also indicates whether the scroll bar is positioned horizontally, vertically, or both. It must be one of the following:  
  
- **SB_CTL** Retrieves the parameters for a scroll bar control. The `m_hWnd` data member must be the handle of the scroll bar control.  
  
- **SB_HORZ** Retrieves the parameters for the window's standard horizontal scroll bar.  
  
- **SB_VERT** Retrieves the parameters for the window's standard vertical scroll bar.  
  
 `lpScrollInfo`  
 A pointer to a [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure. See the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information about this structure.  
  
 `nMask`  
 Specifies the scroll bar parameters to retrieve. The default specifies a combination of **SIF_PAGE**, **SIF_POS**, **SIF_TRACKPOS**, and **SIF_RANGE**. See `SCROLLINFO` for more information on the *nMask* values.  
  
### Return Value  
 If the message retrieved any values, the return is **TRUE**. Otherwise, it is **FALSE**.  
  
### Remarks  
 `GetScrollInfo` enables applications to use 32-bit scroll positions.  
  
 The [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure contains information about a scroll bar, including the minimum and maximum scrolling positions, the page size, and the position of the scroll box (the thumb). See the `SCROLLINFO` structure topic in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information about changing the structure defaults.  
  
 The MFC Windows message handlers that indicate scroll-bar position, [CWnd::OnHScroll](#onhscroll) and [CWnd::OnVScroll](#onvscroll), provide only 16 bits of position data. `GetScrollInfo` and `SetScrollInfo` provide 32 bits of scroll-bar position data. Thus, an application can call `GetScrollInfo` while processing either `CWnd::OnHScroll` or `CWnd::OnVScroll` to obtain 32-bit scroll-bar position data.  
  
##  <a name="getscrolllimit"></a>  CWnd::GetScrollLimit  
 Call this member function to retrieve the maximum scrolling position of the scroll bar.  
  
```  
Int GetScrollLimit (Int nBar);
```  
  
### Parameters  
 `nBar`  
 Specifies the type of scroll bar. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the scroll limit of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the scroll limit of the vertical scroll bar.  
  
### Return Value  
 Specifies the maximum position of a scroll bar if successful; otherwise 0.  
  
##  <a name="getscrollpos"></a>  CWnd::GetScrollPos  
 Retrieves the current position of the scroll box of a scroll bar.  
  
```  
Int GetScrollPos (Int nBar) konstant ist.  
```  
  
### Parameters  
 `nBar`  
 Specifies the scroll bar to examine. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
### Return Value  
 Specifies the current position of the scroll box in the scroll bar if successful; otherwise 0.  
  
### Remarks  
 The current position is a relative value that depends on the current scrolling range. For example, if the scrolling range is 50 to 100 and the scroll box is in the middle of the bar, the current position is 75.  
  
##  <a name="getscrollrange"></a>  CWnd::GetScrollRange  
 Copies the current minimum and maximum scroll-bar positions for the given scroll bar to the locations specified by `lpMinPos` and `lpMaxPos`.  
  
```  
void GetScrollRange (Int nBar,  
    LPINT-lpMinPos  
    LPINT LpMaxPos) const;  
```  
  
### Parameters  
 `nBar`  
 Specifies the scroll bar to examine. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
 `lpMinPos`  
 Points to the integer variable that is to receive the minimum position.  
  
 `lpMaxPos`  
 Points to the integer variable that is to receive the maximum position.  
  
### Remarks  
 If `CWnd` does not have a scroll bar, then the `GetScrollRange` member function copies 0 to `lpMinPos` and `lpMaxPos`.  
  
 The default range for a standard scroll bar is 0 to 100. The default range for a scroll-bar control is empty (both values are 0).  
  
##  <a name="getstyle"></a>  CWnd::GetStyle  
 Returns the current window style.  
  
```  
DWORD GetStyle() const;  
```  
  
### Return Value  
 The window's style. For more information about the window styles used in MFC, see [Window Styles](../../mfc/reference/window-styles.md).  
  
##  <a name="getsystemmenu"></a>  CWnd::GetSystemMenu  
 Allows the application to access the Control menu for copying and modification.  
  
```  
CMenu * const GetSystemMenu(BOOL bRevert);  
```  
  
### Parameters  
 `bRevert`  
 Specifies the action to be taken. If `bRevert` is **FALSE**, `GetSystemMenu` returns a handle to a copy of the Control menu currently in use. This copy is initially identical to the Control menu but can be modified. If `bRevert` is **TRUE**, `GetSystemMenu` resets the Control menu back to the default state. The previous, possibly modified, Control menu, if any, is destroyed. The return value is undefined in this case.  
  
### Return Value  
 Identifies a copy of the Control menu if `bRevert` is **FALSE**. If `bRevert` is **TRUE**, the return value is undefined.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 Any window that does not use `GetSystemMenu` to make its own copy of the Control menu receives the standard Control menu.  
  
 The pointer returned by the `GetSystemMenu` member function can be used with the [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu), or [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu) functions to change the Control menu.  
  
 The Control menu initially contains items identified with various ID values such as **SC_CLOSE**, **SC_MOVE**, and **SC_SIZE**. Items on the Control menu generate [WM_SYSCOMMAND](#onsyscommand) messages. All predefined Control-menu items have ID numbers greater than 0xF000. If an application adds items to the Control menu, it should use ID numbers less than F000.  
  
 Windows may automatically make items unavailable on the standard Control menu. `CWnd` can carry out its own selection or unavailability by responding to the [WM_INITMENU](#oninitmenu) messages, which are sent before any menu is displayed.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#99](../../mfc/reference/codesnippet/cpp/cwnd-class_39.cpp)]  
  
##  <a name="gettitlebarinfo"></a>  CWnd::GetTitleBarInfo  
 Retrieves information about the specified title bar.  
  
```  
BOOL GetTitleBarInfo(PTITLEBARINFO pti) const;  
```  
  
### Parameters  
 *pti*  
 Pointer to a [TITLEBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms632608) structure that receives the information.  
  
### Remarks  
 This member function emulates the functionality of the function [GetTitleBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms633513), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettoplevelframe"></a>  CWnd::GetTopLevelFrame  
 Call this member function to retrieve the window's top level frame window, if any.  
  
```  
CFrameWnd * const GetTopLevelFrame();  
```  
  
### Return Value  
 Identifies the top-level frame window of the window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 If `CWnd` has no attached window, or its top-level parent is not a [CFrameWnd](../../mfc/reference/cframewnd-class.md)-derived object, this function returns **NULL**.  
  
##  <a name="gettoplevelowner"></a>  CWnd::GetTopLevelOwner  
 Call this member function to retrieve the top-level window.  
  
```  
CWnd * const GetTopLevelOwner();  
```  
  
### Return Value  
 Identifies the top-level window. The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The top-level window is the window that is a child of the desktop. If `CWnd` has no attached window, this function returns **NULL**.  
  
##  <a name="gettoplevelparent"></a>  CWnd::GetTopLevelParent  
 Call this member function to retrieve the window's top-level parent.  
  
```  
CWnd * const GetTopLevelParent();  
```  
  
### Return Value  
 Identifies the top-level parent window of the window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `GetTopLevelParent` is similar to [GetTopLevelFrame](#gettoplevelframe) and [GetTopLevelOwner](#gettoplevelowner); however, it ignores the value set as the current owner window.  
  
##  <a name="gettopwindow"></a>  CWnd::GetTopWindow  
 Searches for the top-level child window that belongs to `CWnd`.  
  
```  
CWnd * const GetTopWindow();  
```  
  
### Return Value  
 Identifies the top-level child window in a `CWnd` linked list of child windows. If no child windows exist, the value is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 If `CWnd` has no children, this function returns **NULL**.  
  
##  <a name="getupdaterect"></a>  CWnd::GetUpdateRect  
 Retrieves the coordinates of the smallest rectangle that completely encloses the update region.  
  
```  
BOOL GetUpdateRect (LPRECT LpRect,  
    BOOL bErase = FALSE);
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or [RECT structure](../../mfc/reference/rect-structure1.md) that is to receive the client coordinates of the update that encloses the update region.  
  
 Set this parameter to **NULL** to determine whether an update region exists within the `CWnd`. If `lpRect` is **NULL**, the `GetUpdateRect` member function returns nonzero if an update region exists and 0 if one does not. This provides a way to determine whether a `WM_PAINT` message resulted from an invalid area. Do not set this parameter to **NULL** in Windows version 3.0 and earlier.  
  
 `bErase`  
 Specifies whether the background in the update region is to be erased.  
  
### Return Value  
 Specifies the status of the update region. The value is nonzero if the update region is not empty; otherwise 0.  
  
 If the `lpRect` parameter is set to **NULL**, the return value is nonzero if an update region exists; otherwise 0.  
  
### Remarks  
 If `CWnd` was created with the **CS_OWNDC** style and the mapping mode is not `MM_TEXT`, the `GetUpdateRect` member function gives the rectangle in logical coordinates. Otherwise, `GetUpdateRect` gives the rectangle in client coordinates. If there is no update region, `GetUpdateRect` sets the rectangle to be empty (sets all coordinates to 0).  
  
 The `bErase` parameter specifies whether `GetUpdateRect` should erase the background of the update region. If `bErase` is **TRUE** and the update region is not empty, the background is erased. To erase the background, `GetUpdateRect` sends the [WM_ERASEBKGND](#onerasebkgnd) message.  
  
 The update rectangle retrieved by the [BeginPaint](#beginpaint) member function is identical to that retrieved by the `GetUpdateRect` member function.  
  
 The `BeginPaint` member function automatically validates the update region, so any call to `GetUpdateRect` made immediately after a call to `BeginPaint` retrieves an empty update region.  
  
##  <a name="getupdatergn"></a>  CWnd::GetUpdateRgn  
 Retrieves the update region into a region identified by `pRgn`.  
  
```  
Int GetUpdateRgn (CRgn * PRNG,  
    BOOL bErase = FALSE);
```  
  
### Parameters  
 `pRgn`  
 Identifies the update region.  
  
 `bErase`  
 Specifies whether the background will be erased and nonclient areas of child windows will be drawn. If the value is **FALSE**, no drawing is done.  
  
### Return Value  
 Specifies a short-integer flag that indicates the type of resulting region. The value can take any one of the following:  
  
- **SIMPLEREGION** The region has no overlapping borders.  
  
- **COMPLEXREGION** The region has overlapping borders.  
  
- **NULLREGION** The region is empty.  
  
- **ERROR** No region was created.  
  
### Remarks  
 The coordinates of this region are relative to the upper-left corner (client coordinates).  
  
 The [BeginPaint](#beginpaint) member function automatically validates the update region, so any call to `GetUpdateRgn` made immediately after a call to `BeginPaint` retrieves an empty update region.  
  
##  <a name="getwindow"></a>  CWnd::GetWindow  
 Returns a pointer to the window requested, or **NULL** if none.  
  
```  
CWnd * const GetWindow(UINT nCmd);  
```  
  
### Parameters  
 `nCmd`  
 Specifies the relationship between `CWnd` and the returned window. It can take one of the following values:  
  
- **GW_CHILD** Identifies the `CWnd` first child window.  
  
- **GW_HWNDFIRST** If `CWnd` is a child window, returns the first sibling window. Otherwise, it returns the first top-level window in the list.  
  
- **GW_HWNDLAST** If `CWnd` is a child window, returns the last sibling window. Otherwise, it returns the last top-level window in the list.  
  
- **GW_HWNDNEXT** Returns the next window on the window manager's list.  
  
- **GW_HWNDPREV** Returns the previous window on the window manager's list.  
  
- **GW_OWNER** Identifies the `CWnd` owner.  
  
### Return Value  
 The returned pointer may be temporary and should not be stored for later use.  
  
##  <a name="getwindowcontexthelpid"></a>  CWnd::GetWindowContextHelpId  
 Call this member function to retrieve the help context identifier, if any, associated with the window.  
  
```  
DWORD GetWindowContextHelpId() const;  
```  
  
### Return Value  
 The help context identifier. Returns 0 if the window has none.  
  
##  <a name="getwindowedchildcount"></a>  CWnd::GetWindowedChildCount  
 Call this member function to retrieve the number of associated child windows.  
  
```  
lange GetWindowedChildCount();
```  
  
### Return Value  
 The number of child windows associated with the `CWnd` object.  
  
##  <a name="getwindowdc"></a>  CWnd::GetWindowDC  
 Retrieves the display context for the entire window, including caption bar, menus, and scroll bars.  
  
```  
CDC * GetWindowDC();
```  
  
### Return Value  
 Identifies the display context for the given window if the function is successful; otherwise **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use. [ReleaseDC](#releasedc) should be called once for each successful call to `GetWindowDC`.  
  
### Remarks  
 A window display context permits painting anywhere in `CWnd`, since the origin of the context is the upper-left corner of `CWnd` instead of the client area.  
  
 Default attributes are assigned to the display context each time it retrieves the context. Previous attributes are lost.  
  
 `GetWindowDC` is intended to be used for special painting effects within the `CWnd` nonclient area. Painting in nonclient areas of any window is not recommended.  
  
 The [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function can be used to retrieve the dimensions of various parts of the nonclient area, such as the caption bar, menu, and scroll bars.  
  
 After painting is complete, the [ReleaseDC](#releasedc) member function must be called to release the display context. Failure to release the display context will seriously affect painting requested by applications due to limitations on the number of device contexts that can be open at the same time.  
  
##  <a name="getwindowinfo"></a>  CWnd::GetWindowInfo  
 Retrieves information about the window.  
  
```  
BOOL GetWindowInfo(PWINDOWINFO pwi) const;  
```  
  
### Parameters  
 *pwi*  
 A pointer to a [WINDOWINFO](http://msdn.microsoft.com/library/windows/desktop/ms632610) structure.  
  
### Remarks  
 This member function emulates the functionality of the function [GetWindowInfo](http://msdn.microsoft.com/library/windows/desktop/ms633516), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getwindowlesschildcount"></a>  CWnd::GetWindowlessChildCount  
 Retrieves the number of associated windowless child windows.  
  
```  
lange GetWindowlessChildCount();
```  
  
### Return Value  
 The number of windowless child windows associated with the `CWnd` object.  
  
##  <a name="getwindowplacement"></a>  CWnd::GetWindowPlacement  
 Retrieves the show state and the normal (restored), minimized, and maximized positions of a window.  
  
```  
BOOL GetWindowPlacement(WINDOWPLACEMENT* lpwndpl) const;  
```  
  
### Parameters  
 `lpwndpl`  
 Points to the `WINDOWPLACEMENT` structure that receives the show state and position information.  
  
### Return Value  
 Nonzero if the function is successful; otherwise 0.  
  
### Remarks  
 The **flags** member of the [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md) structure retrieved by this function is always 0. If `CWnd` is maximized, the **showCmd** member of `WINDOWPLACEMENT` is **SW_SHOWMAXIMIZED**. If the window is minimized, it is **SW_SHOWMINIMIZED.** It is **SW_SHOWNORMAL** otherwise.  
  
##  <a name="getwindowrect"></a>  CWnd::GetWindowRect  
 Copies the dimensions of the bounding rectangle of the `CWnd` object to the structure pointed to by `lpRect`.  
  
```  
void GetWindowRect (LPRECT LpRect) const;  
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or a [RECT structure](../../mfc/reference/rect-structure1.md) that will receive the screen coordinates of the upper-left and lower-right corners.  
  
### Remarks  
 The dimensions are given in screen coordinates relative to the upper-left corner of the display screen. The dimensions of the caption, border, and scroll bars, if present, are included.  
  
##  <a name="getwindowrgn"></a>  CWnd::GetWindowRgn  
 Call this member function to get the window region of a window.  
  
```  
Int GetWindowRgn (HRGN hRgn) konstant ist.  
```  
  
### Parameters  
 `hRgn`  
 A handle to a window region.  
  
### Return Value  
 The return value specifies the type of the region that the function obtains. It can be one of the following values:  
  
- **NULLREGION** The region is empty.  
  
- **SIMPLEREGION** The region is a single rectangle.  
  
- **COMPLEXREGION** The region is more than one rectangle.  
  
- **ERROR** An error occurred; the region is unaffected.  
  
### Remarks  
 The window region determines the area within the window where the operating system permits drawing. The operating system does not display any portion of a window that lies outside of the window region.  
  
 The coordinates of a window's window region are relative to the upper-left corner of the window, not the client area of the window.  
  
 To set the window region of a window, call [CWnd::SetWindowRgn](#setwindowrgn).  
  
##  <a name="getwindowtext"></a>  CWnd::GetWindowText  
 Copies the `CWnd` caption title (if it has one) into the buffer pointed to by `lpszStringBuf` or into the destination string `rString`.  
  
```  
Int GetWindowText (LPTSTR LpszStringBuf,  
    Int nMaxCount) const;  
  
void GetWindowText (CString & rString) const;  
```  
  
### Parameters  
 `lpszStringBuf`  
 Points to the buffer that is to receive the copied string of the window's title.  
  
 `nMaxCount`  
 Specifies the maximum number of characters to be copied to the buffer, including the terminating null character. If the string is longer than the number of characters specified in `nMaxCount`, it is truncated.  
  
 `rString`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that is to receive the copied string of the window's title.  
  
### Return Value  
 Specifies the length, in characters, of the copied string, not including the terminating null character. It is 0 if `CWnd` has no caption or if the caption is empty.  
  
### Remarks  
 If the `CWnd` object is a control, the `GetWindowText` member function copies the text within the control instead of copying the caption.  
  
 This member function causes the [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627) message to be sent to the `CWnd` object.  
  
### Example  
  See the example for [CWnd::SetWindowText](#setwindowtext).  
  
##  <a name="getwindowtextlength"></a>  CWnd::GetWindowTextLength  
 Returns the length of the `CWnd` object caption title.  
  
```  
GetWindowTextLength() const Int.  
```  
  
### Return Value  
 Specifies the text length in characters, not including any null-termination character. The value is 0 if no such text exists.  
  
### Remarks  
 If `CWnd` is a control, the `GetWindowTextLength` member function returns the length of the text within the control instead of the caption.  
  
 This member function causes the [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) message to be sent to the `CWnd` object.  
  
### Example  
  See the example for [CWnd::SetWindowText](#setwindowtext).  
  
##  <a name="hidecaret"></a>  CWnd::HideCaret  
 Hides the caret by removing it from the display screen.  
  
```  
void HideCaret();
```  
  
### Remarks  
 Although the caret is no longer visible, it can be displayed again by using the [ShowCaret](#showcaret) member function. Hiding the caret does not destroy its current shape.  
  
 Hiding is cumulative. If `HideCaret` has been called five times in a row, the `ShowCaret` member function must be called five times before the caret will be shown.  
  
##  <a name="hilitemenuitem"></a>  CWnd::HiliteMenuItem  
 Highlights or removes the highlight from a top-level (menu-bar) menu item.  
  
```  
BOOL HiliteMenuItem (CMenu * pMenu,  
    UINT-nIDHiliteItem  
    UINT-nHilite);
```  
  
### Parameters  
 `pMenu`  
 Identifies the top-level menu that contains the item to be highlighted.  
  
 `nIDHiliteItem`  
 Specifies the menu item to be highlighted, depending on the value of the `nHilite` parameter.  
  
 `nHilite`  
 Specifies whether the menu item is highlighted or the highlight is removed. It can be a combination of **MF_HILITE** or **MF_UNHILITE** with **MF_BYCOMMAND** or **MF_BYPOSITION**. The values can be combined using the bitwise OR operator. These values have the following meanings:  
  
- **MF_BYCOMMAND** Interprets `nIDHiliteItem` as the menu-item ID (the default interpretation).  
  
- **MF_BYPOSITION** Interprets `nIDHiliteItem` as the zero-based offset of the menu item.  
  
- **MF_HILITE** Highlights the item. If this value is not given, the highlight is removed from the item.  
  
- **MF_UNHILITE** Removes the highlight from the item.  
  
### Return Value  
 Specifies whether the menu item was highlighted. Nonzero if the item was highlighted; otherwise 0.  
  
### Remarks  
 The **MF_HILITE** and **MF_UNHILITE** flags can be used only with this member function; they cannot be used with the [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu) member function.  
  
##  <a name="htmlhelp"></a>  CWnd::HtmlHelp  
 Call this member function to invoke the HTMLHelp application.  
  
```  
virtuelle void HtmlHelp (DWORD_PTR DwData,  
    UINT nCmd = 0x000F);
```  
  
### Parameters  
 `dwData`  
 Specifies additional data. The value used depends on the value of the `nCmd` parameter.  
  
 `nCmd`  
 Specifies the type of help requested. For a list of possible values and how they affect the `dwData` parameter, see the `uCommand` parameter described in the HTML Help API Reference in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 See [CWinApp::HtmlHelp](../../mfc/reference/cwinapp-class.md#htmlhelp) for more information.  
  
##  <a name="initdynamiclayout"></a>  CWnd::InitDynamicLayout  
 Called by the framework to initialize dynamic layout for a window.  
  
```  
void InitDynamicLayout();
```  
  
### Remarks  
 Do not call this method directly.  
  
##  <a name="invalidate"></a>  CWnd::Invalidate  
 Invalidates the entire client area of `CWnd`.  
  
```  
void Invalidate (BOOL bErase = TRUE);
```  
  
### Parameters  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The client area is marked for painting when the next [WM_PAINT](#onpaint) message occurs. The region can also be validated before a `WM_PAINT` message occurs by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region, not just in the given part, is erased.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
### Example  
  See the example for [CWnd::UpdateWindow](#updatewindow).  
  
##  <a name="invalidaterect"></a>  CWnd::InvalidateRect  
 Invalidates the client area within the given rectangle by adding that rectangle to the `CWnd` update region.  
  
```  
void InvalidateRect (LPCRECT LpRect,  
    BOOL bErase = TRUE);
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or a [RECT structure](../../mfc/reference/rect-structure1.md) that contains the rectangle (in client coordinates) to be added to the update region. If `lpRect` is **NULL**, the entire client area is added to the region.  
  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The invalidated rectangle, along with all other areas in the update region, is marked for painting when the next [WM_PAINT](#onpaint) message is sent. The invalidated areas accumulate in the update region until the region is processed when the next `WM_PAINT` call occurs, or until the region is validated by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region is erased, not just in the given part.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
##  <a name="invalidatergn"></a>  CWnd::InvalidateRgn  
 Invalidates the client area within the given region by adding it to the current update region of `CWnd`.  
  
```  
void InvalidateRgn (CRgn * PRNG,  
    BOOL bErase = TRUE);
```  
  
### Parameters  
 `pRgn`  
 A pointer to a [CRgn](../../mfc/reference/crgn-class.md) object that identifies the region to be added to the update region. The region is assumed to have client coordinates. If this parameter is **NULL**, the entire client area is added to the update region.  
  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The invalidated region, along with all other areas in the update region, is marked for painting when the [WM_PAINT](#onpaint) message is next sent. The invalidated areas accumulate in the update region until the region is processed when a `WM_PAINT` message is next sent, or until the region is validated by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region, not just in the given part, is erased.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
 The given region must have been previously created by one of the region functions.  
  
##  <a name="invokehelper"></a>  CWnd::InvokeHelper  
 Call this member function to invoke the ActiveX Control method or property specified by `dwDispID`, in the context specified by `wFlags`.  
  
```  
void AFX_CDECL InvokeHelper (DISPID DwDispID,  
    WORD-wFlags  
    VARTYPE-vtRet  
    void* PvRet, const BYTE* PbParamInfo,  
 ...);
```  
  
### Parameters  
 `dwDispID`  
 Identifies the method or property to be invoked.  
  
 `wFlags`  
 Flags describing the context of the call to **IDispatch::Invoke**.  
  
 `vtRet`  
 Specifies the type of the return value. For possible values, see the Remarks section for [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvRet`  
 Address of the variable that will that will receive the property value or return value. It must match the type specified by `vtRet`.  
  
 `pbParamInfo`  
 Pointer to a null-terminated string of bytes specifying the types of the parameters following `pbParamInfo`. For possible values, see the Remarks section for `COleDispatchDriver::InvokeHelper`.  
  
 *...*  
 Variable List of parameters, of types specified in `pbParamInfo`.  
  
### Remarks  
 The `pbParamInfo` parameter specifies the types of the parameters passed to the method or property. The variable list of arguments is represented by *...* in the syntax declaration.  
  
 This function converts the parameters to **VARIANTARG** values, then invokes the **IDispatch::Invoke** method on the ActiveX control. If the call to **IDispatch::Invoke** fails, this function will throw an exception. If the `SCODE` (status code) returned by **IDispatch::Invoke** is `DISP_E_EXCEPTION`, this function throws a [COleException](../../mfc/reference/coleexception-class.md) object, otherwise it throws a [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).  
  
> [!NOTE]
>  This function should be called only on a `CWnd` object that represents an ActiveX control.  
  
 For more information about using this member function with ActiveX Control Containers, see the article [ActiveX Control Containers: Programming ActiveX Controls in an ActiveX Control Container](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="ischild"></a>  CWnd::IsChild  
 Indicates whether the window specified by `pWnd` is a child window or other direct descendant of `CWnd`.  
  
```  
BOOL IsChild(const CWnd* pWnd) const;  
```  
  
### Parameters  
 `pWnd`  
 Identifies the window to be tested.  
  
### Return Value  
 Specifies the outcome of the function. The value is nonzero if the window identified by `pWnd` is a child window of `CWnd`; otherwise 0.  
  
### Remarks  
 A child window is the direct descendant of `CWnd` if the `CWnd` object is in the chain of parent windows that leads from the original pop-up window to the child window.  
  
##  <a name="isd2dsupportenabled"></a>  CWnd::IsD2DSupportEnabled  
 Determines whether D2D support is enabled.  
  
```  
BOOL IsD2DSupportEnabled();
```  
  
### Return Value  
 TRUE if the feature is enabled; otherwise FALSE.  
  
##  <a name="isdialogmessage"></a>  CWnd::IsDialogMessage  
 Call this member function to determine whether the given message is intended for a modeless dialog box; if it is, this function processes the message.  
  
```  
BOOL IsDialogMessage(LPMSG lpMsg);
```  
  
### Parameters  
 `lpMsg`  
 Points to an [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message to be checked.  
  
### Return Value  
 Specifies whether the member function has processed the given message. It is nonzero if the message has been processed; otherwise 0. If the return is 0, call the [CWnd::PreTranslateMessage](#pretranslatemessage) member function of the base class to process the message. In an override of the `CWnd::PreTranslateMessage` member function the code looks like this :  
  
 [!code-cpp[NVC_MFCWindowing#100](../../mfc/reference/codesnippet/cpp/cwnd-class_40.cpp)]  
  
### Remarks  
 When the `IsDialogMessage` function processes a message, it checks for keyboard messages and converts them to selection commands for the corresponding dialog box. For example, the TAB key selects the next control or group of controls, and the DOWN ARROW key selects the next control in a group.  
  
 You must not pass a message processed by `IsDialogMessage` to the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) or [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows functions, because it has already been processed.  
  
##  <a name="isdlgbuttonchecked"></a>  CWnd::IsDlgButtonChecked  
 Determines whether a button control has a check mark next to it.  
  
```  
UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### Parameters  
 `nIDButton`  
 Specifies the integer identifier of the button control.  
  
### Return Value  
 Nonzero if the given control is checked, and 0 if it is not checked. Only radio buttons and check boxes can be checked. For three-state buttons, the return value can be 2 if the button is indeterminate. This member function returns 0 for a pushbutton.  
  
### Remarks  
 If the button is a three-state control, the member function determines whether it is dimmed, checked, or neither.  
  
##  <a name="isdynamiclayoutenabled"></a>  CWnd::IsDynamicLayoutEnabled  
 Determines whether dynamic layout is enabled on this window. If dynamic layout is enabled, the position and size of child windows can change when the user resizes the parent window.  
  
```  
BOOL IsDynamicLayoutEnabled() const;  
```  
  
### Return Value  
 TRUE if dynamic layout is enabled; otherwise FALSE.  
  
### Remarks  
  
##  <a name="isiconic"></a>  CWnd::IsIconic  
 Specifies whether `CWnd` is minimized (iconic).  
  
```  
BOOL IsIconic() const;  
```  
  
### Return Value  
 Nonzero if `CWnd` is minimized; otherwise 0.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#101](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="istouchwindow"></a>  CWnd::IsTouchWindow  
 Specifies whether `CWnd` has touch support.  
  
```  
BOOL IsTouchWindow() const;  
```  
  
### Return Value  
 `TRUE` if `CWnd` has touch support; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="iswindowenabled"></a>  CWnd::IsWindowEnabled  
 Specifies whether `CWnd` is enabled for mouse and keyboard input.  
  
```  
BOOL IsWindowEnabled() const;  
```  
  
### Return Value  
 Nonzero if `CWnd` is enabled; otherwise 0.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#102](../../mfc/reference/codesnippet/cpp/cwnd-class_42.cpp)]  
  
##  <a name="iswindowvisible"></a>  CWnd::IsWindowVisible  
 Determines the visibility state of the given window.  
  
```  
BOOL IsWindowVisible() const;  
```  
  
### Return Value  
 Nonzero if `CWnd` is visible (has the [WS_VISIBLE](../../mfc/reference/window-styles.md) style bit set, and parent window is visible). Because the return value reflects the state of the **WS_VISIBLE** style bit, the return value may be nonzero even though `CWnd` is totally obscured by other windows.  
  
### Remarks  
 A window possesses a visibility state indicated by the **WS_VISIBLE** style bit. When this style bit is set with a call to the [ShowWindow](#showwindow) member function, the window is displayed and subsequent drawing to the window is displayed as long as the window has the style bit set.  
  
 Any drawing to a window that has the **WS_VISIBLE** style will not be displayed if the window is covered by other windows or is clipped by its parent window.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#103](../../mfc/reference/codesnippet/cpp/cwnd-class_43.cpp)]  
  
##  <a name="iszoomed"></a>  CWnd::IsZoomed  
 Determines whether `CWnd` has been maximized.  
  
```  
BOOL IsZoomed() const;  
```  
  
### Return Value  
 Nonzero if `CWnd` is maximized; otherwise 0.  
  
##  <a name="killtimer"></a>  CWnd::KillTimer  
 Kills the timer event identified by `nIDEvent` from the earlier call to `SetTimer`.  
  
```  
BOOL KillTimer(UINT_PTR nIDEvent);
```  
  
### Parameters  
 `nIDEvent`  
 The value of the timer event passed to [SetTimer](#settimer).  
  
### Return Value  
 Specifies the outcome of the function. The value is nonzero if the event was killed. It is 0 if the `KillTimer` member function could not find the specified timer event.  
  
### Remarks  
 Pending [WM_TIMER](#ontimer) messages associated with the timer are not removed from the message queue.  
  
### Example  
  See the example for [CWnd::SetTimer](#settimer).  
  
##  <a name="loaddynamiclayoutresource"></a>  CWnd::LoadDynamicLayoutResource  
 Called by the framework to load dynamic layout information from the resource file.  
  
```  
BOOL LoadDynamicLayoutResource(LPCTSTR lpszResourceName);
```  
  
### Parameters  
 `lpszResourceName`  
 The name of the resource that contains the desired dynamic layout information for this window.  
  
### Return Value  
 Nonzero if the function is successful. It is 0 if a failure occurs.  
  
### Remarks  
 Do not call this method directly.  
  
##  <a name="lockwindowupdate"></a>  CWnd::LockWindowUpdate  
 Disables drawing in the given window.  
  
```  
BOOL LockWindowUpdate();
```  
  
### Return Value  
 Nonzero if the function is successful. It is 0 if a failure occurs or if the `LockWindowUpdate` function has been used to lock another window.  
  
### Remarks  
 A locked window cannot be moved. Only one window can be locked at a time. To unlock a window locked with `LockWindowUpdate`, call [UnlockWindowUpdate](#unlockwindowupdate).  
  
 If an application with a locked window (or any locked child windows) calls the [GetDC,](http://msdn.microsoft.com/library/windows/desktop/dd144871) [GetDCEx,](http://msdn.microsoft.com/library/windows/desktop/dd144873) or [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) Windows function, the called function returns a device context whose visible region is empty. This will occur until the application unlocks the window by calling the `UnlockWindowUpdate` member function.  
  
 While window updates are locked, the system keeps track of the bounding rectangle of any drawing operations to device contexts associated with a locked window. When drawing is reenabled, this bounding rectangle is invalidated in the locked window and its child windows to force an eventual [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message to update the screen. If no drawing has occurred while the window updates were locked, no area is invalidated.  
  
 The `LockWindowUpdate` member function does not make the given window invisible and does not clear the [WS_VISIBLE](../../mfc/reference/window-styles.md) style bit.  
  
##  <a name="m_hwnd"></a>  CWnd::m_hWnd  
 The handle of the Windows window attached to this `CWnd`.  
  
```  
HWND M_hWnd;  
```  
  
### Remarks  
 The `m_hWnd` data member is a public variable of type `HWND`.  
  
##  <a name="mapwindowpoints"></a>  CWnd::MapWindowPoints  
 Converts (maps) a set of points from the coordinate space of the `CWnd` to the coordinate space of another window.  
  
```  
void MapWindowPoints (CWnd * PwndTo,  
    LPRECT-LpRect) const;  
  
void MapWindowPoints (CWnd * PwndTo,  
    LPPOINT-lpPoint  
    UINT nCount) const;  
```  
  
### Parameters  
 *pwndTo*  
 Identifies the window to which points are converted. If this parameter is **NULL**, the points are converted to screen coordinates.  
  
 `lpRect`  
 Specifies the rectangle whose points are to be converted. The first version of this function is available only for Windows 3.1 and later.  
  
 `lpPoint`  
 A pointer to an array of [POINT structure](../../mfc/reference/point-structure1.md) that contain the set of points to be converted.  
  
 `nCount`  
 Specifies the number of **POINT** structures in the array pointed to by `lpPoint`.  
  
##  <a name="messagebox"></a>  CWnd::MessageBox  
 Creates and displays a window that contains an application-supplied message and caption, plus a combination of the predefined icons and pushbuttons described in the [Message-Box Styles](../../mfc/reference/message-box-styles.md) list.  
  
```  
Int MessageBox (LPCTSTR LpszText,  
    LPCTSTR LpszCaption = NULL  
    UINT %nbenachrichtigungen = MB_OK);
```  
  
### Parameters  
 `lpszText`  
 Points to a `CString` object or null-terminated string containing the message to be displayed.  
  
 `lpszCaption`  
 Points to a `CString` object or null-terminated string to be used for the message-box caption. If `lpszCaption` is **NULL**, the default caption "Error" is used.  
  
 `nType`  
 Specifies the contents and behavior of the message box.  
  
### Return Value  
 This method utilizes the [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) function as defined in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This method returns the result of calling this function.  
  
### Remarks  
 Use the global function [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) instead of this member function to implement a message box in your application.  
  
 The following shows the various system icons that can be used in a message box:  
  
|||  
|-|-|  
|![Stop &#40;x&#41; icon](../../mfc/reference/media/vc364f1.gif "vc364f1")|**MB_ICONHAND**, **MB_ICONSTOP**, and **MB_ICONERROR**|  
|![Help &#40;&#41; icon](../../mfc/reference/media/vc364f2.gif "vc364f2")|**MB_ICONQUESTION**|  
|![Important &#40;&#33;&#41; icon](../../mfc/reference/media/vc364f3.gif "vc364f3")|**MB_ICONEXCLAMATION** and **MB_ICONWARNING**|  
|![Information &#40;i&#41; icon](../../mfc/reference/media/vc364f4.gif "vc364f4")|**MB_ICONASTERISK** and **MB_ICONINFORMATION**|  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#104](../../mfc/reference/codesnippet/cpp/cwnd-class_44.cpp)]  
  
##  <a name="modifystyle"></a>  CWnd::ModifyStyle  
 Call this member function to modify a window's style.  
  
```  
BOOL ModifyStyle (DWORD DwRemove,  
    DWORD-dwAdd  
    UINT nFlags = 0);
```  
  
### Parameters  
 `dwRemove`  
 Specifies window styles to be removed during style modification.  
  
 `dwAdd`  
 Specifies window styles to be added during style modification.  
  
 `nFlags`  
 Flags to be passed to [SetWindowPos](#setwindowpos), or zero if `SetWindowPos` should not be called. The default is zero. See the Remarks section for a list of preset flags.  
  
### Return Value  
 Nonzero if style was successfully modified; otherwise, 0.  
  
### Remarks  
 Styles to be added or removed can be combined by using the bitwise OR (&#124;) operator. See the topics [Window Styles](http://msdn.microsoft.com/library/windows/desktop/ms632600) and [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information about the available window styles.  
  
 If `nFlags` is nonzero, `ModifyStyle` calls the Windows API function [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) and redraws the window by combining `nFlags` with the following four preset flags:  
  
- `SWP_NOSIZE` Retains the current size.  
  
- `SWP_NOMOVE` Retains the current position.  
  
- `SWP_NOZORDER` Retains the current Z order.  
  
- `SWP_NOACTIVATE` Does not activate the window.  
  
 To modify a window's extended styles, see [ModifyStyleEx](#modifystyleex).  
  
> [!NOTE]
>  For some styles in certain controls (the **ES_READONLY** style in the edit control, for example), **ModifyStyle** may not properly change the style because the control may need to perform special internal processing. In these cases, a corresponding message to change the style will be available ( **EM_SETREADONLY** in the example mentioned).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#105](../../mfc/reference/codesnippet/cpp/cwnd-class_45.cpp)]  
  
##  <a name="modifystyleex"></a>  CWnd::ModifyStyleEx  
 Call this member function to modify a window's extended style.  
  
```  
BOOL ModifyStyleEx (DWORD DwRemove,  
    DWORD-dwAdd  
    UINT nFlags = 0);
```  
  
### Parameters  
 `dwRemove`  
 Specifies extended styles to be removed during style modification.  
  
 `dwAdd`  
 Specifies extended styles to be added during style modification.  
  
 `nFlags`  
 Flags to be passed to [SetWindowPos](#setwindowpos), or zero if `SetWindowPos` should not be called. The default is zero. See the Remarks section for a list of preset flags.  
  
### Return Value  
 Nonzero if style was successfully modified; otherwise, 0.  
  
### Remarks  
 Styles to be added or removed can be combined by using the bitwise OR (&#124;) operator. See the topics [Extended Window Styles](../../mfc/reference/extended-window-styles.md) in this book and [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information about the available extended styles  
  
 If `nFlags` is nonzero, `ModifyStyleEx` calls the Windows API function [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) and redraws the window by combining `nFlags` with the following four preset flags:  
  
- `SWP_NOSIZE` Retains the current size.  
  
- `SWP_NOMOVE` Retains the current position.  
  
- `SWP_NOZORDER` Retains the current Z order.  
  
- `SWP_NOACTIVATE` Does not activate the window.  
  
 To modify windows using regular window styles, see [ModifyStyle](#modifystyle).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#106](../../mfc/reference/codesnippet/cpp/cwnd-class_46.cpp)]  
  
##  <a name="movewindow"></a>  CWnd::MoveWindow  
 Changes the position and dimensions.  
  
```  
void MoveWindow (Int X,  
    Int-y  
    Int-nWidth  
    Int-nHeight  
    BOOL bRepaint = TRUE);

 
void MoveWindow (LPCRECT LpRect, BOOL bRepaint = TRUE);
```  
  
### Parameters  
 *x*  
 Specifies the new position of the left side of the `CWnd`.  
  
 *y*  
 Specifies the new position of the top of the `CWnd`.  
  
 `nWidth`  
 Specifies the new width of the `CWnd`.  
  
 `nHeight`  
 Specifies the new height of the `CWnd`.  
  
 `bRepaint`  
 Specifies whether `CWnd` is to be repainted. If **TRUE**, `CWnd` receives a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message in its [OnPaint](#onpaint) message handler as usual. If this parameter is **FALSE**, no repainting of any kind occurs. This applies to the client area, to the nonclient area (including the title and scroll bars), and to any part of the parent window uncovered as a result of `CWnd`'s move. When this parameter is **FALSE**, the application must explicitly invalidate or redraw any parts of `CWnd` and parent window that must be redrawn.  
  
 `lpRect`  
 The [CRect](../../atl-mfc-shared/reference/crect-class.md) object or [RECT structure](../../mfc/reference/rect-structure1.md) that specifies the new size and position.  
  
### Remarks  
 For a top-level `CWnd` object, the *x* and *y* parameters are relative to the upper-left corner of the screen. For a child `CWnd` object, they are relative to the upper-left corner of the parent window's client area.  
  
 The `MoveWindow` function sends the [WM_GETMINMAXINFO](#ongetminmaxinfo) message. Handling this message gives `CWnd` the opportunity to modify the default values for the largest and smallest possible windows. If the parameters to the `MoveWindow` member function exceed these values, the values can be replaced by the minimum or maximum values in the `WM_GETMINMAXINFO` handler.  
  
### Example  
  See the example for [CWnd::ClientToScreen](#clienttoscreen).  
  
##  <a name="notifywinevent"></a>  CWnd::NotifyWinEvent  
 Signals the system that a predefined event occurred. If any client applications have registered a hook function for the event, the system calls the client's hook function.  
  
```  
void NotifyWinEvent (DWORD-Ereignis  
    LANGE idObjectType  
    LANGE IdObject);
```  
  
### Parameters  
 `event`  
 Specifies the event that occurred. This value must be one of the [event constants](http://msdn.microsoft.com/library/windows/desktop/dd318066).  
  
 *idObjectType*  
 Identifies the kind of object that generated the event. This value is one of the predefined [object identifiers](http://msdn.microsoft.com/library/windows/desktop/dd373606) or a custom object ID value.  
  
 `idObject`  
 Identifies whether the event was generated by an object or a child element of the object. If this value is **CHILDID_SELF**, the event was generated by the object itself. If not, this value is the child ID of the element that generated the event.  
  
### Remarks  
 This member function emulates the functionality of the function [NotifyWinEvent](http://msdn.microsoft.com/library/windows/desktop/dd373603), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onactivate"></a>  CWnd::OnActivate  
 The framework calls this member function when a `CWnd` object is being activated or deactivated.  
  
```  
Afx_msg void OnActivate (UINT nState,  
    CWnd * pWndOther,  
    BOOL bMinimized);
```  
  
### Parameters  
 `nState`  
 Specifies whether the `CWnd` is being activated or deactivated. It can be one of the following values:  
  
- **WA_INACTIVE** The window is being deactivated.  
  
- **WA_ACTIVE** The window is being activated through some method other than a mouse click (for example, by use of the keyboard interface to select the window).  
  
- **WA_CLICKACTIVE** The window is being activated by a mouse click.  
  
 *pWndOther*  
 Pointer to the `CWnd` being activated or deactivated. The pointer can be **NULL**, and it may be temporary.  
  
 *bMinimized*  
 Specifies the minimized state of the `CWnd` being activated or deactivated. A value of **TRUE** indicates the window is minimized.  
  
 If **TRUE**, the `CWnd` is being activated; otherwise deactivated.  
  
### Remarks  
 If the `CWnd` object is activated with a mouse click, it will also receive an [OnMouseActivate](#onmouseactivate) member function call.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onactivateapp"></a>  CWnd::OnActivateApp  
 The framework calls this member function to all top-level windows of the task being activated and for all top-level windows of the task being deactivated.  
  
```  
Afx_msg void OnActivateApp (BOOL bActive,  
    DWORD-DwThreadID);
```  
  
### Parameters  
 `bActive`  
 Specifies whether the `CWnd` is being activated or deactivated. **TRUE** means the `CWnd` is being activated. **FALSE** means the `CWnd` is being deactivated.  
  
 *dwThreadID*  
 Specifies the value of the thread ID. If `bActive` is **TRUE**, *dwThreadID* identifies the thread that owns the `CWnd` being deactivated. If `bActive` is **FALSE**, *dwThreadID* identifies the thread that owns the `CWnd` being activated.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onambientproperty"></a>  CWnd::OnAmbientProperty  
 The framework calls this member function to obtain ambient property values from a window that contains OLE controls.  
  
```  
virtuelle BOOL OnAmbientProperty (COleControlSite* pSite, DISPID Dispid, Variante* Pvar);
```  
  
### Parameters  
 `pSite`  
 Pointer to the site of the control that requested the ambient property.  
  
 `dispid`  
 The dispatch ID of the requested ambient property.  
  
 `pvar`  
 Pointer to a caller-allocated `VARIANT` structure, through which the ambient property's value will be returned.  
  
### Return Value  
 **TRUE** if the ambient property is supported; **FALSE** if not.  
  
### Remarks  
 Override this function to alter the default ambient property values returned by an OLE control container to its controls. Any ambient property requests not handled by an overriding function should be forwarded to the base class implementation.  
  
##  <a name="onappcommand"></a>  CWnd::OnAppCommand  
 The framework calls this member function when the user generates an application command event. Such an event occurs when the user clicks an application command button or types an application command key.  
  
```  
Afx_msg void OnAppCommand (CWnd * aufnehmen,  
    UINT-nCmd  
    UINT-nDevice  
    UINT-nKey);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pWnd`|Pointer to a `CWnd` object that represents the window where the user clicked the comman button or pressed the command key. This window can be a child window of the window receiving the message.|  
|[in] `nCmd`|Indicates the application command. For a list of possible values, see the commands under the *cmd* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275).|  
|[in] `nDevice`|The input device that generated the input event. For a list of possible values, see the devices under the *uDevice* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275).|  
|[in] `nKey`|Indicates any virtual keys that are down, such as the CTRL key or the left mouse button. For a list of possible values, see the keys under the *dwKeys* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275). For more information, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
  
### Remarks  
 This method receives the [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onaskcbformatname"></a>  CWnd::OnAskCbFormatName  
 The framework calls this member function when the Clipboard contains a data handle for the `CF_OWNERDISPLAY` format (that is, when the Clipboard owner will display the Clipboard contents).  
  
```  
Afx_msg void OnAskCbFormatName (UINT nMaxCount,  
    LPTSTR LpszString);
```  
  
### Parameters  
 `nMaxCount`  
 Specifies the maximum number of bytes to copy.  
  
 `lpszString`  
 Points to the buffer where the copy of the format name is to be stored.  
  
### Remarks  
 The Clipboard owner should provide a name for its format.  
  
 Override this member function and copy the name of the `CF_OWNERDISPLAY` format into the specified buffer, not exceeding the maximum number of bytes specified.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncancelmode"></a>  CWnd::OnCancelMode  
 The framework calls this member function to inform `CWnd` to cancel any internal mode.  
  
```  
Afx_msg void OnCancelMode();
```  
  
### Remarks  
 If the `CWnd` object has the focus, its `OnCancelMode` member function is called when a dialog box or message box is displayed. This gives the `CWnd` the opportunity to cancel modes such as mouse capture.  
  
 The default implementation responds by calling the [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) Windows function. Override this member function in your derived class to handle other modes.  
  
##  <a name="oncapturechanged"></a>  CWnd::OnCaptureChanged  
 The framework calls this member function to notify the window that is losing the mouse capture.  
  
```  
Afx_msg void OnCaptureChanged (CWnd * aufnehmen);
```  
  
### Parameters  
 `pWnd`  
 A pointer to the window to gain mouse capture  
  
### Remarks  
 A window receives this message even if it calls [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) itself. An application should not attempt to set the mouse capture in response to this message. When it receives this message, a window should redraw itself, if necessary, to reflect the new mouse-capture state.  
  
 See the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information on the `ReleaseCapture` Windows function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchangecbchain"></a>  CWnd::OnChangeCbChain  
 The framework calls this member function for each window in the Clipboard-viewer chain to notify it that a window is being removed from the chain.  
  
```  
Afx_msg void OnChangeCbChain (HWND hWndRemove,  
    HWND hWndAfter);
```  
  
### Parameters  
 `hWndRemove`  
 Specifies the window handle that is being removed from the Clipboard-viewer chain.  
  
 `hWndAfter`  
 Specifies the window handle that follows the window being removed from the Clipboard-viewer chain.  
  
### Remarks  
 Each `CWnd` object that receives an `OnChangeCbChain` call should use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function to send the [WM_CHANGECBCHAIN](http://msdn.microsoft.com/library/windows/desktop/ms649019) message to the next window in the Clipboard-viewer chain (the handle returned by `SetClipboardViewer`). If `hWndRemove` is the next window in the chain, the window specified by `hWndAfter` becomes the next window, and Clipboard messages are passed on to it.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchangeuistate"></a>  CWnd::OnChangeUIState  
 Called when the user interface (UI) state should be changed.  
  
```  
Afx_msg void OnChangeUIState (UINT nDie Aktion wurde,  
    UINT-nUIElement);
```  
  
### Parameters  
 `nAction`  
 Specifies the action to be taken. Can be one of the following values:  
  
- **UIS_CLEAR** The UI state element (specified by `nUIElement`) should be hidden.  
  
- **UIS_INITIALIZE** The UI state element (specified by `nUIElement`) should be changed based on the last input event. For more information, see the **Remarks** section of [WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342).  
  
- **UIS_SET** The UI state element (specified by `nUIElement`) should be visible.  
  
 `nUIElement`  
 Specifies which UI state elements are affected or the style of the control. Can be one of the following values:  
  
- **UISF_HIDEACCEL** Keyboard accelerators.  
  
- **UISF_HIDEFOCUS** Focus indicators.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onchar"></a>  CWnd::OnChar  
 The framework calls this member function when a keystroke translates to a nonsystem character.  
  
```  
Afx_msg void OnChar (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Contains the character code value of the key.  
  
 `nRepCnt`  
 Contains the repeat count, the number of times the keystroke is repeated when user holds down the key.  
  
 `nFlags`  
 Contains the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0-15|Specifies the repeat count. The value is the number of times the keystroke is repeated as a result of the user holding down the key.|  
|16-23|Specifies the scan code. The value depends on the original equipment manufacturer (OEM)|  
|24|Specifies whether the key is an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101- or 102-key keyboard. The value is 1 if it is an extended key; otherwise, it is 0.|  
|25-28|Used internally by Windows.|  
|29|Specifies the context code. The value is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.|  
|30|Specifies the previous key state. The value is 1 if the key is down before the message is sent, or it is 0 if the key is up.|  
|31|Specifies the transition state. The value is 1 if the key is being released, or it is 0 if the key is being pressed.|  
  
### Remarks  
 This function is called before the [OnKeyUp](#onkeyup) member function and after the [OnKeyDown](#onkeydown) member function are called. `OnChar` contains the value of the keyboard key being pressed or released.  
  
 Because there is not necessarily a one-to-one correspondence between keys pressed and `OnChar` calls generated, the information in `nFlags` is generally not useful to applications. The information in `nFlags` applies only to the most recent call to the `OnKeyUp` member function or the `OnKeyDown` member function that precedes the call to `OnChar`.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchartoitem"></a>  CWnd::OnCharToItem  
 Called when a list box with the [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) style sends its owner a [WM_CHARTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761358) message in response to a [WM_CHAR](#onchar) message.  
  
```  
Afx_msg Int OnCharToItem (UINT nChar,  
    CListBox-* pListBox,  
    UINT nIndex);
```  
  
### Parameters  
 `nChar`  
 Specifies the value of the key pressed by the user.  
  
 `pListBox`  
 Specifies a pointer to the list box. It may be temporary.  
  
 `nIndex`  
 Specifies the current caret position.  
  
### Return Value  
 The framework calls this member function to specify the action that the application performed in response to the call. A return value of –2 indicates that the application handled all aspects of selecting the item and wants no further action by the list box. A return value of –1 indicates that the list box should perform the default action in response to the keystroke. A return value of 0 or greater specifies the zero-based index of an item in the list box and indicates that the list box should perform the default action for the keystroke on the given item.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchildactivate"></a>  CWnd::OnChildActivate  
 If the `CWnd` object is a multiple document interface (MDI) child window, `OnChildActivate` is called by the framework when the user clicks the window's title bar or when the window is activated, moved, or sized.  
  
```  
Afx_msg void OnChildActivate();
```  
  
##  <a name="onchildnotify"></a>  CWnd::OnChildNotify  
 This member function is called by this window's parent window when it receives a notification message that applies to this window.  
  
```  
virtuelle BOOL OnChildNotify (UINT-Nachricht,  
    WPARAM wParam-Parameter  
    LPARAM lParam  
    LRESULT* pResult);
```  
  
### Parameters  
 `message`  
 A Windows message number sent to a parent window.  
  
 `wParam`  
 The **wparam** associated with the message.  
  
 `lParam`  
 The **lparam** associated with the message.  
  
 `pLResult`  
 A pointer to a value to be returned from the parent's window procedure. This pointer will be **NULL** if no return value is expected.  
  
### Return Value  
 Nonzero if this window is responsible for handling the message sent to its parent; otherwise 0.  
  
### Remarks  
 Never call this member function directly.  
  
 The default implementation of this member function returns 0, which means that the parent should handle the message.  
  
 Override this member function to extend the manner in which a control responds to notification messages.  
  
##  <a name="onclipboardupdate"></a>  CWnd::OnClipboardUpdate  
 The framework calls this member function when the contents of the clipboard have changed.  
  
```  
Afx_msg void OnClipboardUpdate();
```  
  
##  <a name="onclose"></a>  CWnd::OnClose  
 The framework calls this member function as a signal that the `CWnd` or an application is to terminate.  
  
```  
Afx_msg void OnOpen();
```  
  
### Remarks  
 The default implementation calls `DestroyWindow`.  
  
##  <a name="oncolorizationcolorchanged"></a>  CWnd::OnColorizationColorChanged  
 The framework calls this member when the rendering policy for the nonclient area has changed.  
  
```  
Afx_msg void OnColorizationColorChanged (DWORD DwColorizationColor,   
    BOOL bOpacity);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `dwColorizationColor`|Specifies the new colorization color.<br /><br /> The color format is a hexadecimal number of the form 0xAARRGGBB, where each of the four components ranges from 0x00 through 0xFF. The AA component is the alpha value, RR is the color red, GG is green, and BB is blue.|  
|[in] `bOpacity`|`true` if the new color is blended with opacity; `false` if it is not.|  
  
### Remarks  
 This method receives the [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388198) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncommand"></a>  CWnd::OnCommand  
 The framework calls this member function when the user selects an item from a menu, when a child control sends a notification message, or when an accelerator keystroke is translated.  
  
```  
virtuelle BOOL OnCommand (wParam WPARAM-Parameter  
    LPARAM lParam);
```  
  
### Parameters  
 `wParam`  
 The low-order word of `wParam` identifies the command ID of the menu item, control, or accelerator. The high-order word of `wParam` specifies the notification message if the message is from a control. If the message is from an accelerator, the high-order word is 1. If the message is from a menu, the high-order word is 0.  
  
 `lParam`  
 Identifies the control that sends the message if the message is from a control. Otherwise, `lParam` is 0.  
  
### Return Value  
 An application returns nonzero if it processes this message; otherwise 0.  
  
### Remarks  
 `OnCommand` processes the message map for control notification and `ON_COMMAND` entries, and calls the appropriate member function.  
  
 Override this member function in your derived class to handle the [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message. An override will not process the message map unless the base class `OnCommand` is called.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompacting"></a>  CWnd::OnCompacting  
 The framework calls this member function for all top-level windows when Windows detects that more than 12.5 percent of system time over a 30- to 60-second interval is being spent compacting memory.  
  
```  
Afx_msg void OnCompacting (UINT nCpuTime);
```  
  
### Parameters  
 *nCpuTime*  
 Specifies the ratio of CPU time currently spent by Windows compacting memory to CPU time spent performing other operations. For example, 8000h represents 50 percent of CPU time spent compacting memory.  
  
### Remarks  
 This indicates that system memory is low.  
  
 When a `CWnd` object receives this call, it should free as much memory as possible, taking into account the current level of activity of the application and the total number of applications running in Windows. The application can call the Windows function to determine how many applications are running.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompareitem"></a>  CWnd::OnCompareItem  
 The framework calls this member function to specify the relative position of a new item in a child sorted owner-draw combo or list box.  
  
```  
Afx_msg Int OnCompareItem (Int nIDCtl,  
    LPCOMPAREITEMSTRUCT LpCompareItemStruct);
```  
  
### Parameters  
 `nIDCtl`  
 The identifier of the control that sent the `WM_COMPAREITEM` message.  
  
 `lpCompareItemStruct`  
 Contains a long pointer to a [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) data structure that contains the identifiers and application-supplied data for two items in the combo or list box.  
  
### Return Value  
 Indicates the relative position of the two items. It may be any of the following values:  
  
|Value|Meaning|  
|-----------|-------------|  
|–1|Item 1 sorts before item 2.|  
|0|Item 1 and item 2 sort the same.|  
|1|Item 1 sorts after item 2.|  
  
### Remarks  
 If a combo or list box is created with the [CBS_SORT](../../mfc/reference/combo-box-styles.md) or [LBS_SORT](../../mfc/reference/list-box-styles.md) style, Windows sends the combo-box or list-box owner a `WM_COMPAREITEM` message whenever the application adds a new item.  
  
 Two items in the combo or list box are reformed in a `COMPAREITEMSTRUCT` structure pointed to by `lpCompareItemStruct`. `OnCompareItem` should return a value that indicates which of the items should appear before the other. Typically, Windows makes this call several times until it determines the exact position for the new item.  
  
 If the **hwndItem** member of the `COMPAREITEMSTRUCT` structure belongs to a [CListBox](../../mfc/reference/clistbox-class.md) or [CComboBox](../../mfc/reference/ccombobox-class.md) object, then the `CompareItem` virtual function of the appropriate class is called. Override `CComboBox::CompareItem` or `CListBox::CompareItem` in your derived `CListBox` or `CComboBox` class to do the item comparison.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompositionchanged"></a>  CWnd::OnCompositionChanged  
 The framework calls this member function for all top-level windows when the Desktop Window Manager (DWM) composition is enabled or disabled.  
  
```  
Afx_msg void OnCompositionChanged();
```  
  
### Remarks  
 This method receives the [WM_DWMCOMPOSITIONCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388199) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncontextmenu"></a>  CWnd::OnContextMenu  
 Called by the framework when the user has clicked the right mouse button (right clicked) in the window.  
  
```  
Afx_msg void OnContextMenu (CWnd * aufnehmen,  
    CPoint pos);
```  
  
### Parameters  
 `pWnd`  
 Handle to the window in which the user right clicked the mouse. This can be a child window of the window receiving the message. For more information about processing this message, see the Remarks section.  
  
 `pos`  
 Position of the cursor, in screen coordinates, at the time of the mouse click.  
  
### Remarks  
 You can process this message by displaying a context menu using the [TrackPopupMenu](../../mfc/reference/cmenu-class.md#trackpopupmenu).  
  
 If you do not display a context menu you should pass this message onto the [DefWindowProc](#defwindowproc) function. If your window is a child window, `DefWindowProc` sends the message to the parent. Otherwise, `DefWindowProc` displays a default context menu if the specified position is in the window's caption.  
  
##  <a name="oncopydata"></a>  CWnd::OnCopyData  
 This member function is called by the framework to copy data from one application to another.  
  
```  
Afx_msg BOOL OnCopyData (CWnd* aufnehmen, COPYDATASTRUCT* pCopyDataStruct);
```  
  
### Parameters  
 `pWnd`  
 A pointer to a `CWnd` object that is sending the data.  
  
 `pCopyDataStruct`  
 A pointer to a [COPYDATASTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms649010) structure that contains the data being sent.  
  
### Return Value  
 Returns **TRUE** if the receiving application successfully accepts the data. Otherwise, returns **FALSE**.  
  
### Remarks  
 The data being passed must not contain pointers or other references to objects not accessible to the application receiving the data.  
  
 While the data is being copied, it must not be changed by another thread of the sending process.  
  
 The receiving application should consider the data read-only. The structure pointed to by the parameter `pCopyDataStruct` is valid only during the transfer of data; however, the receiving application should not free the memory associated with the structure.  
  
 If the receiving application needs access to the data after this function returns, it must copy the data received to a local buffer.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncreate"></a>  CWnd::OnCreate  
 The framework calls this member function when an application requests that the Windows window be created by calling the [Create](#create) or [CreateEx](#createex) member function.  
  
```  
Afx_msg Int OnCreate (LPCREATESTRUCT LpCreateStruct);
```  
  
### Parameters  
 `lpCreateStruct`  
 Points to a [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) structure that contains information about the `CWnd` object being created.  
  
### Return Value  
 `OnCreate` must return 0 to continue the creation of the `CWnd` object. If the application returns –1, the window will be destroyed.  
  
### Remarks  
 The `CWnd` object receives this call after the window is created but before it becomes visible. `OnCreate` is called before the **Create** or `CreateEx` member function returns.  
  
 Override this member function to perform any needed initialization of a derived class.  
  
 The `CREATESTRUCT` structure contains copies of the parameters used to create the window.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onctlcolor"></a>  CWnd::OnCtlColor  
 The framework calls this member function when a child control is about to be drawn.  
  
```  
Afx_msg HBRUSH OnCtlColor (CDC* pDC, CWnd* aufnehmen,  
    UINT-nCtlColor);
```  
  
### Parameters  
 `pDC`  
 Contains a pointer to the display context for the child window. May be temporary.  
  
 `pWnd`  
 Contains a pointer to the control asking for the color. May be temporary.  
  
 `nCtlColor`  
 Contains one of the following values, specifying the type of control:  
  
- **CTLCOLOR_BTN** Button control  
  
- **CTLCOLOR_DLG** Dialog box  
  
- **CTLCOLOR_EDIT** Edit control  
  
- **CTLCOLOR_LISTBOX** List-box control  
  
- **CTLCOLOR_MSGBOX** Message box  
  
- **CTLCOLOR_SCROLLBAR** Scroll-bar control  
  
- **CTLCOLOR_STATIC** Static control  
  
### Return Value  
 `OnCtlColor` must return a handle to the brush that is to be used for painting the control background.  
  
### Remarks  
 Most controls send this message to their parent (usually a dialog box) to prepare the `pDC` for drawing the control using the correct colors.  
  
 To change the text color, call the `SetTextColor` member function with the desired red, green, and blue (RGB) values.  
  
 To change the background color of a single-line edit control, set the brush handle in both the **CTLCOLOR_EDIT** and **CTLCOLOR_MSGBOX** message codes, and call the [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) function in response to the **CTLCOLOR_EDIT** code.  
  
 `OnCtlColor` will not be called for the list box of a drop-down combo box because the drop-down list box is actually a child of the combo box and not a child of the window. To change the color of the drop-down list box, create a `CComboBox` with an override of `OnCtlColor` that checks for **CTLCOLOR_LISTBOX** in the `nCtlColor` parameter. In this handler, the `SetBkColor` member function must be used to set the background color for the text.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function. To add the following method to your dialog class, use the Visual Studio properties pane to add a message handler for WM_CTLCOLOR. Alternatively, you can manually add an ON_WM_CTLCOLOR() entry to the message map.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#107](../../mfc/reference/codesnippet/cpp/cwnd-class_47.cpp)]  
  
##  <a name="ondeadchar"></a>  CWnd::OnDeadChar  
 The framework calls this member function when the [OnKeyUp](#onkeyup) member function and the [OnKeyDown](#onkeydown) member functions are called.  
  
```  
Afx_msg void OnDeadChar (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Specifies the dead-key character value.  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
### Remarks  
 This member function can be used to specify the character value of a dead key. A dead key is a key, such as the umlaut (double-dot) character, that is combined with other characters to form a composite character. For example, the umlaut-O character consists of the dead key, umlaut, and the O key.  
  
 An application typically uses `OnDeadChar` to give the user feedback about each key pressed. For example, an application can display the accent in the current character position without moving the caret.  
  
 Since there is not necessarily a one-to-one correspondence between keys pressed and `OnDeadChar` calls, the information in `nFlags` is generally not useful to applications. The information in `nFlags` applies only to the most recent call to the [OnKeyUp](#onkeyup) member function or the [OnKeyDown](#onkeydown) member function that precedes the `OnDeadChar` call.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondeleteitem"></a>  CWnd::OnDeleteItem  
 The framework calls this member function to inform the owner of an owner-draw list box or combo box that the list box or combo box is destroyed or that items have been removed by [CComboBox::DeleteString](../../mfc/reference/ccombobox-class.md#deletestring), [CListBox::DeleteString](../../mfc/reference/clistbox-class.md#deletestring), [CComboBox::ResetContent](../../mfc/reference/ccombobox-class.md#resetcontent), or [CListBox::ResetContent](../../mfc/reference/clistbox-class.md#resetcontent).  
  
```  
Afx_msg void OnDeleteItem (Int nIDCtl,  
    LPDELETEITEMSTRUCT LpDeleteItemStruct);
```  
  
### Parameters  
 `nIDCtl`  
 The identifier of the control that sent the `WM_DELETEITEM` message.  
  
 `lpDeleteItemStruct`  
 Specifies a long pointer to a [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) data structure that contains information about the deleted list box item.  
  
### Remarks  
 If the **hwndItem** member of the `DELETEITEMSTRUCT` structure belongs to a combo box or list box, then the `DeleteItem` virtual function of the appropriate class is called. Override the `DeleteItem` member function of the appropriate control's class to delete item-specific data.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondestroy"></a>  CWnd::OnDestroy  
 The framework calls this member function to inform the `CWnd` object that it is being destroyed.  
  
```  
Afx_msg void OnDestroy();
```  
  
### Remarks  
 `OnDestroy` is called after the `CWnd` object is removed from the screen.  
  
 `OnDestroy` is called first for the `CWnd` being destroyed, then for the child windows of `CWnd` as they are destroyed. It can be assumed that all child windows still exist while `OnDestroy` runs.  
  
 If the `CWnd` object being destroyed is part of the Clipboard-viewer chain (set by calling the [SetClipboardViewer](#setclipboardviewer) member function), the `CWnd` must remove itself from the Clipboard-viewer chain by calling the [ChangeClipboardChain](#changeclipboardchain) member function before returning from the `OnDestroy` function.  
  
##  <a name="ondestroyclipboard"></a>  CWnd::OnDestroyClipboard  
 The framework calls this member function for the Clipboard owner when the Clipboard is emptied through a call to the [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows function.  
  
```  
Afx_msg void OnDestroyClipboard();
```  
  
##  <a name="ondevicechange"></a>  CWnd::OnDeviceChange  
 The framework calls this member function to notify an application or device driver of a change to the hardware configuration of a device or the computer.  
  
```  
Afx_msg BOOL OnDeviceChange (nEventType UINT,  
    DWORD_PTR DwData);
```  
  
### Parameters  
 *nEventType*  
 An event type. See the Remarks section for a description of the available values  
  
 `dwData`  
 The address of a structure that contains event-specific data. Its meaning depends on the given event.  
  
### Remarks  
 For devices that offer software-controllable features, such as ejection and locking, the operating system typically sends a **DBT_DEVICEREMOVEPENDING** message to let applications and device drivers end their use of the device gracefully.  
  
 If the operating system forcefully removes of a device, it may not send a **DBT_DEVICEQUERYREMOVE** message before doing so.  
  
 The *nEvent* parameter can be one of these values:  
  
- [DBT_DEVICEARRIVAL](http://msdn.microsoft.com/library/windows/desktop/aa363205) A device has been inserted and is now available.  
  
- [DBT_DEVICEQUERYREMOVE](http://msdn.microsoft.com/library/windows/desktop/aa363206) Permission to remove a device is requested. Any application can deny this request and cancel the removal.  
  
- [DBT_DEVICEQUERYREMOVEFAILED](http://msdn.microsoft.com/library/windows/desktop/aa363207) Request to remove a device has been canceled.  
  
- [DBT_DEVICEREMOVEPENDING](http://msdn.microsoft.com/library/windows/desktop/aa363209) Device is about to be removed. Cannot be denied.  
  
- [DBT_DEVICEREMOVECOMPLETE](http://msdn.microsoft.com/library/windows/desktop/aa363208) Device has been removed.  
  
- [DBT_DEVICETYPESPECIFIC](http://msdn.microsoft.com/library/windows/desktop/aa363210) Device-specific event.  
  
- [DBT_CONFIGCHANGED](http://msdn.microsoft.com/library/windows/desktop/aa363203) Current configuration has changed.  
  
- **DBT_DEVNODES_CHANGED** Device node has changed.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondevmodechange"></a>  CWnd::OnDevModeChange  
 The framework calls this member function for all top-level `CWnd` objects when the user changes device-mode settings.  
  
```  
Afx_msg void OnDevModeChange (LPTSTR LpDeviceName);
```  
  
### Parameters  
 *lpDeviceName*  
 Points to the device name specified in the Windows initialization file, WIN.INI.  
  
### Remarks  
 Applications that handle the `WM_DEVMODECHANGE` message may reinitialize their device-mode settings. Applications that use the Windows **ExtDeviceMode** function to save and restore device settings typically do not process this function.  
  
 This function is not called when the user changes the default printer from Control Panel. In this case, the `OnWinIniChange` function is called.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondrawclipboard"></a>  CWnd::OnDrawClipboard  
 The framework calls this member function for each window in the Clipboard-viewer chain when the contents of the Clipboard change.  
  
```  
Afx_msg void OnDrawClipboard();
```  
  
### Remarks  
 Only applications that have joined the Clipboard-viewer chain by calling the [SetClipboardViewer](#setclipboardviewer) member function need to respond to this call.  
  
 Each window that receives an `OnDrawClipboard` call should call the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function to pass a [WM_DRAWCLIPBOARD](http://msdn.microsoft.com/library/windows/desktop/ms649025) message on to the next window in the Clipboard-viewer chain. The handle of the next window is returned by the [SetClipboardViewer](#setclipboardviewer) member function; it may be modified in response to an [OnChangeCbChain](#onchangecbchain) member function call.  
  
##  <a name="ondrawiconicthumbnailorlivepreview"></a>  CWnd::OnDrawIconicThumbnailOrLivePreview  
 Called by the framework when it needs to obtain a bitmap to be displayed on Windows 7 tab thumbnail, or on the client for application peek.  
  
```  
virtuelle void OnDrawIconicThumbnailOrLivePreview (CDC & dc  
    CRect-rect  
    CSize-szRequiredThumbnailSize  
    BOOL-bIsThumbnail  
    BOOL & bAlphaChannelSet);
```  
  
### Parameters  
 `dc`  
 Specifies the device context.  
  
 `rect`  
 Specifies the bounding rectangle of the area to render.  
  
 `szRequiredThumbnailSize`  
 Specifies the size of the target thumbnail. Should be ignored if `bIsThumbnail` is `FALSE`.  
  
 `bIsThumbnail`  
 Specifies whether this method is called for iconic thumbnail or live preview (peek).  
  
 `bAlphaChannelSet`  
 [out] Set it to `TRUE` if your implementation initializes the alpha channel of a bitmap selected in `dc`.  
  
### Remarks  
 Override this method in a derived class and draw on the specified device context in order to customize thumbnail and peek. If `bThumbnail` is `TRUE`, `szRequiredThumbnailSize` can be ignored. In this case you should be aware that you draw full sized bitmap (that is, a bitmap that covers the whole client area). The device context ( `dc`) comes with selected 32 bits bitmap. The default implementation sends WM_PRINT to this window with PRF_CLIENT, PRF_CHILDREN, and PRF_NONCLIENT flags.  
  
##  <a name="ondrawitem"></a>  CWnd::OnDrawItem  
 The framework calls this member function for the owner of an owner-draw button control, combo-box control, list-box control, or menu when a visual aspect of the control or menu has changed.  
  
```  
Afx_msg void OnDrawItem (Int nIDCtl,  
    LPDRAWITEMSTRUCT LpDrawItemStruct);
```  
  
### Parameters  
 `nIDCtl`  
 Contains the identifier of the control that sent the `WM_DRAWITEM` message. If a menu sent the message, `nIDCtl` contains 0.  
  
 `lpDrawItemStruct`  
 Specifies a long pointer to a `DRAWITEMSTRUCT` data structure that contains information about the item to be drawn and the type of drawing required.  
  
### Remarks  
 The **itemAction** member of the [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) structure defines the drawing operation that is to be performed. The data in this member allows the owner of the control to determine what drawing action is required.  
  
 Before returning from processing this message, an application should ensure that the device context identified by the `hDC` member of the `DRAWITEMSTRUCT` structure is restored to the default state.  
  
 If the **hwndItem** member belongs to a [CButton](../../mfc/reference/cbutton-class.md), [CMenu](../../mfc/reference/cmenu-class.md), [CListBox](../../mfc/reference/clistbox-class.md), or [CComboBox](../../mfc/reference/ccombobox-class.md) object, then the `DrawItem` virtual function of the appropriate class is called. Override the `DrawItem` member function of the appropriate control's class to draw the item.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondropfiles"></a>  CWnd::OnDropFiles  
 The framework calls this member function when the user releases the left mouse button over a window that has registered itself as the recipient of dropped files.  
  
```  
Afx_msg void OnDropFiles (HDROP hDropInfo);
```  
  
### Parameters  
 *hDropInfo*  
 A pointer to an internal data structure that describes the dropped files. This handle is used by the **DragFinish**, **DragQueryFile**, and **DragQueryPoint** Windows functions to retrieve information about the dropped files.  
  
### Remarks  
 Typically, a derived class will be designed to support dropped files and it will register itself during window construction.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onenable"></a>  CWnd::OnEnable  
 The framework calls this member function when an application changes the enabled state of the `CWnd` object.  
  
```  
Afx_msg void OnEnable (BOOL bAktivieren);
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the `CWnd` object has been enabled or disabled. This parameter is **TRUE** if the `CWnd` has been enabled; it is **FALSE** if the `CWnd` has been disabled.  
  
### Remarks  
 `OnEnable` is called before the [EnableWindow](#enablewindow) member function returns, but after the window enabled state ( [WS_DISABLED](../../mfc/reference/window-styles.md) style bit) has changed.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onendsession"></a>  CWnd::OnEndSession  
 The framework calls this member function after the `CWnd` object has returned a nonzero value from a [OnQueryEndSession](#onqueryendsession) member function call.  
  
```  
Afx_msg void OnEndSession(BOOL bEnding);
```  
  
### Parameters  
 `bEnding`  
 Specifies whether or not the session is being ended. It is **TRUE** if the session is being ended; otherwise **FALSE**.  
  
### Remarks  
 The `OnEndSession` call informs the `CWnd` object whether the session is actually ending.  
  
 If `bEnding` is **TRUE**, Windows can terminate any time after all applications have returned from processing this call. Consequently, have an application perform all tasks required for termination within `OnEndSession`.  
  
 You do not need to call the [DestroyWindow](#destroywindow) member function or [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) Windows function when the session is ending.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onenteridle"></a>  CWnd::OnEnterIdle  
 The framework calls this member function to inform an application's main window procedure that a modal dialog box or a menu is entering an idle state.  
  
```  
Afx_msg void OnEnterIdle (UINT nWhy,  
    CWnd* pWho);
```  
  
### Parameters  
 `nWhy`  
 Specifies whether the message is the result of a dialog box or a menu being displayed. This parameter can be one of the following values:  
  
- **MSGF_DIALOGBOX** The system is idle because a dialog box is being displayed.  
  
- **MSGF_MENU** The system is idle because a menu is being displayed.  
  
 *pWho*  
 Specifies a pointer to the dialog box (if `nWhy` is **MSGF_DIALOGBOX**), or the window that contains the displayed menu (if `nWhy` is **MSGF_MENU**). This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 A modal dialog box or menu enters an idle state when no messages are waiting in its queue after it has processed one or more previous messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onentermenuloop"></a>  CWnd::OnEnterMenuLoop  
 The framework calls this member function when a menu modal loop has been entered.  
  
```  
Afx_msg void OnEnterMenuLoop (BOOL bIsTrackPopupMenu);
```  
  
### Parameters  
 `bIsTrackPopupMenu`  
 Specifies whether the menu involved is a popup menu. Has a nonzero value if the function is successful; otherwise 0.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onentersizemove"></a>  CWnd::OnEnterSizeMove  
 The framework calls this member function one time after the affected window enters a moving or sizing modal loop.  
  
```  
Afx_msg void OnEnterSizeMove();
```  
  
### Remarks  
 This method receives the [WM_ENTERSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632622) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 A window enters a moving or sizing modal loop when the user clicks the window's title bar or sizing border, or when the window passes the [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) message to the [CWnd::DefWindowProc](#defwindowproc) function and the `wParam` parameter of that message specifies `SC_MOVE` or `SC_SIZE`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onerasebkgnd"></a>  CWnd::OnEraseBkgnd  
 The framework calls this member function when the `CWnd` object background needs erasing (for example, when resized).  
  
```  
Afx_msg BOOL OnEraseBkgnd(CDC* pDC);
```  
  
### Parameters  
 `pDC`  
 Specifies the device-context object.  
  
### Return Value  
 Nonzero if it erases the background; otherwise 0.  
  
### Remarks  
 It is called to prepare an invalidated region for painting.  
  
 The default implementation erases the background using the window class background brush specified by the **hbrBackground** member of the window class structure.  
  
 If the **hbrBackground** member is **NULL**, your overridden version of `OnEraseBkgnd` should erase the background color. Your version should also align the origin of the intended brush with the `CWnd` coordinates by first calling [UnrealizeObject](http://msdn.microsoft.com/library/windows/desktop/dd145164) for the brush, and then selecting the brush.  
  
 An overridden `OnEraseBkgnd` should return nonzero in response to `WM_ERASEBKGND` if it processes the message and erases the background; this indicates that no further erasing is required. If it returns 0, the window will remain marked as needing to be erased. (Typically, this means that the **fErase** member of the `PAINTSTRUCT` structure will be **TRUE**.)  
  
 Windows assumes the background is computed with the `MM_TEXT` mapping mode. If the device context is using any other mapping mode, the area erased may not be within the visible part of the client area.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onexitmenuloop"></a>  CWnd::OnExitMenuLoop  
 The framework calls this member function when a menu modal loop has been exited.  
  
```  
Afx_msg void OnExitMenuLoop (BOOL bIsTrackPopupMenu);
```  
  
### Parameters  
 `bIsTrackPopupMenu`  
 Specifies whether the menu involved is a pop-up menu. Has a nonzero value if the function is successful; otherwise 0.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onexitsizemove"></a>  CWnd::OnExitSizeMove  
 The framework calls this member function one time after the affected window exits a moving or sizing modal loop.  
  
```  
Afx_msg void OnExitSizeMove();
```  
  
### Remarks  
 This method receives the [WM_EXITSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632623) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 A window enters a moving or sizing modal loop when the user clicks the window's title bar or sizing border, or when the window passes the [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) message to the [CWnd::DefWindowProc](#defwindowproc) function and the `wParam` parameter of that message specifies `SC_MOVE` or `SC_SIZE`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onfontchange"></a>  CWnd::OnFontChange  
 All top-level windows in the system receive an `OnFontChange` call from the framework after the application changes the pool of font resources.  
  
```  
Afx_msg void OnFontChange();
```  
  
### Remarks  
 An application that adds or removes fonts from the system (for example, through the [AddFontResource](http://msdn.microsoft.com/library/windows/desktop/dd183326) or [RemoveFontResource](http://msdn.microsoft.com/library/windows/desktop/dd162922) Windows function) should send the [WM_FONTCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd145211) message to all top-level windows.  
  
 To send this message, use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with the `hWnd` parameter set to **HWND_BROADCAST**.  
  
##  <a name="ongetdlgcode"></a>  CWnd::OnGetDlgCode  
 Called for a control so the control can process arrow-key and TAB-key input itself.  
  
```  
Afx_msg UINT OnGetDlgCode();
```  
  
### Return Value  
 One or more of the following values, indicating which type of input the application processes:  
  
- **DLGC_BUTTON** Button (generic).  
  
- **DLGC_DEFPUSHBUTTON** Default pushbutton.  
  
- **DLGC_HASSETSEL EM_SETSEL** messages.  
  
- **DLGC_UNDEFPUSHBUTTON** No default pushbutton processing. (An application can use this flag with **DLGC_BUTTON** to indicate that it processes button input but relies on the system for default pushbutton processing.)  
  
- **DLGC_RADIOBUTTON** Radio button.  
  
- **DLGC_STATIC** Static control.  
  
- **DLGC_WANTALLKEYS** All keyboard input.  
  
- **DLGC_WANTARROWS** Arrow keys.  
  
- **DLGC_WANTCHARS** `WM_CHAR` messages.  
  
- **DLGC_WANTMESSAGE** All keyboard input. The application passes this message on to the control.  
  
- **DLGC_WANTTAB** TAB key.  
  
### Remarks  
 Normally, Windows handles all arrow-key and TAB-key input to a `CWnd` control. By overriding `OnGetDlgCode`, a `CWnd` control can choose a particular type of input to process itself.  
  
 The default `OnGetDlgCode` functions for the predefined control classes return a code appropriate for each class.  
  
##  <a name="ongetminmaxinfo"></a>  CWnd::OnGetMinMaxInfo  
 The framework calls this member function whenever Windows needs to know the maximized position or dimensions, or the minimum or maximum tracking size.  
  
```  
Afx_msg void OnGetMinMaxInfo (MINMAXINFO * LpMMI);
```  
  
### Parameters  
 *lpMMI*  
 Points to a `MINMAXINFO` structure that contains information about a window's maximized size and position and its minimum and maximum tracking size. For more about this structure, see the [MINMAXINFO](../../mfc/reference/minmaxinfo-structure.md) structure.  
  
### Remarks  
 The maximized size is the size of the window when its borders are fully extended. The maximum tracking size of the window is the largest window size that can be achieved by using the borders to size the window. The minimum tracking size of the window is the smallest window size that can be achieved by using the borders to size the window.  
  
 Windows fills in an array of points specifying default values for the various positions and dimensions. The application may change these values in `OnGetMinMaxInfo`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onhelp"></a>  CWnd::OnHelp  
 Handles F1 Help within the application (using the current context).  
  
```  
Afx_msg void OnHelp();
```  
  
### Remarks  
 See [CWinApp::OnHelp](../../mfc/reference/cwinapp-class.md#onhelp) for more information.  
  
##  <a name="onhelpfinder"></a>  CWnd::OnHelpFinder  
 Handles the **ID_HELP_FINDER** and **ID_DEFAULT_HELP** commands.  
  
```  
Afx_msg void OnHelpFinder();
```  
  
### Remarks  
 See [CWinApp::OnHelpFinder](../../mfc/reference/cwinapp-class.md#onhelpfinder) for more information.  
  
##  <a name="onhelpindex"></a>  CWnd::OnHelpIndex  
 Handles the **ID_HELP_INDEX** command and provides a default Help topic.  
  
```  
Afx_msg void OnHelpIndex();
```  
  
### Remarks  
 See [CWinApp::OnHelpIndex](../../mfc/reference/cwinapp-class.md#onhelpindex) for more information.  
  
##  <a name="onhelpinfo"></a>  CWnd::OnHelpInfo  
 Called by the framework when the user presses the F1 key.  
  
```  
Afx_msg BOOL OnHelpInfo(HELPINFO* lpHelpInfo);
```  
  
### Parameters  
 *lpHelpInfo*  
 Pointer to a [HELPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773313) structure that contains information about the menu item, control, dialog box, or window for which help is requested.  
  
### Return Value  
 Returns TRUE if a window has the keyboard focus or if a menu is active within a window. If no window has the keyboard focus, returns FALSE.  
  
### Remarks  
 If a menu is active when F1 is pressed, **WM_HELP** is sent to the window associated with the menu; otherwise, **WM_HELP** is sent to the window that has the keyboard focus. If no window has the keyboard focus, **WM_HELP** is sent to the currently active window.  
  
##  <a name="onhelpusing"></a>  CWnd::OnHelpUsing  
 Handles the **ID_HELP_USING** command.  
  
```  
Afx_msg void OnHelpUsing();
```  
  
### Remarks  
 See [CWinApp::OnHelpUsing](../../mfc/reference/cwinapp-class.md#onhelpusing) for more information.  
  
##  <a name="onhotkey"></a>  CWnd::OnHotKey  
 The framework calls this member function when the user presses a system-wide hot key.  
  
```  
Afx_msg void OnHotKey (nHotKeyId UINT,   
    UINT-nKey1   
    UINT-nKey2);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHotKeyId`|Identifier for the hot key that generated the message. If the message was generated by a system-defined hot key, this parameter will be one of the following values:<br /><br /> - `IDHOT_SNAPDESKTOP` - The snap desktop hot key was pressed.<br />- `IDHOT_SNAPWINDOW` - The snap window hot key was pressed.|  
|[in] `nKey1`|A bitwise combination (OR) of flags that indicate the keys that were pressed in combination with the key specified by the `nKey2` parameter. The possible values are:<br /><br /> - `MOD_ALT` - Either ALT key was held down.<br />- `MOD_CONTROL` - Either CTRL key was held down.<br />- `MOD_SHIFT` - Either SHIFT key was held down.<br />- `MOD_WIN` - Either WINDOWS key was held down. These keys are labeled with the Microsoft Windows logo.|  
|[in] `nKey2`|The virtual key code of the hot key.|  
  
### Remarks  
 This method receives the [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is placed at the top of the message queue associated with the thread that registered the hot key. Use the [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) function to register a system-wide hot key.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onhscroll"></a>  CWnd::OnHScroll  
 The framework calls this member function when the user clicks a window's horizontal scroll bar.  
  
```  
Afx_msg void OnHScroll (UINT nSBCode,  
    UINT-nPos  
    CScrollBar* pScrollBar);
```  
  
### Parameters  
 `nSBCode`  
 Specifies a scroll-bar code that indicates the user's scrolling request. This parameter can be one of the following:  
  
- **SB_LEFT** Scroll to far left.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINELEFT** Scroll left.  
  
- **SB_LINERIGHT** Scroll right.  
  
- **SB_PAGELEFT** Scroll one page left.  
  
- **SB_PAGERIGHT** Scroll one page right.  
  
- **SB_RIGHT** Scroll to far right.  
  
- **SB_THUMBPOSITION** Scroll to absolute position. The current position is specified by the `nPos` parameter.  
  
- **SB_THUMBTRACK** Drag scroll box to specified position. The current position is specified by the `nPos` parameter.  
  
 `nPos`  
 Specifies the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION** or **SB_THUMBTRACK**; otherwise, not used. Depending on the initial scroll range, `nPos` may be negative and should be cast to an `int` if necessary.  
  
 `pScrollBar`  
 If the scroll message came from a scroll-bar control, contains a pointer to the control. If the user clicked a window's scroll bar, this parameter is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The **SB_THUMBTRACK** scroll-bar code typically is used by applications that give some feedback while the scroll box is being dragged.  
  
 If an application scrolls the contents controlled by the scroll bar, it must also reset the position of the scroll box with the [SetScrollPos](#setscrollpos) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#108](../../mfc/reference/codesnippet/cpp/cwnd-class_48.cpp)]  
  
##  <a name="onhscrollclipboard"></a>  CWnd::OnHScrollClipboard  
 The Clipboard owner's `OnHScrollClipboard` member function is called by the Clipboard viewer when the Clipboard data has the `CF_OWNERDISPLAY` format and there is an event in the Clipboard viewer's horizontal scroll bar.  
  
```  
Afx_msg void OnHScrollClipboard (CWnd * pClipAppWnd,  
    UINT-nSBCode  
    UINT nPos);
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to a Clipboard-viewer window. The pointer may be temporary and should not be stored for later use.  
  
 `nSBCode`  
 Specifies one of the following scroll-bar codes in the low-order word:  
  
- **SB_BOTTOM** Scroll to lower right.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to upper left.  
  
 `nPos`  
 Contains the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION**; otherwise not used.  
  
### Remarks  
 The owner should scroll the Clipboard image, invalidate the appropriate section, and update the scroll-bar values.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oniconerasebkgnd"></a>  CWnd::OnIconEraseBkgnd  
 The framework calls this member function for a minimized (iconic) `CWnd` object when the background of the icon must be filled before painting the icon.  
  
```  
Afx_msg void OnIconEraseBkgnd (CDC * pDC);
```  
  
### Parameters  
 `pDC`  
 Specifies the device-context object of the icon. May be temporary and should not be stored for later use.  
  
### Remarks  
 `CWnd` receives this call only if a class icon is defined for the window default implementation; otherwise [OnEraseBkgnd](#onerasebkgnd) is called.  
  
 The [DefWindowProc](#defwindowproc) member function fills the icon background with the background brush of the parent window.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninitmenu"></a>  CWnd::OnInitMenu  
 The framework calls this member function when a menu is about to become active.  
  
```  
Afx_msg void OnInitMenu (CMenu * pMenu);
```  
  
### Parameters  
 `pMenu`  
 Specifies the menu to be initialized. May be temporary and should not be stored for later use.  
  
### Remarks  
 `OnInitMenu` is called when the user clicks an item on the menu bar or presses a menu key. Override this member function to modify the menu before it is displayed.  
  
 `OnInitMenu` is only called once, when a menu is first accessed (for example, when a user clicks an item on the menu bar). This method does not provide information about menu items. As the user moves to items within the menu (for example, by moving the mouse across several menu items) the function is not called again. Once the user exits from the menu (for example, by clicking on the application client area) and later clicks an item on the menu bar, the function will be called again.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninitmenupopup"></a>  CWnd::OnInitMenuPopup  
 The framework calls this member function when a pop-up menu is about to become active.  
  
```  
Afx_msg void OnInitMenuPopup (CMenu * pPopupMenu,  
    UINT-nIndex  
    BOOL bSysMenu);
```  
  
### Parameters  
 *pPopupMenu*  
 Specifies the menu object of the pop-up menu. May be temporary and should not be stored for later use.  
  
 `nIndex`  
 Specifies the index of the pop-up menu in the main menu.  
  
 *bSysMenu*  
 **TRUE** if the pop-up menu is the Control menu; otherwise **FALSE**.  
  
### Remarks  
 This allows an application to modify the pop-up menu before it is displayed without changing the entire menu.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputdevicechange"></a>  CWnd::OnInputDeviceChange  
 The framework calls this member function when an I/O device is added or removed from the system.  
  
```  
Afx_msg void OnInputDeviceChange (unsigned short uFlag);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `uFlag`|This flag can contain the following values:<br /><br /> - `GIDC_ARRIVAL` - A new device has been added to the system.<br />- `GIDC_REMOVAL` - A device has been removed from the system.|  
  
### Remarks  
 This method receives the [WM_INPUT_DEVICE_CHANGE](http://msdn.microsoft.com/library/windows/desktop/ms645591) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The is a generic input device message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputlangchange"></a>  CWnd::OnInputLangChange  
 The framework calls this member for the topmost affected window after an application's input language has been changed.  
  
```  
Afx_msg void OnInputLangChange (UINT nCharSet,   
    UINT-nLocaleId);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nCharSet`|The character set of the new locale. For more information, see the `lfCharSet` parameter of the [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.|  
|[in] `nLocaleId`|The input locale identifier. For more information, see [Language Identifier Constants and Strings](http://msdn.microsoft.com/library/windows/desktop/dd318693).|  
  
### Remarks  
 This method receives the [WM_INPUTLANGCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms632629) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputlangchangerequest"></a>  CWnd::OnInputLangChangeRequest  
 The framework calls this member for window with the focus when the user chooses a new input language.  
  
```  
Afx_msg void OnInputLangChangeRequest (UINT nFlags,   
    UINT-nLocaleId);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise (OR) combination of flags that indicate the new locale was selected from the previous or next locale in the installed list of locales, or that the new input locale's keyboard layout can be used with the system character set.<br /><br /> The possible values are `INPUTLANGCHANGE_BACKWARD`, `INPUTLANGCHANGE_FORWARD`, and `INPUTLANGCHANGE_SYSCHARSET`.|  
|[in] `nLocaleId`|The input locale identifier. For more information, see [Language Identifier Constants and Strings](http://msdn.microsoft.com/library/windows/desktop/dd318693).|  
  
### Remarks  
 This method receives the [WM_INPUTLANGCHANGEREQUEST](http://msdn.microsoft.com/library/windows/desktop/ms632630) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted when the user chooses a new input language with either a hotkey that is specified in the keyboard control panel application, or from the indicator on the system taskbar.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkeydown"></a>  CWnd::OnKeyDown  
 The framework calls this member function when a nonsystem key is pressed.  
  
```  
Afx_msg void OnKeyDown (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the given key. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value).|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For a `WM_KEYDOWN` message, the key-transition bit (bit 15) is 0 and the context-code bit (bit 13) is 0.  
  
### Remarks  
 A nonsystem key is a keyboard key that is pressed when the ALT key is not pressed or a keyboard key that is pressed when `CWnd` has the input focus.  
  
 Because of auto-repeat, more than one `OnKeyDown` call may occur before an [OnKeyUp](#onkeyup) member function call is made. The bit that indicates the previous key state can be used to determine whether the `OnKeyDown` call is the first down transition or a repeated down transition.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkeyup"></a>  CWnd::OnKeyUp  
 The framework calls this member function when a nonsystem key is released.  
  
```  
Afx_msg void OnKeyUp (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the given key. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For a `WM_KEYUP` message, the key-transition bit (bit 15) is 1 and the context-code bit (bit 13) is 0.  
  
### Remarks  
 A nonsystem key is a keyboard key that is pressed when the ALT key is not pressed or a keyboard key that is pressed when the `CWnd` has the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkillfocus"></a>  CWnd::OnKillFocus  
 The framework calls this member function immediately before losing the input focus.  
  
```  
Afx_msg void OnKillFocus (CWnd * pNewWnd);
```  
  
### Parameters  
 *pNewWnd*  
 Specifies a pointer to the window that receives the input focus (may be **NULL** or may be temporary).  
  
### Remarks  
 If the `CWnd` object is displaying a caret, the caret should be destroyed at this point.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttondblclk"></a>  CWnd::OnLButtonDblClk  
 The framework calls this member function when the user double-clicks the left mouse button.  
  
```  
Afx_msg void OnLButtonDblClk (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style will receive `OnLButtonDblClk` calls. This is the default for Microsoft Foundation Class windows. Windows calls `OnLButtonDblClk` when the user presses, releases, and then presses the left mouse button again within the system's double-click time limit. Double-clicking the left mouse button actually generates four events: [WM_LBUTTONDOWN](#onlbuttondown), [WM_LBUTTONUP](#onlbuttonup) messages, the `WM_LBUTTONDBLCLK` call, and another `WM_LBUTTONUP` message when the button is released.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttondown"></a>  CWnd::OnLButtonDown  
 The framework calls this member function when the user presses the left mouse button.  
  
```  
Afx_msg void OnLButtonDown (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttonup"></a>  CWnd::OnLButtonUp  
 The framework calls this member function when the user releases the left mouse button.  
  
```  
Afx_msg void OnLButtonUp (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttondblclk"></a>  CWnd::OnMButtonDblClk  
 The framework calls this member function when the user double-clicks the middle mouse button.  
  
```  
Afx_msg void OnMButtonDblClk (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style will receive `OnMButtonDblClk` calls. This is the default for all Microsoft Foundation Class windows. Windows generates an `OnMButtonDblClk` call when the user presses, releases, and then presses the middle mouse button again within the system's double-click time limit. Double-clicking the middle mouse button actually generates four events: [WM_MBUTTONDOWN](#onmbuttondown) and [WM_MBUTTONUP](#onmbuttonup) messages, the `WM_MBUTTONDBLCLK` call, and another `WM_MBUTTONUP` message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttondown"></a>  CWnd::OnMButtonDown  
 The framework calls this member function when the user presses the middle mouse button.  
  
```  
Afx_msg void OnMButtonDown (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttonup"></a>  CWnd::OnMButtonUp  
 The framework calls this member function when the user releases the middle mouse button.  
  
```  
Afx_msg void OnMButtonUp (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmdiactivate"></a>  CWnd::OnMDIActivate  
 The framework calls this member function for the child window being deactivated and the child window being activated.  
  
```  
Afx_msg void OnMDIActivate (BOOL bActivate,  
    CWnd* pActivateWnd CWnd* pDeactivateWnd);
```  
  
### Parameters  
 `bActivate`  
 **TRUE** if the child is being activated and **FALSE** if it is being deactivated.  
  
 `pActivateWnd`  
 Contains a pointer to the MDI child window to be activated. When received by an MDI child window, `pActivateWnd` contains a pointer to the child window being activated. This pointer may be temporary and should not be stored for later use.  
  
 *pDeactivateWnd*  
 Contains a pointer to the MDI child window being deactivated. This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 An MDI child window is activated independently of the MDI frame window. When the frame becomes active, the child window that was last activated with a `OnMDIActivate` call receives an [WM_NCACTIVATE](#onncactivate) message to draw an active window frame and caption bar, but it does not receive another `OnMDIActivate` call.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmeasureitem"></a>  CWnd::OnMeasureItem  
 The framework calls this member function by the framework for the owner of an owner-draw button, combo box, list box, or menu item when the control is created.  
  
```  
Afx_msg void OnMeasureItem (Int nIDCtl, LPMEASUREITEMSTRUCT LpMeasureItemStruct);
```  
  
### Parameters  
 `nIDCtl`  
 The ID of the control.  
  
 `lpMeasureItemStruct`  
 Points to a [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) data structure that contains the dimensions of the owner-draw control.  
  
### Remarks  
 Override this member function and fill in the `MEASUREITEMSTRUCT` data structure pointed to by `lpMeasureItemStruct` and return; this informs Windows of the dimensions of the control and allows Windows to process user interaction with the control correctly.  
  
 If a list box or combo box is created with the [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) or [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) style, the framework calls this function for the owner for each item in the control; otherwise this function is called once.  
  
 Windows initiates the call to `OnMeasureItem` for the owner of combo boxes and list boxes created with the **OWNERDRAWFIXED** style before sending the [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) message. As a result, when the owner receives this call, Windows has not yet determined the height and width of the font used in the control; function calls and calculations that require these values should occur in the main function of the application or library.  
  
 If the item being measured is a `CMenu`, `CListBox` or `CComboBox` object, then the `MeasureItem` virtual function of the appropriate class is called. Override the `MeasureItem` member function of the appropriate control's class to calculate and set the size of each item.  
  
 `OnMeasureItem` will be called only if the control's class is created at run time, or it is created with the **LBS_OWNERDRAWVARIABLE** or **CBS_OWNERDRAWVARIABLE** style. If the control is created by the dialog editor, `OnMeasureItem` will not be called. This is because the [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) message is sent early in the creation process of the control. If you subclass by using `DDX_Control`, `SubclassDlgItem`, or `SubclassWindow`, the subclassing usually occurs after the creation process. Therefore, there is no way to handle the [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) message in the control's `OnChildNotify` function, which is the mechanism MFC uses to implement **ON_WM_MEASUREITEM_REFLECT**.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenuchar"></a>  CWnd::OnMenuChar  
 The framework calls this member function when the user presses a menu mnemonic character that doesn't match any of the predefined mnemonics in the current menu.  
  
```  
Afx_msg LRESULT OnMenuChar (UINT nChar,  
    UINT-nFlags  
    CMenu* pMenu);
```  
  
### Parameters  
 `nChar`  
 Depending on the build settings, specifies the ANSI or Unicode character that the user pressed.  
  
 `nFlags`  
 Contains the **MF_POPUP** flag if the menu is a pop-up menu. It contains the **MF_SYSMENU** flag if the menu is a Control menu.  
  
 `pMenu`  
 Contains a pointer to the selected `CMenu`. The pointer may be temporary and should not be stored.  
  
### Return Value  
 The high-order word of the return value should contain one of the following command codes:  
  
|Value|Description|  
|-----------|-----------------|  
|0|Tells Windows to discard the character that the user pressed and creates a short beep on the system speaker.|  
|1|Tells Windows to close the current menu.|  
|2|Informs Windows that the low-order word of the return value contains the item number for a specific item. This item is selected by Windows.|  
  
 The low-order word is ignored if the high-order word contains 0 or 1. Applications should process this message when accelerator (shortcut) keys are used to select bitmaps placed in a menu.  
  
### Remarks  
 It is sent to the `CWnd` that owns the menu. `OnMenuChar` is also called when the user presses ALT and any other key, even if the key does not correspond to a mnemonic character. In this case, `pMenu` points to the menu owned by the `CWnd`, and `nFlags` is 0.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenudrag"></a>  CWnd::OnMenuDrag  
 The framework calls this member function of the current drag-and-drop menu when the user begins to drag a menu item.  
  
```  
Afx_msg UINT OnMenuDrag (UINT nPos,   
    CMenu* pMenu);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPos`|The index position of the menu item when the drag operation begins.|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that contains the menu item.|  
  
### Return Value  
  
|Return Value|Meaning|  
|------------------|-------------|  
|`MND_CONTINUE`|The menu should remain active. If the mouse is released, it should be ignored.|  
|`MND_ENDMENU`|The menu should be ended.|  
  
### Remarks  
 This method receives the [WM_MENUDRAG](http://msdn.microsoft.com/library/windows/desktop/ms647606) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenugetobject"></a>  CWnd::OnMenuGetObject  
 The framework calls this member function of the current drag-and-drop menu when the mouse cursor enters a menu item or moves from the center of the item to the top or bottom of the item.  
  
```  
Afx_msg UINT OnMenuGetObject(MENUGETOBJECTINFO* pMenuGetObjectInfo);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pMenu`|Pointer to a [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572) structure that contains information about the drag-and-drop menu the mouse cursor is on.|  
  
### Return Value  
  
|Return Value|Meaning|  
|------------------|-------------|  
|`MNGO_NOERROR`|An interface pointer that supports drop-and-drag operations is returned in the `pvObj` member of the [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572) structure. Currently, only the [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) interface is supported.|  
|`MNGO_NOINTERFACE`|No drop-and-drag interface is supported.|  
  
### Remarks  
 This method receives the [WM_MENUGETOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms647607) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenurbuttonup"></a>  CWnd::OnMenuRButtonUp  
 The framework calls this member function when the user releases the right mouse button while the cursor is on a menu item.  
  
```  
Afx_msg void OnMenuRButtonUp (UINT nPos,  
    CMenu* pMenu);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPos`|The index position of the menu item when the right mouse button was released.|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that contains the menu item.|  
  
### Remarks  
 This method receives the [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610) message enables an application to provide a context-sensitive menu for the menu item specified in the message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenuselect"></a>  CWnd::OnMenuSelect  
 If the `CWnd` object is associated with a menu, `OnMenuSelect` is called by the framework when the user selects a menu item.  
  
```  
Afx_msg void OnMenuSelect (UINT nItemID,  
    UINT-nFlags  
    HMENU hSysMenu);
```  
  
### Parameters  
 `nItemID`  
 Identifies the item selected. If the selected item is a menu item, `nItemID` contains the menu-item ID. If the selected item contains a pop-up menu, `nItemID` contains the pop-up menu index, and *hSysMenu* contains the handle of the main (clicked-on) menu.  
  
 `nFlags`  
 Contains a combination of the following menu flags:  
  
- **MF_BITMAP** Item is a bitmap.  
  
- **MF_CHECKED** Item is checked.  
  
- **MF_DISABLED** Item is disabled.  
  
- **MF_GRAYED** Item is dimmed.  
  
- **MF_MOUSESELECT** Item was selected with a mouse.  
  
- `MF_OWNERDRAW` Item is an owner-draw item.  
  
- **MF_POPUP** Item contains a pop-up menu.  
  
- **MF_SEPARATOR** Item is a menu-item separator.  
  
- **MF_SYSMENU** Item is contained in the Control menu.  
  
 `hSysMenu`  
 If `nFlags` contains **MF_SYSMENU**, identifies the menu associated with the message. If `nFlags` contains **MF_POPUP**, identifies the handle of the main menu. If `nFlags` contains neither **MF_SYSMENU** nor **MF_POPUP**, it is unused.  
  
### Remarks  
 If `nFlags` contains 0xFFFF and `hSysMenu` contains 0, Windows has closed the menu because the user pressed the ESC key or clicked outside the menu.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmouseactivate"></a>  CWnd::OnMouseActivate  
 The framework calls this member function when the cursor is in an inactive window and the user presses a mouse button.  
  
```  
Afx_msg Int OnMouseActivate (CWnd * pDesktopWnd  
    UINT-nHitTest  
    UINT Message);
```  
  
### Parameters  
 *pDesktopWnd*  
 Specifies a pointer to the top-level parent window of the window being activated. The pointer may be temporary and should not be stored.  
  
 `nHitTest`  
 Specifies the [hit-test](#onnchittest) area code. A hit test is a test that determines the location of the cursor.  
  
 `message`  
 Specifies the mouse message number.  
  
### Return Value  
 Specifies whether to activate the `CWnd` and whether to discard the mouse event. It must be one of the following values:  
  
- **MA_ACTIVATE** Activate `CWnd` object.  
  
- **MA_NOACTIVATE** Do not activate `CWnd` object.  
  
- **MA_ACTIVATEANDEAT** Activate `CWnd` object and discard the mouse event.  
  
- **MA_NOACTIVATEANDEAT** Do not activate `CWnd` object and discard the mouse event.  
  
### Remarks  
 The default implementation passes this message to the parent window before any processing occurs. If the parent window returns **TRUE**, processing is halted.  
  
 For a description of the individual hit-test area codes, see the [OnNcHitTest](#onnchittest) member function  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCAxCtl#9](../../mfc/reference/codesnippet/cpp/cwnd-class_49.cpp)]  
  
##  <a name="onmousehover"></a>  CWnd::OnMouseHover  
 The framework calls this member function when the cursor hovers over the client area of the window for the period of time specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
Afx_msg void OnMouseHover (nFlags UINT,   
    Zeigen Sie CPoint);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_MOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645613) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousehwheel"></a>  CWnd::OnMouseHWheel  
 The framework calls this member when the current window is composed by the Desktop Window Manager (DWM), and that window is maximized.  
  
```  
Afx_msg void OnMouseHWheel (nFlags UINT,   
    kurze zDelta   
    CPoint pt);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.<br /><br /> For a list of flags, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
|[in] `zDelta`|Indicates the distance the wheel is rotated, expressed in multiples or divisions of `WHEEL_DELTA`, which is 120. A positive value indicates that the wheel was rotated to the right; a negative value indicates that the wheel was rotated to the left.|  
|[in] `pt`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_MOUSEHWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645614) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is sent to the window that has the focus when the mouse's horizontal scroll wheel is tilted or rotated.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmouseleave"></a>  CWnd::OnMouseLeave  
 The framework calls this member function when the cursor leaves the client area of the window specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
Afx_msg void OnMouseLeave();
```  
  
### Remarks  
 This method receives the [WM_MOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645615) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousemove"></a>  CWnd::OnMouseMove  
 The framework calls this member function when the mouse cursor moves.  
  
```  
Afx_msg void OnMouseMove (nFlags UINT,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 If the mouse is not captured, the `WM_MOUSEMOVE` message is received by the `CWnd` object beneath the mouse cursor; otherwise, the message goes to the window that has captured the mouse.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousewheel"></a>  CWnd::OnMouseWheel  
 The framework calls this member function as a user rotates the mouse wheel and encounters the wheel's next notch.  
  
```  
Afx_msg BOOL OnMouseWheel (nFlags UINT,  
    kurze zDelta  
    CPoint pt);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `zDelta`  
 Indicates distance rotated. The `zDelta` value is expressed in multiples or divisions of **WHEEL_DELTA**, which is 120. A value less than zero indicates rotating back (toward the user) while a value greater than zero indicates rotating forward (away from the user). The user can reverse this response by changing the Wheel setting in the mouse software. See the Remarks for more information about this parameter.  
  
 `pt`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the screen.  
  
### Return Value  
 Nonzero if mouse wheel scrolling is enabled; otherwise 0.  
  
### Remarks  
 Unless overridden, `OnMouseWheel` calls the default of [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617). Windows automatically routes the message to the control or child window that has the focus. The Win32 function [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) propagates the message up the parent chain to the window that processes it.  
  
 The `zDelta` parameter is a multiple of **WHEEL_DELTA**, which is set at 120. This value is the threshold for an action to be taken, and one such action (for example, scrolling forward one notch) should occur for each delta.  
  
 **WHEEL_DELTA** was set to 120 to allow for finer-resolution wheels, such as a freely-rotating wheel with no notches. A finer-resolution wheel sends more messages per rotation, but each message has a smaller delta value. To use such a wheel, either add the incoming `zDelta` values until **WHEEL_DELTA** is reached (so that you get the same response for a given delta-rotation), or scroll partial lines in response to the more frequent messages. You can also choose a scroll granularity and accumulate deltas until **WHEEL_DELTA** is reached.  
  
 Override this member function to provide your own mouse-wheel scrolling behavior.  
  
> [!NOTE]
> `OnMouseWheel` handles messages for Windows NT 4.0 and later versions. For Windows 95/98 or Windows NT 3.51 message handling, use [OnRegisteredMouseWheel](#onregisteredmousewheel).  
  
##  <a name="onmove"></a>  CWnd::OnMove  
 The framework calls this member function after the `CWnd` object has been moved.  
  
```  
Afx_msg void OnMove (Int X,  
    Int y);
```  
  
### Parameters  
 *x*  
 Specifies the new x-coordinate location of the upper-left corner of the client area. This new location is given in screen coordinates for overlapped and pop-up windows, and parent-client coordinates for child windows.  
  
 *y*  
 Specifies the new y-coordinate location of the upper-left corner of the client area. This new location is given in screen coordinates for overlapped and pop-up windows, and parent-client coordinates for child windows.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmoving"></a>  CWnd::OnMoving  
 The framework calls this member function while a user is moving a `CWnd` object.  
  
```  
Afx_msg void OnMoving (UINT-n,  
    LPRECT-LpRect);
```  
  
### Parameters  
 `nSide`  
 The edge of window to be moved.  
  
 `lpRect`  
 Address of the [CRect](../../atl-mfc-shared/reference/crect-class.md) or [RECT structure](../../mfc/reference/rect-structure1.md) that will contain the item's coordinates.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncactivate"></a>  CWnd::OnNcActivate  
 The framework calls this member function when the nonclient area needs to be changed to indicate an active or inactive state.  
  
```  
Afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### Parameters  
 `bActive`  
 Specifies when a caption bar or icon needs to be changed to indicate an active or inactive state. The `bActive` parameter is **TRUE** if an active caption or icon is to be drawn. It is **FALSE** for an inactive caption or icon.  
  
### Return Value  
 Nonzero if Windows should proceed with default processing; 0 to prevent the caption bar or icon from being deactivated.  
  
### Remarks  
 The default implementation draws the title bar and title-bar text in their active colors if `bActive` is **TRUE** and in their inactive colors if `bActive` is **FALSE**.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnccalcsize"></a>  CWnd::OnNcCalcSize  
 The framework calls this member function when the size and position of the client area needs to be calculated.  
  
```  
Afx_msg void OnNcCalcSize (BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS* Lpncsp);
```  
  
### Parameters  
 `bCalcValidRects`  
 Specifies whether the application should specify which part of the client area contains valid information. Windows will copy the valid information to the specified area within the new client area. If this parameter is **TRUE**, the application should specify which part of the client area is valid.  
  
 `lpncsp`  
 Points to a [NCCALCSIZE_PARAMS](../../mfc/reference/nccalcsize-params-structure.md) data structure that contains information an application can use to calculate the new size and position of the `CWnd` rectangle (including client area, borders, caption, scroll bars, and so on).  
  
### Remarks  
 By processing this message, an application can control the contents of the window's client area when the size or position of the window changes.  
  
 Regardless of the value of `bCalcValidRects`, the first rectangle in the array specified by the **rgrc** structure member of the `NCCALCSIZE_PARAMS` structure contains the coordinates of the window. For a child window, the coordinates are relative to the parent window's client area. For top-level windows, the coordinates are screen coordinates. An application should modify the **rgrc[0]** rectangle to reflect the size and position of the client area.  
  
 The **rgrc[1]** and **rgrc[2]** rectangles are valid only if `bCalcValidRects` is **TRUE**. In this case, the **rgrc[1]** rectangle contains the coordinates of the window before it was moved or resized. The **rgrc[2]** rectangle contains the coordinates of the window's client area before the window was moved. All coordinates are relative to the parent window or screen.  
  
 The default implementation calculates the size of the client area based on the window characteristics (presence of scroll bars, menu, and so on), and places the result in `lpncsp`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnccreate"></a>  CWnd::OnNcCreate  
 The framework calls this member function prior to the [WM_CREATE](#oncreate) message when the `CWnd` object is first created.  
  
```  
Afx_msg BOOL OnNcCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### Parameters  
 `lpCreateStruct`  
 Points to the [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) data structure for `CWnd`.  
  
### Return Value  
 Nonzero if the nonclient area is created. It is 0 if an error occurs; the **Create** function will return **failure** in this case.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncdestroy"></a>  CWnd::OnNcDestroy  
 Called by the framework when the nonclient area is being destroyed, and is the last member function called when the Windows window is destroyed.  
  
```  
Afx_msg void OnNcDestroy();
```  
  
### Remarks  
 The default implementation performs some cleanup, then calls the virtual member function [PostNcDestroy](#postncdestroy).  
  
 Override `PostNcDestroy` if you want to perform your own cleanup, such as a **delete this** operation. If you override `OnNcDestroy`, you must call `OnNcDestroy` in your base class to ensure that any memory internally allocated for the window is freed.  
  
##  <a name="onnchittest"></a>  CWnd::OnNcHitTest  
 The framework calls this member function for the `CWnd` object that contains the cursor (or the `CWnd` object that used the [SetCapture](#setcapture) member function to capture the mouse input) every time the mouse is moved.  
  
```  
Afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### Parameters  
 `point`  
 Contains the x- and y-coordinates of the cursor. These coordinates are always screen coordinates.  
  
### Return Value  
 One of the mouse hit-test enumerated values listed below.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttondblclk"></a>  CWnd::OnNcLButtonDblClk  
 The framework calls this member function when the user double-clicks the left mouse button while the cursor is within a nonclient area of `CWnd`.  
  
```  
Afx_msg void OnNcLButtonDblClk (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) message is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttondown"></a>  CWnd::OnNcLButtonDown  
 The framework calls this member function when the user presses the left mouse button while the cursor is within a nonclient area of the `CWnd` object.  
  
```  
Afx_msg void OnNcLButtonDown (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received.If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttonup"></a>  CWnd::OnNcLButtonUp  
 The framework calls this member function when the user releases the left mouse button while the cursor is within a nonclient area.  
  
```  
Afx_msg void OnNcLButtonUp (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, [WM_SYSCOMMAND](#onsyscommand) is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttondblclk"></a>  CWnd::OnNcMButtonDblClk  
 The framework calls this member function when the user double-clicks the middle mouse button while the cursor is within a nonclient area.  
  
```  
Afx_msg void OnNcMButtonDblClk (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttondown"></a>  CWnd::OnNcMButtonDown  
 The framework calls this member function when the user presses the middle mouse button while the cursor is within a nonclient area.  
  
```  
Afx_msg void OnNcMButtonDown (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttonup"></a>  CWnd::OnNcMButtonUp  
 The framework calls this member function when the user releases the middle mouse button while the cursor is within a nonclient area.  
  
```  
Afx_msg void OnNcMButtonUp (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmousehover"></a>  CWnd::OnNcMouseHover  
 The framework calls this member function when the cursor hovers over the nonclient area of the window for the period of time specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
Afx_msg void OnNcMouseHover (UINT nHitTest,   
    Zeigen Sie CPoint);  
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCMOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645625) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmouseleave"></a>  CWnd::OnNcMouseLeave  
 The framework calls this member function when the cursor leaves the nonclient area of the window specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
Afx_msg void OnNcMouseLeave();
```  
  
### Remarks  
 This method receives the [WM_NCMOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645626) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmousemove"></a>  CWnd::OnNcMouseMove  
 The framework calls this member function when the cursor is moved within a nonclient area.  
  
```  
Afx_msg void OnNcMouseMove (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) message is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncpaint"></a>  CWnd::OnNcPaint  
 The framework calls this member function when the nonclient area needs to be painted.  
  
```  
Afx_msg void OnNcPaint();
```  
  
### Remarks  
 The default implementation paints the window frame.  
  
 An application can override this call and paint its own custom window frame. The clipping region is always rectangular, even if the shape of the frame is altered.  
  
##  <a name="onncrbuttondblclk"></a>  CWnd::OnNcRButtonDblClk  
 The framework calls this member function when the user double-clicks the right mouse button while the cursor is within a nonclient area of `CWnd`.  
  
```  
Afx_msg void OnNcRButtonDblClk (nHitTest UINT,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrbuttondown"></a>  CWnd::OnNcRButtonDown  
 The framework calls this member function when the user presses the right mouse button while the cursor is within a nonclient area.  
  
```  
Afx_msg void OnNcRButtonDown (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrbuttonup"></a>  CWnd::OnNcRButtonUp  
 The framework calls this member function when the user releases the right mouse button while the cursor is within a nonclient area.  
  
```  
Afx_msg void OnNcRButtonUp (UINT nHitTest,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrenderingchanged"></a>  CWnd::OnNcRenderingChanged  
 The framework calls this member when the rendering policy for the nonclient area has changed.  
  
```  
Afx_msg void OnNcRenderingChanged (BOOL bIsRendering);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `bIsRendering`|`true` if Desktop Window Manager (DWM) rendering is enabled for the nonclient area of the window; `false` if rendering is disabled.|  
  
### Remarks  
 This method receives the [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388200) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttondblclk"></a>  CWnd::OnNcXButtonDblClk  
 The framework calls this member function when the user double-clicks XBUTTON1 or XBUTTON2 while the cursor is in the nonclient area of a window.  
  
```  
void OnNcXButtonDblClk (kurze nHitTest,   
    UINT-nButton   
    Zeigen Sie CPoint);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button is double-clicked, or `XBUTTON2` if the second X button is double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttondown"></a>  CWnd::OnNcXButtonDown  
 The framework calls this member function when the user presses XBUTTON1 or XBUTTON2 of the mouse while the cursor is in the nonclient area of a window.  
  
```  
Afx_msg void OnNcXButtonDown (kurze nHitTest,   
    UINT-nButton   
    Zeigen Sie CPoint);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first mouse X button is pressed, or `XBUTTON2` if the second X button is pressed.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCXBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645632) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttonup"></a>  CWnd::OnNcXButtonUp  
 The framework calls this member function when the user releases XBUTTON1 or XBUTTON2 of the mouse while the cursor is in the nonclient area of a window.  
  
```  
Afx_msg void OnNcXButtonUp (kurze nHitTest,   
    UINT-nButton   
    Zeigen Sie CPoint);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first mouse X button is released, or `XBUTTON2` if the second X button is released.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCXBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646240) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnextmenu"></a>  CWnd::OnNextMenu  
 The framework calls this member function when when the right or left arrow key is used to switch between the menu bar and the system menu.  
  
```  
Afx_msg void OnNextMenu (UINT nKey,  
    LPMDINEXTMENU LpMdiNextMenu);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nKey`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.<br /><br /> For a list of flags, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
|[in] `lpMdiNextMenu`|Pointer to a [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561) structure that contains information about the menu to be activated.|  
  
### Remarks  
 This method receives the [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In response to this message, your application can set the `hmenuNext` member of the [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561) structure to specify the menu to switch to, and the `hwndNext` member to specify the window to receive menu notification messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnotify"></a>  CWnd::OnNotify  
 The framework calls this member function to inform the parent window of a control that an event has occurred in the control or that the control requires some kind of information.  
  
```  
virtuelle BOOL OnNotify (wParam WPARAM-Parameter  
    LPARAM lParam  
    LRESULT* pResult);
```  
  
### Parameters  
 `wParam`  
 Identifies the control that sends the message if the message is from a control. Otherwise, `wParam` is 0.  
  
 `lParam`  
 Pointer to a notification message ( **NMHDR**) structure that contains the notification code and additional information. For some notification messages, this parameter points to a larger structure that has the **NMHDR** structure as its first member.  
  
 `pResult`  
 Pointer to an **LRESULT** variable in which to store the result code if the message is handled.  
  
### Return Value  
 An application returns nonzero if it processes this message; otherwise 0.  
  
### Remarks  
 `OnNotify` processes the message map for control notification.  
  
 Override this member function in your derived class to handle the **WM_NOTIFY** message. An override will not process the message map unless the base class `OnNotify` is called.  
  
 For more information on the WM_NOTIFY message, see Technical Note 61 (TN061), [ON_NOTIFY and WM_NOTIFY messages](../../mfc/tn061-on-notify-and-wm-notify-messages.md). You may also be interested the related topics described in [Control Topics](../../mfc/controls-mfc.md), and TN062, [Message Reflection for Windows Controls](../../mfc/tn062-message-reflection-for-windows-controls.md).  
  
##  <a name="onnotifyformat"></a>  CWnd::OnNotifyFormat  
 The framework calls this member function to determine if the current window accepts ANSI or Unicode structures in the WM_NOTIFY notification message.  
  
```  
Afx_msg UINT OnNotifyFormat (CWnd * aufnehmen,   
    UINT-%nbefehl);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pWnd`|A pointer to a `CWnd` object that represents the window sending the [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) message.<br /><br /> This parameter is the pointer to a control if the `nCommand` parameter is `NF_QUERY`, or the pointer to the parent window of a control if `nCommand` is `NF_REQUERY`.|  
|[in] `nCommand`|A command value that specializes the **WM_NOTIFY** message. The possible values are:<br /><br /> - `NF_QUERY` -<br />     The message is a query to determine whether ANSI or Unicode structures should be used in **WM_NOTIFY** messages. This message is sent from a control to its parent window during the creation of a control, and in response to the `NF_REQUERY` form of this message.<br />- `NF_REQUERY` -<br />     The message is a request for a control to send the `NF_QUERY` form of this message to its parent window. This request is sent from the parent window, and asks the control to requery the parent about the type of structure to use in **WM_NOTIFY** messages. If the `nCommand` parameter is `NF_REQUERY`, the return value is the result of the requery operation.|  
  
### Return Value  
  
|Return value|Meaning|  
|------------------|-------------|  
|`NFR_ANSI`|ANSI structures should be used in **WM_NOTIFY** messages sent by the control.|  
|`NFR_UNICODE`|Unicode structures should be used in **WM_NOTIFY** messages sent by the control.|  
|0|An error occurred.|  
  
### Remarks  
 This method receives the [WM_NOTIFYFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb775584) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. **WM_NOTIFY** messages are sent from a common control to its parent window, and from the parent window to the common control.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpaint"></a>  CWnd::OnPaint  
 The framework calls this member function when Windows or an application makes a request to repaint a portion of an application's window.  
  
```  
Afx_msg void OnPaint()-Methode;
```  
  
### Remarks  
 The [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145137) message is sent when the [UpdateWindow](#updatewindow) or [RedrawWindow](#redrawwindow) member function is called.  
  
 A window may receive internal paint messages as a result of calling the `RedrawWindow` member function with the **RDW_INTERNALPAINT** flag set. In this case, the window may not have an update region. An application should call the [GetUpdateRect](#getupdaterect) member function to determine whether the window has an update region. If `GetUpdateRect` returns 0, the application should not call the [BeginPaint](#beginpaint) and [EndPaint](#endpaint) member functions.  
  
 It is an application's responsibility to check for any necessary internal repainting or updating by looking at its internal data structures for each `WM_PAINT` message because a `WM_PAINT` message may have been caused by both an invalid area and a call to the `RedrawWindow` member function with the **RDW_INTERNALPAINT** flag set.  
  
 An internal `WM_PAINT` message is sent only once by Windows. After an internal `WM_PAINT` message is sent to a window by the `UpdateWindow` member function, no further `WM_PAINT` messages will be sent or posted until the window is invalidated or until the `RedrawWindow` member function is called again with the **RDW_INTERNALPAINT** flag set.  
  
 For information on rendering an image in document/view applications, see [CView::OnDraw](../../mfc/reference/cview-class.md#ondraw).  
  
 For more information about using **WM_Paint**, see the following topics in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:  
  
- [The WM_PAINT Message](http://msdn.microsoft.com/library/windows/desktop/dd145137)  
  
- [Using the WM_PAINT Message](http://msdn.microsoft.com/library/windows/desktop/dd145193)  
  
##  <a name="onpaintclipboard"></a>  CWnd::OnPaintClipboard  
 A Clipboard owner's `OnPaintClipboard` member function is called by a Clipboard viewer when the Clipboard owner has placed data on the Clipboard in the `CF_OWNERDISPLAY` format and the Clipboard viewer's client area needs repainting.  
  
```  
Afx_msg void OnPaintClipboard (CWnd * pClipAppWnd,  
    HGLOBAL hPaintStruct);
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to the Clipboard-application window. The pointer may be temporary and should not be stored for later use.  
  
 *hPaintStruct*  
 Identifies a [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) data structure that defines what part of the client area to paint.  
  
### Remarks  
 To determine whether the entire client area or just a portion of it needs repainting, the Clipboard owner must compare the dimensions of the drawing area given in the **rcpaint** member of the `PAINTSTRUCT` structure to the dimensions given in the most recent [OnSizeClipboard](#onsizeclipboard) member function call.  
  
 `OnPaintClipboard` should use the [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) Windows function to lock the memory that contains the `PAINTSTRUCT` data structure and unlock that memory with the [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows function before it exits.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpalettechanged"></a>  CWnd::OnPaletteChanged  
 The framework calls this member function for all top-level windows after the window with input focus has realized its logical palette, thereby changing the system palette.  
  
```  
Afx_msg void OnPaletteChanged (CWnd * pFocusWnd);
```  
  
### Parameters  
 `pFocusWnd`  
 Specifies a pointer to the window that caused the system palette to change. The pointer may be temporary and should not be stored.  
  
### Remarks  
 This call allows a window without the input focus that uses a color palette to realize its logical palettes and update its client area.  
  
 The `OnPaletteChanged` member function is called for all top-level and overlapped windows, including the one that changed the system palette and caused the `WM_PALETTECHANGED` message to be sent. If any child window uses a color palette, this message must be passed on to it.  
  
 To avoid an infinite loop, the window shouldn't realize its palette unless it determines that `pFocusWnd` does not contain a pointer to itself.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpaletteischanging"></a>  CWnd::OnPaletteIsChanging  
 The framework calls this member function to inform applications that an application is going to realize its logical palette.  
  
```  
Afx_msg void OnPaletteIsChanging (CWnd * pRealizeWnd);
```  
  
### Parameters  
 *pRealizeWnd*  
 Specifies the window that is about to realize its logical palette.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onparentnotify"></a>  CWnd::OnParentNotify  
 A parent's `OnParentNotify` member function is called by the framework when its child window is created or destroyed, or when the user clicks a mouse button while the cursor is over the child window.  
  
```  
Afx_msg void OnParentNotify (UINT-Nachricht,  
    LPARAM lParam);
```  
  
### Parameters  
 `message`  
 Specifies the event for which the parent is being notified and the identifier of the child window. The event is the low-order word of `message`. If the event is `WM_CREATE` or `WM_DESTROY`, the high-order word of `message` is the identifier of the child window; otherwise, the high-order word is undefined. The event (low-order word of `message`) can be any of these values:  
  
- `WM_CREATE` The child window is being created.  
  
- `WM_DESTROY` The child window is being destroyed.  
  
- `WM_LBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the left mouse button.  
  
- `WM_MBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the middle mouse button.  
  
- `WM_RBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the right mouse button.  
  
 `lParam`  
 If the event (low-order word) of `message` is `WM_CREATE` or `WM_DESTROY`, `lParam` specifies the window handle of the child window; otherwise `lParam` contains the x and y coordinates of the cursor. The x coordinate is in the low-order word and the y coordinate is in the high-order word.  
  
### Remarks  
 When the child window is being created, the system calls `OnParentNotify` just before the [Create](#create) member function that creates the window returns. When the child window is being destroyed, the system calls `OnParentNotify` before any processing takes place to destroy the window.  
  
 `OnParentNotify` is called for all ancestor windows of the child window, including the top-level window.  
  
 All child windows except those that have the [WS_EX_NOPARENTNOTIFY](../../mfc/reference/extended-window-styles.md) style send this message to their parent windows. By default, child windows in a dialog box have the **WS_EX_NOPARENTNOTIFY** style unless the child window was created without this style by calling the [CreateEx](#createex) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpowerbroadcast"></a>  CWnd::OnPowerBroadcast  
 The framework calls this member function when a power-management event occurs.  
  
```  
Afx_msg UINT OnPowerBroadcast (UINT nPowerEvent,   
    UINT-nEventData);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPowerEvent`|The power-management event.|  
|[in] `nEventData`|Event-specific data.|  
  
### Return Value  
 If the event is a request, return `true` to grant the request, or `BROADCAST_QUERY_DENY` to deny the request.  
  
### Remarks  
 This method receives the [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nPowerEvent` parameter specifies events such as battery power is low, the power status has changed, permission to suspend operation is requested or denied, an operation is resuming automatically after an event, the system is suspending operation, or an operation is resuming after suspension. The `nEventData` parameter is typically not used. For more information, see the `wParam` and `lParam` parameters of the [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onquerydragicon"></a>  CWnd::OnQueryDragIcon  
 The framework calls this member function by a minimized (iconic) window that does not have an icon defined for its class.  
  
```  
Afx_msg folgende OnQueryDragIcon();
```  
  
### Return Value  
 A doubleword value that contains a cursor or icon handle in the low-order word. The cursor or icon must be compatible with the display driver's resolution. If the application returns **NULL**, the system displays the default cursor. The default return value is **NULL**.  
  
### Remarks  
 The system makes this call to obtain the cursor to display while the user drags the minimized window. If an application returns the handle of an icon or cursor, the system converts it to black-and-white. If an application returns a handle, the handle must identify a monochrome cursor or icon compatible with the display driver's resolution. The application can call the [CWinApp::LoadCursor](../../mfc/reference/cwinapp-class.md#loadcursor) or [CWinApp::LoadIcon](../../mfc/reference/cwinapp-class.md#loadicon) member functions to load a cursor or icon from the resources in its executable file and to obtain this handle.  
  
##  <a name="onqueryendsession"></a>  CWnd::OnQueryEndSession  
 The framework calls this member function when the user chooses to end the Windows session or when an application calls the [ExitWindows](http://msdn.microsoft.com/library/windows/desktop/aa376867) Windows function.  
  
```  
Afx_msg BOOL OnQueryEndSession();
```  
  
### Return Value  
 Nonzero if an application can be conveniently shut down; otherwise 0.  
  
### Remarks  
 If any application returns 0, the Windows session is not ended. Windows stops calling `OnQueryEndSession` as soon as one application returns 0 and sends the [WM_ENDSESSION](#onendsession) message with a parameter value of **FALSE** for any application that has already returned nonzero.  
  
##  <a name="onquerynewpalette"></a>  CWnd::OnQueryNewPalette  
 The framework calls this member function when the `CWnd` object is about to receive the input focus, giving the `CWnd` an opportunity to realize its logical palette when it receives the focus.  
  
```  
Afx_msg BOOL OnQueryNewPalette();
```  
  
### Return Value  
 Nonzero if the `CWnd` realizes its logical palette; otherwise 0.  
  
##  <a name="onqueryopen"></a>  CWnd::OnQueryOpen  
 The framework calls this member function when the `CWnd` object is minimized and the user requests that the `CWnd` be restored to its preminimized size and position.  
  
```  
Afx_msg BOOL OnQueryOpen();
```  
  
### Return Value  
 Nonzero if the icon can be opened, or 0 to prevent the icon from being opened.  
  
### Remarks  
 While in `OnQueryOpen`, `CWnd` should not perform any action that would cause an activation or focus change (for example, creating a dialog box).  
  
##  <a name="onqueryuistate"></a>  CWnd::OnQueryUIState  
 Called to retrieve the user interface (UI) state for a window.  
  
```  
Afx_msg UINT OnQueryUIState();
```  
  
### Return Value  
 The return value is **NULL** if the focus indicators and the keyboard accelerators are visible. Otherwise, the return value can be one or more of the following values:  
  
- **UISF_HIDEFOCUS** Focus indicators are hidden.  
  
- **UISF_HIDEACCEL** Keyboard accelerators are hidden.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_QUERYUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646355) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onrawinput"></a>  CWnd::OnRawInput  
 The framework calls this member function when the current window gets raw input.  
  
```  
Afx_msg void OnRawInput (UINT nInputCode,  
    HRAWINPUT hRawInput);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nInputCode`|Input code that indicates whether the input occurred while the application was in the foreground or not. In either case, the application must call [CWnd::DefWindowProc](#defwindowproc) so the system can perform cleanup.<br /><br /> This parameter can be one of the following values:<br /><br /> - `RIM_INPUT` - Input occurred while the application was in the foreground.<br />- `RIM_INPUTSINK` - Input occurred while the application was not in the foreground.|  
|[in] `hRawInput`|Handle to a [RAWINPUT](http://msdn.microsoft.com/library/windows/desktop/ms645562) structure that contains the raw input from the device.|  
  
### Remarks  
 This method receives the [WM_INPUT](http://msdn.microsoft.com/library/windows/desktop/ms646275) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttondblclk"></a>  CWnd::OnRButtonDblClk  
 The framework calls this member function when the user double-clicks the right mouse button.  
  
```  
Afx_msg void OnRButtonDblClk (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_RBUTTON** Set if right mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style can receive `OnRButtonDblClk` calls. This is the default for windows within the Microsoft Foundation Class Library. Windows calls `OnRButtonDblClk` when the user presses, releases, and then again presses the right mouse button within the system's double-click time limit. Double-clicking the right mouse button actually generates four events: [WM_RBUTTONDOWN](#onrbuttondown) and [WM_RBUTTONUP](#onrbuttonup) messages, the `OnRButtonDblClk` call, and another `WM_RBUTTONUP` message when the button is released.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttondown"></a>  CWnd::OnRButtonDown  
 The framework calls this member function when the user presses the right mouse button.  
  
```  
Afx_msg void OnRButtonDown (UINT nFlags,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_RBUTTON** Set if right mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttonup"></a>  CWnd::OnRButtonUp  
 The framework calls this member function when the user releases the right mouse button.  
  
```  
Afx_msg void OnRButtonUp (nFlags UINT,  
    Zeigen Sie CPoint);
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onregisteredmousewheel"></a>  CWnd::OnRegisteredMouseWheel  
 The framework calls this member function as a user rotates the mouse wheel and encounters the wheel's next notch.  
  
```  
Afx_msg LRESULT OnRegisteredMouseWheel (wParam WPARAM-Parameter  
    LPARAM lParam);
```  
  
### Parameters  
 `wParam`  
 Horizontal position of the pointer.  
  
 `lParam`  
 Vertical position of the pointer.  
  
### Return Value  
 Insignificant at this time. Always zero.  
  
### Remarks  
 Unless overridden, `OnRegisteredMouseWheel` routes the message to the appropriate window (the parent window with focus), and calls the [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617) handler for that window.  
  
 Override this member function to provide your own message routing or to alter the mouse-wheel scrolling behavior.  
  
> [!NOTE]
> `OnRegisteredMouseWheel` handles messages for Windows 95/98 and Windows NT 3.51. For Windows NT 4.0 message handling, use [OnMouseWheel](#onmousewheel).  
  
##  <a name="onrenderallformats"></a>  CWnd::OnRenderAllFormats  
 The Clipboard owner's `OnRenderAllFormats` member function is called by the framework when the owner application is being destroyed.  
  
```  
Afx_msg void OnRenderAllFormats();
```  
  
### Remarks  
 The Clipboard owner should render the data in all the formats it is capable of generating and pass a data handle for each format to the Clipboard by calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function. This ensures that the Clipboard contains valid data even though the application that rendered the data is destroyed. The application should call the [OpenClipboard](#openclipboard) member function before calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function and call the [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windows function afterward.  
  
##  <a name="onrenderformat"></a>  CWnd::OnRenderFormat  
 The Clipboard owner's `OnRenderFormat` member function is called by the framework when a particular format with delayed rendering needs to be rendered.  
  
```  
Afx_msg void OnRenderFormat (UINT nFormat);
```  
  
### Parameters  
 `nFormat`  
 Specifies the Clipboard format.  
  
### Remarks  
 The receiver should render the data in that format and pass it to the Clipboard by calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function.  
  
 Do not call the `OpenClipboard` member function or the **CloseClipboard** Windows function from within `OnRenderFormat`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsessionchange"></a>  CWnd::OnSessionChange  
 The framework calls this member function to notify an application of a change in session state.  
  
```  
Afx_msg void OnSessionChange (nSessionState UINT,   
    UINT-nId);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nSessionState`|A status code describes the session state change.|  
|[in] `nId`|A session identifier.|  
  
### Remarks  
 This method receives the [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nSessionState` parameter specifies that a session is connected or disconnected from the console or a remote terminal, a user logged on or off, a session is locked or unlocked, or a session has changed to remote-controlled status. For more information, see the `wParam` parameter of the the [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828) message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsetcursor"></a>  CWnd::OnSetCursor  
 The framework calls this member function if mouse input is not captured and the mouse causes cursor movement within the `CWnd` object.  
  
```  
Afx_msg BOOL OnSetCursor (CWnd * aufnehmen,  
    UINT-nHitTest  
    UINT Message);
```  
  
### Parameters  
 `pWnd`  
 Specifies a pointer to the window that contains the cursor. The pointer may be temporary and should not be stored for later use.  
  
 `nHitTest`  
 Specifies the [hit-test](#onnchittest) area code. The hit test determines the cursor's location.  
  
 `message`  
 Specifies the mouse message number.  
  
### Return Value  
 Nonzero to halt further processing, or 0 to continue.  
  
### Remarks  
 The default implementation calls the parent window's `OnSetCursor` before processing. If the parent window returns **TRUE**, further processing is halted. Calling the parent window gives the parent window control over the cursor's setting in a child window.  
  
 The default implementation sets the cursor to an arrow if it is not in the client area or to the registered-class cursor if it is.  
  
 If `nHitTest` is **HTERROR** and `message` is a mouse button-down message, the **MessageBeep** member function is called.  
  
 The `message` parameter is 0 when `CWnd` enters menu mode.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsetfocus"></a>  CWnd::OnSetFocus  
 The framework calls this member function after gaining the input focus.  
  
```  
Afx_msg void OnSetFocus (CWnd * pOldWnd);
```  
  
### Parameters  
 *pOldWnd*  
 Contains the `CWnd` object that loses the input focus (may be **NULL**). The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 To display a caret, `CWnd` should call the appropriate caret functions at this point.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsettingchange"></a>  CWnd::OnSettingChange  
 The framework calls `OnSettingChange` for all top-level windows when the Win32 SystemParametersInfo function changes a system-wide setting.  
  
```  
Afx_msg void OnSettingChange (UINT uFlags,  
    LPCTSTR LpszSection);
```  
  
### Parameters  
 `uFlags`  
 When the system sends the message as a result of a **SystemParametersInfo** call, this parameter is a flag that indicates the system parameter that was changed. For a list of values, see [SystemParametersInfo](http://msdn.microsoft.com/library/windows/desktop/ms724947) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. When an application sends the message, this parameter must be 0.  
  
 `lpszSection`  
 Points to a string that specifies the name of the section that has changed. (The string does not include the square brackets that enclose the section name.)  
  
### Remarks  
 An application should send the message to all top-level windows when it makes changes to system parameters, and Windows will send the message if the user changes settings via the Control Panel.  
  
 The **ON_WM_SETTINGCHANGE** message is similar to the **ON_WM_WININICHANGE** message, with the following difference:  
  
-   Use **ON_WM_SETTINGCHANGE** when running Windows NT 4.0 or newer, or under Windows 95/98.  
  
-   Use **ON_WININICHANGE** when running Windows NT 3.51 or older. This message is now obsolete.  
  
 You should have only one of these macros in your message map. To write a program that works for both Windows 95/98 and Windows NT 4.0, write a handler for **ON_WM_SETTINGCHANGE**. Under Windows NT 3.51, your handler will be called by `OnSettingChange` and `uFlags` and will always be zero.  
  
##  <a name="onshowwindow"></a>  CWnd::OnShowWindow  
 The framework calls this member function when the `CWnd` object is about to be hidden or shown.  
  
```  
Afx_msg void OnShowWindow (BOOL bShow,  
    UINT-nStatus);
```  
  
### Parameters  
 `bShow`  
 Specifies whether a window is being shown. It is **TRUE** if the window is being shown; it is **FALSE** if the window is being hidden.  
  
 `nStatus`  
 Specifies the status of the window being shown. It is 0 if the message is sent because of a `ShowWindow` member function call; otherwise `nStatus` is one of the following:  
  
- **SW_PARENTCLOSING** Parent window is closing (being made iconic) or a pop-up window is being hidden.  
  
- **SW_PARENTOPENING** Parent window is opening (being displayed) or a pop-up window is being shown.  
  
### Remarks  
 A window is hidden or shown when the `ShowWindow` member function is called, when an overlapped window is maximized or restored, or when an overlapped or pop-up window is closed (made iconic) or opened (displayed on the screen). When an overlapped window is closed, all pop-up windows associated with that window are hidden.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsize"></a>  CWnd::OnSize  
 The framework calls this member function after the window's size has changed.  
  
```  
Afx_msg void OnSize (UINT %nbenachrichtigungen,  
    Int-cx  
    Int cy);
```  
  
### Parameters  
 `nType`  
 Specifies the type of resizing requested. This parameter can be one of the following values:  
  
- **SIZE_MAXIMIZED** Window has been maximized.  
  
- **SIZE_MINIMIZED** Window has been minimized.  
  
- **SIZE_RESTORED** Window has been resized, but neither **SIZE_MINIMIZED** nor **SIZE_MAXIMIZED** applies.  
  
- **SIZE_MAXHIDE** Message is sent to all pop-up windows when some other window is maximized.  
  
- **SIZE_MAXSHOW** Message is sent to all pop-up windows when some other window has been restored to its former size.  
  
 `cx`  
 Specifies the new width of the client area.  
  
 `cy`  
 Specifies the new height of the client area.  
  
### Remarks  
 If the [SetScrollPos](#setscrollpos) or [MoveWindow](#movewindow) member function is called for a child window from `OnSize`, the `bRedraw` parameter of `SetScrollPos` or `MoveWindow` should be nonzero to cause the `CWnd` to be repainted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#109](../../mfc/reference/codesnippet/cpp/cwnd-class_50.cpp)]  
  
##  <a name="onsizeclipboard"></a>  CWnd::OnSizeClipboard  
 The Clipboard owner's `OnSizeClipboard` member function is called by the Clipboard viewer when the Clipboard contains data with the `CF_OWNERDISPLAY` attribute and the size of the client area of the Clipboard-viewer window has changed.  
  
```  
Afx_msg void OnSizeClipboard (CWnd * pClipAppWnd,  
    HGLOBAL hRect);
```  
  
### Parameters  
 `pClipAppWnd`  
 Identifies the Clipboard-application window. The pointer may be temporary and should not be stored.  
  
 *hRect*  
 Identifies a global memory object. The memory object contains a RECT data structure that specifies the area for the Clipboard owner to paint.  
  
### Remarks  
 The `OnSizeClipboard` member function is called with a null rectangle (0,0,0,0) as the new size when the Clipboard application is about to be destroyed or minimized. This permits the Clipboard owner to free its display resources.  
  
 Within `OnSizeClipboard`, an application must use the [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) Windows function to lock the memory that contains the RECT data structure. Have the application unlock that memory with the [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows function before it yields or returns control.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsizing"></a>  CWnd::OnSizing  
 The framework calls this member function to indicate that the user is resizing the rectangle.  
  
```  
Afx_msg void OnSizing (UINT-n,  
    LPRECT-LpRect);
```  
  
### Parameters  
 `nSide`  
 The edge of window to be moved.  
  
 `lpRect`  
 Address of the [CRect](../../atl-mfc-shared/reference/crect-class.md) or [RECT structure](../../mfc/reference/rect-structure1.md) that will contain the item's coordinates.  
  
### Remarks  
 By processing this message, an application can monitor the size and position of the drag rectangle and, if needed, change its size or position.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#110](../../mfc/reference/codesnippet/cpp/cwnd-class_51.cpp)]  
  
##  <a name="onspoolerstatus"></a>  CWnd::OnSpoolerStatus  
 The framework calls this member function from Print Manager whenever a job is added to or removed from the Print Manager queue.  
  
```  
Afx_msg void OnSpoolerStatus (UINT nStatus,  
    UINT-nJobs);
```  
  
### Parameters  
 `nStatus`  
 Specifies the **SP_JOBSTATUS** flag.  
  
 *nJobs*  
 Specifies the number of jobs remaining in the Print Manager queue.  
  
### Remarks  
 This call is for informational purposes only.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onstylechanged"></a>  CWnd::OnStyleChanged  
 The framework calls this member function after the [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) function has changed one or more of the window's styles.  
  
```  
Afx_msg void OnStyleChanged (Int nStyleType,  
    LPSTYLESTRUCT LpStyleStruct);
```  
  
### Parameters  
 `nStyleType`  
 Specifies whether the window's extended or nonextended styles have changed. This parameter can be a combination of the following values:  
  
- **GWL_EXSTYLE** The window's extended styles have changed.  
  
- **GWL_STYLE** The window's nonextended styles have changed.  
  
 `lpStyleStruct`  
 Points to a [STYLESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632607) structure that contains the new styles for the window. An application can examine the styles, but it can not change them.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onstylechanging"></a>  CWnd::OnStyleChanging  
 The framework calls this member function when the [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) function is about to change one or more of the window's styles.  
  
```  
Afx_msg void OnStyleChanging (Int nStyleType,  
    LPSTYLESTRUCT LpStyleStruct);
```  
  
### Parameters  
 `nStyleType`  
 Specifies whether the window's extended or nonextended styles have changed. This parameter can be a combination of the following values:  
  
- **GWL_EXSTYLE** The window's extended styles have changed.  
  
- **GWL_STYLE** The window's nonextended styles have changed.  
  
 `lpStyleStruct`  
 Points to a [STYLESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632607) structure that contains the new styles for the window. An application can examine the styles and change them.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyschar"></a>  CWnd::OnSysChar  
 The framework calls this member function if `CWnd` has the input focus and the [WM_SYSKEYUP](#onsyskeyup) and [WM_SYSKEYDOWN](#onsyskeydown) messages are translated.  
  
```  
Afx_msg void OnSysChar (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Specifies the ASCII-character key code of a Control-menu key.  
  
 `nRepCnt`  
 Specifies the repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 The `nFlags` parameter can have these values:  
  
|Value|Meaning|  
|-----------|-------------|  
|0-15|Specifies the repeat count. The value is the number of times the keystroke is repeated as a result of the user holding down the key..|  
|16-23|Specifies the scan code. The value depends on the original equipment manufacturer (OEM)|  
|24|Specifies whether the key is an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101- or 102-key keyboard. The value is 1 if it is an extended key; otherwise, it is 0.|  
|25-28|Used internally by Windows.|  
|29|Specifies the context code. The value is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.|  
|30|Specifies the previous key state. The value is 1 if the key is down before the message is sent, or it is 0 if the key is up.|  
|31|Specifies the transition state. The value is 1 if the key is being released, or it is 0 if the key is being pressed.|  
  
### Remarks  
 It specifies the virtual key code of the Control-menu key. (For a list of of standard virtual key codes, see Winuser.h)  
  
 When the context code is 0, `WM_SYSCHAR` can pass the [WM_SYSCHAR](http://msdn.microsoft.com/library/windows/desktop/ms646357) message to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system character-key. This allows accelerator keys to be used with the active window even if the active window does not have the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyscolorchange"></a>  CWnd::OnSysColorChange  
 The framework calls this member function for all top-level windows when a change is made in the system color setting.  
  
```  
Afx_msg void OnSysColorChange();
```  
  
### Remarks  
 Windows calls `OnSysColorChange` for any window that is affected by a system color change.  
  
 Applications that have brushes that use the existing system colors should delete those brushes and re-create them with the new system colors.  
  
##  <a name="onsyscommand"></a>  CWnd::OnSysCommand  
 The framework calls this member function when the user selects a command from the Control menu, or when the user selects the Maximize or the Minimize button.  
  
```  
Afx_msg void OnSysCommand (UINT nID  
    LPARAM lParam);
```  
  
### Parameters  
 `nID`  
 Specifies the type of system command requested. This parameter can be any one of the following values:  
  
- **SC_CLOSE** Close the `CWnd` object.  
  
- **SC_HOTKEY** Activate the `CWnd` object associated with the application-specified hot key. The low-order word of `lParam` identifies the `HWND` of the window to activate.  
  
- **SC_HSCROLL** Scroll horizontally.  
  
- **SC_KEYMENU** Retrieve a menu through a keystroke.  
  
- **SC_MAXIMIZE** (or **SC_ZOOM**)   Maximize the `CWnd` object.  
  
- **SC_MINIMIZE** (or **SC_ICON**)   Minimize the `CWnd` object.  
  
- **SC_MOUSEMENU** Retrieve a menu through a mouse click.  
  
- **SC_MOVE** Move the `CWnd` object.  
  
- **SC_NEXTWINDOW** Move to the next window.  
  
- **SC_PREVWINDOW** Move to the previous window.  
  
- **SC_RESTORE** Restore window to normal position and size.  
  
- **SC_SCREENSAVE** Executes the screen-saver application specified in the [boot] section of the SYSTEM.INI file.  
  
- **SC_SIZE** Size the `CWnd` object.  
  
- **SC_TASKLIST** Execute or activate the Windows Task Manager application.  
  
- **SC_VSCROLL** Scroll vertically.  
  
 `lParam`  
 If a Control-menu command is chosen with the mouse, `lParam` contains the cursor coordinates. The low-order word contains the x coordinate, and the high-order word contains the y coordinate. Otherwise this parameter is not used.  
  
- **SC_HOTKEY** Activate the window associated with the application-specified hot key. The low-order word of `lParam` identifies the window to activate.  
  
- **SC_SCREENSAVE** Execute the screen-save application specified in the Desktop section of Control Panel.  
  
### Remarks  
 By default, `OnSysCommand` carries out the Control-menu request for the predefined actions specified in the preceding table.  
  
 In `WM_SYSCOMMAND` messages, the four low-order bits of the `nID` parameter are used internally by Windows. When an application tests the value of `nID`, it must combine the value 0xFFF0 with the `nID` value by using the bitwise-AND operator to obtain the correct result.  
  
 The menu items in a Control menu can be modified with the `GetSystemMenu`, `AppendMenu`, `InsertMenu`, and `ModifyMenu` member functions. Applications that modify the Control menu must process `WM_SYSCOMMAND` messages, and any `WM_SYSCOMMAND` messages not handled by the application must be passed on to `OnSysCommand`. Any command values added by an application must be processed by the application and cannot be passed to `OnSysCommand`.  
  
 An application can carry out any system command at any time by passing a `WM_SYSCOMMAND` message to `OnSysCommand`.  
  
 Accelerator (shortcut) keystrokes that are defined to select items from the Control menu are translated into `OnSysCommand` calls; all other accelerator keystrokes are translated into [WM_COMMAND](#oncommand) messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsysdeadchar"></a>  CWnd::OnSysDeadChar  
 The framework calls this member function if the `CWnd` object has the input focus when the [OnSysKeyUp](#onsyskeyup) or [OnSysKeyDown](#onsyskeydown) member function is called.  
  
```  
Afx_msg void OnSysDeadChar (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Specifies the dead-key character value.  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
### Remarks  
 It specifies the character value of a dead key.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyskeydown"></a>  CWnd::OnSysKeyDown  
 If the `CWnd` object has the input focus, the `OnSysKeyDown` member function is called by the framework when the user holds down the ALT key and then presses another key.  
  
```  
Afx_msg void OnSysKeyDown (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the key being pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed, 0 otherwise).|  
|14|Previous key state (1 if the key is down before the message is sent, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For `OnSysKeyDown` calls, the key-transition bit (bit 15) is 0. The context-code bit (bit 13) is 1 if the ALT key is down while the key is pressed; it is 0 if the message is sent to the active window because no window has the input focus.  
  
### Remarks  
 If no window currently has the input focus, the active window's `OnSysKeyDown` member function is called. The `CWnd` object that receives the message can distinguish between these two contexts by checking the context code in `nFlags`.  
  
 When the context code is 0, the `WM_SYSKEYDOWN` message received by `OnSysKeyDown` can be passed to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system-key message. This allows accelerator keys to be used with the active window even if the active window does not have the input focus.  
  
 Because of auto-repeat, more than one `OnSysKeyDown` call may occur before the [WM_SYSKEYUP](#onsyskeyup) message is received. The previous key state (bit 14) can be used to determine whether the `OnSysKeyDown` call indicates the first down transition or a repeated down transition.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyskeyup"></a>  CWnd::OnSysKeyUp  
 If the `CWnd` object has the focus, the `OnSysKeyUp` member function is called by the framework when the user releases a key that was pressed while the ALT key was held down.  
  
```  
Afx_msg void OnSysKeyUp (UINT nChar,  
    UINT-nRepCnt  
    UINT-nFlags);
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the key being pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed, 0 otherwise).|  
|14|Previous key state (1 if the key is down before the message is sent, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For `OnSysKeyUp` calls, the key-transition bit (bit 15) is 1. The context-code bit (bit 13) is 1 if the ALT key is down while the key is pressed; it is 0 if the message is sent to the active window because no window has the input focus.  
  
### Remarks  
 If no window currently has the input focus, the active window's `OnSysKeyUp` member function is called. The `CWnd` object that receives the call can distinguish between these two contexts by checking the context code in `nFlags`.  
  
 When the context code is 0, the `WM_SYSKEYUP` message received by `OnSysKeyUp` can be passed to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system-key message. This allows accelerator (shortcut) keys to be used with the active window even if the active window does not have the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
 For non-U.S. Enhanced 102-key keyboards, the right ALT key is handled as the CTRL+ALT key combination. The following shows the sequence of messages and calls that result when the user presses and releases this key:  
  
|Sequence|Function Accessed|Message Passed|  
|--------------|-----------------------|--------------------|  
|1.|[WM_KEYDOWN](#onkeydown)|**VK_CONTROL**|  
|2.|[WM_KEYDOWN](#onkeydown)|**VK_MENU**|  
|3.|[WM_KEYUP](#onkeyup)|**VK_CONTROL**|  
|4.|[WM_SYSKEYUP](http://msdn.microsoft.com/library/windows/desktop/ms646287)|**VK_MENU**|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ontcard"></a>  CWnd::OnTCard  
 The framework calls this member function when the user clicks an authorable button.  
  
```  
Afx_msg void OnTCard (UINT IdAction,  
    DWORD-DwActionData);
```  
  
### Parameters  
 `idAction`  
 Indicates the action the user has taken. This parameter can be one of these values:  
  
- **IDABORT** The user clicked an authorable Abort button.  
  
- **IDCANCEL** The user clicked an authorable Cancel button.  
  
- **IDCLOSE** The user closed the training card.  
  
- **IDHELP** The user clicked an authorable Windows Help button.  
  
- **IDIGNORE** The user clicked an authorable Ignore button.  
  
- **IDOK** The user clicked an authorable OK button.  
  
- **IDNO** The user clicked an authorable No button.  
  
- **IDRETRY** The user clicked an authorable Retry button.  
  
- **HELP_TCARD_DATA** The user clicked an authorable button. The `dwActionData` parameter contains a long integer specified by the help author.  
  
- **HELP_TCARD_NEXT** The user clicked an authorable Next button.  
  
- **HELP_TCARD_OTHER_CALLER** Another application has requested training cards.  
  
- **IDYES** The user clicked an authorable Yes button.  
  
 `dwActionData`  
 If `idAction` specifies **HELP_TCARD_DATA**, this parameter is a long integer specified by the help author. Otherwise, this parameter is zero.  
  
### Remarks  
 This function is called only when an application has initiated a training card with Windows Help. An application initiates a training card by specifying the **HELP_TCARD** command in a call to the [WinHelp](../../mfc/reference/cwinapp-class.md#winhelp) function.  
  
##  <a name="ontimechange"></a>  CWnd::OnTimeChange  
 The framework calls this member function after the system time is changed.  
  
```  
Afx_msg void OnTimeChange();
```  
  
### Remarks  
 Have any application that changes the system time send this message to all top-level windows. To send the `WM_TIMECHANGE` message to all top-level windows, an application can use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with its *hwnd* parameter set to **HWND_BROADCAST**.  
  
##  <a name="ontimer"></a>  CWnd::OnTimer  
 The framework calls this member function after each interval specified in the [SetTimer](#settimer) member function used to install a timer.  
  
```  
Afx_msg void OnTimer (UINT_PTR nIDEvent);
```  
  
### Parameters  
 `nIDEvent`  
 Specifies the identifier of the timer.  
  
### Remarks  
 The [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows function sends a [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902) message when no other messages are in the application's message queue.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
  See the example in [CWnd::SetTimer](#settimer).  
  
##  <a name="ontoolhittest"></a>  CWnd::OnToolHitTest  
 The framework calls this member function to detemine whether a point is in the bounding rectangle of the specified tool.  
  
```  
virtuelle INT_PTR OnToolHitTest (CPoint Punkt  
    TOOLINFO* pTI) const;  
```  
  
### Parameters  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window  
  
 `pTI`  
 A pointer to a [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) structure. The following structure values are set by default:  
  
- *hwnd* = `m_hWnd` Handle to a window  
  
- `uId` = **(UINT)hWndChild** Handle to a child window  
  
- `uFlags` &#124;= **TTF_IDISHWND** Handle of the tool  
  
- `lpszText` = **LPSTR_TEXTCALLBACK** Pointer to the string that is to be displayed in the specified window  
  
### Return Value  
 If the tooltip control was found, the window control ID. If the tooltip control was not found, -1.  
  
### Remarks  
 If the point is in the rectangle, it retrieves information about the tool.  
  
 If the area with which the tooltip is associated is not a button, `OnToolHitTest` sets the structure flags to **TTF_NOTBUTTON** and **TTF_CENTERTIP**.  
  
 Override `OnToolHitTest` to provide different information than the default provides.  
  
 See [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256), in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], for more information about the structure.  
  
##  <a name="ontouchinput"></a>  CWnd::OnTouchInput  
 Process single input from Windows touch.  
  
```  
virtuelle BOOL OnTouchInput (CPoint pt,  
    Int-nInputNumber  
    Int-nInputsCount  
    PTOUCHINPUT pInput);
```  
  
### Parameters  
 `pt`  
 Point where screen has been touched (in the client coordinates).  
  
 `nInputNumber`  
 Number of touch input.  
  
 `nInputsCount`  
 Total number of touch inputs.  
  
 `pInput`  
 Pointer to TOUCHINPUT structure.  
  
### Return Value  
 `TRUE` if the application processes Windows touch input; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="ontouchinputs"></a>  CWnd::OnTouchInputs  
 Processes inputs from Windows touch.  
  
```  
virtuelle BOOL OnTouchInputs (nInputsCount UINT,  
    PTOUCHINPUT pInputs);
```  
  
### Parameters  
 `nInputsCount`  
 Total number of Windows touch inputs.  
  
 `pInputs`  
 Array of TOUCHINPUT.  
  
### Return Value  
 `TRUE` if application processes Windows touch inputs; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="onunichar"></a>  CWnd::OnUniChar  
 The framework calls this member function when a key is pressed. That is, the current window has the keyboard focus and a [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) message is translated by the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) function.  
  
```  
Afx_msg void OnUniChar (UINT nChar,   
    UINT-nRepCnt   
    UINT-nFlags);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nChar`|Specifies the character code of the pressed key.|  
|[in] `nRepCnt`|Specifies the repeat count for the current message. The value is the number of times the keystroke is autorepeated as a result of the user holding down the key. If the keystroke is held long enough, multiple messages are sent. However, the repeat count is not cumulative.|  
|[in] `nFlags`|Flags that specify the scan code, extended key, context code, previous key state, and transition state, as shown in the following table:<br /><br /> **0-7:** Specifies the scan code. The value depends on the original equipment manufacturer (OEM).<br /><br /> **8:** Specifies an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101 or 102-key keyboard. The flag is 1 if the key is an extended key; otherwise, it is 0.<br /><br /> **9-12:**  Used internally by Windows.<br /><br /> **13:**  Specifies the context code. The flag is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.<br /><br /> **14:**  Specifies the previous key state. The flag is 1 if the key is down before the message is sent, or 0 if the key is up.<br /><br /> **15:**  Specifies the transition state. The flag is 1 if the key is being released, or 0 if the key is being pressed.|  
  
### Remarks  
 This method receives the [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288) message is designed to send or post Unicode characters to ANSI windows. It is equivalent to the [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276) message, but uses Unicode Transformation Format-32 encoding (UTF-32), whereas the [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276) message uses UTF-16.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onuninitmenupopup"></a>  CWnd::OnUnInitMenuPopup  
 The framework calls this member function when a drop-down menu or submenu has been destroyed.  
  
```  
Afx_msg void OnUnInitMenuPopup (CMenu * pPopupMenu,   
    UINT-nFlags);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that represents the menu or submenu.|  
|[in] `nFlags`|The menu that was destroyed. Currently, it can only be the window menu, `MF_SYSMENU`.|  
  
### Remarks  
 This method receives the [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onupdateuistate"></a>  CWnd::OnUpdateUIState  
 Called to to change the user interface (UI) state for the specified window and all its child windows.  
  
```  
Afx_msg void OnUpdateUIState (UINT nDie Aktion wurde,  
    UINT-nUIElement);
```  
  
### Parameters  
 `nAction`  
 Specifies the action to be performed. Can be one of the following values:  
  
- **UIS_CLEAR** The UI state element (specified by `nUIElement`) should be hidden.  
  
- **UIS_INITIALIZE** The UI state element (specified by `nUIElement`) should be changed based on the last input event. For more information, see the **Remarks** section of [WM_UPDATEISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361).  
  
- **UIS_SET** The UI state element (specified by `nUIElement`) should be visible.  
  
 `nUIElement`  
 Specifies which UI state elements are affected or the style of the control. Can be one of the following values:  
  
- **UISF_HIDEACCEL** Keyboard accelerators.  
  
- **UISF_HIDEFOCUS** Focus indicators.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_UPDATEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onuserchanged"></a>  CWnd::OnUserChanged  
 The framework calls this member for all windows after the user has logged on or off.  
  
```  
Afx_msg void OnUserChanged();
```  
  
### Remarks  
 This method receives the [WM_USERCHANGED](http://msdn.microsoft.com/library/windows/desktop/ms632651) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. When the user logs on or off, the operating system updates user-specific settings. The system sends this message immediately after updating the settings.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvkeytoitem"></a>  CWnd::OnVKeyToItem  
 If the `CWnd` object owns a list box with the [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) style, the list box will send the `WM_VKEYTOITEM` message in response to a `WM_KEYDOWN` message.  
  
```  
Afx_msg Int OnVKeyToItem (UINT nKey,  
    CListBox-* pListBox,  
    UINT nIndex);
```  
  
### Parameters  
 `nKey`  
 Specifies the virtual key code of the key that the user pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `pListBox`  
 Specifies a pointer to the list box. The pointer may be temporary and should not be stored for later use.  
  
 `nIndex`  
 Specifies the current caret position.  
  
### Return Value  
 Specifies the action that the application performed in response to the message. A return value of –2 indicates that the application handled all aspects of selecting the item and requires no further action by the list box. A return value of –1 indicates that the list box should perform the default action in response to the keystroke. A return value of 0 or greater specifies the zero-based index of an item in the list box and indicates that the list box should perform the default action for the keystroke on the given item.  
  
### Remarks  
 This member function is called by the framework only for list boxes that have the [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) style.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvscroll"></a>  CWnd::OnVScroll  
 The framework calls this member function when the user clicks the window's vertical scroll bar.  
  
```  
Afx_msg void OnVScroll (UINT nSBCode,  
    UINT-nPos  
    CScrollBar* pScrollBar);
```  
  
### Parameters  
 `nSBCode`  
 Specifies a scroll-bar code that indicates the user's scrolling request. This parameter can be one of the following:  
  
- **SB_BOTTOM** Scroll to bottom.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_THUMBTRACK** Drag scroll box to specified position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to top.  
  
 `nPos`  
 Contains the current scroll-box position if the scroll-bar code is **SB_THUMBPOSITION** or **SB_THUMBTRACK**; otherwise not used. Depending on the initial scroll range, `nPos` may be negative and should be cast to an `int` if necessary.  
  
 `pScrollBar`  
 If the scroll message came from a scroll-bar control, contains a pointer to the control. If the user clicked a window's scroll bar, this parameter is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `OnVScroll` typically is used by applications that give some feedback while the scroll box is being dragged.  
  
 If `OnVScroll` scrolls the contents of the `CWnd` object, it must also reset the position of the scroll box with the [SetScrollPos](#setscrollpos) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvscrollclipboard"></a>  CWnd::OnVScrollClipboard  
 The Clipboard owner's `OnVScrollClipboard` member function is called by the Clipboard viewer when the Clipboard data has the `CF_OWNERDISPLAY` format and there is an event in the Clipboard viewer's vertical scroll bar.  
  
```  
Afx_msg void OnVScrollClipboard (CWnd * pClipAppWnd,  
    UINT-nSBCode  
    UINT nPos);
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to a Clipboard-viewer window. The pointer may be temporary and should not be stored for later use.  
  
 `nSBCode`  
 Specifies one of the following scroll-bar values:  
  
- **SB_BOTTOM** Scroll to bottom.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to top.  
  
 `nPos`  
 Contains the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION**; otherwise `nPos` is not used.  
  
### Remarks  
 The owner should scroll the Clipboard image, invalidate the appropriate section, and update the scroll-bar values.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowmaximizedchanged"></a>  CWnd::OnWindowMaximizedChanged  
 The framework calls this member when the current window is maximized, and the window is composed by the Desktop Window Manager (DWM).  
  
```  
Afx_msg void OnWindowMaximizedChanged (BOOL bIsMaximized);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `bIsMaximized`|`true` if the current window is maximized, and `false` if it is not.|  
  
### Remarks  
 This method receives the [WM_DWMWINDOWMAXIMIZEDCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd388201) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowposchanged"></a>  CWnd::OnWindowPosChanged  
 The framework calls this member function when the size, position, or Z-order has changed as a result of a call to the [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) member function or another window-management function.  
  
```  
Afx_msg void OnWindowPosChanged (WINDOWPOS * Lpwndpos);
```  
  
### Parameters  
 `lpwndpos`  
 Points to a [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) data structure that contains information about the window's new size and position.  
  
### Remarks  
 The default implementation sends the [WM_SIZE](http://msdn.microsoft.com/library/windows/desktop/ms632646) and [WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631) messages to the window. These messages are not sent if an application handles the `OnWindowPosChanged` call without calling its base class. It is more efficient to perform any move or size change processing during the call to `OnWindowPosChanged` without calling its base class.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowposchanging"></a>  CWnd::OnWindowPosChanging  
 The framework calls this member function when the size, position, or Z-order is about to change as a result of a call to the [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) member function or another window-management function.  
  
```  
Afx_msg void OnWindowPosChanging (WINDOWPOS * Lpwndpos);
```  
  
### Parameters  
 `lpwndpos`  
 Points to a `WINDOWPOS` data structure that contains information about the window's new size and position.  
  
### Remarks  
 An application can prevent changes to the window by setting or clearing the appropriate bits in the **flags** member of the [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) structure.  
  
 For a window with the [WS_OVERLAPPED](../../mfc/reference/window-styles.md) or [WS_THICKFRAME](../../mfc/reference/window-styles.md) style, the default implementation sends a [WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) message to the window. This is done to validate the new size and position of the window and to enforce the **CS_BYTEALIGNCLIENT** and **CS_BYTEALIGN** client styles. An application can override this functionality by not calling its base class.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwininichange"></a>  CWnd::OnWinIniChange  
 The framework calls this member function after a change has been made to the Windows initialization file, WIN.INI.  
  
```  
Afx_msg void OnWinIniChange (LPCTSTR LpszSection);
```  
  
### Parameters  
 `lpszSection`  
 Points to a string that specifies the name of the section that has changed. (The string does not include the square brackets that enclose the section name.)  
  
### Remarks  
 The [SystemParametersInfo](http://msdn.microsoft.com/library/windows/desktop/ms724947) Windows function calls `OnWinIniChange` after an application uses the function to change a setting in the WIN.INI file.  
  
 To send the `WM_WININICHANGE` message to all top-level windows, an application can use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with its *hwnd* parameter set to **HWND_BROADCAST**.  
  
 If an application changes many different sections in WIN.INI at the same time, the application should send one `WM_WININICHANGE` message with `lpszSection` set to **NULL**. Otherwise, an application should send `WM_WININICHANGE` each time it makes a change to WIN.INI.  
  
 If an application receives an `OnWinIniChange` call with `lpszSection` set to **NULL**, the application should check all sections in WIN.INI that affect the application.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwndmsg"></a>  CWnd::OnWndMsg  
 This member function is called by `WindowProc`, or is called during message reflection.  
  
```  
virtuelle BOOL OnWndMsg (UINT-Nachricht,  
    WPARAM wParam-Parameter  
    LPARAM lParam  
    LRESULT* pResult);
```  
  
### Parameters  
 `message`  
 Specifies the message to be sent.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
 `pResult`  
 The return value of [WindowProc](#windowproc). Depends on the message; may be **NULL**.  
  
### Return Value  
 **TRUE** if message was handled; otherwise **FALSE**.  
  
### Remarks  
 `OnWndMsg` determines the message type and either calls the appropriate framework function (for example, [OnCommand](#oncommand) for **WM_COMMAND**) or finds the appropriate message in the message map.  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="onxbuttondblclk"></a>  CWnd::OnXButtonDblClk  
 The framework calls this member function when the user double-clicks XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
Afx_msg void OnXButtonDblClk (UINT nFlags,   
    UINT-nButton   
    Zeigen Sie CPoint);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button is double-clicked, or `XBUTTON2` if the second X button is double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onxbuttondown"></a>  CWnd::OnXButtonDown  
 The framework calls this member function when the user presses XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
Afx_msg void OnXButtonDown (UINT nFlags,   
    UINT-nButton   
    Zeigen Sie CPoint);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button was clicked, or `XBUTTON2` if the second X button was clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646245) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onxbuttonup"></a>  CWnd::OnXButtonUp  
 The framework calls this member function when the user releases XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
Afx_msg void OnXButtonUp (UINT nFlags,   
    UINT-nButton   
    Zeigen Sie CPoint);
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button was double-clicked, or `XBUTTON2` if the second X button was double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646246) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="openclipboard"></a>  CWnd::OpenClipboard  
 Opens the Clipboard.  
  
```  
BOOL OpenClipboard();
```  
  
### Return Value  
 Nonzero if the Clipboard is opened via `CWnd`, or 0 if another application or window has the Clipboard open.  
  
### Remarks  
 Other applications will not be able to modify the Clipboard until the [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windows function is called.  
  
 The current `CWnd` object will not become the owner of the Clipboard until the [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows function is called.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#111](../../mfc/reference/codesnippet/cpp/cwnd-class_52.cpp)]  
  
##  <a name="operator_hwnd"></a>  CWnd::operator HWND  
 Use this operator to get the handle to the `CWnd` object.  
  
```  
HWND() const-Operator  
```  
  
##  <a name="operator_neq"></a>  CWnd::operator !=  
 Compares two `CWnd` objects to determine if they do not have the same [m_hWnd](#m_hwnd).  
  
```  
BOOL-Operator! = (const CWnd & Wnd) const;  
```  
  
### Parameters  
 `wnd`  
 A reference to a `CWnd` object.  
  
### Return Value  
 Nonzero if equal; otherwise 0.  
  
##  <a name="operator_eq_eq"></a>  CWnd::operator ==  
 Compares two `CWnd` objects to determine if they have the same [m_hWnd](#m_hwnd).  
  
```  
BOOL-Operator == (const CWnd & Wnd) const;  
```  
  
### Parameters  
 `wnd`  
 A reference to a `CWnd` object.  
  
### Return Value  
 Nonzero if equal; otherwise 0.  
  
##  <a name="paintwindowlesscontrols"></a>  CWnd::PaintWindowlessControls  
 Draws windowless controls on the control container.  
  
```  
BOOL PaintWindowlessControls(CDC* pDC);
```  
  
### Parameters  
 `pDC`  
 The device context on which to draw the windowless controls.  
  
### Return Value  
 Returns TRUE if there is a control container and the windowless controls are drawn successfully, otherwise FALSE.  
  
##  <a name="postmessage"></a>  CWnd::PostMessage  
 Places a message in the window's message queue and then returns without waiting for the corresponding window to process the message.  
  
```  
BOOL PostMessage (UINT-Nachricht,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### Parameters  
 `message`  
 Specifies the message to be posted.  
  
 `wParam`  
 Specifies additional message information. The content of this parameter depends on the message being posted.  
  
 `lParam`  
 Specifies additional message information. The content of this parameter depends on the message being posted.  
  
### Return Value  
 Nonzero if the message is posted; otherwise 0.  
  
### Remarks  
 Messages in a message queue are retrieved by calls to the [GetMessage](http://msdn.microsoft.com/library/windows/desktop/ms644936) or [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Windows function.  
  
 The Windows [PostMessage](http://msdn.microsoft.com/library/windows/desktop/ms644944) function can be used to access another application.  
  
### Example  
  See the example for [AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd).  
  
##  <a name="postncdestroy"></a>  CWnd::PostNcDestroy  
 Called by the default [OnNcDestroy](#onncdestroy) member function after the window has been destroyed.  
  
```  
virtuelle void PostNcDestroy();
```  
  
### Remarks  
 Derived classes can use this function for custom cleanup such as the deletion of the **this** pointer.  
  
##  <a name="precreatewindow"></a>  CWnd::PreCreateWindow  
 Called by the framework before the creation of the Windows window attached to this `CWnd` object.  
  
```  
virtuelle BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### Parameters  
 *cs*  
 A [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) structure.  
  
### Return Value  
 Nonzero if the window creation should continue; 0 to indicate creation failure.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of `cs` to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 Never call this function directly.  
  
 The default implementation of this function checks for a **NULL** window class name and substitutes an appropriate default. Override this member function to modify the `CREATESTRUCT` structure before the window is created.  
  
 Each class derived from `CWnd` adds its own functionality to its override of `PreCreateWindow`. By design, these derivations of `PreCreateWindow` are not documented. To determine the styles appropriate to each class and the interdependencies between the styles, you can examine the MFC source code for your application's base class. If you choose to override **PreCreateWindow,** you can determine whether the styles used in your application's base class provide the functionality you need by using information gathered from the MFC source code.  
  
 For more information on changing window styles, see the [Changing the Styles of a Window Created by MFC](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#112](../../mfc/reference/codesnippet/cpp/cwnd-class_53.cpp)]  
  
##  <a name="presubclasswindow"></a>  CWnd::PreSubclassWindow  
 This member function is called by the framework to allow other necessary subclassing to occur before the window is subclassed.  
  
```  
virtuelle void PreSubclassWindow();
```  
  
### Remarks  
 Overriding this member function allows for dynamic subclassing of controls. It is an advanced overridable.  
  
##  <a name="pretranslatemessage"></a>  CWnd::PreTranslateMessage  
 Used by class [CWinApp](../../mfc/reference/cwinapp-class.md) to translate window messages before they are dispatched to the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) and [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows functions.  
  
```  
virtuelle BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### Parameters  
 `pMsg`  
 Points to a [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message to process.  
  
### Return Value  
 Nonzero if the message was translated and should not be dispatched; 0 if the message was not translated and should be dispatched.  
  
##  <a name="print"></a>  CWnd::Print  
 Call this member function to draw the current window in the specified device context, which is most commonly in a printer device context.  
  
```  
Drucken (pDC CDC *, void  
    DWORD DwFlags) const;  
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context.  
  
 `dwFlags`  
 Specifies the drawing options. This parameter can be one or more of these flags:  
  
- `PRF_CHECKVISIBLE` Draw the window only if it is visible.  
  
- `PRF_CHILDREN` Draw all visible children windows.  
  
- `PRF_CLIENT` Draw the client area of the window.  
  
- `PRF_ERASEBKGND` Erase the background before drawing the window.  
  
- `PRF_NONCLIENT` Draw the nonclient area of the window.  
  
- `PRF_OWNED` Draw all owned windows.  
  
### Remarks  
 [CWnd::DefWindowProc](#defwindowproc) function processes this message based on which drawing option is specified:  
  
-   If `PRF_CHECKVISIBLE` is specified and the window is not visible, do nothing.  
  
-   If `PRF_NONCLIENT` is specified, draw the nonclient area in the given device context.  
  
-   If `PRF_ERASEBKGND` is specified, send the window a [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message.  
  
-   If `PRF_CLIENT` is specified, send the window a [WM_PRINTCLIENT](http://msdn.microsoft.com/library/windows/desktop/dd145217) message.  
  
-   If `PRF_CHILDREN` is set, send each visible child window a [WM_PRINT](http://msdn.microsoft.com/library/windows/desktop/dd145216) message.  
  
-   If `PRF_OWNED` is set, send each visible owned window a `WM_PRINT` message.  
  
##  <a name="printclient"></a>  CWnd::PrintClient  
 Call this member function to draw any window in the specified device context (usually a printer device context).  
  
```  
void PrintClient (CDC * pDC,  
    DWORD DwFlags) const;  
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context.  
  
 `dwFlags`  
 Specifies drawing options. This parameter can be one or more of these flags:  
  
- `PRF_CHECKVISIBLE` Draw the window only if it is visible.  
  
- `PRF_CHILDREN` Draw all visible children windows.  
  
- `PRF_CLIENT` Draw the client area of the window.  
  
- `PRF_ERASEBKGND` Erase the background before drawing the window.  
  
- `PRF_NONCLIENT` Draw the nonclient area of the window.  
  
- `PRF_OWNED` Draw all owned windows.  
  
##  <a name="printwindow"></a>  CWnd::PrintWindow  
 Copies a visual window into the specified device context, typically a printer DC.  
  
```  
BOOL PrintWindow (CDC * pDC,  
    UINT-nFlags) const;  
```  
  
### Parameters  
 `pDC`  
 A pointer to the device context to be printed to.  
  
 `nFlags`  
 Specifies the drawing options. For a list of possible values, see [PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="redrawwindow"></a>  CWnd::RedrawWindow  
 Updates the specified rectangle or region in the given window's client area.  
  
```  
BOOL RedrawWindow (LPCRECT LpRectUpdate = NULL  
    CRgn * PrgnUpdate = NULL  
    UINT-Flags = RDW_INVALIDATE | RDW_UPDATENOW | RDW_ERASE);
```  
  
### Parameters  
 `lpRectUpdate`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) containing the coordinates of the update rectangle. This parameter is ignored if *prgnUpdate* contains a valid region handle.  
  
 *prgnUpdate*  
 Identifies the update region. If both *prgnUpdate* and `lpRectUpdate` are **NULL**, the entire client area is added to the update region.  
  
 `flags`  
 The following flags are used to invalidate the window:  
  
- **RDW_ERASE** Causes the window to receive a [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message when the window is repainted. The **RDW_INVALIDATE** flag must also be specified; otherwise **RDW_ERASE** has no effect.  
  
- **RDW_FRAME** Causes any part of the nonclient area of the window that intersects the update region to receive a [WM_NCPAINT](http://msdn.microsoft.com/library/windows/desktop/dd145212) message. The **RDW_INVALIDATE** flag must also be specified; otherwise **RDW_FRAME** has no effect.  
  
- **RDW_INTERNALPAINT** Causes a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message to be posted to the window regardless of whether the window contains an invalid region.  
  
- **RDW_INVALIDATE** Invalidate `lpRectUpdate` or *prgnUpdate* (only one may be not **NULL**). If both are **NULL**, the entire window is invalidated.  
  
 The following flags are used to validate the window:  
  
- **RDW_NOERASE** Suppresses any pending `WM_ERASEBKGND` messages.  
  
- **RDW_NOFRAME** Suppresses any pending `WM_NCPAINT` messages. This flag must be used with **RDW_VALIDATE** and is typically used with **RDW_NOCHILDREN**. This option should be used with care, as it could prevent parts of a window from painting properly.  
  
- **RDW_NOINTERNALPAINT** Suppresses any pending internal `WM_PAINT` messages. This flag does not affect `WM_PAINT` messages resulting from invalid areas.  
  
- **RDW_VALIDATE** Validates `lpRectUpdate` or *prgnUpdate* (only one may be not **NULL**). If both are **NULL**, the entire window is validated. This flag does not affect internal `WM_PAINT` messages.  
  
 The following flags control when repainting occurs. Painting is not performed by the `RedrawWindow` function unless one of these bits is specified.  
  
- **RDW_ERASENOW** Causes the affected windows (as specified by the **RDW_ALLCHILDREN** and **RDW_NOCHILDREN** flags) to receive `WM_NCPAINT` and `WM_ERASEBKGND` messages, if necessary, before the function returns. `WM_PAINT` messages are deferred.  
  
- **RDW_UPDATENOW** Causes the affected windows (as specified by the **RDW_ALLCHILDREN** and **RDW_NOCHILDREN** flags) to receive `WM_NCPAINT`, `WM_ERASEBKGND`, and `WM_PAINT` messages, if necessary, before the function returns.  
  
 By default, the windows affected by the `RedrawWindow` function depend on whether the specified window has the **WS_CLIPCHILDREN** style. The child windows of **WS_CLIPCHILDREN** windows are not affected. However, those windows that are not **WS_CLIPCHILDREN** windows are recursively validated or invalidated until a **WS_CLIPCHILDREN** window is encountered. The following flags control which windows are affected by the `RedrawWindow` function:  
  
- **RDW_ALLCHILDREN** Includes child windows, if any, in the repainting operation.  
  
- **RDW_NOCHILDREN** Excludes child windows, if any, from the repainting operation.  
  
### Return Value  
 Nonzero if the window was redrawn successfully; otherwise 0.  
  
### Remarks  
 When the `RedrawWindow` member function is used to invalidate part of the desktop window, that window does not receive a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message. To repaint the desktop, an application should use [CWnd::ValidateRgn](#validatergn), [CWnd::InvalidateRgn](#invalidatergn), [CWnd::UpdateWindow](#updatewindow), or [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)  
  
##  <a name="reflectchildnotify"></a>  CWnd::ReflectChildNotify  
 This message function is called by the framework from [OnChildNotify](#onchildnotify).  
  
```  
BOOL ReflectChildNotify (UINT-Nachricht,  
    WPARAM wParam-Parameter  
    LPARAM lParam  
    LRESULT* pResult);
```  
  
### Parameters  
 `message`  
 Specifies the message to be reflected.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
 `pResult`  
 The result generated by the child window to be returned by the parent window. Can be **NULL**.  
  
### Return Value  
 **TRUE** if message was reflected; otherwise **FALSE**.  
  
### Remarks  
 It is a helper function which reflects `message` to its source.  
  
 Reflected messages are sent directly to [CWnd::OnWndMsg](#onwndmsg) or [CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg).  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="reflectlastmsg"></a>  CWnd::ReflectLastMsg  
 This member function is called by the framework to reflect the last message to the child window.  
  
```  
statische BOOL PASCAL ReflectLastMsg (HWND hWndChild,  
    LRESULT* pResult = NULL);
```  
  
### Parameters  
 `hWndChild`  
 A handle to a child window.  
  
 `pResult`  
 The result generated by the child window to be returned by the parent window. Can be **NULL**.  
  
### Return Value  
 Nonzero if the message was handled; otherwise 0.  
  
### Remarks  
 This member function calls [SendChildNotifyLastMsg](#sendchildnotifylastmsg) if the window identified by `hWndChild` is an OLE control or a window in the permanent map.  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="releasedc"></a>  CWnd::ReleaseDC  
 Releases a device context, freeing it for use by other applications.  
  
```  
Int ReleaseDC (CDC * pDC);
```  
  
### Parameters  
 `pDC`  
 Identifies the device context to be released.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 The effect of the `ReleaseDC` member function depends on the device-context type.  
  
 The application must call the `ReleaseDC` member function for each call to the [GetWindowDC](#getwindowdc) member function and for each call to the [GetDC](#getdc) member function.  
  
##  <a name="repositionbars"></a>  CWnd::RepositionBars  
 Called to reposition and resize control bars in the client area of a window.  
  
```  
void RepositionBars (UINT nIDFirst, "uint" nIDLast, "uint" nIDLeftOver, "uint" nFlag = ReposDefault LPRECT LpRectParam = NULL, LPCRECT LpRectClient = NULL, BOOL bStretch = TRUE);  
```  
  
### Parameters  
 `nIDFirst`  
 The ID of the first in a range of control bars to reposition and resize.  
  
 `nIDLast`  
 The ID of the last in a range of control bars to reposition and resize.  
  
 `nIDLeftOver`  
 Specifies ID of pane that fills the rest of the client area.  
  
 `nFlag`  
 Can have one of the following values:  
  
- **CWnd::reposDefault** Performs the layout of the control bars. `lpRectParam` is not used and can be **NULL**.  
  
- **CWnd::reposQuery** The layout of the control bars is not done; instead `lpRectParam` is initialized with the size of the client area, as if the layout had actually been done.  
  
- **CWnd::reposExtra** Adds the values of `lpRectParam` to the client area of `nIDLast` and also performs the layout *.*  
  
 `lpRectParam`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md); the usage of which depends on the value of `nFlag`.  
  
 *lpRectClient*  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) containing the available client area. If **NULL**, the window's client area will be used.  
  
 `bStretch`  
 Indicates whether the bar should be stretched to the size of the frame.  
  
### Remarks  
 The `nIDFirst` and `nIDLast` parameters define a range of control-bar IDs to be repositioned in the client area. The `nIDLeftOver` parameter specifies the ID of the child window (normally the view) which is repositioned and resized to fill the rest of the client area not filled by control bars.  
  
##  <a name="runmodalloop"></a>  CWnd::RunModalLoop  
 Call this member function to retrieve, translate, or dispatch messages until [ContinueModal](#continuemodal) returns **FALSE**.  
  
```  
Int RunModalLoop (DWORD DwFlags = 0);
```  
  
### Parameters  
 `dwFlags`  
 Specifies the Windows message to be sent. Can be one of the following values:  
  
- **MLF_NOIDLEMSG** Don't send [WM_ENTERIDLE](http://msdn.microsoft.com/library/windows/desktop/ms645422) messages to the parent.  
  
- **MLF_NOKICKIDLE** Don't send **WM_KICKIDLE** messages to the window.  
  
- **MLF_SHOWONIDLE** Show the window when message queue goes idle.  
  
### Return Value  
 Specifies the value of the `nResult` parameter passed to the [EndModalLoop](#endmodalloop) member function, which is then used to end the modal loop.  
  
### Remarks  
 By default, `ContinueModal` returns **FALSE** after `EndModalLoop` is called. Returns the value provided as `nResult` to `EndModalLoop`.  
  
##  <a name="screentoclient"></a>  CWnd::ScreenToClient  
 Converts the screen coordinates of a given point or rectangle on the display to client coordinates.  
  
```  
void ScreenToClient (LPPOINT LpPoint) const;  void ScreenToClient (LPRECT LpRect) const;  ```  
  
### <a name="parameters"></a>Parameter  
 `lpPoint`  
 Verweist auf eine [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt oder [POINT-Struktur](../../mfc/reference/point-structure1.md) , enthält die Bildschirmkoordinaten konvertiert werden.  
  
 `lpRect`  
 Verweist auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT-Struktur](../../mfc/reference/rect-structure1.md) , enthält die Bildschirmkoordinaten konvertiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die `ScreenToClient` Memberfunktion ersetzt die im angegebenen Bildschirmkoordinaten `lpPoint` oder `lpRect` mit Clientkoordinaten. Die neuen Koordinaten werden relativ zur oberen linken Ecke des der `CWnd` des Clientbereichs.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListCtrl::GetItemRect](../../mfc/reference/clistctrl-class.md#getitemrect).  
  
##  <a name="a-namescrollwindowa--cwndscrollwindow"></a><a name="scrollwindow"></a>CWnd::ScrollWindow  
 Der Inhalt des Clientbereichs des aktuellen `CWnd` Objekt.  
  
```  
void ScrollWindow(
    int xAmount,  
    int yAmount,  
    LPCRECT lpRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `xAmount`  
 Gibt die Menge in Geräteeinheiten von horizontalen Bildlauf an. Dieser Parameter muss einen negativen Wert auf der linken Seite einen Bildlauf durchführen.  
  
 `yAmount`  
 Gibt die Menge in Geräteeinheiten, einen vertikalen Bildlauf ausführen. Dieser Parameter muss ein negativer Wert Bildlauf nach oben.  
  
 `lpRect`  
 Verweist auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT-Struktur](../../mfc/reference/rect-structure1.md) , der den Teil des Clientbereichs den Bildlauf angibt. Wenn `lpRect` ist **NULL**, der gesamten Clientbereich ein Bildlauf durchgeführt wird. Die Einfügemarke wird neu positioniert werden, wenn der Cursor-Rechteck das Scroll-Rechteck überschneidet.  
  
 `lpClipRect`  
 Verweist auf eine `CRect` Objekt oder `RECT` Struktur, die das Auswahlrechteck Scrollen angibt. Nur die Bits in dieses Rechteck werden durchgeführt. Bits außerhalb dieses Rechteck sind nicht betroffen, auch wenn sie in sind die `lpRect` Rechteck. Wenn `lpClipRect` ist **NULL**, ohne Clipping für das Bildlaufrechteck ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Einfügemarke in die `CWnd` wird ein Bildlauf durchgeführt, `ScrollWindow` automatisch Blendet die Einfügemarke, um zu verhindern, dass es gelöscht wird und anschließend die Einfügemarke nach Abschluss der Bildlaufleiste wird wiederhergestellt. Die Position der Einfügemarke wird entsprechend angepasst.  
  
 Der Bereich aufgedeckt werden, indem die `ScrollWindow` Memberfunktion wird nicht aktualisiert, aber in der aktuellen kombiniert `CWnd` Aktualisierungsbereich des Objekts. Schließlich empfängt die Anwendung eine [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Meldung benachrichtigt sie, dass die Region zeichnende. Um die nicht abgedeckten Bereich gleichzeitig Zeichnen der Bildlauf durchgeführt wird, rufen Sie die [UpdateWindow](#updatewindow) Memberfunktion sofort nach dem Aufruf von `ScrollWindow`.  
  
 Wenn `lpRect` ist **NULL**, die Positionen für beliebige untergeordnete Fenster im Fenster werden durch den angegebenen Betrag versetzt `xAmount` und `yAmount`, und alle ungültigen (unlackierten) Bereiche in der `CWnd` werden auch versetzt. `ScrollWindow`ist schneller, wenn `lpRect` ist **NULL**.  
  
 Wenn `lpRect` nicht **NULL**, die Positionen von untergeordneten Fenstern sind nicht geändert und ungültige Bereiche `CWnd` nicht ausgeglichen sind. Um zu verhindern aktualisieren Probleme beim `lpRect` ist nicht **NULL**, rufen Sie die `UpdateWindow` Memberfunktion neu aufgebaut werden kann `CWnd` vor dem Aufruf von `ScrollWindow`.  
  
##  <a name="a-namescrollwindowexa--cwndscrollwindowex"></a><a name="scrollwindowex"></a>CWnd::ScrollWindowEx  
 Führt einen Bildlauf des Clientbereichs des Fensters.  
  
```  
int ScrollWindowEx(
    int dx,  
    int dy,  
    LPCRECT lpRectScroll,  
    LPCRECT lpRectClip,  
    CRgn* prgnUpdate,  
    LPRECT lpRectUpdate,  
    UINT flags);
```  
  
### <a name="parameters"></a>Parameter  
 `dx`  
 Gibt die Menge in Geräteeinheiten von horizontalen Bildlauf an. Dieser Parameter benötigen einen negativen Wert auf der linken Seite einen Bildlauf durchführen.  
  
 *dy*  
 Gibt die Menge in Geräteeinheiten, einen vertikalen Bildlauf ausführen. Dieser Parameter muss einen Bildlauf nach oben negativen Wert aufweisen.  
  
 `lpRectScroll`  
 Verweist auf eine [RECT-Struktur](../../mfc/reference/rect-structure1.md) , der den Teil des Clientbereichs den Bildlauf angibt. Wenn dieser Parameter **NULL**, der gesamten Clientbereich ein Bildlauf durchgeführt wird.  
  
 `lpRectClip`  
 Verweist auf eine `RECT` Struktur, die das Auswahlrechteck Scrollen angibt. Diese Struktur hat Vorrang vor dem Rechteck, das auf den `lpRectScroll`. Nur die Bits in dieses Rechteck werden durchgeführt. Bits außerhalb dieses Rechteck sind nicht betroffen, auch wenn sie in sind die `lpRectScroll` Rechteck. Wenn dieser Parameter **NULL**, ohne Clipping für das Bildlaufrechteck ausgeführt wird.  
  
 *prgnUpdate*  
 Gibt die Region, die geändert wird, um den Bereich für ungültig erklärt, indem Sie einen Bildlauf zu halten. Dieser Parameter ist möglicherweise **NULL**.  
  
 `lpRectUpdate`  
 Verweist auf eine `RECT` -Struktur, die die Grenzen des Rechtecks für ungültig erklärt, indem Sie einen Bildlauf zu erhalten. Dieser Parameter ist möglicherweise **NULL**.  
  
 `flags`  
 Dabei kann es sich um einen der folgenden Werte aufweisen:  
  
- **SW_ERASE** in Verbindung mit **SW_INVALIDATE**, löscht den neu für ungültig erklärten Bereich durch das Senden einer [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) Meldung im Fenster.  
  
- **SW_INVALIDATE** durch identifizierten erklärt *PrgnUpdate* Bildlauf nach unten.  
  
- **SW_SCROLLCHILDREN** verschiebt alle untergeordneten Fenster, die auf das Rechteck überschneiden `lpRectScroll` durch die Anzahl der Pixel, die im angegebenen `dx` und *dy*. Windows sendet eine [WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631) Nachricht an alle untergeordneten Fenster, die sich überschneiden `lpRectScroll`, auch wenn diese nicht verschoben werden. Die Einfügemarke wird neu positioniert werden, wenn ein untergeordnetes Fenster wird ein Bildlauf durchgeführt, und der Cursor Rechteck eine Schnittmenge das Scroll-Rechteck bilden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist **SIMPLEREGION** (rechteckigen für ungültig erklärten Bereich), **COMPLEXREGION** (nicht rechteckige für ungültig erklärten Bereich: überlappende Rechtecke), oder **NULLREGION** (kein Ungültiger Bereich), wenn die Funktion erfolgreich ist; andernfalls der Rückgabewert ist **Fehler**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist vergleichbar mit der [ScrollWindow](http://msdn.microsoft.com/library/windows/desktop/bb787591) -Funktion, mit einige zusätzlichen Funktionen.  
  
 Wenn [SW_INVALIDATE](http://msdn.microsoft.com/library/windows/desktop/bb787593) und [SW_ERASE](http://msdn.microsoft.com/library/windows/desktop/bb787593) nicht angegeben sind, die `ScrollWindowEx` Member-Funktion wird nicht den Bereich, der ein Bildlauf, von durchgeführt wird ungültig. Wenn eines dieser Flags festgelegt ist, `ScrollWindowEx` in diesem Bereich ungültig. Bereich erst dann aktualisiert die Anwendung ruft die [UpdateWindow](http://msdn.microsoft.com/library/windows/desktop/dd145167) Member-Funktion, ruft der [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) Member-Funktion (angeben [RDW_UPDATENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911) oder [RDW_ERASENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911)), ab der [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht aus der Warteschlange.  
  
 Wenn das Fenster verfügt über die [WS_CLIPCHILDREN](http://msdn.microsoft.com/library/windows/desktop/ms632679) Stil, die zurückgegebene Bereiche, die durch angegebene *PrgnUpdate* und `lpRectUpdate` den gesamten Bereich des Fensters ein Bildlauf ausgeführt wird, die aktualisiert werden muss, einschließlich der Bereiche in untergeordnete Fenster, die die zu aktualisierenden darstellen.  
  
 Wenn die [SW_SCROLLCHILDREN](http://msdn.microsoft.com/library/windows/desktop/bb787593) Flag angegeben wird, Windows werden nicht ordnungsgemäß aktualisiert den Bildschirm Teil eines untergeordneten Fensters ein Bildlauf durchgeführt wird. Der Teil der Bildlauf untergeordnetes Fenster, die sich außerhalb des Quellrechtecks werden nicht gelöscht und wird nicht neu gezeichnet, ordnungsgemäß in das neue Ziel. Verwenden der [DeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632681) -Funktion von Windows verschieben untergeordneten Fenstern, die nicht vollständig in liegen die `lpRectScroll` Rechteck. Der Cursor wird neu positioniert werden, wenn die **SW_SCROLLCHILDREN** Flag festgelegt ist und die Einfügemarke Rechteck eine Schnittmenge bilden das Scroll-Rechteck.  
  
 Alle Eingabe- und Koordinaten (für `lpRectScroll`, `lpRectClip`, `lpRectUpdate`, und *PrgnUpdate*) wird angenommen, dass in Clientkoordinaten, unabhängig davon, ob das Fenster der **CS_OWNDC** oder **CS_CLASSDC** -Klassenstil. Verwenden der [LPtoDP](http://msdn.microsoft.com/library/windows/desktop/dd145042) und [DPtoLP](http://msdn.microsoft.com/library/windows/desktop/dd162474) Windows-Funktionen zum Konvertieren in und aus den logischen Koordinaten bei Bedarf.  
  
##  <a name="a-namesendchildnotifylastmsga--cwndsendchildnotifylastmsg"></a><a name="sendchildnotifylastmsg"></a>CWnd::SendChildNotifyLastMsg  
 Diese Member-Funktion wird aufgerufen, durch das Framework eine Benachrichtigung zu einem untergeordneten Fenster aus dem übergeordneten Fenster bereitstellen, damit das untergeordnete Fenster ein Vorgangs behandeln kann.  
  
```  
BOOL SendChildNotifyLastMsg(LRESULT* pResult = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pResult`  
 Das Ergebnis generiert, die für das untergeordnete Fenster, die vom übergeordneten Fenster zurückgegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das untergeordnete Fenster zum übergeordneten gesendete Nachricht behandelt hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `SendChildNotifyLastMsg`die aktuelle Nachricht an die Datenquelle gesendet, wenn sie eine Meldung, die wiedergegeben wird.  
  
 Weitere Informationen zur Nachricht, finden Sie unter [reflektiert Nachrichten Behandeln von](../../mfc/handling-reflected-messages.md).  
  
##  <a name="a-namesenddlgitemmessagea--cwndsenddlgitemmessage"></a><a name="senddlgitemmessage"></a>CWnd::SendDlgItemMessage  
 Sendet eine Nachricht an ein Steuerelement.  
  
```  
LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Gibt den Bezeichner für das Steuerelement, das die Nachricht empfangen wird.  
  
 `message`  
 Gibt die Nachricht gesendet werden.  
  
 `wParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
 `lParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert von Fensterprozedur für das Steuerelement, oder 0 zurückgegeben, wenn das Steuerelement nicht gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Der `SendDlgItemMessage` Member-Funktion gibt keinen zurück, bis die Nachricht verarbeitet wurde.  
  
 Mit `SendDlgItemMessage` entspricht dem Abrufen einer `CWnd`* mit dem angegebenen Steuerelement und Aufrufen der [SendMessage](#sendmessage) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#113;](../../mfc/reference/codesnippet/cpp/cwnd-class_54.cpp)]  
  
##  <a name="a-namesendmessagea--cwndsendmessage"></a><a name="sendmessage"></a>Funktion CWnd:: SendMessage  
 Sendet die angegebene Meldung in diesem Fenster.  
  
```  
LRESULT SendMessage(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Gibt die Nachricht gesendet werden.  
  
 `wParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
 `lParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Verarbeitung der Nachricht. der Wert hängt von der gesendeten Nachricht ab.  
  
### <a name="remarks"></a>Hinweise  
 Die **SendMessage** Member-Funktion ruft die Prozedur direkt und nicht zurückgegeben, bis diese Fensterprozedur die Meldung verarbeitet hat. Dies ist im Gegensatz zu den [PostMessage](#postmessage) Memberfunktion, die platziert die Nachricht in die Nachrichtenwarteschlange das Fenster und kehrt sofort zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#101;](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="a-namesendmessagetodescendantsa--cwndsendmessagetodescendants"></a><a name="sendmessagetodescendants"></a>Wm_idleupdatecmdui  
 Rufen Sie diese Memberfunktion zum angegebene Windows-Meldung an alle untergeordneten Fenster zu senden.  
  
```  
void SendMessageToDescendants(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0,  
    BOOL bDeep = TRUE,  
    BOOL bOnlyPerm = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Gibt die Nachricht gesendet werden.  
  
 `wParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
 `lParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
 `bDeep`  
 Gibt die Ebene, auf dem gesucht werden soll. Wenn **TRUE**, rekursiven Durchsuchen aller untergeordneten Elemente; Wenn **FALSE**, nur unmittelbar untergeordnete Elemente zu suchen.  
  
 `bOnlyPerm`  
 Gibt an, ob die Nachricht von temporären Windows empfangen werden. Wenn **TRUE**, temporäre Windows erhalten die Meldung, wenn **FALSE**nur permanente Windows die Meldung angezeigt. Weitere Informationen zu temporären Windows finden Sie unter [Technische Hinweis 3](../../mfc/tn003-mapping-of-windows-handles-to-objects.md).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bDeep` ist **FALSE**, die Nachricht wird gesendet, um die unmittelbar untergeordneten Elemente des Fensters; andernfalls wird die Nachricht an alle untergeordneten Fenster gesendet.  
  
 Wenn `bDeep` und `bOnlyPerm` sind **TRUE**, die Suche wird fortgesetzt, unten temporäre Windows. In diesem Fall Meldung nur permanente Windows aufgetreten während der Suche die. Wenn `bDeep` ist **FALSE**, nur für die unmittelbar untergeordneten Elemente des Fensters wird die Nachricht gesendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#114;](../../mfc/reference/codesnippet/cpp/cwnd-class_55.cpp)]  
  
##  <a name="a-namesendnotifymessagea--cwndsendnotifymessage"></a><a name="sendnotifymessage"></a>CWnd::SendNotifyMessage  
 Sendet die angegebene Meldung an das Fenster an.  
  
```  
BOOL SendNotifyMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Gibt die Nachricht gesendet werden.  
  
 `wParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
 `lParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Fenster vom aufrufenden Thread erstellt wurde `SendNotifyMessage` Ruft die Fensterprozedur für das Fenster, und nicht zurückgegeben, bis die Fensterprozedur die Meldung verarbeitet hat. Wenn das Fenster von einem anderen Thread erstellt wurde `SendNotifyMessage` übergibt die Nachricht an die Prozedur und gibt sofort; er wartet nicht auf die Fensterprozedur in die Nachricht verarbeitet.  
  
##  <a name="a-namesetactivewindowa--cwndsetactivewindow"></a><a name="setactivewindow"></a>CWnd::SetActiveWindow  
 Macht `CWnd` das aktive Fenster.  
  
```  
CWnd* SetActiveWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fenster, das zuvor aktiv war.  
  
 Der zurückgegebene Zeiger kann temporär sein und sollte nicht zur späteren Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die `SetActiveWindow` Memberfunktion sollte mit Vorsicht verwendet werden, da eine Anwendung das aktive Fenster und den Eingabefokus willkürlich übernehmen können. Alle Aktivierung in der Regel übernimmt Windows.  
  
##  <a name="a-namesetcapturea--cwndsetcapture"></a><a name="setcapture"></a>CWnd::SetCapture  
 Bewirkt, dass alle nachfolgenden Mauseingaben an das aktuelle `CWnd` Objekt unabhängig von der Position des Cursors.  
  
```  
CWnd* SetCapture();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Window-Objekt, das zuvor alle Mauseingabe empfangen. Es ist `NULL` , wenn kein solcher Fenster vorhanden ist. Der zurückgegebene Zeiger kann temporär sein und sollte nicht zur späteren Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `CWnd` nicht mehr erforderlich, alle Eingaben mit der Maus, sollte die Anwendung aufrufen, die [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) Funktion so, dass andere Fenster Mauseingabe empfangen können.  
  
 Während die Maus erfasst wird, keine `WM_NCHITTEST` oder `WM_SETCURSOR` zum aktiven Fenster gesendet werden.  
  
##  <a name="a-namesetcaretposa--cwndsetcaretpos"></a><a name="setcaretpos"></a>CWnd::SetCaretPos  
 Legt die Position der Einfügemarke fest.  
  
```  
static void PASCAL SetCaretPos(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Gibt den neuen x- und y-Koordinaten (in Clientkoordinaten) des Caretzeichens.  
  
### <a name="remarks"></a>Hinweise  
 Die `SetCaretPos` Memberfunktion verschiebt die Einfügemarke nur, wenn es von einem Fenster in der aktuellen Aufgabe gehört. `SetCaretPos`Verschiebt die Einfügemarke an, unabhängig davon, ob die Einfügemarke ausgeblendet ist.  
  
 Die Einfügemarke wird eine freigegebene Ressource. Ein Fenster sollte nicht die Einfügemarke verschieben, wenn sie die Einfügemarke nicht besitzt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#115;](../../mfc/reference/codesnippet/cpp/cwnd-class_56.cpp)]  
  
##  <a name="a-namesetclipboardviewera--cwndsetclipboardviewer"></a><a name="setclipboardviewer"></a>CWnd::SetClipboardViewer  
 Fügt diesem Fenster auf die Kette von Windows, die benachrichtigt werden (von der `WM_DRAWCLIPBOARD` Nachricht) jedes Mal, wenn der Inhalt der Zwischenablage geändert wird.  
  
```  
HWND SetClipboardViewer();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das nächste Fenster in der Zwischenablage-Viewer-Kette, falls erfolgreich. Clientanwendungen sollten dieses Handle (kann als Membervariable gespeichert werden), speichern und verwenden, wenn die Zwischenablage Kette Nachrichten reagiert.  
  
### <a name="remarks"></a>Hinweise  
 Ein Fenster, das Teil der Zwischenablage Kette ist, muss auf Antworten [WM_DRAWCLIPBOARD](#ondrawclipboard), [WM_CHANGECBCHAIN](#onchangecbchain), und [WM_DESTROY](#ondestroy) Nachrichten und die Nachricht an das nächste Fenster in der Kette übergeben.  
  
 Diese Memberfunktion sendet eine `WM_DRAWCLIPBOARD` Meldung im Fenster. Da das Handle für das nächste Fenster in der Zwischenablage Kette noch nicht zurückgegeben wurde, leitet die Anwendung sollte nicht auf die `WM_DRAWCLIPBOARD` Nachricht, die während des Aufrufs empfangen `SetClipboardViewer`.  
  
 Um sich selbst aus der Zwischenablage Kette zu entfernen, muss eine Anwendung Aufrufen der [ChangeClipboardChain](#changeclipboardchain) Member-Funktion.  
  
##  <a name="a-namesetdlgctrlida--cwndsetdlgctrlid"></a><a name="setdlgctrlid"></a>CWnd::SetDlgCtrlID  
 Legt die Fenster oder Steuerelement-ID für das Fenster auf einen neuen Wert fest.  
  
```  
int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der neue Wert für das Steuerelement-ID festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Bezeichner des Fensters, falls erfolgreich. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Fenster kann untergeordneten Fenster nicht nur ein Steuerelement in einem Dialogfeld sein. Das Fenster der obersten Ebene nicht möglich.  
  
##  <a name="a-namesetdlgiteminta--cwndsetdlgitemint"></a><a name="setdlgitemint"></a>CWnd::SetDlgItemInt  
 Legt den Text eines bestimmten Steuerelements in einem Dialogfeld auf die Zeichenfolgendarstellung für einen angegebenen ganzzahligen Wert fest.  
  
```  
void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Gibt die ganzzahlige ID des Steuerelements geändert werden.  
  
 `nValue`  
 Gibt den ganzzahligen Wert verwendet, um den Elementtext zu generieren.  
  
 `bSigned`  
 Gibt an, ob der ganzzahligen Wert mit oder ohne Vorzeichen ist. Wenn dieser Parameter **TRUE**, `nValue` ist signiert. Wenn dieser Parameter **TRUE** und `nValue` ist kleiner als 0 ist, ein Minuszeichen anmelden werden vor der ersten Ziffer in der Zeichenfolge platziert. Wenn dieser Parameter **FALSE**, `nValue` ist nicht signiert.  
  
### <a name="remarks"></a>Hinweise  
 `SetDlgItemInt`sendet eine [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) Nachricht für das angegebene Steuerelement.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::SetDlgItemText](#setdlgitemtext).  
  
##  <a name="a-namesetdlgitemtexta--cwndsetdlgitemtext"></a><a name="setdlgitemtext"></a>CWnd::SetDlgItemText  
 Legt die Beschriftung oder Text eines Steuerelements im Besitz von einem Fenster oder Dialogfeld.  
  
```  
void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Identifiziert das Steuerelement, dessen Text ist, festgelegt werden.  
  
 `lpszString`  
 Verweist auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt oder Null-terminierte Zeichenfolge mit dem Text in das Steuerelement kopiert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 `SetDlgItemText`sendet eine [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) Nachricht für das angegebene Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&116;](../../mfc/reference/codesnippet/cpp/cwnd-class_57.cpp)]  
  
##  <a name="a-namesetforegroundwindowa--cwndsetforegroundwindow"></a><a name="setforegroundwindow"></a>CWnd::SetForegroundWindow  
 Versetzt den Thread, durch den das Fenster erstellt wurde, in den Vordergrund und aktiviert das Fenster.  
  
```  
BOOL SetForegroundWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Eingaben über die Tastatur gesteuert wird, um das Fenster, und verschiedene visuelle Hinweise für den Benutzer geändert werden. Wird das Fenster mit dem der Benutzer gerade arbeitet. Das Fenster im Vordergrund gilt nur für Fenster der obersten Ebene (Frame Fenster und Dialogfelder schachteln).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::FindWindow](#findwindow).  
  
##  <a name="a-namesetfocusa--cwndsetfocus"></a><a name="setfocus"></a>CWnd::SetFocus  
 Beansprucht den Eingabefokus.  
  
```  
CWnd* SetFocus();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Window-Objekt, das zuvor des Eingabefokus besitzt. Es ist **NULL** , wenn kein solcher Fenster vorhanden ist. Der zurückgegebene Zeiger kann temporär sein und sollte nicht gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Der Eingabefokus leitet alle nachfolgenden Tastatureingaben in diesem Fenster. Jedes Fenster, die bisher den Eingabefokus verliert er.  
  
 Die `SetFocus` Member-Funktion sendet eine [WM_KILLFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646282) Meldung im Fenster, das den Eingabefokus verliert und einen [WM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646283) Nachricht an das Fenster, das den Eingabefokus erhält. Außerdem aktiviert, wird das Fenster oder das übergeordnete Element.  
  
 Wenn das aktuelle Fenster aktiv ist, jedoch nicht den Fokus (d. h. kein Fenster den Fokus besitzt), eine beliebige Taste gedrückt Nachrichten erzeugt [WM_SYSCHAR](#onsyschar), [WM_SYSKEYDOWN](#onsyskeydown), oder [WM_SYSKEYUP](#onsyskeyup).  
  
##  <a name="a-namesetfonta--cwndsetfont"></a><a name="setfont"></a>CWnd::SetFont  
 Sendet die `WM_SETFONT` Meldung im Fenster mit der angegebenen Schriftart.  
  
```  
void SetFont(
    CFont* pFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 Zeiger auf ein `CFont` Objekt.  
  
 `bRedraw`  
 `TRUE`für das Fenster unmittelbar im Anschluss neu zeichnen verarbeitet die `WM_SETFONT` Meldung; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode hat keine Auswirkung, wenn das Fenster verarbeitet die `WM_SETFONT` Nachricht. Viele abgeleitete MFC-Klassen `CWnd` diese Nachricht nicht verarbeiten, da sie eine vordefinierte Fensterklasse zugeordnet sind, die einen Meldungshandler für umfasst die `WM_SETFONT` Nachricht. Mit dieser Methode, Klassen, die beim Ableiten von `CWnd` müssen ein Methodenhandler für definieren die `WM_SETFONT` Nachricht.  
  
##  <a name="a-nameseticona--cwndseticon"></a><a name="seticon"></a>CWnd::SetIcon  
 Rufen Sie diese Memberfunktion, um das Handle für ein bestimmtes Symbol festzulegen, wie identifizierte `hIcon`.  
  
```  
HICON SetIcon(
    HICON hIcon,  
    BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Ein Handle für ein Symbol "zurück".  
  
 `bBigIcon`  
 Ein 32 Pixel von 32 Pixel großes Symbol gibt an, ob **TRUE**; ein 16 Pixel von 16 Pixel großes Symbol gibt an, ob **FALSE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Fensterklasse registriert ist, wird ein Symbol ausgewählt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::GetSystemMenu](#getsystemmenu).  
  
##  <a name="a-namesetlayeredwindowattributesa--cwndsetlayeredwindowattributes"></a><a name="setlayeredwindowattributes"></a>CWnd::SetLayeredWindowAttributes  
 Legt die Deckkraft- und Transparenzfarbenschlüssel eines überlappenden Fensters fest.  
  
```  
BOOL SetLayeredWindowAttributes(
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `crKey`  
 Zeiger auf eine **COLORREF** Wert, der den Colorkey Transparenz verwendet werden, wenn das überlappende Fenster verfassen angibt. Alle Pixel, die vom Fenster in dieser Farbe gezeichnet werden transparent sein. Zum Generieren einer **COLORREF**, verwenden Sie die RGB-Makro.  
  
 `bAlpha`  
 Alpha-Wert verwendet, um die Deckkraft des überlappenden Fensters beschreiben. Weitere Informationen finden Sie unter der **SourceConstantAlpha** Mitglied der [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393) Struktur. Wenn `bAlpha` gleich 0 ist, das Fenster transparent ist. Wenn `bAlpha` beträgt 255, das Fenster ist nicht transparent.  
  
 `dwFlags`  
 Gibt die Aktion ausgeführt werden soll. Dieser Parameter kann eine oder mehrere der folgenden Werte sein. Eine Liste der möglichen Werte finden Sie unter [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540).  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmenua--cwndsetmenu"></a><a name="setmenu"></a>CWnd::SetMenu  
 Legt das aktuelle Menü auf das angegebene Menü fest.  
  
```  
BOOL SetMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `pMenu`  
 Gibt das neue Menü. Wenn dieser Parameter **NULL**, das aktuelle Menü wird entfernt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Menü geändert wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bewirkt, dass das Fenster neu gezeichnet wird, um das Menü widerzuspiegeln.  
  
 `SetMenu`ein Menü mit vorherigen werden nicht gelöscht werden. Eine Anwendung aufrufen, sollte der [CMenu::DestroyMenu](../../mfc/reference/cmenu-class.md#destroymenu) Memberfunktion zum Ausführen dieser Aufgabe.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::LoadMenu](../../mfc/reference/cmenu-class.md#loadmenu).  
  
##  <a name="a-namesetownera--cwndsetowner"></a><a name="setowner"></a>CWnd::SetOwner  
 Legt den Besitzer des aktuellen Fensters auf das angegebene fest.  
  
```  
void SetOwner(CWnd* pOwnerWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pOwnerWnd*  
 Identifiziert den neuen Besitzer des Window-Objekts. Wenn dieser Parameter **NULL**, Window-Objekt hat keinen Besitzer.  
  
### <a name="remarks"></a>Hinweise  
 Diese Besitzer kann dann Befehl Nachrichten aus dem aktuellen Fensterobjekt empfangen. Standardmäßig ist das übergeordnete Element des aktuellen Fensters Besitzer.  
  
 Es ist oft hilfreich zum Herstellen von Verbindungen zwischen Windows-Objekte, die nicht mit dem Fensterhierarchie verbunden sind. Beispielsweise [CToolBar](../../mfc/reference/ctoolbar-class.md) sendet Benachrichtigungen an seinen Besitzer statt zu seinem übergeordneten Element. Dadurch wird die Symbolleiste, um das untergeordnete Element von einem Fenster (z. B. ein Anwendungsfenster der OLE-Container) werden beim Senden von Benachrichtigungen auf ein anderes Fenster (z. B. Direktes Rahmenfenster). Außerdem, wenn eine Serverfenster deaktiviert oder wird, während der direkten aktiviert ist bearbeiten, jedes Fenster im Besitz des Rahmenfensters ein- oder ausgeblendet. Diese Besitzrechte explizit festgelegt ist, mit einem Aufruf von `SetOwner`.  
  
 Das Konzept der Besitz dieser Funktion unterscheidet sich das Konzept des Besitzes der [GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515).  
  
##  <a name="a-namesetparenta--cwndsetparent"></a><a name="setparent"></a>CWnd::SetParent  
 Ändert das übergeordnete Fenster eines untergeordneten Fensters.  
  
```  
CWnd* SetParent(CWnd* pWndNewParent);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndNewParent*  
 Identifiziert den neuen übergeordneten Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das vorherige übergeordnete Fensterobjekt zurück. Der zurückgegebene Zeiger kann temporär sein und sollte nicht zur späteren Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das untergeordnete Fenster sichtbar ist, führt Windows den entsprechenden Neuzeichnen und neu aufgebaut.  
  
##  <a name="a-namesetpropertya--cwndsetproperty"></a><a name="setproperty"></a>CWnd::SetProperty  
 Rufen Sie diese Memberfunktion zum Festlegen der OLE-Steuerelementeigenschaft, die durch angegebene `dwDispID`.  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Gibt die festzulegende Eigenschaft an.  
  
 `vtProp`  
 Gibt den Typ der festzulegenden Eigenschaft an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Ein einzelner Parameter des durch `vtProp`angegebenen Typs.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Funktion sollte aufgerufen werden, nur auf einem `CWnd` -Objekt, das ein OLE-Steuerelement darstellt.  
  
 Weitere Informationen zur Verwendung von dieser Memberfunktion mit OLE-Steuerelementcontainer finden Sie im Artikel [ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="a-namesetredrawa--cwndsetredraw"></a><a name="setredraw"></a>CWnd::SetRedraw  
 Eine Anwendung ruft `SetRedraw` zu Änderungen zu zeichnenden oder um zu verhindern, dass die Änderungen neu gezeichnet wird.  
  
```  
void SetRedraw(BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bRedraw`  
 Gibt den Status des Flags liegt. Wenn dieser Parameter **TRUE**, das Neuzeichnen-Flag festgelegt ist, wenn **FALSE**, das Flag gelöscht wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion legt fest oder löscht das Neuzeichnen-Flag. Während das Neuzeichnen Flag deaktiviert ist, wird der Inhalt werden nicht nach jeder Änderung aktualisiert werden und werden nicht aktualisiert werden, bis das Neuzeichnen-Flag festgelegt ist. Z. B. kann eine Anwendung, die ein Listenfeld, das mehrere Elemente hinzugefügt werden soll das Neuzeichnen-Flag zu löschen, fügen Sie die Elemente und legen Sie dann das Neuzeichnen-Flag. Die Anwendung kann schließlich Aufrufen der [Invalidate](#invalidate) oder [InvalidateRect](#invalidaterect) Memberfunktion, die dazu führen, dass im Listenfeld neu gezeichnet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#117;](../../mfc/reference/codesnippet/cpp/cwnd-class_58.cpp)]  
  
##  <a name="a-namesetscrollinfoa--cwndsetscrollinfo"></a><a name="setscrollinfo"></a>CWnd::SetScrollInfo  
 Rufen Sie diese Memberfunktion auf, legen Sie die Informationen, die die `SCROLLINFO` Struktur verwaltet, über eine Bildlaufleiste angezeigt.  
  
```  
BOOL SetScrollInfo(
    int nBar,  
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nBar`  
 Gibt an, ob die Bildlaufleiste ein Steuerelement oder einen Teil der nicht-Clientbereich eines Fensters. Ist er Teil der nicht-Clientbereich, gibt nBar auch an, ob die Bildlaufleiste horizontal, vertikal positioniert wird, oder beides. Es muss eine der folgenden sein:  
  
- **SB_CTL** enthält die Parameter für eine Bildlaufleiste. Der `m_hWnd` -Datenmember muss das Handle des Bildlaufleisten-Steuerelements.  
  
- **SB_HORZ** gibt an, dass das Fenster eine horizontale Bildlaufleiste angezeigt wird.  
  
- **SB_VERT** gibt an, dass das Fenster eine vertikale Bildlaufleiste angezeigt wird.  
  
 `lpScrollInfo`  
 Ein Zeiger auf eine [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur. Finden Sie unter den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu dieser Struktur.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden sollte, an die neue Position wiederzugeben. Wenn `bRedraw` ist **TRUE**, die Bildlaufleiste neu gezeichnet wird. Ist dies **FALSE**, ihn nicht neu gezeichnet wird. Standardmäßig aktualisiert der Bildlaufleiste angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Rückgabe **TRUE**. Andernfalls wird **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Die [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur enthält Informationen über eine Bildlaufleiste, einschließlich die Mindest- und Höchstwerte Bildlauf Positionen, die Größe und die Position des Bildlauffeld (Ziehpunkt). Finden Sie unter der `SCROLLINFO` Struktur Thema in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zum Ändern der Struktur Standardwerte.  
  
 Die MFC-Windows-Meldung Handler, die Position der Bildlaufleiste, anzugeben [CWnd::OnHScroll](#onhscroll) und [CWnd::OnVScroll](#onvscroll), nur 16 Bits der Positionsdaten bereitzustellen. [GetScrollInfo](#getscrollinfo) und `SetScrollInfo` 32 Bits der Bildlaufleiste Positionsdaten bereitzustellen. Daher kann eine Anwendung aufrufen `GetScrollInfo` beim Verarbeiten einer `CWnd::OnHScroll` oder `CWnd::OnVScroll` zum Abrufen von Daten für 32-Bit-Bildlaufleisten-Position.  
  
> [!NOTE]
> [CWnd::GetScrollInfo](#getscrollinfo) ermöglicht Clientanwendungen über 32-Bit-Bildlaufleisten-Positionen.  
  
##  <a name="a-namesetscrollposa--cwndsetscrollpos"></a><a name="setscrollpos"></a>CWnd::SetScrollPos  
 Setzt die aktuelle Position des Bildlauffelds und, falls angefordert, zeichnet die Bildlaufleiste, um die neue Position des Bildlauffelds wiedergegeben.  
  
```  
int SetScrollPos(
    int nBar,  
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nBar`  
 Gibt die Bildlaufleiste so festgelegt werden. Dieser Parameter kann einen der folgenden sein:  
  
- **SB_HORZ** legt die Position des Bildlauffelds auf der horizontalen Bildlaufleiste des Fensters.  
  
- **SB_VERT** legt die Position des Bildlauffelds auf der vertikalen Bildlaufleiste des Fensters.  
  
 `nPos`  
 Gibt die neue Position des Bildlauffelds. Es muss innerhalb des Bereichs der Bildlaufleiste.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden sollte, an die neue Position des Bildlauffelds wiedergegeben. Wenn dieser Parameter **TRUE**, die Bildlaufleiste wird aktualisiert, wenn **FALSE**, die Bildlaufleiste wird nicht aktualisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Position des Bildlauffelds.  
  
### <a name="remarks"></a>Hinweise  
 Festlegen von `bRedraw` auf **FALSE** ist sinnvoll, wenn die Bildlaufleiste durch einen nachfolgenden Aufruf an eine andere Funktion neu gezeichnet wird.  
  
##  <a name="a-namesetscrollrangea--cwndsetscrollrange"></a><a name="setscrollrange"></a>CWnd::SetScrollRange  
 Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.  
  
```  
void SetScrollRange(
    int nBar,  
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nBar`  
 Gibt die Bildlaufleiste so festgelegt werden. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **SB_HORZ** legt den Bereich der horizontalen Bildlaufleiste des Fensters fest.  
  
- **SB_VERT** legt den Bereich der vertikalen Bildlaufleiste des Fensters fest.  
  
 `nMinPos`  
 Gibt die minimale Bildlaufposition.  
  
 `nMaxPos`  
 Gibt die maximale Bildlaufposition.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden soll, entsprechend die Änderung. Wenn `bRedraw` ist **TRUE**, die Bildlaufleiste neu gezeichnet wird, wenn **FALSE**, die Bildlaufleiste nicht neu gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Auch kann verwendet werden, um standard-Bildlaufleisten anzeigen oder ausblenden.  
  
 Eine Anwendung sollte diese Funktion, um eine Bildlaufleiste auszublenden, während der Verarbeitung einer Bildlaufleiste Benachrichtigung nicht aufrufen.  
  
 Wenn der Aufruf von `SetScrollRange` unmittelbar folgt einen Aufruf der [SetScrollPos](#setscrollpos) Member-Funktion, die `bRedraw` -Parameter in der `SetScrollPos` Member-Funktion sollte 0, um zu verhindern, dass die Bildlaufleiste zweimal gezeichnet werden.  
  
 Der Standardbereich für eine Bildlaufleiste standard ist 0 bis 100. Der Standardbereich für eine Bildlaufleiste ist leer (sowohl die `nMinPos` und `nMaxPos` Werte sind 0). Der Unterschied zwischen den Werten, die durch angegebene `nMinPos` und `nMaxPos` darf nicht größer sein als **INT_MAX**.  
  
##  <a name="a-namesettimera--cwndsettimer"></a><a name="settimer"></a>CWnd::SetTimer  
 Installiert einen Systemtimer.  
  
```  
UINT_PTR SetTimer(
    UINT_PTR nIDEvent,  
    UINT nElapse,  
    void (CALLBACK* lpfnTimer)(HWND,  
    UINT, 
    UINT_PTR, 
    DWORD));
```  
  
### <a name="parameters"></a>Parameter  
 `nIDEvent`  
 Gibt einen Timerbezeichner ungleich&0; (null) an. Wenn der Zeitgeberbezeichner eindeutig ist, wird von `SetTimer` der gleiche Wert zurückgegeben. Andernfalls wird von `SetTimer` ein neuer eindeutiger Wert festgelegt und zurückgegeben. Bei einem Fensterzeitgeber (der eine NULL-Rückruffunktion besitzt), muss der Wert nur für andere Fensterzeitgeber eindeutig sein, die dem aktiven Fenster zugeordnet sind. Für einen Rückrufzeitgeber muss der Wert für alle Zeitgeber in allen Prozessen eindeutig sein. Beim Erstellen eines Rückruftimers ist es daher wahrscheinlicher, dass der zurückgegebene Wert von dem von Ihnen angegebenen Wert abweicht.  
  
 `nElapse`  
 Gibt den Timeoutwert oder Intervall in Millisekunden an.  
  
 `lpfnTimer`  
 Gibt die Adresse von der Anwendung bereitgestellten `TimerProc` -Rückruffunktion an, die [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902) Nachrichten. Wenn dieser Parameter `NULL` ist, werden die `WM_TIMER` - Meldungen in der Meldungswarteschlange der Anwendung platziert und vom `CWnd`-Objekt behandelt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Timerbezeichner des neuen Timers, wenn die Funktion erfolgreich ist. Dieser Wert kann dem durch den Parameter `nIDEvent` übergebenen Wert entsprechen oder auch nicht. Eine Anwendung sollte immer übergeben Sie den Rückgabewert in die [KillTimer](#killtimer) Memberfunktion des Zeitgebers. Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Ein Intervallwert wird angegeben, und bei jedem Ausführen des Intervalls wird vom System eine `WM_TIMER`-Meldung in der Meldungswarteschlange der installierenden Anwendung platziert, oder sie wird an eine anwendungsdefinierte `TimerProc`-Rückruffunktion weitergeleitet.  
  
 Die Rückruffunktion `lpfnTimer` muss nicht den Namen `TimerProc` tragen, aber sie muss als statisch deklariert und wie folgt definiert werden.  
  
```  
void CALLBACK TimerProc(
    HWND hWnd,   // handle of CWnd that called SetTimer  
    UINT nMsg,   // WM_TIMER  
    UINT_PTR nIDEvent,   // timer identification  
    DWORD dwTime    // system time);
```  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel werden `CWnd::SetTimer`, `CWnd::OnTimer` und `CWnd::KillTimer` zum Behandeln von `WM_TIMER`-Nachrichten verwendet. Der erste Zeitgeber so festgelegt, dass alle 2 Sekunden eine `WM_TIMER`-Meldung an das Hauptrahmenfenster in `OnStartTimer` zu senden. Der Ereignishandler `OnTimer` behandelt `WM_TIMER`-Meldungen für das Hauptrahmenfenster. Bei dieser Methode piept der PC-Lautsprecher alle 2 Sekunden. Der zweite Zeitgeber sendet alle 3,75 Sekunden eine Meldung an die Rückruffunktion. `OnStopTimer` beendet beide Zeitgeber, indem für jede Zeitgeber-ID `CWnd::KillTimer` aufgerufen wird.  
  
 [!code-cpp[NVC_MFCWindowing&#118;](../../mfc/reference/codesnippet/cpp/cwnd-class_59.cpp)]  
  
##  <a name="a-namesetwindowcontexthelpida--cwndsetwindowcontexthelpid"></a><a name="setwindowcontexthelpid"></a>CWnd::SetWindowContextHelpId  
 Rufen Sie diese Memberfunktion, um das angegebene Fenster eine Hilfekontextbezeichner zuzuordnen.  
  
```  
BOOL SetWindowContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>Parameter  
 `dwContextHelpId`  
 Der Bezeichner für den Hilfe-Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein untergeordnetes Fenster eine Hilfekontextbezeichner nicht besitzt, erbt es die ID des übergeordneten Fensters. Wenn ein Fenster im Besitz einer Hilfekontextbezeichner nicht besitzt, erbt es entsprechend den Bezeichner des Besitzerfensters. Die Vererbung von Hilfe-Kontext-IDs kann eine Anwendung nur einen Bezeichner für ein Dialogfeld, und alle Steuerelemente fest.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#119;](../../mfc/reference/codesnippet/cpp/cwnd-class_60.cpp)]  
  
##  <a name="a-namesetwindowplacementa--cwndsetwindowplacement"></a><a name="setwindowplacement"></a>CWnd::SetWindowPlacement  
 Legt den Anzeigestatus und die normalen (wiederhergestellt), minimierten und maximierten Positionen für ein Fenster fest.  
  
```  
BOOL SetWindowPlacement(const WINDOWPLACEMENT* lpwndpl);
```  
  
### <a name="parameters"></a>Parameter  
 `lpwndpl`  
 Verweist auf eine [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md) -Struktur, die neue Ansichtszustand und Positionen angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
##  <a name="a-namesetwindowposa--cwndsetwindowpos"></a><a name="setwindowpos"></a>CWnd:: SetWindowPos  
 Ändert die Größe, Position und Z-Reihenfolge von untergeordneten, Popup-Fenstern und der obersten Ebene Windows.  
  
```  
BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndInsertAfter`  
 Identifiziert die `CWnd` -Objekt, das vorangestellt wird (größer als sein) diese `CWnd` Objekt in der Z-Reihenfolge. Dieser Parameter kann ein Zeiger auf eine `CWnd` oder **Zeiger** auf einen der folgenden Werte:  
  
- **WndBottom** schaltet das Fenster am unteren Rand der Z-Reihenfolge. Wenn diese `CWnd` wird als oberstes Fenster das Fenster den obersten Status verliert; das Fenster am unteren Rand von allen anderen Fenstern platziert.  
  
- **WndTop** schaltet das Fenster am Anfang der Z-Reihenfolge.  
  
- **WndTopMost** schaltet das Fenster über allen höchsten Windows. Das Fenster behält seine oberste Position, selbst wenn es deaktiviert wird.  
  
- **WndNoTopMost** verschiebt das Fenster am Anfang aller höchsten Fenster (d. h. hinter alle oberste Fenster). Dieses Flag hat keine Auswirkung, wenn das Fenster bereits ein höchsten Fenster ist.  
  
 Informationen zur Verwendung dieses Parameters finden Sie unter dem Abschnitt "Hinweise" in diesem Thema.  
  
 *x*  
 Gibt die neue Position der linken Seite des Fensters.  
  
 *y*  
 Gibt die neue Position für den oberen Rand des Fensters.  
  
 `cx`  
 Gibt die neue Breite des Fensters.  
  
 `cy`  
 Gibt die neue Höhe des Fensters.  
  
 `nFlags`  
 Gibt an, Größe und Position von Optionen. Dieser Parameter kann eine Kombination der folgenden Werte sein:  
  
- **SWP_DRAWFRAME** zeichnet einen Rahmen (definiert, wenn das Fenster erstellt wurde), um das Fenster.  
  
- **SWP_FRAMECHANGED** sendet eine `WM_NCCALCSIZE` Meldung in das Fenster, auch wenn die Größe des Fensters nicht geändert wird. Wenn dieses Flag nicht angegeben ist, `WM_NCCALCSIZE` wird nur gesendet, wenn die Größe des Fensters geändert wird.  
  
- **SWP_HIDEWINDOW** Blendet das Fenster aus.  
  
- `SWP_NOACTIVATE`Das Fenster wird nicht aktiviert werden. Wenn dieses Flag nicht festgelegt ist, wird das Fenster aktiviert und an den Anfang der obersten oder die höchsten verschoben (abhängig von der Einstellung der `pWndInsertAfter` Parameter).  
  
- **SWP_NOCOPYBITS** verwirft den gesamten Inhalt des Clientbereichs. Wenn dieses Flag nicht angegeben ist, werden der gültige Inhalt des Clientbereichs gespeichert und wieder in den Clientbereich kopiert werden, nachdem das Fenster angepasst oder neu angeordnet wird.  
  
- `SWP_NOMOVE`Behält die aktuelle Position (ignoriert die *x* und *y* Parameter).  
  
- **SWP_NOOWNERZORDER** ändert nicht das Besitzerfenster Position in der Z-Reihenfolge.  
  
- **SWP_NOREDRAW** Änderungen wird nicht neu gezeichnet. Wenn dieses Flag festgelegt ist, tritt kein Neuzeichnen jeglicher Art. Dies gilt für den Clientbereich, den nicht-Clientbereich (einschließlich der Titel und Bildlaufleisten) und einen beliebigen Teil des übergeordneten Fensters als Ergebnis der verschobenen Fenster aufgedeckt. Wenn dieses Flag festgelegt ist, muss die Anwendung explizit für ungültig erklären oder neu gezeichnet werden alle Teile des Fensters und des übergeordneten Fensters, das neu gezeichnet werden muss.  
  
- **SWP_NOREPOSITION** wie **SWP_NOOWNERZORDER**.  
  
- **SWP_NOSENDCHANGING** verhindert, empfangen die `WM_WINDOWPOSCHANGING` Nachricht.  
  
- `SWP_NOSIZE`Aktuelle Größe beibehält (ignoriert die `cx` und `cy` Parameter).  
  
- `SWP_NOZORDER`Beibehalten der aktuellen Sortierung (ignoriert `pWndInsertAfter`).  
  
- **SWP_SHOWWINDOW** zeigt das Fenster an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Windows werden auf dem Bildschirm gemäß ihrer Z-Reihenfolge sortiert; Das Fenster am Anfang der Z-Reihenfolge wird vor allen anderen Fenstern in der Reihenfolge angezeigt.  
  
 Alle Koordinaten für untergeordnete Fenster sind Clientkoordinaten (relativ zu der oberen linken Ecke des Clientbereichs des übergeordneten Fensters).  
  
 Ein Fenster kann am Anfang der Z-Reihenfolge verschoben werden durch Festlegen der `pWndInsertAfter` Parameter **& WndTopMost** und sicherstellen, dass die `SWP_NOZORDER` Flag nicht festgelegt wird oder indem Sie ein Fenster der Z-Reihenfolge, damit es über keine vorhandenen oberste Fenster ist. Wenn ein nicht-oberstes Fenster oberster Ebene erfolgt, werden auch seine eigenen Fenster oberster Ebene vorgenommen. Die Besitzer werden nicht geändert.  
  
 Ein oberstes Fenster ist nicht mehr oberste, wenn sie nach unten positioniert ist ( **& WndBottom**) der Z-Reihenfolge oder nach jedem höchsten Fenster. Wenn ein oberstes Fenster höchsten vorgenommen wird, werden alle ihrer Besitzer und die zugehörige Windows auch höchsten Windows vorgenommen.  
  
 Wenn weder `SWP_NOACTIVATE` noch `SWP_NOZORDER` angegeben wird (d. h., wenn die Anwendung angefordert wird, dass ein Fenster werden gleichzeitig aktiviert und in der angegebenen Z-Reihenfolge), die im angegebenen Wert `pWndInsertAfter` wird nur in folgenden Situationen verwendet:  
  
-   Weder **& WndTopMost** noch **& WndNoTopMost** wird angegeben, der `pWndInsertAfter` Parameter.  
  
-   Dieses Fenster ist nicht das aktive Fenster.  
  
 Eine Anwendung kann kein inaktiver aktiviert, ohne dass es auch am Anfang der Z-Reihenfolge. Clientanwendungen können die Z-Reihenfolge eine aktivierte Fenster ohne Einschränkungen ändern.  
  
 Ein nicht-oberstes Fenster kann ein oberstes Fenster verwenden, besitzen aber nicht umgekehrt. Jedes Fenster (z. B. ein Dialogfeld), die im Besitz eines obersten Fensters ist selbst ein oberstes Fenster, um sicherzustellen, dass alle systemeigener Windows über deren Besitzer bleiben.  
  
 Mit Windows-Versionen 3.1 und höher, Windows am Anfang der Z-Reihenfolge verschoben und dort durch Festlegen gesperrt werden können ihre **WS_EX_TOPMOST** Formate. Solche oberstes Fenster verwaltet die oberste Position, selbst wenn es deaktiviert. Beispielsweise wählen Sie den Befehl WinHelp immer im Vordergrund macht das oberste Hilfefenster, und es dann sichtbar bleibt, wenn Sie zu Ihrer Anwendung zurückzukehren.  
  
 Rufen Sie zum Erstellen eines Fensters der obersten `SetWindowPos` mit der `pWndInsertAfter` Parameter gleich **& WndTopMost**, oder legen Sie die **WS_EX_TOPMOST** formatieren, wenn Sie das Fenster erstellen.  
  
 Die Z-Reihenfolge enthält alle Fenster mit der **WS_EX_TOPMOST** Formatvorlage, ein Fenster verschoben der **& WndTopMost** Wert wird am Anfang aller höchsten Fenster, jedoch unterhalb oberste Fenster platziert. Wenn eine Anwendung eine inaktive Fenster ohne aktiviert die **WS_EX_TOPMOST** bit, wird das Fenster über alle höchsten Windows aber unter oberste Fenster verschoben.  
  
 Wenn `SetWindowPos` wird aufgerufen, wenn die `pWndInsertAfter` Parameter ist **& WndBottom** und `CWnd` wird als oberstes Fenster das Fenster den obersten Status verliert ( **WS_EX_TOPMOST** deaktiviert ist), und das Fenster am unteren Rand der Z-Reihenfolge platziert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#120;](../../mfc/reference/codesnippet/cpp/cwnd-class_61.cpp)]  
  
##  <a name="a-namesetwindowrgna--cwndsetwindowrgn"></a><a name="setwindowrgn"></a>CWnd::SetWindowRgn  
 Rufen Sie diese Memberfunktion zum Bereich des Fensters festlegen.  
  
```  
int SetWindowRgn(
    HRGN hRgn,  
    BOOL bRedraw);
```  
  
### <a name="parameters"></a>Parameter  
 `hRgn`  
 Ein Handle für einen Bereich.  
  
 `bRedraw`  
 Wenn **TRUE**, das Betriebssystem zeichnet das Fenster nach dem Festlegen der Region; andernfalls nicht der Fall. In der Regel `bRedraw` auf **TRUE** , wenn das Fenster sichtbar ist. Wenn auf festgelegt **TRUE**, sendet das System die `WM_WINDOWPOSCHANGING` und `WM_WINDOWPOSCHANGED` Nachrichten an das Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich NULL. Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null.  
  
### <a name="remarks"></a>Hinweise  
 Die Koordinaten der Fensterbereich des Fensters sind relativ zur oberen linken Ecke des Fensters, nicht den Clientbereich des Fensters.  
  
 Nach einem erfolgreichen Aufruf von `SetWindowRgn`, das Betriebssystem besitzt, das vom Handle Region die Region `hRgn`. Das Betriebssystem macht eine Kopie des Bereichs nicht, also nehmen Sie keine weiteren Funktionsaufrufe mit diesem Handle Region und schließen Sie diese Region Handle nicht.  
  
##  <a name="a-namesetwindowtexta--cwndsetwindowtext"></a><a name="setwindowtext"></a>CWnd::SetWindowText  
 Wird der Titel des Fensters auf den angegebenen Text.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Verweist auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt oder Null-terminierte Zeichenfolge als den neuen Text für Titel oder Steuerelement verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Fenster ein Steuerelement ist, wird der Text innerhalb des Steuerelements festgelegt.  
  
 Diese Funktion bewirkt, dass ein [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) Nachricht an das Fenster gesendet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#121;](../../mfc/reference/codesnippet/cpp/cwnd-class_62.cpp)]  
  
##  <a name="a-nameshowcareta--cwndshowcaret"></a><a name="showcaret"></a>CWnd::ShowCaret  
 Zeigt die Einfügemarke auf dem Bildschirm an der aktuellen Position der Einfügemarke.  
  
```  
void ShowCaret();
```  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Anzeige erfolgt, blinkt das Caretzeichen automatisch auf.  
  
 Der `ShowCaret` Member-Funktion zeigt nur der Einfügemarke mit einer aktuellen Form und nicht ausgeblendet mehrmals nacheinander. Wenn die Einfügemarke nicht Besitzer dieses Fenster ist, wird die Einfügemarke nicht angezeigt.  
  
 Die Einfügemarke ausgeblendet wird. Wenn die [HideCaret](#hidecaret) -Memberfunktion aufgerufen wurde fünf Mal fortlaufend `ShowCaret` muss fünf Mal aufgerufen werden, um die Einfügemarke anzuzeigen.  
  
 Die Einfügemarke wird eine freigegebene Ressource. Das Fenster zeigt die Einfügemarke nur, wenn sie den Eingabefokus besitzt oder aktiv ist.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::CreateCaret](#createcaret).  
  
##  <a name="a-nameshowownedpopupsa--cwndshowownedpopups"></a><a name="showownedpopups"></a>CWnd::ShowOwnedPopups  
 Anzeigen oder Ausblenden aller Popup-Fenster, die im Besitz dieses Fensters.  
  
```  
void ShowOwnedPopups(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob Popupfenster angezeigt oder ausgeblendet werden. Wenn dieser Parameter **TRUE**, werden alle ausgeblendeten Popup-Fenster angezeigt. Wenn dieser Parameter **FALSE**, werden alle sichtbaren Popup-Fenster ausgeblendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd:: SetWindowPos](#setwindowpos).  
  
##  <a name="a-nameshowscrollbara--cwndshowscrollbar"></a><a name="showscrollbar"></a>CWnd::ShowScrollBar  
 Anzeigen oder ausblenden eine Bildlaufleiste.  
  
```  
void ShowScrollBar(
    UINT nBar,  
    BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nBar`  
 Gibt an, ob die Bildlaufleiste ein Steuerelement oder einen Teil der nicht-Clientbereich eines Fensters. Ist er Teil der nicht-Clientbereich `nBar` gibt außerdem an, ob die Bildlaufleiste horizontal, vertikal positioniert wird, oder beides. Es muss eine der folgenden sein:  
  
- **SB_BOTH** gibt die horizontale und vertikale Schiebeleisten des Fensters.  
  
- **SB_HORZ** gibt an, dass das Fenster eine horizontale Bildlaufleiste angezeigt wird.  
  
- **SB_VERT** gibt an, dass das Fenster eine vertikale Bildlaufleiste angezeigt wird.  
  
 `bShow`  
 Gibt an, ob Windows Blendet die Bildlaufleiste. Wenn dieser Parameter **TRUE**, die Schiebeleiste angezeigt wird, andernfalls die Bildlaufleiste ausgeblendet ist.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung sollte nicht aufrufen `ShowScrollBar` eine Bildlaufleiste ausgeblendet, während der Verarbeitung einer Bildlaufleiste Benachrichtigung.  
  
##  <a name="a-nameshowwindowa--cwndshowwindow"></a><a name="showwindow"></a>ShowWindow  
 Legt den Sichtbarkeitszustand des Fensters fest.  
  
```  
BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Parameter  
 `nCmdShow`  
 Gibt an, wie die `CWnd` angezeigt werden. Es muss einer der folgenden Werte sein:  
  
- **SW_HIDE** Blendet das Fenster aus und übergibt die Aktivierung zu einem anderen Fenster.  
  
- **SW_MINIMIZE** minimiert das Fenster, und das Fenster das obersten Ebene in der Liste des Systems aktiviert.  
  
- **SW_RESTORE** aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert wird, wird es von Windows in ihrer ursprünglichen Größe und Position wiederhergestellt.  
  
- **SW_SHOW** wird das Fenster aktiviert und in seiner aktuellen Größe und Position angezeigt.  
  
- **SW_SHOWMAXIMIZED** wird das Fenster aktiviert und wird in Form eines maximierten Fensters angezeigt.  
  
- **SW_SHOWMINIMIZED** wird das Fenster aktiviert und wird als Symbol angezeigt.  
  
- **SW_SHOWMINNOACTIVE** zeigt das Fenster als Symbol an. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNA** zeigt das Fenster im aktuellen Zustand an. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNOACTIVATE** zeigt das Fenster in der letzten Größe und Position. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNORMAL** aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert wird, wird es von Windows in ihrer ursprünglichen Größe und Position wiederhergestellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Fenster bereits sichtbar war; 0, wenn die `CWnd` wurde zuvor ausgeblendet.  
  
### <a name="remarks"></a>Hinweise  
 `ShowWindow`muss nur einmal aufgerufen werden, pro Anwendung für das Hauptfenster mit [CWinApp::m_nCmdShow](../../mfc/reference/cwinapp-class.md#m_ncmdshow). Nachfolgende Aufrufe von `ShowWindow` müssen, verwenden Sie einen der Werte anstelle der oben aufgeführten `CWinApp::m_nCmdShow`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::CalcWindowRect](#calcwindowrect).  
  
##  <a name="a-namesubclassdlgitema--cwndsubclassdlgitem"></a><a name="subclassdlgitem"></a>CWnd::SubclassDlgItem  
 Rufen Sie diese Memberfunktion auf "dynamisch Unterklasse" ein Steuerelement aus einer Dialogfeldvorlage erstellt und an diese angefügt `CWnd` Objekt.  
  
```  
BOOL SubclassDlgItem(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 ID des Steuerelements  
  
 `pParent`  
 Übergeordnete Element des Steuerelements (normalerweise ein Dialogfeld).  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Steuerelement dynamisch als Unterklasse definiert ist, leitet Windows-Meldungen über die `CWnd`des Nachricht zuordnen und Meldungshandler in Aufrufen der `CWnd`der ersten Klasse. Nachrichten, die an die Basisklasse übergeben werden, werden an der Standardhandler für die Nachricht in das Steuerelement übergeben werden.  
  
 Diese Memberfunktion fügt die Windows-Steuerelement für eine `CWnd` -Objekt und ersetzt das Steuerelement **WndProc** und **fxWndProc** Funktionen. Die Funktion speichert das alte **WndProc** in den Speicherort zurückgegeben wird, indem Sie die `GetSuperWndProcAddr` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#122;](../../mfc/reference/codesnippet/cpp/cwnd-class_63.cpp)]  
  
##  <a name="a-namesubclasswindowa--cwndsubclasswindow"></a><a name="subclasswindow"></a>CWnd:: SubclassWindow  
 Rufen Sie diese Memberfunktion auf "dynamisch Unterklasse" ein Fenster, und fügen Sie es mit diesem `CWnd` Objekt.  
  
```  
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Ein Handle für das Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Fenster dynamisch als Unterklasse definiert ist, leitet Windows-Nachrichten über die `CWnd`des Nachricht zuordnen und Meldungshandler in Aufrufen der `CWnd`der ersten Klasse. Nachrichten, die an die Basisklasse übergeben werden, werden an den Standard-Meldungshandler im Fenster übergeben werden.  
  
 Diese Memberfunktion fügt die Windows-Steuerelement für eine `CWnd` -Objekt und ersetzt des Fensters **WndProc** und **fxWndProc** Funktionen. Die Funktion speichert einen Zeiger auf die alte **WndProc** in den `CWnd` Objekt.  
  
> [!NOTE]
>  Das Fenster muss nicht bereits zu einem MFC-Objekt angefügt werden, wenn diese Funktion aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#123;](../../mfc/reference/codesnippet/cpp/cwnd-class_64.cpp)]  
  
##  <a name="a-nameunlockwindowupdatea--cwndunlockwindowupdate"></a><a name="unlockwindowupdate"></a>CWnd::UnlockWindowUpdate  
 Rufen Sie diese Memberfunktion, um ein Fenster mit aufheben wurde `CWnd::LockWindowUpdate`.  
  
```  
void UnlockWindowUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Nur ein Fenster zu einem Zeitpunkt kann gesperrt werden, mithilfe von `LockWindowUpdate`. Finden Sie unter [CWnd::LockWindowUpdate](#lockwindowupdate) oder die Win32-Funktion [LockWindowUpdate](http://msdn.microsoft.com/library/windows/desktop/dd145034) Weitere Informationen über das Sperren von Windows.  
  
##  <a name="a-nameunsubclasswindowa--cwndunsubclasswindow"></a><a name="unsubclasswindow"></a>CWnd::UnsubclassWindow  
 Rufen Sie diese Memberfunktion festlegen **WndProc** auf den ursprünglichen Wert zurück und trennen Sie das Fenster identifizierten `HWND` aus der **CWnd** Objekt.  
  
```  
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das unsubclassed Fenster.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd:: SubclassWindow](#subclasswindow).  
  
##  <a name="a-nameupdatedataa--cwndupdatedata"></a><a name="updatedata"></a>CWnd::UpdateData  
 Rufen Sie diese Memberfunktion auf, Daten in einem Dialogfeld zu initialisieren oder zum Abrufen und Überprüfen von Dialogfelddaten.  
  
```  
BOOL UpdateData(BOOL bSaveAndValidate = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bSaveAndValidate`  
 Flag, das angibt, ob im Dialogfeld initialisiert wird ( **FALSE**) oder die Daten abgerufen werden ( **TRUE**).  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich ist; andernfalls 0. Wenn *bSaveAndValidat*e **TRUE**, und klicken Sie dann ein Wert ungleich NULL bedeutet, dass die Daten erfolgreich überprüft werden.  
  
### <a name="remarks"></a>Hinweise  
 Ruft das Framework automatisch `UpdateData` mit `bSaveAndValidate` festgelegt **FALSE** Wenn ein modales Dialogfeld erstellt wird, in der Standardimplementierung der [CDialog::](../../mfc/reference/cdialog-class.md#oninitdialog). Der Aufruf erfolgt, bevor das Dialogfeld angezeigt wird. Die standardmäßige Implementierung des [CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok) ruft diese Memberfunktion mit `bSaveAndValidate` festgelegt **TRUE** zum Abrufen der Daten, und bei Erfolg wird das Dialogfeld zu schließen. (Wenn im Dialogfeld die Schaltfläche Abbrechen geklickt wird, wird das Dialogfeld ohne die abgerufenen Daten geschlossen.)  
  
##  <a name="a-nameupdatedialogcontrolsa--cwndupdatedialogcontrols"></a><a name="updatedialogcontrols"></a>CWnd::UpdateDialogControls  
 Rufen Sie diese Memberfunktion zum Aktualisieren Sie den Zustand von Schaltflächen und anderen Steuerelementen in einem Dialogfeld oder ein Fenster, das verwendet die [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) Rückrufmechanismus.  
  
```  
void UpdateDialogControls(
    CCmdTarget* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 `pTarget`  
 Verweist auf das Hauptrahmenfenster der Anwendung und dient zum Weiterleiten von Nachrichten Update *.*  
  
 `bDisableIfNoHndler`  
 Flag, die angibt, ob ein Steuerelement, das kein updatehandler verfügbar ist, automatisch als deaktiviert angezeigt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Ein untergeordnetes Steuerelement keinen Handler und `bDisableIfNoHndler` ist **TRUE**, und klicken Sie dann das untergeordnete Steuerelement deaktiviert wird.  
  
 Das Framework ruft diese Member-Funktion für Steuerelemente im Dialogfeld Balken oder Symbolleisten als Teil der Anwendung im Leerlauf verarbeiten.  
  
##  <a name="a-nameupdatelayeredwindowa--cwndupdatelayeredwindow"></a><a name="updatelayeredwindow"></a>CWnd::UpdateLayeredWindow  
 Aktualisiert die Position, Größe, Form, Inhalte und Lichtdurchlässigkeit eines überlappenden Fensters.  
  
```  
BOOL UpdateLayeredWindow(
    CDC* pDCDst,  
    POINT* pptDst,  
    SIZE* psize,  
    CDC* pDCSrc,  
    POINT* pptSrc,  
    COLORREF crKey,  
    BLENDFUNCTION* pblend,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `pDCDst`  
 Ein Zeiger auf einen Gerätekontext für den Bildschirm. Hiermit wird für die Palette Farbe entsprechen, wenn der Inhalt im Befehlsfenster aktualisiert werden. Wenn `pDCDst` ist **NULL**, die Standardpalette verwendet werden.  
  
 If `pDCSrc` is **NULL**, `pDCDst` must be **NULL**.  
  
 `pptDst`  
 Ein Zeiger auf eine **Punkt** -Struktur, die die neue Bildschirmposition des überlappenden Fensters angibt. Wenn die aktuelle Position nicht ändert, `pptDst` kann **NULL**.  
  
 *psize*  
 Zeiger auf eine **Größe** Struktur, die die neue Größe des überlappenden Fensters angibt. Wenn die Größe des Fensters nicht ändert, *Psize* kann **NULL**.  
  
 If `pDCSrc` is **NULL**, *psize* must be **NULL**.  
  
 `pDCSrc`  
 Ein Zeiger auf einen Domänencontroller für die Fläche, die das überlappende Fenster definiert. Wenn die Form und die visuellen Kontext des Fensters nicht ändern, `pDCSrc` kann **NULL**.  
  
 `pptSrc`  
 Zeiger auf eine **Punkt** -Struktur, die den Speicherort der Ebene im Gerätekontext angibt.  
  
 If `pDCSrc` is **NULL**, `pptSrc` should be **NULL**.  
  
 `crKey`  
 Zeiger auf eine **COLORREF** Wert, der den Colorkey Transparenz verwendet werden, wenn das überlappende Fenster verfassen angibt. Alle Pixel, die vom Fenster in dieser Farbe gezeichnet werden transparent sein. Zum Generieren einer **COLORREF**, verwenden Sie die RGB-Makro.  
  
 *pblend*  
 Zeiger auf eine [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393) Struktur, die verwendet werden, wenn das überlappende Fenster verfassen Transparenz den Wert angibt.  
  
 `dwFlags`  
 Gibt die Aktion ausgeführt werden soll. Dieser Parameter kann eine oder mehrere der folgenden Werte sein. Eine Liste der möglichen Werte finden Sie unter [UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556).  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameupdatewindowa--cwndupdatewindow"></a><a name="updatewindow"></a>CWnd::UpdateWindow  
 Aktualisiert den Clientbereich durch Senden einer [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht, falls es sich bei der Aktualisierungsbereich nicht leer ist.  
  
```  
void UpdateWindow();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `UpdateWindow` Member-Funktion sendet eine `WM_PAINT` Nachricht direkt unter Umgehung der Warteschlange. Wenn der Aktualisierungsbereich leer ist, `WM_PAINT` wird nicht gesendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#124;](../../mfc/reference/codesnippet/cpp/cwnd-class_65.cpp)]  
  
##  <a name="a-namevalidaterecta--cwndvalidaterect"></a><a name="validaterect"></a>CWnd::ValidateRect  
 Überprüft den Clientbereich innerhalb des angegebenen Rechtecks durch entfernen das Rechteck aus dem Aktualisierungsbereich des Fensters.  
  
```  
void ValidateRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT-Struktur](../../mfc/reference/rect-structure1.md) , enthält der Clientkoordinaten des Rechtecks aus dem Aktualisierungsbereich entfernt werden soll. Wenn `lpRect` ist **NULL**, das gesamte Fenster wird überprüft.  
  
### <a name="remarks"></a>Hinweise  
 Die [BeginPaint](#beginpaint) Memberfunktion überprüft automatisch den gesamten Clientbereich. Weder der `ValidateRect` noch die [ValidateRgn](#validatergn) -Memberfunktion aufgerufen werden, wenn ein Teil der Aktualisierungsbereich muss vor dem validiert werden [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) wird als Nächstes generiert.  
  
 Windows weiterhin generieren `WM_PAINT` Nachrichten, bis der aktuelle Aktualisierungsbereich überprüft wird.  
  
##  <a name="a-namevalidatergna--cwndvalidatergn"></a><a name="validatergn"></a>CWnd::ValidateRgn  
 Überprüft den Clientbereich innerhalb dieser Region durch Entfernen der Region aus dem aktuellen Update im Bereich des Fensters.  
  
```  
void ValidateRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Ein Zeiger auf eine [CRgn](../../mfc/reference/crgn-class.md) -Objekt, das einen Bereich, definiert, identifiziert den Bereich aus dem Aktualisierungsbereich entfernt werden soll. Wenn dieser Parameter **NULL**, der gesamten Clientbereich wird entfernt.  
  
### <a name="remarks"></a>Hinweise  
 Die angegebene Region muss zuvor von einer Region-Funktion erstellt worden sein. Die Region-Koordinaten werden als Clientkoordinaten angesehen.  
  
 Die [BeginPaint](#beginpaint) Memberfunktion überprüft automatisch den gesamten Clientbereich. Weder der [ValidateRect](#validaterect) noch die `ValidateRgn` -Memberfunktion aufgerufen werden, wenn ein Teil der Aktualisierungsbereich werden, bevor der nächste überprüft muss [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Meldung generiert wird.  
  
##  <a name="a-namewindowfrompointa--cwndwindowfrompoint"></a><a name="windowfrompoint"></a>CWnd::WindowFromPoint  
 Ruft ab, das Fenster, das den angegebenen Punkt enthält. `point` geben die Bildschirmkoordinaten eines Punkts auf dem Bildschirm.  
  
```  
static CWnd* PASCAL WindowFromPoint(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Gibt eine [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt oder [zeigen](../../mfc/reference/point-structure1.md) -Datenstruktur, die den Punkt zu überprüfende definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Window-Objekt, das in dem der Punkt liegt. Es ist **NULL** Wenn kein Fenster am angegebenen Punkt vorhanden ist. Der zurückgegebene Zeiger kann temporär sein und sollte nicht zur späteren Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 `WindowFromPoint`ein Fenster ausgeblendet oder deaktiviert werden, auch wenn der Punkt innerhalb des Fensters ist nicht abrufen. Eine Anwendung verwenden, sollten die [ChildWindowFromPoint](#childwindowfrompoint) Memberfunktion für eine restriktive Suche.  
  
##  <a name="a-namewindowproca--cwndwindowproc"></a><a name="windowproc"></a>CWnd::WindowProc  
 Stellt ein Windows-Verfahren ( `WindowProc`) für eine `CWnd` Objekt.  
  
```  
virtual LRESULT WindowProc(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Gibt die Windows-Meldung verarbeitet werden.  
  
 `wParam`  
 Enthält zusätzliche Informationen, die bei der Verarbeitung der Nachricht verwendet. Der Wert des Parameters hängt von der Nachricht ab.  
  
 `lParam`  
 Enthält zusätzliche Informationen, die bei der Verarbeitung der Nachricht verwendet. Der Wert des Parameters hängt von der Nachricht ab.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert hängt von der Meldung ab.  
  
### <a name="remarks"></a>Hinweise  
 Er sendet Nachrichten über das Fenster Nachricht zuordnen.  
  
##  <a name="a-namewinhelpa--cwndwinhelp"></a><a name="winhelp"></a>CWnd::WinHelp  
 Wird aufgerufen, um die WinHelp-Anwendung zu initiieren.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parameter  
 `dwData`  
 Gibt zusätzliche Daten an. Der verwendete Wert hängt vom Wert von der `nCmd` Parameter.  
  
 `nCmd`  
 Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und deren Auswirkung auf die der `dwData` -Parameter finden Sie unter der [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows-Funktion der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CWinApp::WinHelp](../../mfc/reference/cwinapp-class.md#winhelp) Weitere Informationen.  
  
##  <a name="a-nameregistertouchwindowa--cwndregistertouchwindow"></a><a name="registertouchwindow"></a>CWnd::RegisterTouchWindow  
 Register oder hebt die Registrierung von Windows Touch-Unterstützung.  
  
```  
BOOL RegisterTouchWindow(
    BOOL bRegister = TRUE,  
    ULONG ulFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `bRegister`  
 `TRUE`Gibt an, registrieren Sie sich Windows touch-Unterstützung; `FALSE` andernfalls.  
  
 `ulFlags`  
 Ein Satz von Bitflags, die optionale Änderungen angeben. Dieses Feld kann 0 oder einen der folgenden Werte enthalten: TWF_FINETOUCH, TWF_WANTPALM.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameresizedynamiclayouta--cwndresizedynamiclayout"></a><a name="resizedynamiclayout"></a>CWnd::ResizeDynamicLayout  
 Wird durch das Framework aufgerufen, wenn sich die Fenstergröße ändert, um das Layout der untergeordneten Fenster anzupassen, wenn das dynamische Layout für das Fenster aktiviert ist.  
  
```  
virtual void ResizeDynamicLayout();
```  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)

