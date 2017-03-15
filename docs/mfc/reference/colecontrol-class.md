---
title: COleControl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControl
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, MFC
- windowless controls, MFC
- windowless controls
- controls [MFC], OLE
- controls [MFC], windowless
- COleControl class
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
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
ms.openlocfilehash: 7ef5621aaf940be3ebe2806971dfc65d06972a5a
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrol-class"></a>COleControl-Klasse
Eine leistungsstarke Basisklasse zum Entwickeln von OLE-Steuerelementen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleControl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControl::COleControl](#colecontrol)|Erstellt ein `COleControl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControl::AmbientAppearance](#ambientappearance)|Ruft die aktuelle Darstellung des Steuerelements ab.|  
|[COleControl::AmbientBackColor](#ambientbackcolor)|Gibt den Wert der ambient-BackColor-Eigenschaft.|  
|[COleControl::AmbientDisplayName](#ambientdisplayname)|Gibt den Namen des Steuerelements als angegebenen Container zurück.|  
|[COleControl::AmbientFont](#ambientfont)|Gibt den Wert der ambient-Font-Eigenschaft.|  
|[COleControl::AmbientForeColor](#ambientforecolor)|Gibt den Wert der ambient-ForeColor-Eigenschaft.|  
|[COleControl:: AmbientLocaleID](#ambientlocaleid)|Gibt den Container Gebietsschema-ID.|  
|[COleControl::AmbientScaleUnits](#ambientscaleunits)|Gibt den Typ der vom Container verwendeten Einheiten.|  
|[COleControl::AmbientShowGrabHandles](#ambientshowgrabhandles)|Bestimmt, ob die Ziehpunkte angezeigt werden soll.|  
|[COleControl::AmbientShowHatching](#ambientshowhatching)|Bestimmt, ob Schraffur angezeigt werden soll.|  
|[COleControl::AmbientTextAlign](#ambienttextalign)|Gibt den Typ der Ausrichtung des Texts durch den Container angegeben.|  
|[COleControl::AmbientUIDead](#ambientuidead)|Bestimmt, ob das Steuerelement auf der Benutzeroberfläche Aktionen reagieren soll.|  
|[COleControl::AmbientUserMode](#ambientusermode)|Bestimmt den Modus des Containers.|  
|[COleControl::BoundPropertyChanged](#boundpropertychanged)|Benachrichtigt dem Container über eine gebundene Eigenschaft geändert wurde.|  
|[COleControl::BoundPropertyRequestEdit](#boundpropertyrequestedit)|Fordert die Berechtigung so bearbeiten Sie den Wert der Eigenschaft.|  
|[COleControl::ClientToParent](#clienttoparent)|Übersetzt einen Punkt relativ zum Ursprung des Steuerelements, bis zu einem Zeitpunkt relativ zum Ursprung des Containers.|  
|[COleControl::ClipCaretRect](#clipcaretrect)|Ein Caretzeichen Rechteck passt, wenn es von einem Steuerelement überlappt wird.|  
|[COleControl::ControlInfoChanged](#controlinfochanged)|Rufen Sie diese Funktion aus, nachdem das mnemonische Zeichen vom Steuerelement verarbeitet geändert wurden.|  
|[COleControl::DisplayError](#displayerror)|Werden vordefinierte Fehlerereignisse Benutzer des Steuerelements angezeigt.|  
|[COleControl::DoClick](#doclick)|Implementierung der Aktie `DoClick` Methode.|  
|[COleControl:: DoPropExchange](#dopropexchange)|Serialisiert die Eigenschaften einer `COleControl` Objekt.|  
|[COleControl::DoSuperclassPaint](#dosuperclasspaint)|Zeichnet ein OLE-Steuerelement, das von einem Windows-Steuerelement erstellt wurde.|  
|[COleControl::EnableSimpleFrame](#enablesimpleframe)|Ermöglicht die einfache Frame-Unterstützung für ein Steuerelement.|  
|[COleControl::ExchangeExtent](#exchangeextent)|Serialisiert die Breite und Höhe des Steuerelements.|  
|[COleControl::ExchangeStockProps](#exchangestockprops)|Serialisiert die vordefinierten Eigenschaften des Steuerelements.|  
|[COleControl:: ExchangeVersion](#exchangeversion)|Serialisiert die Versionsnummer des Steuerelements.|  
|[COleControl::FireClick](#fireclick)|Löst die Stock `Click` Ereignis.|  
|[COleControl::FireDblClick](#firedblclick)|Löst die Stock `DblClick` Ereignis.|  
|[COleControl:: FireError](#fireerror)|Löst die Stock `Error` Ereignis.|  
|[COleControl::](#fireevent)|Löst ein benutzerdefiniertes Ereignis.|  
|[COleControl::FireKeyDown](#firekeydown)|Löst die Stock `KeyDown` Ereignis.|  
|[COleControl::FireKeyPress](#firekeypress)|Löst die Stock `KeyPress` Ereignis.|  
|[COleControl::FireKeyUp](#firekeyup)|Löst die Stock `KeyUp` Ereignis.|  
|[COleControl::FireMouseDown](#firemousedown)|Löst die Stock `MouseDown` Ereignis.|  
|[COleControl::FireMouseMove](#firemousemove)|Löst die Stock `MouseMove` Ereignis.|  
|[COleControl::FireMouseUp](#firemouseup)|Löst die Stock `MouseUp` Ereignis.|  
|[COleControl::FireReadyStateChange](#firereadystatechange)|Löst ein Ereignis aus, wenn der aktuelle Status des Steuerelements ändert.|  
|[COleControl:: GetActivationPolicy](#getactivationpolicy)|Ändert das Standardverhalten für die Aktivierung von einem Steuerelement, unterstützt die `IPointerInactive` Schnittstelle.|  
|[COleControl:: GetAmbientProperty](#getambientproperty)|Gibt den Wert der angegebenen ambient-Eigenschaft.|  
|[COleControl::GetAppearance](#getappearance)|Gibt den Wert der vordefinierten Appearance-Eigenschaft.|  
|[COleControl::GetBackColor](#getbackcolor)|Gibt den Wert der vordefinierten BackColor-Eigenschaft.|  
|[COleControl::GetBorderStyle](#getborderstyle)|Gibt den Wert der vordefinierten BorderStyle-Eigenschaft.|  
|[COleControl::GetCapture](#getcapture)|Bestimmt, ob ein Steuerelementobjekt fensterlose, aktiviert das Erfassen von Mauseingaben.|  
|[COleControl::GetClassID](#getclassid)|Ruft die OLE-Klassen-ID des Steuerelements ab.|  
|[COleControl::GetClientOffset](#getclientoffset)|Ruft die Differenz zwischen der oberen linken Ecke des rechteckigen Bereichs des Steuerelements und der linken Ecke des Clientbereichs ab.|  
|[COleControl::GetClientRect](#getclientrect)|Ruft die Größe des Clientbereichs des Steuerelements ab.|  
|[COleControl::GetClientSite](#getclientsite)|Abfragen ein Objekts für den Zeiger auf die aktuelle Site in dessen Container.|  
|[COleControl:: GetControlFlags](#getcontrolflags)|Ruft die Steuerelement-Flageinstellungen ab.|  
|[COleControl::GetControlSize](#getcontrolsize)|Gibt die Position und Größe des OLE-Steuerelements.|  
|[COleControl::GetDC](#getdc)|Ermöglicht ein fensterloses Steuerelement einen Gerätekontext des Containers ab.|  
|[COleControl::GetEnabled](#getenabled)|Gibt den Wert der Aktie Enabled-Eigenschaft.|  
|[COleControl::GetExtendedControl](#getextendedcontrol)|Ruft einen Zeiger zu einem erweiterten Steuerelements-Objekt, das dem Container gehören.|  
|[COleControl::GetFocus](#getfocus)|Bestimmt, ob das Steuerelement den Fokus besitzt.|  
|[COleControl::GetFont](#getfont)|Gibt den Wert der vordefinierten Font-Eigenschaft.|  
|[COleControl::GetFontTextMetrics](#getfonttextmetrics)|Gibt die Metriken von einem `CFontHolder` Objekt.|  
|[COleControl::GetForeColor](#getforecolor)|Gibt den Wert der vordefinierten ForeColor-Eigenschaft.|  
|[COleControl::GetHwnd](#gethwnd)|Gibt den Wert der vordefinierten hWnd-Eigenschaft.|  
|[COleControl::GetMessageString](#getmessagestring)|Stellt den Text der Statusleiste für ein Menüelement bereit.|  
|[COleControl::GetNotSupported](#getnotsupported)|Verhindert den Zugriff auf den Eigenschaftswert eines Steuerelements, durch den Benutzer.|  
|[COleControl::GetReadyState](#getreadystate)|Gibt den Zustand des Steuerelements bereit.|  
|[COleControl::GetRectInContainer](#getrectincontainer)|Gibt das Rechteck des Steuerelements relativ zu seinem Container.|  
|[COleControl::GetStockTextMetrics](#getstocktextmetrics)|Gibt die Metriken der vordefinierten Font-Eigenschaft zurück.|  
|[COleControl::GetText](#gettext)|Gibt den Wert der Systemeigenschaft Text oder die Beschriftung zurück.|  
|[COleControl:: GetWindowlessDropTarget](#getwindowlessdroptarget)|Überschreiben Sie, um ein fensterloses Steuerelement das Ziel des Drag und drop-Operationen zulassen.|  
|[COleControl::InitializeIIDs](#initializeiids)|Benachrichtigt die Basisklasse den IIDs, die das Steuerelement verwendet.|  
|[COleControl::InternalGetFont](#internalgetfont)|Gibt ein `CFontHolder` -Objekt für die vordefinierte Schriftarteigenschaft.|  
|[COleControl::InternalGetText](#internalgettext)|Ruft die vordefinierte Beschriftung oder Text-Eigenschaft ab.|  
|[COleControl::InternalSetReadyState](#internalsetreadystate)|Legt den Zustand des Steuerelements Bereitschaft und löst das Ereignis Zustandsänderung bereit.|  
|[COleControl::InvalidateControl](#invalidatecontrol)|Erklärt einen Bereich des angezeigten Steuerelements, dass es neu gezeichnet wird.|  
|[COleControl::InvalidateRgn](#invalidatergn)|Erklärt die Container Clientbereich innerhalb dieser Region. Kann verwendet werden, in der Region Fensterlose Steuerelemente neu zeichnen.|  
|[COleControl::IsConvertingVBX](#isconvertingvbx)|Können spezielle Laden eines OLE-Steuerelements.|  
|[COleControl::IsModified](#ismodified)|Bestimmt, ob der Zustand des Steuerelements geändert hat.|  
|[COleControl::IsOptimizedDraw](#isoptimizeddraw)|Gibt an, ob der Container für den aktuellen Vorgang optimierte Zeichnung unterstützt.|  
|[COleControl::IsSubclassedControl](#issubclassedcontrol)|Wird aufgerufen, um festzustellen, ob steuern, die Unterklassen der Steuerelemente einer Windows.|  
|[COleControl::Load](#load)|Setzt alle vorherigen asynchronen Daten und initiiert ein neues Laden der asynchronen Eigenschaften des Steuerelements.|  
|[COleControl::LockInPlaceActive](#lockinplaceactive)|Bestimmt, ob das Steuerelement vom Container deaktiviert werden kann.|  
|[COleControl::OnAmbientPropertyChange](#onambientpropertychange)|Wird aufgerufen, wenn eine Ambiente-Eigenschaft geändert wird.|  
|[COleControl::OnAppearanceChanged](#onappearancechanged)|Wird aufgerufen, wenn die vordefinierte Appearance-Eigenschaft geändert wird.|  
|[COleControl::OnBackColorChanged](#onbackcolorchanged)|Wird aufgerufen, wenn die vordefinierte BackColor-Eigenschaft geändert wird.|  
|[COleControl::OnBorderStyleChanged](#onborderstylechanged)|Wird aufgerufen, wenn die vordefinierte BorderStyle-Eigenschaft geändert wird.|  
|[COleControl::OnClick](#onclick)|Wird aufgerufen, um den Bestand auf auslösen Ereignis.|  
|[COleControl::OnClose](#onclose)|Benachrichtigt das Steuerelement, `IOleControl::Close` aufgerufen wurde.|  
|[COleControl::OnDoVerb](#ondoverb)|Wird aufgerufen, nachdem ein Steuerelement Verb ausgeführt wurde.|  
|[COleControl:: OnDraw aufgerufen](#ondraw)|Wird aufgerufen, wenn ein Steuerelement neu gezeichnet wird.|  
|[OnDrawMetafile](#ondrawmetafile)|Vom Container aufgerufen, wenn ein Steuerelement neu mit einem Metadatei-Gerätekontext gezeichnet wird.|  
|[COleControl::OnEdit](#onedit)|Aufgerufen vom Container zum Aktivieren der Benutzeroberfläche ein OLE-Steuerelements.|  
|[COleControl::OnEnabledChanged](#onenabledchanged)|Wird aufgerufen, wenn der Bestand Enabled-Eigenschaft geändert wird.|  
|[COleControl::OnEnumVerbs](#onenumverbs)|Wird von der Container des Steuerelements Verben aufgelistet werden.|  
|[COleControl::OnEventAdvise](#oneventadvise)|Wird aufgerufen, wenn Ereignishandler von einem Steuerelement getrennt oder verbunden sind.|  
|[COleControl::OnFontChanged](#onfontchanged)|Wird aufgerufen, wenn die vordefinierte Schriftarteigenschaft geändert wird.|  
|[COleControl::OnForeColorChanged](#onforecolorchanged)|Wird aufgerufen, wenn die vordefinierte ForeColor-Eigenschaft geändert wird.|  
|[COleControl::OnFreezeEvents](#onfreezeevents)|Wird aufgerufen, wenn ein Steuerelement Ereignisse nicht eingefroren oder gesperrt sind.|  
|[COleControl::OnGetColorSet](#ongetcolorset)|Benachrichtigt das Steuerelement, `IOleObject::GetColorSet` aufgerufen wurde.|  
|[COleControl::OnGetControlInfo](#ongetcontrolinfo)|Mnemonische Informationen in den Container.|  
|[COleControl::OnGetDisplayString](#ongetdisplaystring)|Wird aufgerufen, um eine Zeichenfolge, die einen Eigenschaftswert dar, zu erhalten.|  
|[COleControl::OnGetInPlaceMenu](#ongetinplacemenu)|Fordert das Handle des Steuerelements Menü, das zusammengeführt werden mit dem Container.|  
|[COleControl::OnGetNaturalExtent](#ongetnaturalextent)|Überschreiben Sie, um die Größe des Steuerelements anzeigen, die die vorgeschlagene Größe und Umfang Modus am nächsten abrufen.|  
|[COleControl::OnGetPredefinedStrings](#ongetpredefinedstrings)|Gibt Zeichenfolgen, die möglichen Werte für eine Eigenschaft darstellt.|  
|[COleControl::OnGetPredefinedValue](#ongetpredefinedvalue)|Gibt den Wert einer vordefinierten Zeichenfolge entspricht.|  
|[COleControl::OnGetViewExtent](#ongetviewextent)|Überschreiben Sie, um die Größe des Steuerelements Anzeigebereiche abrufen (kann verwendet werden, aktivieren Sie zweistufige).|  
|[COleControl::OnGetViewRect](#ongetviewrect)|Überschreiben Sie, um die Größe des Steuerelements in ein Rechteck, beginnend an einer bestimmten Position zu konvertieren.|  
|[COleControl::OnGetViewStatus](#ongetviewstatus)|Überschreiben Sie, um das Anzeigen des Status des Steuerelements abzurufen.|  
|[COleControl::OnHideToolBars](#onhidetoolbars)|Wird vom Container aufgerufen, wenn das Steuerelement der Benutzeroberfläche deaktiviert wird.|  
|[COleControl::OnInactiveMouseMove](#oninactivemousemove)|Überschreiben, um den Container für das Steuerelement inaktiv, unter der Mauszeiger Verteilung haben `WM_MOUSEMOVE` Nachrichten an das Steuerelement.|  
|[COleControl::OnInactiveSetCursor](#oninactivesetcursor)|Überschreiben, um den Container für das Steuerelement inaktiv, unter der Mauszeiger Verteilung haben `WM_SETCURSOR` Nachrichten an das Steuerelement.|  
|[COleControl::OnKeyDownEvent](#onkeydownevent)|Wird aufgerufen, nachdem das vordefinierte KeyDown-Ereignis ausgelöst wurde.|  
|[COleControl::OnKeyPressEvent](#onkeypressevent)|Wird aufgerufen, nachdem das vordefinierte KeyPress-Ereignis ausgelöst wurde.|  
|[COleControl::OnKeyUpEvent](#onkeyupevent)|Wird aufgerufen, nachdem das vordefinierte KeyUp-Ereignis ausgelöst wurde.|  
|[COleControl::OnMapPropertyToPage](#onmappropertytopage)|Gibt an, welche Eigenschaftenseite zum Bearbeiten einer Eigenschaft verwenden.|  
|[COleControl::OnMnemonic](#onmnemonic)|Wird aufgerufen, wenn eine mnemonische Taste des Steuerelements gedrückt wurde.|  
|[COleControl::OnProperties](#onproperties)|Wird aufgerufen, wenn das Steuerelement "Eigenschaften" Verb aufgerufen wurde.|  
|[COleControl::OnQueryHitPoint](#onqueryhitpoint)|Überschreiben Sie Abfrage, ob ein Steuerelement einen bestimmten Zeitpunkt überlappt.|  
|[COleControl::OnQueryHitRect](#onqueryhitrect)|Überschreiben Sie Abfrage, ob die Anzeige eines Steuerelements auf einem beliebigen Punkt in einem bestimmten Rechteck überschneidet.|  
|[COleControl::OnRenderData](#onrenderdata)|Vom Framework aufgerufen wird zum Abrufen von Daten im angegebenen Format.|  
|[COleControl::OnRenderFileData](#onrenderfiledata)|Vom Framework aufgerufen wird zum Abrufen von Daten aus einer Datei im angegebenen Format.|  
|[COleControl::OnRenderGlobalData](#onrenderglobaldata)|Vom Framework aufgerufen wird zum Abrufen von Daten aus dem globalen Arbeitsspeicher im angegebenen Format.|  
|[COleControl:: OnResetState ein](#onresetstate)|Eigenschaften des Steuerelements zurückgesetzt auf die Standardwerte.|  
|[COleControl:: OnSetClientSite](#onsetclientsite)|Benachrichtigt das Steuerelement, `IOleControl::SetClientSite` aufgerufen wurde.|  
|[COleControl::OnSetData](#onsetdata)|Ersetzt die Daten des Steuerelements mit einem anderen Wert.|  
|[COleControl::OnSetExtent](#onsetextent)|Wird aufgerufen, nachdem die Daten des Steuerelements geändert hat.|  
|[COleControl::OnSetObjectRects](#onsetobjectrects)|Wird aufgerufen, nachdem das Steuerelement Dimensionen geändert wurden.|  
|[COleControl::OnShowToolBars](#onshowtoolbars)|Wird aufgerufen, wenn das Steuerelement Benutzeroberfläche aktiviert wurde.|  
|[COleControl::OnTextChanged](#ontextchanged)|Wird aufgerufen, wenn der Bestand Text oder Caption-Eigenschaft geändert wird.|  
|[COleControl::OnWindowlessMessage](#onwindowlessmessage)|Verarbeitet Windows-Nachrichten (mit Ausnahme des Maus- und Nachrichten) für fensterlose Steuerelemente.|  
|[COleControl::ParentToClient](#parenttoclient)|Übersetzt einen Punkt relativ zum Ursprung des Containers, an einem Punkt relativ zum Ursprung des Steuerelements.|  
|[COleControl::PostModalDialog](#postmodaldialog)|Zeigt dem Container an, dass ein modales Dialogfeld geschlossen wurde.|  
|[COleControl::PreModalDialog](#premodaldialog)|Benachrichtigt den Container, der ein modales Dialogfeld angezeigt werden.|  
|[COleControl::RecreateControlWindow](#recreatecontrolwindow)|Zerstört und neu erstellt das Fenster des Steuerelements.|  
|[COleControl::Refresh](#refresh)|Erzwingt das Neuzeichnen der Darstellung eines Steuerelements.|  
|[COleControl::ReleaseCapture](#releasecapture)|Versionen von Mauseingaben.|  
|[COleControl::ReleaseDC](#releasedc)|Gibt den Anzeigegerätekontext, der ein Container für ein fensterloses Steuerelement frei.|  
|[COleControl::ReparentControlWindow](#reparentcontrolwindow)|Das übergeordnete Element des Steuerelementfensters wird zurückgesetzt.|  
|[COleControl::ResetStockProps](#resetstockprops)|Initialisiert `COleControl` vordefinierte Eigenschaften mit ihren Standardwerten.|  
|[COleControl::ResetVersion](#resetversion)|Initialisiert die Versionsnummer auf einen angegebenen Wert.|  
|[COleControl::ScrollWindow](#scrollwindow)|Ermöglicht ein fensterloses Steuerelement um einen Bereich innerhalb der direkte aktiven Bild auf der Anzeige zu scrollen.|  
|[COleControl::SelectFontObject](#selectfontobject)|Wählt eine benutzerdefinierte Schriftarteigenschaft in einem Gerätekontext.|  
|[COleControl:: SelectStockFont](#selectstockfont)|Wählt die vordefinierte Schriftarteigenschaft einen Gerätekontext.|  
|[COleControl::SerializeExtent](#serializeextent)|Serialisiert, oder der Speicherplatz für das Steuerelement initialisiert.|  
|[COleControl::SerializeStockProps](#serializestockprops)|Serialisiert bzw. initialisiert die `COleControl` vordefinierte Eigenschaften.|  
|[COleControl::SerializeVersion](#serializeversion)|Serialisiert bzw. Versionsinformationen des Steuerelements initialisiert.|  
|[COleControl::SetAppearance](#setappearance)|Legt den Wert der vordefinierten Appearance-Eigenschaft.|  
|[COleControl::SetBackColor](#setbackcolor)|Legt den Wert der vordefinierten BackColor-Eigenschaft.|  
|[COleControl::SetBorderStyle](#setborderstyle)|Legt den Wert der vordefinierten BorderStyle-Eigenschaft.|  
|[COleControl::SetCapture](#setcapture)|Bewirkt, dass das Fenster des Steuerelements Container besitzt das Erfassen von Mauseingaben im Auftrag des Steuerelements ausführen.|  
|[COleControl::SetControlSize](#setcontrolsize)|Legt die Position und Größe des OLE-Steuerelements.|  
|[COleControl::SetEnabled](#setenabled)|Legt den Wert der Aktie Enabled-Eigenschaft.|  
|[COleControl::SetFocus](#setfocus)|Bewirkt, dass das Fenster des Steuerelements Container, schalten Sie Namen für das Steuerelement den Eingabefokus besitzt.|  
|[COleControl::SetFont](#setfont)|Legt den Wert der vordefinierten Font-Eigenschaft.|  
|[COleControl::SetForeColor](#setforecolor)|Legt den Wert der vordefinierten ForeColor-Eigenschaft.|  
|[COleControl::SetInitialSize](#setinitialsize)|Legt die Größe eines OLE-Steuerelements, wenn erstmals in einem Container angezeigt.|  
|[COleControl::SetModifiedFlag](#setmodifiedflag)|Ändert den Status eines Steuerelements geänderten.|  
|[COleControl::SetNotPermitted](#setnotpermitted)|Gibt an, dass eine Bearbeiten-Anforderung fehlgeschlagen ist.|  
|[COleControl::SetNotSupported](#setnotsupported)|Verhindert die Änderung an den Eigenschaftswert eines Steuerelements, durch den Benutzer.|  
|[COleControl::SetRectInContainer](#setrectincontainer)|Legt das Rechteck des Steuerelements relativ zu seinem Container.|  
|[COleControl::SetText](#settext)|Legt den Wert der Systemeigenschaft Text oder die Beschriftung fest.|  
|[ThrowError](#throwerror)|Signalisiert, die in ein OLE-Steuerelement ist ein Fehler aufgetreten ist.|  
|[COleControl::TransformCoords](#transformcoords)|Transformationen Koordinatenwerte zwischen einem Container und das Steuerelement.|  
|[Memberfunktion COleControl:: TranslateColor](#translatecolor)|Konvertiert ein **OLE_COLOR** -Wert in einem **COLORREF** Wert.|  
|[COleControl::WillAmbientsBeValidDuringLoad](#willambientsbevalidduringload)|Bestimmt, ob Umgebungseigenschaften das nächste Mal zur Verfügung stehen, wenn das Steuerelement geladen wird.|  
|[COleControl::WindowProc](#windowproc)|Stellt ein Windows-Verfahren für ein `COleControl` Objekt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControl::DrawContent](#drawcontent)|Wird vom Framework aufgerufen, wenn die Darstellung des Steuerelements muss aktualisiert werden.|  
|[COleControl::DrawMetafile](#drawmetafile)|Wird vom Framework aufgerufen, wenn der Metadatei-Gerätekontext verwendet wird.|  
|[COleControl::IsInvokeAllowed](#isinvokeallowed)|Ermöglicht die Automatisierung-Methodenaufruf.|  
|[COleControl::SetInitialDataFormats](#setinitialdataformats)|Aufgerufen, um die Liste der von dem Steuerelement unterstützten Datenformate zu initialisieren.|  
  
## <a name="remarks"></a>Hinweise  
 Abgeleitet von `CWnd`, diese Klasse erbt alle Funktionen von einem Windows-Fensterobjekt plus zusätzliche spezielle Funktionen für OLE, wie z. B. das Auslösen von Ereignissen und die Möglichkeit, Methoden und Eigenschaften unterstützen.  
  
 OLE-Steuerelemente in der OLE-containeranwendungen eingefügt werden können und kommunizieren mit dem Container über eine bidirektionale System Auslösen von Ereignissen und Verfügbarmachen von Methoden und Eigenschaften in den Container. Beachten Sie, dass die standard-OLE-Container unterstützen nur die grundlegende Funktionalität eines OLE-Steuerelements. Sie können keine erweiterten Funktionen der OLE-Steuerelement unterstützt. Auslösen von Ereignissen tritt auf, wenn Ereignisse in den Container durch bestimmte Aktionen in das Steuerelement gesendet werden. Wiederum kommuniziert der Container mit dem Steuerelement über einen verfügbar gemachten Satz von Methoden und Eigenschaften, die analog zu den Memberfunktionen und Datenmember einer C++-Klasse. Dieser Ansatz ermöglicht den Entwickler, die Darstellung des Steuerelements und den Container zu benachrichtigen, wenn bestimmte Aktionen ausgeführt werden.  
  
## <a name="windowless-controls"></a>Fensterlose Steuerelemente  
 OLE-Steuerelemente können verwendete in-Place aktiv, ohne dass das Fenster sein. Fensterlose Steuerelemente haben bedeutende Vorteile:  
  
-   Fensterlose Steuerelemente können transparent und nicht rechteckige sein.  
  
-   Fensterlose Steuerelemente schnellere Instanz und Erstellung des Objekts  
  
 Ein Fenster erforderlich Steuerelemente nicht. Dienste, die ein Fenster angeboten können einfach über ein einzelnes gemeinsames Fenster (normalerweise dem des Containers) und ein wenig Verteilung Code bereitgestellt werden. Ein Fenster ist größtenteils eine unnötige Schwierigkeit für das Objekt.  
  
 Wenn fensterloser Aktivierung verwendet wird, ist der Container (der ein Fenster) verantwortlich für die Bereitstellung von Diensten, die andernfalls vom Fenster des Steuerelements bereitgestellt würden. Wenn das Steuerelement den Tastaturfokus Abfragen, Abfragen das Erfassen von Mauseingaben oder einen Gerätekontext zu erhalten, werden diese Vorgänge vom Container verwaltet. Die `COleControl` [fensterlose Operation Memberfunktionen](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) rufen Sie diese Vorgänge für den Container.  
  
 Fensterloser Aktivierung aktiviert, die Container-Delegaten eingehende Nachrichten, um des Steuerelements `IOleInPlaceObjectWindowless` Schnittstelle (eine Erweiterung der [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) fensterlose Support). `COleControl`die Implementierung dieser Schnittstelle werden diese Nachrichten über das Steuerelement Nachricht Zuordnung verteilen, nach dem Anpassen der Maus entsprechend koordiniert. Durch die Nachricht Zuordnung die entsprechenden Einträge hinzugefügt, können Sie diese Nachrichten wie normale Windows-Meldungen verarbeiten.  
  
 Sie sollten immer verwenden, in ein fensterloses Steuerelement, das `COleControl` Memberfunktionen anstelle der entsprechenden `CWnd` Memberfunktionen oder den zugehörigen Windows-API-Funktionen.  
  
 OLE-Steuerelement-Objekte können auch ein Fenster erstellen, nur, wenn sie aktiv ist, werden jedoch der Arbeitsaufwand für den inaktiven aktiven Übergang erforderlich steigt und die Geschwindigkeit des Übergangs ausfällt. Es gibt Fälle, wenn dieses Problem auftritt: Betrachten Sie beispielsweise ein Raster mit Textfeldern. Wenn Cursoring nach oben oder unten, bis die Spalte, jedes Steuerelement direktes muss aktiviert und anschließend deaktiviert. Die Geschwindigkeit des Übergangs inaktiv/aktiv wirkt sich direkt auf die Geschwindigkeit des Bildlaufs aus.  
  
 Weitere Informationen zum Entwickeln von einer OLE-Steuerelement-Framework finden Sie in den Artikeln [MFC-ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md) und [Übersicht: Erstellen eines MFC-ActiveX-Steuerelement-Programms](../../mfc/reference/mfc-activex-control-wizard.md). Informationen zum Optimieren von OLE-Steuerelemente, einschließlich fensterlos und flimmerfreie, finden Sie unter [MFC-ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `COleControl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="a-nameambientbackcolora--colecontrolambientbackcolor"></a><a name="ambientbackcolor"></a>COleControl::AmbientBackColor  
 Gibt den Wert der ambient-BackColor-Eigenschaft.  
  
```  
OLE_COLOR AmbientBackColor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Wert des Containers ambient BackColor-Eigenschaft, sofern vorhanden. Wenn die Eigenschaft nicht unterstützt wird, gibt diese Funktion die vom System vorgegebene Windows-Hintergrundfarbe zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Ambiente-BackColor-Eigenschaft ist für alle Steuerelemente verfügbar und wird durch den Container definiert. Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientdisplaynamea--colecontrolambientdisplayname"></a><a name="ambientdisplayname"></a>COleControl::AmbientDisplayName  
 Der Name, der der Container des Steuerelements zugewiesen hat kann in dem Benutzer angezeigten Fehlermeldungen verwendet werden.  
  
```  
CString AmbientDisplayName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des OLE-Steuerelements. Der Standardwert ist eine Zeichenfolge der Länge&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientfonta--colecontrolambientfont"></a><a name="ambientfont"></a>COleControl::AmbientFont  
 Gibt den Wert der ambient-Font-Eigenschaft.  
  
```  
LPFONTDISP AmbientFont();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Container ambient-Schriftart-Dispatch-Schnittstellen. Der Standardwert ist **NULL**. Wenn die Rückgabe nicht entspricht **NULL**, Sie sind verantwortlich für die Freigabe der Schriftartformats durch Aufrufen seiner [IUnknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Die Ambiente-Font-Eigenschaft ist der Container definiert und für alle Steuerelemente verfügbar. Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientforecolora--colecontrolambientforecolor"></a><a name="ambientforecolor"></a>COleControl::AmbientForeColor  
 Gibt den Wert der ambient-ForeColor-Eigenschaft.  
  
```  
OLE_COLOR AmbientForeColor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Wert des Containers ambient ForeColor-Eigenschaft, sofern vorhanden. Wenn nicht unterstützt, gibt diese Funktion vom System vorgegebene Windows die Farbe des Texts zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Ambiente-ForeColor-Eigenschaft ist für alle Steuerelemente verfügbar und wird durch den Container definiert. Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientlocaleida--colecontrolambientlocaleid"></a><a name="ambientlocaleid"></a>COleControl:: AmbientLocaleID  
 Gibt den Container Gebietsschema-ID.  
  
```  
LCID AmbientLocaleID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert der Gebietsschema-ID-Eigenschaft des Containers, sofern vorhanden. Wenn diese Eigenschaft nicht unterstützt wird, gibt diese Funktion 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Der LocaleID-Wert können das Steuerelement die Benutzeroberfläche für bestimmte Gebietsschemas angepasst werden kann. Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientappearancea--colecontrolambientappearance"></a><a name="ambientappearance"></a>COleControl::AmbientAppearance  
 Ruft die aktuelle Einstellung der Darstellung für das Steuerelementobjekt ab.  
  
```  
short AmbientAppearance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Darstellung des Steuerelements:  
  
- **0** Flatfile-Darstellung  
  
- **1** 3D-Darstellung  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Abrufen des aktuellen Werts der **DISPID_AMBIENT_APPEARANCE** -Eigenschaft für das Steuerelement.  
  
##  <a name="a-nameambientscaleunitsa--colecontrolambientscaleunits"></a><a name="ambientscaleunits"></a>COleControl::AmbientScaleUnits  
 Gibt den Typ der vom Container verwendeten Einheiten.  
  
```  
CString AmbientScaleUnits();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die die ambient-ScaleUnits des Containers enthält. Wenn diese Eigenschaft nicht unterstützt wird, gibt diese Funktion eine Zeichenfolge der Länge&0; (null) zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die-Eigenschaft des Containers Ambiente "ScaleUnits" kann verwendet werden, zum Anzeigen von Positionen oder Dimensionen, die mit der ausgewählten Einheit, wie z. B. Twips oder Zentimeter bezeichnet. Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientshowgrabhandlesa--colecontrolambientshowgrabhandles"></a><a name="ambientshowgrabhandles"></a>COleControl::AmbientShowGrabHandles  
 Bestimmt, ob der Container des Steuerelements anzuzeigenden Ziehpunkte für sich selbst beim active zulässt.  
  
```  
BOOL AmbientShowGrabHandles();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Ziehpunkte angezeigt werden soll; andernfalls 0. Wenn diese Eigenschaft nicht unterstützt wird, gibt diese Funktion einen Wert ungleich NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientshowhatchinga--colecontrolambientshowhatching"></a><a name="ambientshowhatching"></a>COleControl::AmbientShowHatching  
 Bestimmt, ob der Container ermöglicht, dass das Steuerelement selbst mit einem schraffierten an Muster, wenn UI aktiv.  
  
```  
BOOL AmbientShowHatching();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schraffur angezeigt werden soll; andernfalls 0. Wenn diese Eigenschaft nicht unterstützt wird, gibt diese Funktion einen Wert ungleich NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambienttextaligna--colecontrolambienttextalign"></a><a name="ambienttextalign"></a>COleControl::AmbientTextAlign  
 Bestimmt den Steuerelementcontainer bevorzugte der Ausrichtung.  
  
```  
short AmbientTextAlign();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status des Containers ambient TextAlign-Eigenschaft. Wenn diese Eigenschaft nicht unterstützt wird, gibt diese Funktion 0 zurück.  
  
 Im folgenden finden eine Liste der gültigen Werte zurückgeben:  
  
|Rückgabewert|Bedeutung|  
|------------------|-------------|  
|0|Allgemeine Ausrichtung (Zahlen, die Text rechts und links).|  
|1|Links ausrichten|  
|2|Center |  
|3|Rechtsbündig|  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft ist für alle eingebetteten Steuerelementen verfügbar und wird durch den Container definiert. Beachten Sie, dass der Container ist nicht erforderlich, diese Eigenschaft unterstützt.  
  
##  <a name="a-nameambientuideada--colecontrolambientuidead"></a><a name="ambientuidead"></a>COleControl::AmbientUIDead  
 Bestimmt, ob der Container des Steuerelements auf der Benutzeroberfläche Aktionen reagieren möchte.  
  
```  
BOOL AmbientUIDead();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement auf der Benutzeroberfläche Aktionen reagieren soll; andernfalls 0. Wenn diese Eigenschaft nicht unterstützt wird, gibt diese Funktion 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. ein Container kann diese Eigenschaft auf festlegen **TRUE** im Entwurfsmodus.  
  
##  <a name="a-nameambientusermodea--colecontrolambientusermode"></a><a name="ambientusermode"></a>COleControl::AmbientUserMode  
 Bestimmt, ob der Container in den Entwurfsmodus oder im Benutzermodus ist.  
  
```  
BOOL AmbientUserMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Container im Benutzermodus ist; Andernfalls wird 0 (im Entwurfsmodus). Wenn diese Eigenschaft nicht unterstützt wird, gibt diese Funktion TRUE zurück.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. ein Container kann diese Eigenschaft auf festlegen **FALSE** im Entwurfsmodus.  
  
##  <a name="a-nameboundpropertychangeda--colecontrolboundpropertychanged"></a><a name="boundpropertychanged"></a>COleControl::BoundPropertyChanged  
 Signalisiert, die den Wert der gebundenen Eigenschaft geändert wurde.  
  
```  
void BoundPropertyChanged(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID einer gebundenen Eigenschaft des Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Dies muss aufgerufen werden, jedes Mal, wenn der Wert der Eigenschaft ändert, sogar in Fällen, in dem die Änderung nicht durch die Eigenschaft vorgenommen wurde, Methode festgelegt. Achten Sie besonders gebundene Eigenschaften, die Member-Variablen zugeordnet sind. Solche ein Variablen ändert, jederzeit `BoundPropertyChanged` muss aufgerufen werden.  
  
##  <a name="a-nameboundpropertyrequestedita--colecontrolboundpropertyrequestedit"></a><a name="boundpropertyrequestedit"></a>COleControl::BoundPropertyRequestEdit  
 Fordert die Berechtigung für die `IPropertyNotifySink` Schnittstelle vom Steuerelement bereitgestellte gebundene Eigenschaftswert zu ändern.  
  
```  
BOOL BoundPropertyRequestEdit(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID einer gebundenen Eigenschaft des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderung zulässig ist; andernfalls 0. Der Standardwert ist ungleich NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Berechtigung verweigert wird, muss das Steuerelement den Wert der Eigenschaftenänderung nicht zulassen. Dies kann erfolgen, von ignoriert, oder wenn die Aktion, die versucht, den Wert der Eigenschaft zu ändern.  
  
##  <a name="a-nameclienttoparenta--colecontrolclienttoparent"></a><a name="clienttoparent"></a>COleControl::ClientToParent  
 Übersetzt die Koordinaten der `pPoint` in übergeordneten Koordinaten.  
  
```  
virtual void ClientToParent(
    LPCRECT lprcBounds, 
    LPPOINT pPoint) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lprcBounds`  
 Ein Zeiger auf die Grenzen des OLE-Steuerelements innerhalb des Containers. Der Client-Bereich jedoch den Bereich des gesamten Steuerelements einschließlich Rahmen und Bildlaufleisten.  
  
 `pPoint`  
 Ein Zeiger auf die OLE-Clientzugriffspunkt Bereich in die Koordinaten des übergeordneten Elements (Container) übersetzt werden.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Eingabe `pPoint` ist relativ zum Ursprung des Clientbereichs des OLE-Steuerelements (obere linke Ecke des Clientbereichs des Steuerelements). Bei der Ausgabe `pPoint` ist relativ zum Ursprung des übergeordneten Elements (obere linke Ecke des Containers).  
  
##  <a name="a-nameclipcaretrecta--colecontrolclipcaretrect"></a><a name="clipcaretrect"></a>COleControl::ClipCaretRect  
 Ein Caretzeichen Rechteck passt, wenn es ganz oder teilweise von überlappenden, nicht transparenten Objekte verdeckt wird.  
  
```  
BOOL ClipCaretRect(LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Bei Eingabe einen Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die die Einfügemarke Bereich angepasst werden. Bei der Ausgabe im Bereich für den angepassten Caretzeichen oder **NULL** Wenn das Caretzeichen Rechteck vollständig abgedeckt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein Caretzeichen ist eine blinkende Linie, blockieren oder Bitmap, die in der Regel an, wo Text oder Grafiken eingefügt werden.  
  
 Ein fensterloses-Objekt kann nicht sicher Caret-Zeichen ohne Rücksprache angezeigt, ob die Einfügemarke ganz oder teilweise ausgeblendet ist, indem überlappende Objekte. Um, die durchgeführt werden können, können ein Objekt `ClipCaretRect` erhalten die Einfügemarke angepasst (reduziert) um sicherzustellen, dass er in den Ausschneidebereich passt.  
  
 Objekte erstellen ein Caretzeichen das Caretzeichen Rechteck senden soll `ClipCaretRect` und verwenden Sie für die Einfügemarke des neuen Rechtecks angepasst. Diese Methode gibt zurück, wenn die Einfügemarke vollständig ausgeblendet ist, **FALSE** und die Einfügemarke nicht angezeigt werden soll auf allen in diesem Fall.  
  
##  <a name="a-namecolecontrola--colecontrolcolecontrol"></a><a name="colecontrol"></a>COleControl::COleControl  
 Erstellt ein `COleControl`-Objekt.  
  
```  
COleControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise nicht direkt aufgerufen. Stattdessen wird das OLE-Steuerelement in der Regel durch die Klassenfactory erstellt.  
  
##  <a name="a-namecontrolinfochangeda--colecontrolcontrolinfochanged"></a><a name="controlinfochanged"></a>COleControl::ControlInfoChanged  
 Rufen Sie diese Funktion, wenn das mnemonische Zeichen vom Steuerelement unterstützten geändert wurden.  
  
```  
void ControlInfoChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach Erhalt dieser Benachrichtigung, erhält der Container des Steuerelements den neuen Satz von Zugriffstasten durch einen Aufruf an [IOleControl::GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730). Beachten Sie, dass der Container ist nicht erforderlich, diese Benachrichtigung zu reagieren.  
  
##  <a name="a-namedisplayerrora--colecontroldisplayerror"></a><a name="displayerror"></a>COleControl::DisplayError  
 Wird vom Framework aufgerufen, nachdem die vordefinierte Error-Ereignis behandelt wurde (es sei denn, der Ereignishandler die Anzeige des Fehlers unterdrückt wurde).  
  
```  
virtual void DisplayError(
    SCODE scode,  
    LPCTSTR lpszDescription,  
    LPCTSTR lpszSource,  
    LPCTSTR lpszHelpFile,  
    UINT nHelpID);
```  
  
### <a name="parameters"></a>Parameter  
 *SCODE*  
 Der Statuswert des Codes gemeldet werden. Eine vollständige Liste der möglichen Fehlercodes, finden Sie im Artikel [ActiveX-Steuerelemente: Weiterführende Themen](../../mfc/mfc-activex-controls-advanced-topics.md).  
  
 `lpszDescription`  
 Die Beschreibung des Fehlers gemeldet wird.  
  
 *lpszSource*  
 Der Name des Moduls, die den Fehler (in der Regel der Name des Moduls OLE-Steuerelement).  
  
 `lpszHelpFile`  
 Der Name der Hilfedatei, die eine Beschreibung des Fehlers enthält.  
  
 `nHelpID`  
 Die Hilfe Kontext-ID des Fehlers gemeldet wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten zeigt ein Meldungsfeld mit der Beschreibung des Fehlers, der in enthaltenen `lpszDescription`.  
  
 Überschreiben Sie diese Funktion, um anzupassen, wie Fehler angezeigt werden.  
  
##  <a name="a-namedoclicka--colecontroldoclick"></a><a name="doclick"></a>COleControl::DoClick  
 Simuliert die Maus auf das Steuerelement.  
  
```  
void DoClick();
```  
  
### <a name="remarks"></a>Hinweise  
 Die überschreibbare `COleControl::OnClick` Memberfunktion aufgerufen werden, und ein Click-Ereignis ausgelöst wird, wenn das Steuerelement unterstützt.  
  
 Diese Funktion wird von unterstützt die `COleControl` -Basisklasse als eine vordefinierte Methode namens DoClick. Weitere Informationen finden Sie im Artikel [ActiveX-Steuerelemente: Methoden](../../mfc/mfc-activex-controls-methods.md).  
  
##  <a name="a-namedopropexchangea--colecontroldopropexchange"></a><a name="dopropexchange"></a>COleControl:: DoPropExchange  
 Vom Framework aufgerufen, wenn beim Laden oder speichern ein Steuerelement aus einer Darstellung permanenten Speicher wie z. B. einen Stream oder eine Eigenschaft festlegen.  
  
```  
virtual void DoPropExchange(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Ein Zeiger auf ein `CPropExchange` Objekt. Das Framework verwendet dieses Objekt, um den Kontext der Exchange-Eigenschaft, einschließlich seiner Richtung zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise die Aufrufe an die **PX_** Funktionsreihe laden oder speichern bestimmte benutzerdefinierte Eigenschaften eines OLE-Steuerelements.  
  
 Wenn Steuerelement-Assistent verwendet wurde, um das OLE-Steuerelementbibliothek-Projekt zu erstellen, wird die überschriebene Version dieser Funktion die Basiseigenschaften, die von unterstützten Serialisieren `COleControl` mit einem Aufruf der Funktion der Basisklasse `COleControl::DoPropExchange`. Hinzufügen von benutzerdefinierten Eigenschaften an das OLE-Steuerelement müssen Sie diese Funktion zum Serialisieren der neuen Eigenschaften zu ändern. Weitere Informationen zur Serialisierung finden Sie im Artikel [ActiveX-Steuerelemente: Serialisierung](../../mfc/mfc-activex-controls-serializing.md).  
  
##  <a name="a-namedosuperclasspainta--colecontroldosuperclasspaint"></a><a name="dosuperclasspaint"></a>COleControl::DoSuperclassPaint  
 Zeichnet ein OLE-Steuerelement, das von einem Windows-Steuerelement erstellt wurde.  
  
```  
void DoSuperclassPaint(
    CDC* pDC,  
    const CRect& rcBounds);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext des Steuerelementcontainers.  
  
 `rcBounds`  
 Der Bereich, in dem das Steuerelement gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um das Zeichnen eines inaktiven OLE-Steuerelements ordnungsgemäß zu behandeln. Diese Funktion sollte nur verwendet werden, wenn die OLE Unterklassen ein Windows-Steuerelements steuern und, in aufgerufen werden der `OnDraw` Funktion des Steuerelements.  
  
 Weitere Informationen zu dieser Funktion und einer Fenstersteuerelement, finden Sie im Artikel [ActiveX-Steuerelemente: Erstellen von Unterklassen eines Windows-Steuerelements](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
##  <a name="a-namedrawcontenta--colecontroldrawcontent"></a><a name="drawcontent"></a>COleControl::DrawContent  
 Wird vom Framework aufgerufen, wenn die Darstellung des Steuerelements muss aktualisiert werden.  
  
```  
void DrawContent(
    CDC* pDC,  
    CRect& rc);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext.  
  
 `rc`  
 Rechteckige Bereich, gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft direkt die überschreibbare `OnDraw` Funktion.  
  
##  <a name="a-namedrawmetafilea--colecontroldrawmetafile"></a><a name="drawmetafile"></a>COleControl::DrawMetafile  
 Wird vom Framework aufgerufen, wenn der Metadatei-Gerätekontext verwendet wird.  
  
```  
void DrawMetafile(
    CDC* pDC,  
    CRect& rc);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext Metadatei.  
  
 `rc`  
 Rechteckige Bereich, gezeichnet werden soll.  
  
##  <a name="a-nameenablesimpleframea--colecontrolenablesimpleframe"></a><a name="enablesimpleframe"></a>COleControl::EnableSimpleFrame  
 Ermöglicht das einfache Frame-Merkmal für die OLE-Steuerelement.  
  
```  
void EnableSimpleFrame();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Merkmal kann eine-Steuerelement visuellen Kapselung von anderen Steuerelementen, aber nicht "true" OLE-Container unterstützen. Ein Beispiel wäre ein Gruppenfeld in mehrere Steuerelemente. Diese Steuerelemente sind nicht enthaltenen OLE, aber sie sind im gleichen Gruppe.  
  
##  <a name="a-nameexchangeextenta--colecontrolexchangeextent"></a><a name="exchangeextent"></a>COleControl::ExchangeExtent  
 Serialisiert bzw. initialisiert den Zustand des Steuerelements Ausmaß (seiner Dimensionen in **HIMETRIC** Einheiten).  
  
```  
BOOL ExchangeExtent(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Ein Zeiger auf eine [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt. Das Framework verwendet dieses Objekt, um den Kontext der Exchange-Eigenschaft, einschließlich seiner Richtung zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, durch die standardmäßige Implementierung des `COleControl::DoPropExchange`.  
  
##  <a name="a-nameexchangestockpropsa--colecontrolexchangestockprops"></a><a name="exchangestockprops"></a>COleControl::ExchangeStockProps  
 Serialisiert bzw. initialisiert den Zustand des vordefinierten Eigenschaften des Steuerelements.  
  
```  
void ExchangeStockProps(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Ein Zeiger auf eine [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt. Das Framework verwendet dieses Objekt, um den Kontext der Exchange-Eigenschaft, einschließlich seiner Richtung zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, durch die standardmäßige Implementierung des `COleControl::DoPropExchange`.  
  
##  <a name="a-nameexchangeversiona--colecontrolexchangeversion"></a><a name="exchangeversion"></a>COleControl:: ExchangeVersion  
 Serialisiert bzw. initialisiert den Zustand des Steuerelements Versionsinformationen.  
  
```  
BOOL ExchangeVersion(
    CPropExchange* pPX,  
    DWORD dwVersionDefault,  
    BOOL bConvert = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pPX`  
 Ein Zeiger auf ein `CPropExchange` Objekt. Das Framework verwendet dieses Objekt, um den Kontext der Exchange-Eigenschaft, einschließlich seiner Richtung zu erstellen.  
  
 `dwVersionDefault`  
 Die aktuelle Versionsnummer des Steuerelements.  
  
 `bConvert`  
 Gibt an, ob permanente Daten konvertiert werden sollen, in das aktuelle Format beim Speichern oder beibehalten werden, in dem Format, das geladen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL für die Funktion erfolgreich ausgeführt werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Normalerweise ist dies die erste Funktion von eines Steuerelements Überschreiben von aufgerufen, `COleControl::DoPropExchange`. Beim Laden, diese Funktion liest die Versionsnummer der permanenten Daten, und setzt das Versionsattribut des der [CPropExchange](../../mfc/reference/cpropexchange-class.md) Objekt entsprechend. Beim Speichern, schreibt dieser Funktion die Versionsnummer der permanenten Daten.  
  
 Weitere Informationen zur Persistenz und Versionskontrolle finden Sie im Artikel [ActiveX-Steuerelemente: Serialisierung](../../mfc/mfc-activex-controls-serializing.md).  
  
##  <a name="a-namefireclicka--colecontrolfireclick"></a><a name="fireclick"></a>COleControl::FireClick  
 Wird vom Framework aufgerufen, wenn die Maus über ein aktives Steuerelement geklickt wird.  
  
```  
void FireClick();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Für die automatische Auslösung von ein Click-Ereignis auftritt, müssen Event-Zuordnung das Steuerelement eine Aktie auf Ereignis definiert.  
  
##  <a name="a-namefiredblclicka--colecontrolfiredblclick"></a><a name="firedblclick"></a>COleControl::FireDblClick  
 Wird vom Framework aufgerufen, wenn die Maus über ein aktives Steuerelement doppelgeklickt wird.  
  
```  
void FireDblClick();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Automatische Auslösen einer DblClick-Ereignis eintritt, müssen das Steuerelement Event-Zuordnung ein vordefiniertes DblClick-Ereignis definiert.  
  
##  <a name="a-namefireerrora--colecontrolfireerror"></a><a name="fireerror"></a>COleControl:: FireError  
 Wird die vordefinierte Error-Ereignis ausgelöst.  
  
```  
void FireError(
    SCODE scode,  
    LPCTSTR lpszDescription,  
    UINT nHelpID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *SCODE*  
 Der Statuswert des Codes gemeldet werden. Eine vollständige Liste der möglichen Fehlercodes, finden Sie im Artikel [ActiveX-Steuerelemente: Weiterführende Themen](../../mfc/mfc-activex-controls-advanced-topics.md).  
  
 `lpszDescription`  
 Die Beschreibung des Fehlers gemeldet wird.  
  
 `nHelpID`  
 Die Hilfe-ID des Fehlers gemeldet wird.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Ereignis bietet eine Möglichkeit, Signalisierung sein können, an den entsprechenden Stellen im Code, der im Steuerelement ein Fehler aufgetreten ist. Im Gegensatz zu anderen vordefinierten Ereignissen, z. B. auf oder MouseMove wird Fehler nie vom Framework ausgelöst.  
  
 Aufrufen, um einen Fehler melden, während ein Property-Get-Funktion, einer Property Set-Funktion oder Automatisierungsmethode, [ThrowError](#throwerror).  
  
 Die Implementierung eines OLE-Steuerelements Stock Fehler Ereignis verwendet ein `SCODE` Wert. Wenn das Steuerelement dieses Ereignis verwendet, und in Visual Basic 4.0 verwendet werden soll, erhalten Sie Fehler, da die `SCODE` Wert wird in Visual Basic nicht unterstützt.  
  
 Um dieses Problem zu beheben, ändern Sie manuell den `SCODE` -Parameter in des Steuerelements. ODL-Datei eine **lang**. Darüber hinaus jede benutzerdefinierte Ereignis, eine Methode oder eine Eigenschaft, die mithilfe einer `SCODE` Parameter bewirkt auch, dass das gleiche Problem.  
  
##  <a name="a-namefireeventa--colecontrolfireevent"></a><a name="fireevent"></a>COleControl::  
 Löst ein benutzerdefiniertes Ereignis über das Steuerelement mit einer beliebigen Anzahl von optionalen Argumenten.  
  
```  
void AFX_CDECL FireEvent(
    DISPID dispid,  
    BYTE* pbParams,  
 ...);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID des Ereignisses ausgelöst werden.  
  
 `pbParams`  
 Ein Deskriptor für das Ereignis Parametertypen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte normalerweise nicht direkt aufgerufen werden. Stattdessen werden Sie die Ereignisse auslösen – Funktionen im Ereignis Map-Abschnitt der Klassendeklaration des Steuerelements aufrufen.  
  
 Die `pbParams` Argument ist eine durch Leerzeichen getrennte Liste der **VTS_**. Einer oder mehrere dieser Werte, durch Leerzeichen (nicht Kommas) getrennt, gibt bzw. geben die Parameterliste der Funktion an. Folgende Werte sind möglich:  
  
|Symbol|Parametertyp|  
|------------|--------------------|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_FONT**|**IFontDisp\***|  
|**VTS_HANDLE**|`HWND`|  
|**VTS_PICTURE**|**IPictureDisp\***|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
  
> [!NOTE]
>  Zusätzliche Variante Konstanten für alle variant-Typen, mit Ausnahme von definiert wurden **VTS_FONT** und **VTS_PICTURE**, die einen Zeiger auf die variant-Daten bereitstellen. Diese Konstanten werden mit dem Namen mit dem **VTS_P** `constantname` Konvention. Beispielsweise **VTS_PCOLOR** ist ein Zeiger auf eine **VTS_COLOR** konstant.  
  
##  <a name="a-namefirekeydowna--colecontrolfirekeydown"></a><a name="firekeydown"></a>COleControl::FireKeyDown  
 Wird vom Framework aufgerufen, wenn eine Taste gedrückt wird, während das Steuerelement UI aktiv ist.  
  
```  
void FireKeyDown(
    USHORT* pnChar,  
    short nShiftState);
```  
  
### <a name="parameters"></a>Parameter  
 `pnChar`  
 Zeiger auf den virtuellen Tastencode-Wert, der die gedrückte Taste. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h  
  
 `nShiftState`  
 Enthält eine Kombination der folgenden Flags:  
  
- **SHIFT_MASK** die UMSCHALTTASTE gedrückt wurde, während der Aktion.  
  
- **CTRL_MASK** die STRG-Taste gedrückt wurde, während der Aktion.  
  
- **ALT_MASK** die ALT-Taste gedrückt wurde, während der Aktion.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Automatische Auslösen einer KeyDown-Ereignis eintritt, müssen das Steuerelement Event-Zuordnung ein vordefiniertes KeyDown-Ereignis definiert.  
  
##  <a name="a-namefirekeypressa--colecontrolfirekeypress"></a><a name="firekeypress"></a>COleControl::FireKeyPress  
 Wird vom Framework aufgerufen, wenn eine Taste gedrückt und losgelassen wird, während das benutzerdefinierte Steuerelement im Container UI aktiv ist.  
  
```  
void FireKeyPress(USHORT* pnChar);
```  
  
### <a name="parameters"></a>Parameter  
 `pnChar`  
 Ein Zeiger auf den Wert des Zeichens von der gedrückten Taste.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Der Empfänger des Ereignisses darf ändern `pnChar`, z. B. alle Kleinbuchstaben in Großbuchstaben zu konvertieren. Wenn Sie das geänderte Zeichen untersuchen möchten, überschreiben Sie `OnKeyPressEvent`.  
  
 Automatische Auslösen einer KeyPress-Ereignis eintritt, müssen das Steuerelement Event-Zuordnung ein vordefiniertes KeyPress-Ereignis definiert.  
  
##  <a name="a-namefirekeyupa--colecontrolfirekeyup"></a><a name="firekeyup"></a>COleControl::FireKeyUp  
 Wird vom Framework aufgerufen, wenn eine Taste losgelassen wird, während das benutzerdefinierte Steuerelement im Container UI aktiv ist.  
  
```  
void FireKeyUp(
    USHORT* pnChar,  
    short nShiftState);
```  
  
### <a name="parameters"></a>Parameter  
 `pnChar`  
 Zeiger auf den virtuellen Tastencode-Wert, der den freigegebenen Schlüssel. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h  
  
 `nShiftState`  
 Enthält eine Kombination der folgenden Flags:  
  
- **SHIFT_MASK** die UMSCHALTTASTE gedrückt wurde, während der Aktion.  
  
- **CTRL_MASK** die STRG-Taste gedrückt wurde, während der Aktion.  
  
- **ALT_MASK** die ALT-Taste gedrückt wurde, während der Aktion.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Automatische Auslösen einer KeyUp-Ereignis eintritt, müssen das Steuerelement Event-Zuordnung ein vordefiniertes KeyUp-Ereignis definiert.  
  
##  <a name="a-namefiremousedowna--colecontrolfiremousedown"></a><a name="firemousedown"></a>COleControl::FireMouseDown  
 Wird vom Framework aufgerufen, wenn eine Maustaste, über ein aktives benutzerdefinierte Steuerelement gedrückt wird.  
  
```  
void FireMouseDown(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>Parameter  
 `nButton`  
 Der numerische Wert der Maustaste gedrückt. Sie können einen der folgenden Werte enthalten:  
  
- **LEFT_BUTTON** die linke Maustaste gedrückt wurde.  
  
- **MIDDLE_BUTTON** die mittleren Maustaste gedrückt wurde.  
  
- **RIGHT_BUTTON** die rechte Maustaste gedrückt wurde.  
  
 `nShiftState`  
 Enthält eine Kombination der folgenden Flags:  
  
- **SHIFT_MASK** die UMSCHALTTASTE gedrückt wurde, während der Aktion.  
  
- **CTRL_MASK** die STRG-Taste gedrückt wurde, während der Aktion.  
  
- **ALT_MASK** die ALT-Taste gedrückt wurde, während der Aktion.  
  
 *x*  
 Die X-Koordinate des Cursors, wenn eine Maustaste gedrückt wurde. Die Koordinate ist relativ zur linken oberen Ecke des Steuerelementfensters.  
  
 *y*  
 Die y-Koordinate des Cursors, wenn eine Maustaste gedrückt wurde. Die Koordinate ist relativ zur linken oberen Ecke des Steuerelementfensters.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Automatische Auslösen einer MouseDown-Ereignis eintritt, müssen das Steuerelement Event-Zuordnung ein vordefiniertes MouseDown-Ereignis definiert.  
  
##  <a name="a-namefiremousemovea--colecontrolfiremousemove"></a><a name="firemousemove"></a>COleControl::FireMouseMove  
 Wird vom Framework aufgerufen, wenn der Mauszeiger über ein aktives benutzerdefinierte Steuerelement bewegt wird.  
  
```  
void FireMouseMove(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>Parameter  
 `nButton`  
 Der numerische Wert der Maustasten gedrückt. Enthält eine Kombination der folgenden Werte:  
  
- **LEFT_BUTTON** die linke Maustaste gedrückt wurde, während der Aktion.  
  
- **MIDDLE_BUTTON** die mittleren Maustaste gedrückt wurde, während der Aktion.  
  
- **RIGHT_BUTTON** die rechte Maustaste gedrückt wurde, während der Aktion.  
  
 `nShiftState`  
 Enthält eine Kombination der folgenden Flags:  
  
- **SHIFT_MASK** die UMSCHALTTASTE gedrückt wurde, während der Aktion.  
  
- **CTRL_MASK** die STRG-Taste gedrückt wurde, während der Aktion.  
  
- **ALT_MASK** die ALT-Taste gedrückt wurde, während der Aktion.  
  
 *x*  
 Die X-Koordinate des Cursors. Die Koordinate ist relativ zur linken oberen Ecke des Steuerelementfensters.  
  
 *y*  
 Die y-Koordinate des Cursors. Die Koordinate ist relativ zur linken oberen Ecke des Steuerelementfensters.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Automatische Auslösen einer MouseMove-Ereignis eintritt, müssen das Steuerelement Event-Zuordnung ein vordefiniertes MouseMove-Ereignis definiert.  
  
##  <a name="a-namefiremouseupa--colecontrolfiremouseup"></a><a name="firemouseup"></a>COleControl::FireMouseUp  
 Vom Framework aufgerufen, wenn eine Maustaste, über ein aktives benutzerdefinierte Steuerelement losgelassen wird.  
  
```  
void FireMouseUp(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>Parameter  
 `nButton`  
 Der numerische Wert, der die Maustaste freigegeben werden soll. Die folgenden Werte sind möglich:  
  
- **LEFT_BUTTON** die linke Maustaste losgelassen wurde.  
  
- **MIDDLE_BUTTON** die mittlere Maustaste losgelassen wurde.  
  
- **RIGHT_BUTTON** die rechte Maustaste losgelassen wurde.  
  
 `nShiftState`  
 Enthält eine Kombination der folgenden Flags:  
  
- **SHIFT_MASK** die UMSCHALTTASTE gedrückt wurde, während der Aktion.  
  
- **CTRL_MASK** die STRG-Taste gedrückt wurde, während der Aktion.  
  
- **ALT_MASK** die ALT-Taste gedrückt wurde, während der Aktion.  
  
 *x*  
 Die X-Koordinate des Cursors, wenn eine Maustaste losgelassen wurde. Die Koordinate ist relativ zur linken oberen Ecke des Steuerelementfensters.  
  
 *y*  
 Die y-Koordinate eines Cursors, wenn eine Maustaste losgelassen wurde. Die Koordinate ist relativ zur linken oberen Ecke des Steuerelementfensters.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Ereignis als ein benutzerdefiniertes Ereignis definiert ist, bestimmen Sie, wann das Ereignis ausgelöst wird.  
  
 Automatische Auslösen einer MouseUp-Ereignis eintritt, müssen das Steuerelement Event-Zuordnung ein vordefiniertes MouseUp-Ereignis definiert.  
  
##  <a name="a-namefirereadystatechangea--colecontrolfirereadystatechange"></a><a name="firereadystatechange"></a>COleControl::FireReadyStateChange  
 Löst ein Ereignis mit dem aktuellen Wert, der den Zustand des Steuerelements.  
  
```  
void FireReadyStateChange();
```  
  
### <a name="remarks"></a>Hinweise  
 Der aktuelle Status möglich der folgenden Werte:  
  
 **READYSTATE_UNINITIALIZED**  
 Initialisierung der Standardstatus  
  
 **READYSTATE_LOADING**  
 Steuerelement wird seine Eigenschaften derzeit geladen werden.  
  
 **READYSTATE_LOADED**  
 Steuerelement wurde initialisiert.  
  
 **READYSTATE_INTERACTIVE**  
 Das Steuerelement genügend Daten für die interaktive werden jedoch nicht alle asynchrone Daten werden noch geladen.  
  
 `READYSTATE_COMPLETE`  
 Steuerelement hat alle darin enthaltenen Daten  
  
 Verwendung [GetReadyState abrufbar](#getreadystate) um aktuelle Bereitschaft des Steuerelements zu bestimmen.  
  
 [InternalSetReadyState beispielsweise](#internalsetreadystate) ändert den Status "bereit" mit dem angegebenen Wert und ruft dann `FireReadyStateChange`.  
  
##  <a name="a-namegetactivationpolicya--colecontrolgetactivationpolicy"></a><a name="getactivationpolicy"></a>COleControl:: GetActivationPolicy  
 Ändert das Standardverhalten für die Aktivierung von einem Steuerelement, unterstützt die `IPointerInactive` Schnittstelle.  
  
```  
virtual DWORD GetActivationPolicy();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von Flags aus der **POINTERINACTIVE** Enumeration. Möglichen-Flags sind:  
  
 **POINTERINACTIVE_ACTIVATEONENTRY**  
 Das Objekt sollte direktes aktiviert, wenn der Mauszeiger während eines Verschiebevorgangs Maus bewegt wird.  
  
 **POINTERINACTIVE_DEACTIVATEONLEAVE**  
 Das Objekt sollte deaktiviert werden, wenn der Mauszeiger das Objekt während eines Verschiebevorgangs Maus wird.  
  
 **POINTERINACTIVE_ACTIVATEONDRAG**  
 Das Objekt sollte aktiviert, wenn die Maus darüber, während eines Ziehvorgangs gezogen wird an Ort und drop-Vorgangs.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `IPointerInactive` Schnittstelle aktiviert ist, wird der Container Delegieren `WM_SETCURSOR` und `WM_MOUSEMOVE` Nachrichten an ihn gesendet. `COleControl`die Implementierung dieser Schnittstelle werden diese Nachrichten über das Steuerelement Nachricht Zuordnung verteilen, nach dem Anpassen der Maus entsprechend koordiniert.  
  
 Jedes Mal, wenn der Container empfängt ein `WM_SETCURSOR` oder `WM_MOUSEMOVE` Nachricht mit den Mauszeiger über einem inaktiven Objekt unterstützt `IPointerInactive`, sollte es aufrufen `GetActivationPolicy` auf die Schnittstelle und die Rückgabe Flags aus der **POINTERINACTIVE** Enumeration.  
  
 Durch die Nachricht Zuordnung die entsprechenden Einträge hinzugefügt, können Sie diese Nachrichten wie normale Windows-Meldungen verarbeiten. In Ihre Ereignishandler verwenden Sie die `m_hWnd` Membervariable (oder Memberfunktionen, die es verwendet) erst überprüfen, dass der Wert nicht **NULL**.  
  
 Jedes Objekt den Zweck, legen Sie den Cursor mehr als und/oder ein MouseMove-Ereignis ausgelöst, z. B. wie spezielles visuelles Feedback, sollte Zurückgeben der **POINTERINACTIVE_ACTIVATEONENTRY** kennzeichnen und zeichnen Sie das Feedback nur, wenn Sie aktiv. Wenn das Objekt dieses Flag zurückgibt, der Container direkt sofort aktivieren und anschließend weiterleiten, die gleiche Nachricht, die den Aufruf von ausgelöst sollten `GetActivationPolicy`.  
  
 Wenn beide der **POINTERINACTIVE_ACTIVATEONENTRY** und **POINTERINACTIVE_DEACTIVATEONLEAVE** Flags werden zurückgegeben, und das Objekt wird nur aktiviert, wenn der Mauszeiger über dem Objekt befindet. Wenn nur der **POINTERINACTIVE_ACTIVATEONENTRY** Flag wird zurückgegeben, und das Objekt wird nur aktiviert, wenn wenn der Mauszeiger das Objekt zuerst eintritt.  
  
 Sie sollten auch ein Inaktives Steuerelement das Ziel einer OLE-Drag und drop-Vorgangs. Dies erfordert, aktivieren das Steuerelement zum Zeitpunkt der Benutzer ein Objekt darüber zieht, damit das Fenster des Steuerelements als Dropziel registriert werden kann. Zurück zum Auslösen des Aktivierung während eines Ziehvorgangs die **POINTERINACTIVE_ACTIVATEONDRAG** Kennzeichen:  
  
 [!code-cpp[NVC_MFCAxCtl&#1;](../../mfc/reference/codesnippet/cpp/colecontrol-class_1.cpp)]  
  
 Die Angaben von `GetActivationPolicy` von einem Container nicht zwischengespeichert werden. Stattdessen sollten diese Methode aufgerufen werden, jedes Mal, wenn der Mauszeiger in einem inaktiven Objekt bewegt wird.  
  
 Wenn einem inaktiven Objekt direktes aktiviert, wenn der Mauszeiger bewegt, es wird werden keine anfordert, sollte Containers nachfolgende senden `WM_SETCURSOR` Nachrichten an dieses Objekt durch Aufrufen von [OnInactiveSetCursor](#oninactivesetcursor) , solange der Mauszeiger über dem Objekt bleibt.  
  
 Aktivieren der `IPointerInactive` Schnittstelle bedeutet normalerweise, dass das Steuerelement immer Mausnachrichten verarbeitet werden soll. Dieses Verhalten in einem Container abgerufen wird, die nicht unterstützt die `IPointerInactive` -Schnittstelle, Sie müssen das Steuerelement immer aktiviert, wenn sichtbar, was bedeutet, dass das Steuerelement muss die **OLEMISC_ACTIVATEWHENVISIBLE** Kennzeichen auf ihre verschiedene Flags. Um zu verhindern, dass dieses Flag aus deren Inkrafttreten in einem Container, die unterstützt jedoch `IPointerInactive`, Sie können auch angeben, die **OLEMISC_IGNOREACTIVATEWHENVISIBLE** Flag:  
  
 [!code-cpp[NVC_MFCAxCtl&#10;](../../mfc/reference/codesnippet/cpp/colecontrol-class_2.cpp)]  
  
##  <a name="a-namegetambientpropertya--colecontrolgetambientproperty"></a><a name="getambientproperty"></a>COleControl:: GetAmbientProperty  
 Ruft den Wert der ambient-Eigenschaft des Containers.  
  
```  
BOOL GetAmbientProperty(
    DISPID dispid,  
    VARTYPE vtProp,  
    void* pvProp);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispid*  
 Die Dispatch-ID der gewünschten ambient-Eigenschaft.  
  
 `vtProp`  
 Ein variant-Typ-Tag, das den Typ des zurückzugebenden Werts angibt `pvProp`.  
  
 `pvProp`  
 Ein Zeiger auf die Adresse der Variablen, die den Wert der Eigenschaft empfangen oder Rückgabewert. Der tatsächliche Typ des this-Zeiger muss den vom angegebenen Typ übereinstimmen `vtProp`.  
  
|vtProp|Typ des pvProp|  
|------------|--------------------|  
|`VT_BOOL`|**BOOL\***|  
|`VT_BSTR`|**CString\***|  
|`VT_I2`|**kurze\***|  
|`VT_I4`|**lange\***|  
|`VT_R4`|**float\***|  
|`VT_R8`|**Double\***|  
|`VT_CY`|**CY\***|  
|**DEN WERT VT_COLOR**|**OLE_COLOR\***|  
|**VT_DISPATCH**|**LPDISPATCH\***|  
|**VT_FONT**|**LPFONTDISP\***|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Ambiente-Eigenschaft unterstützt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei Verwendung von `GetAmbientProperty` legen Sie zum Abrufen der ambient-Eigenschaften "DisplayName" und "ScaleUnits" `vtProp` auf `VT_BSTR` und `pvProp` auf **CString\***. Wenn Sie die Ambiente-Font-Eigenschaft abrufen, `vtProp` auf **VT_FONT** und `pvProp` auf **LPFONTDISP\***.  
  
 Beachten Sie, dass Funktionen wie z. B. bereits allgemeine Umgebungseigenschaften, bereitgestellt worden sind [AmbientBackColor](#ambientbackcolor) und [AmbientFont](#ambientfont).  
  
##  <a name="a-namegetappearancea--colecontrolgetappearance"></a><a name="getappearance"></a>COleControl::GetAppearance  
 Implementiert die Get-Funktion der vordefinierten Appearance-Eigenschaft des Steuerelements.  
  
```  
short GetAppearance ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt die aktuelle Einstellung der Darstellung einer **kurze** ( `VT_I2`) Wert, wenn erfolgreich. Dieser Wert ist 0 (null), wenn die Darstellung des Steuerelements flach und 1 ist, ist die Darstellung des Steuerelements 3D.  
  
##  <a name="a-namegetbackcolora--colecontrolgetbackcolor"></a><a name="getbackcolor"></a>COleControl::GetBackColor  
 Implementiert die Get-Funktion der vordefinierten BackColor-Eigenschaft des Steuerelements.  
  
```  
OLE_COLOR GetBackColor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt die aktuelle Hintergrundfarbe als ein **OLE_COLOR** Wert, wenn erfolgreich. Dieser Wert übersetzt werden kann, um eine **COLORREF** Wert mit einem Aufruf von `TranslateColor`.  
  
##  <a name="a-namegetborderstylea--colecontrolgetborderstyle"></a><a name="getborderstyle"></a>COleControl::GetBorderStyle  
 Implementiert die Get-Funktion der vordefinierten BorderStyle-Eigenschaft des Steuerelements.  
  
```  
short GetBorderStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 1, wenn das Steuerelement einen normalen Rahmen hat. 0, wenn das Steuerelement kein Rahmen hat.  
  
##  <a name="a-namegetcapturea--colecontrolgetcapture"></a><a name="getcapture"></a>COleControl::GetCapture  
 Bestimmt, ob die `COleControl` Objekt verfügt über das Erfassen von Mauseingaben.  
  
```  
CWnd* GetCapture();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Steuerelement aktiviert und das fensterlose ist, gibt **dies** , wenn das Steuerelement gerade das Erfassen von Mauseingaben (wie vom Container des Steuerelements festgelegt wird), hat oder **NULL** verfügt es nicht die Erfassung.  
  
 Andernfalls gibt die `CWnd` -Objekt, das die Maus erfasst wird (wie `CWnd::GetCapture`).  
  
### <a name="remarks"></a>Hinweise  
 Ein aktiviertes fensterloses Steuerelement empfängt die Maus erfassen, wenn [SetCapture](#setcapture) aufgerufen wird.  
  
##  <a name="a-namegetclassida--colecontrolgetclassid"></a><a name="getclassid"></a>COleControl::GetClassID  
 Aufgerufen, um die OLE-Klassen-ID des Steuerelements abzurufen.  
  
```  
virtual HRESULT GetClassID(LPCLSID pclsid) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *pclsid*  
 Zeiger auf den Speicherort der Klasse-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf nicht erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel implementiert, indem die [IMPLEMENT_OLECREATE_EX](class-factories-and-licensing.md#implement_olecreate_ex).  
  
##  <a name="a-namegetclientoffseta--colecontrolgetclientoffset"></a><a name="getclientoffset"></a>COleControl::GetClientOffset  
 Ruft die Differenz zwischen der oberen linken Ecke des rechteckigen Bereichs des Steuerelements und der linken Ecke des Clientbereichs ab.  
  
```  
virtual void GetClientOffset(long* pdxOffset, long* pdyOffset) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pdxOffset*  
 Ein Zeiger auf den horizontalen Offset des Clientbereichs des OLE-Steuerelements.  
  
 *pdyOffset*  
 Ein Zeiger auf den vertikalen Offset des Clientbereichs des OLE-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 OLE-Steuerelement verfügt über einen rechteckigen Bereich innerhalb des Containers. Der Clientbereich des Steuerelements ist ohne Rahmen und Bildlaufleisten Steuerelementbereich. Der Offset von abgerufenen `GetClientOffset` ist der Unterschied zwischen der oberen linken Ecke des rechteckigen Bereichs des Steuerelements und der linken Ecke des Clientbereichs. Wenn das Steuerelement nicht-Client-Elemente als die standardmäßige Rahmen und Bildlaufleisten verfügt, überschreiben Sie diese Memberfunktion, um den Offset angeben.  
  
##  <a name="a-namegetclientrecta--colecontrolgetclientrect"></a><a name="getclientrect"></a>COleControl::GetClientRect  
 Ruft die Größe des Clientbereichs des Steuerelements ab.  
  
```  
virtual void GetClientRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Zeiger auf eine `RECT` -Struktur, die die Dimensionen des Clientbereichs der fensterloses Steuerelement enthält, d. h. die Größe des Steuerelements minus Fensterrahmen, Frames, Bildlaufleisten und So weiter. Die `lpRect` Parameter gibt die Größe des Steuerelements Clientrechteck, nicht seine Position an.  
  
##  <a name="a-namegetclientsitea--colecontrolgetclientsite"></a><a name="getclientsite"></a>COleControl::GetClientSite  
 Abfragen ein Objekts für den Zeiger auf die aktuelle Site in dessen Container.  
  
```  
LPOLECLIENTSITE GetClientSite();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Clientsite des Steuerelements in dessen Container.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Zeiger zeigt auf eine Instanz von `IOleClientSite`. Die `IOleClientSite` Schnittstelle von Containern implementiert ist das Objekt anzeigen seines Kontexts:, wo er im Dokument, in den Speicher, Benutzeroberfläche und andere Ressourcen abgerufen verankert ist.  
  
##  <a name="a-namegetcontrolflagsa--colecontrolgetcontrolflags"></a><a name="getcontrolflags"></a>COleControl:: GetControlFlags  
 Ruft die Steuerelement-Flageinstellungen ab.  
  
```  
virtual DWORD GetControlFlags();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein ORed Kombination der Flags in der Enumeration ControlFlags:  
  
 `enum ControlFlags {`  
  
 `fastBeginPaint = 0x0001,`  
  
 `clipPaintDC = 0x0002,`  
  
 `pointerInactive = 0x0004,`  
  
 `noFlickerActivate = 0x0008,`  
  
 `windowlessActivate = 0x0010,`  
  
 `canOptimizeDraw = 0x0020,`  
  
 `};`  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `GetControlFlags` gibt `fastBeginPaint | clipPaintDC`.  
  
 `fastBeginPaint`  
 Wenn festgelegt, verwendet ein Begin-Paint-Funktion für OLE-Steuerelemente statt zugeschnitten sind die [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) API (Standardeinstellung).  
  
 `clipPaintDC`  
 Wenn nicht festgelegt, deaktiviert den Aufruf von `IntersectClipRect` vom `COleControl` und erhält einen geringen Leistungsvorteil. Wenn Sie fensterlosen Aktivierung verwenden, ist das Flag keine Auswirkung.  
  
 `pointerInactive`  
 Wenn festgelegt, Mausinteraktion bietet, während das Steuerelement mittels inaktiv ist `COleControl`der Implementierung der `IPointerInactive` -Schnittstelle, die standardmäßig deaktiviert ist.  
  
 `noFlickerActivate`  
 Wenn festgelegt ist, entfernt zusätzliche Zeichenoperationen und das damit verbundene Flimmern. Wird verwendet, wenn das Steuerelement selbst in die inaktiven und den aktiven Status identisch zeichnet. Wenn Sie fensterlosen Aktivierung verwenden, ist das Flag keine Auswirkung.  
  
 `windowlessActivate`  
 Wenn festgelegt ist, gibt an, das Steuerelement fensterlosen Aktivierung verwendet.  
  
 `canOptimizeDraw`  
 Wenn festgelegt ist, gibt an, dass das Steuerelement optimierte Zeichnung ausgeführt wird, wenn der Container unterstützt.  
  
 Weitere Informationen zu `GetControlFlags` und andere Optimierungen der OLE-Steuerelemente finden Sie unter [ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-namegetcontrolsizea--colecontrolgetcontrolsize"></a><a name="getcontrolsize"></a>COleControl::GetControlSize  
 Ruft die Größe des Fensters OLE-Steuerelements ab.  
  
```  
void GetControlSize(
    int* pcx,  
    int* pcy);
```  
  
### <a name="parameters"></a>Parameter  
 *PCX*  
 Gibt die Breite des Steuerelements in Pixel.  
  
 *pcy*  
 Gibt die Höhe des Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass alle Koordinaten für Windows Steuerelement relativ zu der oberen linken Ecke des Steuerelements.  
  
##  <a name="a-namegetdca--colecontrolgetdc"></a><a name="getdc"></a>COleControl::GetDC  
 Stellt Sie bereit für ein Objekt fensterlose Gerätekontext Get einen Bildschirm (oder einen kompatiblen) von seinem Container.  
  
```  
CDC* GetDC(
    LPCRECT lprcRect = NULL,
    DWORD dwFlags = OLEDC_PAINTBKGND);
```  
  
### <a name="parameters"></a>Parameter  
 *lprcRect*  
 Ein Zeiger auf das Rechteck fensterloses Steuerelement möchte, in Clientkoordinaten des Steuerelements neu zu zeichnen. **NULL** bedeutet, dass das vollständige Objekt Block.  
  
 `dwFlags`  
 Zeichnen die Attribute des Gerätekontexts. Auswahlmöglichkeiten sind:  
  
- **OLEDC_NODRAW** gibt an, dass das Objekt den Gerätekontext Ausführen jeder Zeichenvorgang jedoch nur zum Abrufen von Informationen zu dem Anzeigegerät verwenden werden. Der Container sollte das Fenster DC einfach ohne weitere Verarbeitung übergeben.  
  
- **OLEDC_PAINTBKGND** angefordert wird, dass der Container den Hintergrund zeichnen, vor der Rückgabe des Domänencontrollers. Ein Objekt sollten dieses Flag verwenden, wenn sie einen DC für das Neuzeichnen eines Bereichs mit transparentem Hintergrund anfordert.  
  
- **OLEDC_OFFSCREEN** informiert den Container, der möchte, dass das Objekt in einer Offscreen-Bitmap gerendert werden, die dann auf den Bildschirm kopiert werden sollen. Ein Objekt sollten dieses Flag verwenden, wenn der Vorgang ausführen, viele Flimmern generiert. Der Container kann diese Anforderung oder nicht berücksichtigt. Jedoch wenn dieses Flag nicht festgelegt ist, der Container muss übergeben wieder ein auf dem Bildschirm DC. Dadurch können Objekte, z. B. eine Auswahl mit direkten Bildschirm Vorgänge (über eine **XOR** Vorgang).  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf den Anzeigegerätekontext für den Container `CWnd` Clientbereich Wenn erfolgreich, andernfalls der Rückgabewert ist **NULL**. Die Anzeige-Gerätekontext kann in nachfolgenden GDI-Funktionen zum Zeichnen im Clientbereich des Fensters für den Container verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die [ReleaseDC](#releasedc) -Memberfunktion aufgerufen werden, um den Kontext freigeben, nachdem das Zeichnen. Beim Aufrufen von `GetDC`, Objekte übergeben, das Rechteck, das sie in in ihre eigenen Clientkoordinaten zeichnen möchten. `GetDC`übersetzt diese Koordinaten des Clientbereichs Container. Das Objekt sollten nicht anfordern einer gewünschten zeichnen Rechteck größer ist als seine eigenen Bereich Clientrechteck, dessen Größe abgerufen werden kann, mit [GetClientRect](#getclientrect). Dadurch wird verhindert, dass Objekte versehentlich zeichnen, in denen nicht auf für Sie bestimmt sind.  
  
##  <a name="a-namegetenableda--colecontrolgetenabled"></a><a name="getenabled"></a>COleControl::GetEnabled  
 Implementiert die Funktion Get an Bestands-Enabled-Eigenschaft des Steuerelements.  
  
```  
BOOL GetEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement aktiviert ist; andernfalls 0.  
  
##  <a name="a-namegetextendedcontrola--colecontrolgetextendedcontrol"></a><a name="getextendedcontrol"></a>COleControl::GetExtendedControl  
 Erhält einen Zeiger auf ein Objekt, das Beibehalten von der Container, der das Steuerelement über einen erweiterten Satz von Eigenschaften darstellt.  
  
```  
LPDISPATCH GetExtendedControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Container des Steuerelementobjekt erweitert. Wenn kein Objekt vorhanden ist, ist der Wert **NULL**.  
  
 Dieses Objekt kann bearbeitet werden, bis die `IDispatch` Schnittstelle. Sie können auch `QueryInterface` zum Abrufen von anderen verfügbaren Schnittstellen, die vom Objekt bereitgestellt werden. Das Objekt ist jedoch nicht erforderlich, um einen bestimmten Satz von Schnittstellen zu unterstützen. Beachten Sie, dass auf bestimmte Features des erweiterten Steuerelementobjekt des Containers die Portabilität des Steuerelements für andere beliebige Container beschränkt.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion, die diese Funktion ruft ist verantwortlich für die Freigabe des Zeigers, wenn das Objekt nicht mehr benötigen. Beachten Sie, dass der Container ist nicht erforderlich, dieses Objekt unterstützt.  
  
##  <a name="a-namegetfocusa--colecontrolgetfocus"></a><a name="getfocus"></a>COleControl::GetFocus  
 Bestimmt, ob die `COleControl` Objekt den Fokus besitzt.  
  
```  
CWnd* GetFocus();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Steuerelement aktiviert und das fensterlose ist, gibt **dies** Wenn das Steuerelement gerade den Tastaturfokus (wie vom Container des Steuerelements festgelegt), verfügt oder **NULL** , wenn sie nicht über den Fokus verfügt.  
  
 Andernfalls gibt die `CWnd` -Objekt, das den Fokus besitzt (wie `CWnd::GetFocus`).  
  
### <a name="remarks"></a>Hinweise  
 Ein aktiviertes fensterloses Steuerelement den Fokus erhält, wenn [SetFocus](#setfocus) aufgerufen wird.  
  
##  <a name="a-namegetfonta--colecontrolgetfont"></a><a name="getfont"></a>COleControl::GetFont  
 Implementiert die Get-Funktion der vordefinierten Font-Eigenschaft.  
  
```  
LPFONTDISP GetFont();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schriftart Dispatch-Schnittstelle des Steuerelements Stock Font-Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass das Objekt nach Abschluss des Aufrufers freigegeben werden muss. Verwenden Sie in der Implementierung des Steuerelements, `InternalGetFont` Zugriff auf das Steuerelement stock Font-Objekt. Weitere Informationen zur Verwendung von Schriftarten in Ihrem Steuerelement finden Sie im Artikel [ActiveX-Steuerelemente: Verwenden von Schriftarten in einem ActiveX-Steuerelement](../../mfc/mfc-activex-controls-using-fonts.md).  
  
##  <a name="a-namegetfonttextmetricsa--colecontrolgetfonttextmetrics"></a><a name="getfonttextmetrics"></a>COleControl::GetFontTextMetrics  
 Misst die Text-Metriken für alle `CFontHolder` Objekt im Besitz des Steuerelements.  
  
```  
void GetFontTextMetrics(
    LPTEXTMETRIC lptm,  
    CFontHolder& fontHolder);
```  
  
### <a name="parameters"></a>Parameter  
 `lptm`  
 Zeiger auf eine [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) Struktur.  
  
 `fontHolder`  
 Ein Verweis auf eine [CFontHolder](../../mfc/reference/cfontholder-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Eine solche Schriftart ausgewählt werden kann, mit der [COleControl::SelectFontObject](#selectfontobject) Funktion. `GetFontTextMetrics`Initialisieren der `TEXTMETRIC` Struktur verweist `lptm` gültige Metriken Informationen `fontHolder`der Schriftart, wenn erfolgreich, oder die Struktur mit Nullen füllen, wenn nicht erfolgreich. Sie sollten diese Funktion nicht verwenden [GetTextMetrics](http://msdn.microsoft.com/library/windows/desktop/dd144941) beim Zeichnen des Steuerelements, da möglicherweise Steuerelemente, wie OLE-Objekt eingebettete zum selbst in einer Metadatei darzustellen.  
  
 Die `TEXTMETRIC` -Struktur für die Standardschriftart ist aktualisiert, wenn die [SelectFontObject](#selectfontobject) -Funktion aufgerufen wird. Rufen Sie `GetFontTextMetrics` nur nach der Auswahl der vordefinierten Schriftarteigenschaft, um die Informationen zu gewährleisten, es bietet, gültig ist.  
  
##  <a name="a-namegetforecolora--colecontrolgetforecolor"></a><a name="getforecolor"></a>COleControl::GetForeColor  
 Implementiert die Get-Funktion der vordefinierten ForeColor-Eigenschaft.  
  
```  
OLE_COLOR GetForeColor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt die aktuelle Vordergrundfarbe als ein **OLE_COLOR** Wert, wenn erfolgreich. Dieser Wert übersetzt werden kann, um eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert mit einem Aufruf von `TranslateColor`.  
  
##  <a name="a-namegethwnda--colecontrolgethwnd"></a><a name="gethwnd"></a>COleControl::GetHwnd  
 Implementiert die Get-Funktion der vordefinierten hWnd-Eigenschaft.  
  
```  
OLE_HANDLE GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das OLE-Steuerelement-Fensterhandle, falls vorhanden; andernfalls **NULL**.  
  
##  <a name="a-namegetmessagestringa--colecontrolgetmessagestring"></a><a name="getmessagestring"></a>COleControl::GetMessageString  
 Aufgerufen, um eine kurze Zeichenfolge abzurufen, die den Zweck des Menüelements identifizierten beschreibt `nID`.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ein Menü-ID auf.  
  
 `rMessage`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt über die eine Zeichenfolge zurückgegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Dies kann verwendet werden, um eine Nachricht für die Anzeige in einer Statusleiste zu erhalten, während das Menüelement hervorgehoben ist. Die standardmäßige Implementierung versucht, beim Laden einer Zeichenfolgenressource identifizierten `nID`.  
  
##  <a name="a-namegetnotsupporteda--colecontrolgetnotsupported"></a><a name="getnotsupported"></a>COleControl::GetNotSupported  
 Verhindert den Zugriff auf den Eigenschaftswert eines Steuerelements, durch den Benutzer.  
  
```  
void GetNotSupported();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion anstelle einer Eigenschaft die Get-Funktion, in dem Abrufen der Eigenschaft vom Benutzer des Steuerelements nicht unterstützt. Ein Beispiel wäre eine Eigenschaft, die nur Schreibzugriff ist.  
  
##  <a name="a-namegetreadystatea--colecontrolgetreadystate"></a><a name="getreadystate"></a>COleControl::GetReadyState  
 Gibt den Status der Bereitschaft des Steuerelements zurück.  
  
```  
long GetReadyState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status der Bereitschaft des Steuerelements einen der folgenden Werte:  
  
 **READYSTATE_UNINITIALIZED**  
 Initialisierung der Standardstatus  
  
 **READYSTATE_LOADING**  
 Steuerelement wird seine Eigenschaften derzeit geladen werden.  
  
 **READYSTATE_LOADED**  
 Steuerelement wurde initialisiert.  
  
 **READYSTATE_INTERACTIVE**  
 Das Steuerelement genügend Daten für die interaktive werden jedoch nicht alle asynchrone Daten werden noch geladen.  
  
 `READYSTATE_COMPLETE`  
 Steuerelement hat alle darin enthaltenen Daten  
  
### <a name="remarks"></a>Hinweise  
 Die meisten einfachen Steuerelemente müssen nie zur Unterscheidung **LOADED** und `INTERACTIVE`. Allerdings Steuerelemente, die Daten Pfadeigenschaften unterstützen möglicherweise nicht interaktive werden, bis mindestens einige Daten asynchron empfangen werden. Ein Steuerelement sollten so bald wie möglich interaktiv.  
  
##  <a name="a-namegetrectincontainera--colecontrolgetrectincontainer"></a><a name="getrectincontainer"></a>COleControl::GetRectInContainer  
 Ruft die Koordinaten der das Rechteck des Steuerelements relativ zu dem Container, ausgedrückt in Geräteeinheiten ab.  
  
```  
BOOL GetRectInContainer(LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Ein Zeiger auf das Rectangle-Struktur, die die Koordinaten des Steuerelements kopiert werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement direkt aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Rechteck ist nur gültig, wenn das Steuerelement direkt aktiv ist.  
  
##  <a name="a-namegetstocktextmetricsa--colecontrolgetstocktextmetrics"></a><a name="getstocktextmetrics"></a>COleControl::GetStockTextMetrics  
 Misst die Text-Metriken für das Steuerelement stock Font-Eigenschaft, die mit ausgewählt werden können die [SelectStockFont](#selectstockfont) Funktion.  
  
```  
void GetStockTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Parameter  
 `lptm`  
 Ein Zeiger auf eine [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die `GetStockTextMetrics` Funktion initialisiert den `TEXTMETRIC` Struktur verweist `lptm` mit gültigen metrikinformationen im Erfolgsfall oder füllen Sie die Struktur mit Nullen aufgefüllt, wenn nicht erfolgreich. Verwenden Sie diese Funktion anstelle von [GetTextMetrics](http://msdn.microsoft.com/library/windows/desktop/dd144941) beim Zeichnen des Steuerelements, da möglicherweise Steuerelemente, wie OLE-Objekt eingebettete zum selbst in einer Metadatei darzustellen.  
  
 Die `TEXTMETRIC` -Struktur für die Standardschriftart ist aktualisiert, wenn die `SelectStockFont` -Funktion aufgerufen wird. Sie sollten diese Funktion aufrufen, erst nach dem Auswählen der vordefinierten Schriftart, die Informationen zu gewährleisten, die es bietet, gültig ist.  
  
##  <a name="a-namegettexta--colecontrolgettext"></a><a name="gettext"></a>COleControl::GetText  
 Implementiert die Get-Funktion der vordefinierten Text oder Caption-Eigenschaft.  
  
```  
BSTR GetText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Wert der Text-Zeichenfolge oder eine Zeichenfolge der Länge&0; (null), wenn keine Zeichenfolge vorhanden ist.  
  
> [!NOTE]
>  Weitere Informationen zu den `BSTR` -Datentyp finden Sie unter [Datentypen](../../mfc/reference/data-types-mfc.md) im Abschnitt Makros und Globals.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die der Aufrufer dieser Funktion aufrufen muss `SysFreeString` auf die Zeichenfolge zurückgegeben, kostenlose Ressource. Verwenden Sie in der Implementierung des Steuerelements, `InternalGetText` auf vordefinierte Text oder Caption-Eigenschaft des Steuerelements zugreifen.  
  
##  <a name="a-namegetwindowlessdroptargeta--colecontrolgetwindowlessdroptarget"></a><a name="getwindowlessdroptarget"></a>COleControl:: GetWindowlessDropTarget  
 Überschreiben Sie `GetWindowlessDropTarget` soll ein fensterloses Steuerelement ist das Ziel ein OLE Drag & drop-Vorgangs.  
  
```  
virtual IDropTarget* GetWindowlessDropTarget();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das Objekt `IDropTarget` Schnittstelle. Ein fensterloses-Objekt kann nicht registriert werden, da sie nicht über ein Fenster verfügt, eine `IDropTarget` Schnittstelle. Jedoch zur Teilnahme an Drag & Drop eine fensterlose Objekt kann weiterhin die-Schnittstelle implementieren und zurück in `GetWindowlessDropTarget`.  
  
### <a name="remarks"></a>Hinweise  
 Normalerweise würde dies erfordern, dass das Fenster des Steuerelements als Dropziel registriert werden. Da das Steuerelement kein eigenes Fenster besitzt, der Container wird jedoch ein eigenes Fenster als Ablageziel. Das Steuerelement muss lediglich eine Implementierung bereitstellen der `IDropTarget` Schnittstelle, der der Container Aufrufe zum entsprechenden Zeitpunkt delegieren. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAxCtl&#2;](../../mfc/reference/codesnippet/cpp/colecontrol-class_3.cpp)]  
  
##  <a name="a-nameinitializeiidsa--colecontrolinitializeiids"></a><a name="initializeiids"></a>COleControl::InitializeIIDs  
 Benachrichtigt die Basisklasse den IIDs, die das Steuerelement verwendet.  
  
```  
void InitializeIIDs(
    const IID* piidPrimary,
    const IID* piidEvents);
```  
  
### <a name="parameters"></a>Parameter  
 *piidPrimary*  
 Ein Zeiger auf die Schnittstellen-ID des Steuerelements primären Dispatch-Schnittstellen.  
  
 *piidEvents*  
 Ein Zeiger auf die Schnittstellen-ID des Steuerelements Ereignisschnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion im Konstruktor des Steuerelements, um die Basisklasse für die Schnittstellen-IDs zu informieren, die das Steuerelement verwenden werden.  
  
##  <a name="a-nameinternalgetfonta--colecontrolinternalgetfont"></a><a name="internalgetfont"></a>COleControl::InternalGetFont  
 Greift auf die vordefinierte Schriftarteigenschaft des Steuerelements  
  
```  
CFontHolder& InternalGetFont();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine [CFontHolder](../../mfc/reference/cfontholder-class.md) -Objekt, das vordefinierte Font-Objekt enthält.  
  
##  <a name="a-nameinternalgettexta--colecontrolinternalgettext"></a><a name="internalgettext"></a>COleControl::InternalGetText  
 Greift auf die vordefinierte Text oder Caption-Eigenschaft des Steuerelements.  
  
```  
const CString& InternalGetText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die Text-Zeichenfolge.  
  
##  <a name="a-nameinternalsetreadystatea--colecontrolinternalsetreadystate"></a><a name="internalsetreadystate"></a>COleControl::InternalSetReadyState  
 Legt die Bereitschaft Zustand des Steuerelements fest.  
  
```  
void InternalSetReadyState(long lNewReadyState);
```  
  
### <a name="parameters"></a>Parameter  
 *lNewReadyState*  
 Der Status der Bereitschaft für das Steuerelement einen der folgenden Werte festgelegt:  
  
 **READYSTATE_UNINITIALIZED**  
 Initialisierung der Standardstatus  
  
 **READYSTATE_LOADING**  
 Steuerelement wird seine Eigenschaften derzeit geladen werden.  
  
 **READYSTATE_LOADED**  
 Steuerelement wurde initialisiert.  
  
 **READYSTATE_INTERACTIVE**  
 Das Steuerelement genügend Daten für die interaktive werden jedoch nicht alle asynchrone Daten werden noch geladen.  
  
 `READYSTATE_COMPLETE`  
 Steuerelement hat alle darin enthaltenen Daten  
  
### <a name="remarks"></a>Hinweise  
 Die meisten einfachen Steuerelemente müssen nie zur Unterscheidung **LOADED** und `INTERACTIVE`. Allerdings Steuerelemente, die Daten Pfadeigenschaften unterstützen möglicherweise nicht interaktive werden, bis mindestens einige Daten asynchron empfangen werden. Ein Steuerelement sollten so bald wie möglich interaktiv.  
  
##  <a name="a-nameinvalidatecontrola--colecontrolinvalidatecontrol"></a><a name="invalidatecontrol"></a>COleControl::InvalidateControl  
 Zwingt das Steuerelement neu gezeichnet werden muss.  
  
```  
void InvalidateControl(
    LPCRECT lpRect = NULL,  
    BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Ein Zeiger auf den Bereich des Steuerelements für ungültig erklärt werden.  
  
 `bErase`  
 Gibt an, ob in den Aktualisierungsbereich Hintergrund gelöscht werden, wenn der Aktualisierungsbereich verarbeitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `lpRect` hat ein **NULL** Wert, wird das gesamte Steuerelement neu gezeichnet werden. Wenn `lpRect` nicht **NULL**, dies weist darauf hin, der Teil des Steuerelements Rechteck, das für ungültig erklärt werden. In Fällen, in dem das Steuerelement verfügt über kein Fenster oder ist nicht aktiviert, das Rechteck wird ignoriert, und ein Aufruf erfolgt der Clientstandort [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337) Member-Funktion. Verwenden Sie diese Funktion anstelle von `CWnd::InvalidateRect` oder `InvalidateRect`.  
  
##  <a name="a-nameinvalidatergna--colecontrolinvalidatergn"></a><a name="invalidatergn"></a>COleControl::InvalidateRgn  
 Erklärt die Container Clientbereich innerhalb dieser Region.  
  
```  
void InvalidateRgn(CRgn* pRgn, BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Ein Zeiger auf eine [CRgn](../../mfc/reference/crgn-class.md) Objekt, das den Anzeigebereich des OLE-Objekts für ungültig zu erklärende in Clientkoordinaten des enthaltenden Fensters identifiziert. Wenn dieser Parameter **NULL**, der Block wird das gesamte Objekt.  
  
 `bErase`  
 Gibt an, ob der Hintergrund der für ungültig erklärten Bereich gelöscht werden. Wenn **TRUE**, Hintergrund wird gelöscht. Wenn **FALSE**, Hintergrund bleibt unverändert.  
  
### <a name="remarks"></a>Hinweise  
 Dies kann zum Neuzeichnen Fensterlose Steuerelemente im Container verwendet werden. Für ungültig erklärten Bereich, zusammen mit allen anderen Bereichen in der Region Update ist für das Zeichnen, wenn markiert den nächsten [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht gesendet wird.  
  
 Wenn `bErase` ist **TRUE** für jeden Teil der Aktualisierungsbereich, den gesamten Bereich nicht nur im angegebenen Teil der Hintergrund wird gelöscht.  
  
##  <a name="a-nameisconvertingvbxa--colecontrolisconvertingvbx"></a><a name="isconvertingvbx"></a>COleControl::IsConvertingVBX  
 Können spezielle Laden eines OLE-Steuerelements.  
  
```  
BOOL IsConvertingVBX();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement konvertiert wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Beim Konvertieren eines Formulars, das VBX verwendet, zu einem, die OLE-Steuerelemente verwendet Steuerelemente, kann spezielle laden-Code für die OLE-Steuerelemente erforderlich sein. Z. B. Wenn Sie eine Instanz des OLE-Steuerelements laden, müssen Sie möglicherweise einen Aufruf von [PX_Font](persistence-of-ole-controls.md#px_font) in Ihrem `DoPropExchange`:  
  
 [!code-cpp[NVC_MFCAxCtl&3;](../../mfc/reference/codesnippet/cpp/colecontrol-class_4.cpp)]  
  
 VBX-Steuerelemente haben jedoch kein Font-Objekt; jedes Font-Eigenschaft wurde einzeln gespeichert. In diesem Fall würden Sie verwenden `IsConvertingVBX` zwischen diesen beiden Fällen unterscheiden:  
  
 [!code-cpp[NVC_MFCAxCtl&4;](../../mfc/reference/codesnippet/cpp/colecontrol-class_5.cpp)]  
  
 Ein weiterer Fall wäre, wenn Ihr VBX-Steuerelement proprietäre Binärdaten gespeichert (in der **VBM_SAVEPROPERTY** Message-Handler), und das OLE-Steuerelement die binären Daten in einem anderen Format gespeichert. Wenn Sie möchten, dass das OLE-Steuerelement werden abwärtskompatibel mit dem VBX-Steuerelement kann sowohl die alten und neuen Formate mit Lesen der `IsConvertingVBX` Funktion unterscheiden, ob der VBX-Steuerelement oder das OLE-Steuerelement geladen wurde.  
  
 In Ihrem Steuerelements `DoPropExchange` -Funktion können Sie für diese Bedingung überprüfen und führen Sie bei "true" Load-Code für diese Konvertierung (z. B. den vorherigen Beispielen). Wenn das Steuerelement nicht konvertiert wird, können Sie normale Auslastung Code ausführen. Diese Funktion gilt nur für Steuerelemente, die von VBX-Entsprechungen konvertiert wird.  
  
##  <a name="a-nameisinvokealloweda--colecontrolisinvokeallowed"></a><a name="isinvokeallowed"></a>COleControl::IsInvokeAllowed  
 Ermöglicht die Automatisierung-Methodenaufruf.  
  
```  
BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Implementierung des Frameworks **IDispatch:: Invoke** Aufrufe **Sie IsInvokeAllowed** bestimmen, ob eine bestimmte Funktion (identifiziert durch `dispid`) aufgerufen werden kann. Das Standardverhalten für ein OLE-Steuerelement ist, ermöglichen die Automatisierungsmethoden aufgerufen werden, nur, wenn das Steuerelement initialisiert wurde. allerdings **Sie IsInvokeAllowed** ist eine virtuelle Funktion und kann überschrieben werden, falls erforderlich (beispielsweise, wenn das Steuerelement als Automatisierungsserver verwendet wird). Weitere Informationen finden Sie im Knowledge Base-Artikel Q166472, "So wird's gemacht: verwenden ein OLE-Steuerelements als Automatisierungsserver." Knowledge Base-Artikeln finden Sie in der MSDN Library Visual Studio-Dokumentation oder unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-nameismodifieda--colecontrolismodified"></a><a name="ismodified"></a>COleControl::IsModified  
 Bestimmt, ob der Zustand des Steuerelements geändert wurde.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Zustand des Steuerelements geändert wurde, seit es zuletzt gespeichert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Zustand eines Steuerelements wird geändert, wenn der Wert eine Eigenschaft geändert wird.  
  
##  <a name="a-nameisoptimizeddrawa--colecontrolisoptimizeddraw"></a><a name="isoptimizeddraw"></a>COleControl::IsOptimizedDraw  
 Bestimmt, ob der Container für den aktuellen Vorgang optimierte Zeichnung unterstützt.  
  
```  
BOOL IsOptimizedDraw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn der Container unterstützt, andernfalls für den aktuellen Zeichenvorgang zeichnen optimierte **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn optimiertes Zeichnen unterstützt wird, muss das Steuerelement nicht wählen alten Objekte (Stifte, Pinsel, Schriftarten, usw.) im Gerätekontext nach Abschluss der Zeichnung.  
  
##  <a name="a-nameissubclassedcontrola--colecontrolissubclassedcontrol"></a><a name="issubclassedcontrol"></a>COleControl::IsSubclassedControl  
 Aufgerufen, um festzustellen, ob steuern, die Unterklassen der Steuerelemente einer Windows.  
  
```  
virtual BOOL IsSubclassedControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement als Unterklasse definiert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie überschreiben diese Funktion und zurückgeben müssen **TRUE** Wenn Ihre OLE Unterklassen eines Windows-Steuerelements.  
  
##  <a name="a-nameloada--colecontrolload"></a><a name="load"></a>COleControl::Load  
 Setzt alle vorherigen Daten asynchron geladen und initialisiert ein neues Laden der asynchronen Eigenschaften des Steuerelements.  
  
```  
void Load(LPCTSTR strNewPath, CDataPathProperty& prop);
```  
  
### <a name="parameters"></a>Parameter  
 *strNewPath*  
 Ein Zeiger auf eine Zeichenfolge mit dem Pfad, der die absolute Position der asynchronen Steuerelementeigenschaft verweist.  
  
 *Prop*  
 Ein [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) Objekt implementiert eine asynchrone Steuerelementeigenschaft.  
  
##  <a name="a-namelockinplaceactivea--colecontrollockinplaceactive"></a><a name="lockinplaceactive"></a>COleControl::LockInPlaceActive  
 Verhindert, dass den Container das Steuerelement deaktivieren.  
  
```  
BOOL LockInPlaceActive(BOOL bLock);
```  
  
### <a name="parameters"></a>Parameter  
 `bLock`  
 **TRUE** ist die direkte aktive Status des Steuerelements gesperrt werden. **FALSE** um entsperrt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Sperre erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass alle Sperren des Steuerelements kombiniert werden muss mit einer Entsperren des Steuerelements Beendigung. Sie sollten nur das Steuerelement für kurze Zeit beim Auslösen eines Ereignisses, z. B. sperren.  
  
##  <a name="a-nameonambientpropertychangea--colecontrolonambientpropertychange"></a><a name="onambientpropertychange"></a>COleControl::OnAmbientPropertyChange  
 Wird vom Framework aufgerufen, wenn eine Ambiente-Eigenschaft des Containers Wert geändert wurde.  
  
```  
virtual void OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 *dispID*  
 Die Dispatch-ID der ambient-Eigenschaft, die geändert, oder **u. DISPID_UNKNOWN lauten** Wenn mehrere Eigenschaften geändert haben.  
  
##  <a name="a-nameonappearancechangeda--colecontrolonappearancechanged"></a><a name="onappearancechanged"></a>COleControl::OnAppearanceChanged  
 Wird vom Framework aufgerufen, wenn die vordefinierte Darstellung-Eigenschaftswert geändert hat.  
  
```  
virtual void OnAppearanceChanged ();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn die Benachrichtigung, nachdem diese Eigenschaft geändert werden soll. Die standardmäßige Implementierung ruft `InvalidateControl`.  
  
##  <a name="a-nameonbackcolorchangeda--colecontrolonbackcolorchanged"></a><a name="onbackcolorchanged"></a>COleControl::OnBackColorChanged  
 Wird vom Framework aufgerufen, wenn die vordefinierte BackColor-Eigenschaftswert geändert hat.  
  
```  
virtual void OnBackColorChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn die Benachrichtigung, nachdem diese Eigenschaft geändert werden soll. Die standardmäßige Implementierung ruft `InvalidateControl`.  
  
##  <a name="a-nameonborderstylechangeda--colecontrolonborderstylechanged"></a><a name="onborderstylechanged"></a>COleControl::OnBorderStyleChanged  
 Wird vom Framework aufgerufen, wenn die vordefinierte BorderStyle-Eigenschaftswert geändert hat.  
  
```  
virtual void OnBorderStyleChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `InvalidateControl`.  
  
 Überschreiben Sie diese Funktion, wenn die Benachrichtigung, nachdem diese Eigenschaft geändert werden soll.  
  
##  <a name="a-nameonclicka--colecontrolonclick"></a><a name="onclick"></a>COleControl::OnClick  
 Wird vom Framework aufgerufen, wenn eine Maustaste geklickt hat, oder die vordefinierte DoClick-Methode aufgerufen wurde.  
  
```  
virtual void OnClick(USHORT iButton);
```  
  
### <a name="parameters"></a>Parameter  
 *iButton*  
 Der Index der zweite Mausklick. Dabei kann es sich um einen der folgenden Werte aufweisen:  
  
- **LEFT_BUTTON** die linke Maustaste gedrückt wurde.  
  
- **MIDDLE_BUTTON** die mittleren Maustaste geklickt wurde.  
  
- **RIGHT_BUTTON** die rechten Maustaste geklickt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `COleControl::FireClick`.  
  
 Überschreiben Sie diese Memberfunktion zum Ändern oder erweitern die Standardbehandlung.  
  
##  <a name="a-nameonclosea--colecontrolonclose"></a><a name="onclose"></a>COleControl::OnClose  
 Vom Framework aufgerufen, wenn der Container des Steuerelements aufgerufen hat **IOleControl:: Close** Funktion.  
  
```  
virtual void OnClose(DWORD dwSaveOption);
```  
  
### <a name="parameters"></a>Parameter  
 `dwSaveOption`  
 Flag, die angibt, ob das Objekt vor dem Laden gespeichert werden soll. Gültige Werte sind:  
  
- `OLECLOSE_SAVEIFDIRTY`  
  
- `OLECLOSE_NOSAVE`  
  
- `OLECLOSE_PROMPTSAVE`  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `OnClose` speichert das Control-Objekt, wenn es geändert wurde und `dwSaveOption` ist entweder `OLECLOSE_SAVEIFDIRTY` oder `OLECLOSE_PROMPTSAVE`.  
  
##  <a name="a-nameondoverba--colecontrolondoverb"></a><a name="ondoverb"></a>COleControl::OnDoVerb  
 Vom Framework aufgerufen, wenn der Container aufruft der **IOleObject** Member-Funktion.  
  
```  
virtual BOOL OnDoVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Der Index des Steuerelements Verbs aufgerufen werden.  
  
 `lpMsg`  
 Ein Zeiger auf die Windows-Meldung, die das Verb aufgerufen werden verursacht hat.  
  
 `hWndParent`  
 Das Handle für das übergeordnete Fenster des Steuerelements. Wenn die Ausführung des Verbs ein Fenster (oder Windows) erstellt `hWndParent` als das übergeordnete Element verwendet werden soll.  
  
 `lpRect`  
 Ein Zeiger auf einen RECT-Struktur, die in der die Koordinaten des Steuerelements relativ zu dem Container kopiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung verwendet die `ON_OLEVERB` und `ON_STDOLEVERB` Nachricht Zuordnungseinträgen bestimmen die geeignete Funktion aufrufen.  
  
 Überschreiben Sie diese Funktion, um die Standardbehandlung des Verbs ändern.  
  
##  <a name="a-nameondrawa--colecontrolondraw"></a><a name="ondraw"></a>COleControl:: OnDraw aufgerufen  
 Vom Framework aufgerufen wird, das OLE-Steuerelement in das angegebene umgebende Rechteck mit den angegebenen Gerätekontext zu zeichnen.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rcBounds,  
    const CRect& rcInvalid);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Der Gerätekontext, in dem die Zeichnung auftritt.  
  
 `rcBounds`  
 Der rechteckige Bereich des Steuerelements, einschließlich der Rahmen.  
  
 `rcInvalid`  
 Der rechteckige Bereich des Steuerelements, das ungültig ist.  
  
### <a name="remarks"></a>Hinweise  
 `OnDraw`wird normalerweise aufgerufen, für die Bildschirmanzeige, übergeben einen Bildschirm-Gerätekontext als `pDC`. Die `rcBounds` Parameter identifiziert das Rechteck in der Ziel-Gerätekontext (relativ zum aktuellen Zuordnungsmodus). Die `rcInvalid` Parameter ist das aktuelle Rechteck, das ungültig ist. In einigen Fällen ist dies einen kleineren Bereich als `rcBounds`.  
  
##  <a name="a-nameondrawmetafilea--colecontrolondrawmetafile"></a><a name="ondrawmetafile"></a>OnDrawMetafile  
 Vom Framework aufgerufen, die das OLE-Steuerelement in das angegebene umgebende Rechteck mit der angegebenen Metadatei-Gerätekontext zu zeichnen.  
  
```  
virtual void OnDrawMetafile(
    CDC* pDC,  
    const CRect& rcBounds);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Der Gerätekontext, in dem die Zeichnung auftritt.  
  
 `rcBounds`  
 Der rechteckige Bereich des Steuerelements, einschließlich der Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft die [OnDraw](#ondraw) Funktion.  
  
##  <a name="a-nameonedita--colecontrolonedit"></a><a name="onedit"></a>COleControl::OnEdit  
 Bewirkt, dass das Steuerelement die UI aktiviert werden.  
  
```  
virtual BOOL OnEdit(
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMsg`  
 Ein Zeiger auf die Windows-Meldung, die das Verb aufgerufen hat.  
  
 `hWndParent`  
 Ein Handle für das übergeordnete Fenster des Steuerelements.  
  
 `lpRect`  
 Ein Zeiger auf das Rechteck, das das Steuerelement im Container verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies hat dieselbe Wirkung wie das Aufrufen des Steuerelements `OLEIVERB_UIACTIVATE` Verb.  
  
 Diese Funktion wird in der Regel verwendet, als die Handlerfunktion für eine `ON_OLEVERB` Eintrag in der Nachricht. Dadurch wird ein Verb "Bearbeiten" auf das Menü des Steuerelements "Object" verfügbar. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAxCtl&5;](../../mfc/reference/codesnippet/cpp/colecontrol-class_6.cpp)]  
  
##  <a name="a-nameonenabledchangeda--colecontrolonenabledchanged"></a><a name="onenabledchanged"></a>COleControl::OnEnabledChanged  
 Wird vom Framework aufgerufen, wenn der Bestand aktiviert-Eigenschaftswert geändert wurde.  
  
```  
virtual void OnEnabledChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn die Benachrichtigung, nachdem diese Eigenschaft geändert werden soll. Die standardmäßige Implementierung ruft [InvalidateControl](#invalidatecontrol).  
  
##  <a name="a-nameonenumverbsa--colecontrolonenumverbs"></a><a name="onenumverbs"></a>COleControl::OnEnumVerbs  
 Vom Framework aufgerufen, wenn der Container aufruft der **IOleObject:: EnumVerbs** Member-Funktion.  
  
```  
virtual BOOL OnEnumVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `ppenumOleVerb`  
 Ein Zeiger auf die **IEnumOLEVERB** -Objekt, das die Verben des Steuerelements aufgelistet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verben verfügbar sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Listet die standardmäßige Implementierung der `ON_OLEVERB` Einträge in der Zuordnung angezeigt.  
  
 Überschreiben Sie diese Funktion, um die Standardmethode für das Auflisten von Verben zu ändern.  
  
##  <a name="a-nameoneventadvisea--colecontroloneventadvise"></a><a name="oneventadvise"></a>COleControl::OnEventAdvise  
 Wird vom Framework aufgerufen, wenn ein Ereignishandler verbunden oder von OLE-Steuerelement getrennt.  
  
```  
virtual void OnEventAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 `bAdvise`  
 **TRUE** gibt an, dass ein Ereignishandler für das Steuerelement verbunden wurde. **FALSE** gibt an, dass das Steuerelement ein Ereignishandler getrennt wurde.  
  
##  <a name="a-nameonfontchangeda--colecontrolonfontchanged"></a><a name="onfontchanged"></a>COleControl::OnFontChanged  
 Wird vom Framework aufgerufen, wenn die vordefinierte Schriftart-Eigenschaftswert geändert wurde.  
  
```  
virtual void OnFontChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `COleControl::InvalidateControl`. Wenn das Steuerelement ein Steuerelement von Windows Unterklassen ist, sendet die standardmäßige Implementierung auch eine **WM_SETFONT** Nachricht an das Fenster des Steuerelements.  
  
 Überschreiben Sie diese Funktion, wenn die Benachrichtigung, nachdem diese Eigenschaft geändert werden soll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl&6;](../../mfc/reference/codesnippet/cpp/colecontrol-class_7.cpp)]  
  
##  <a name="a-nameonforecolorchangeda--colecontrolonforecolorchanged"></a><a name="onforecolorchanged"></a>COleControl::OnForeColorChanged  
 Wird vom Framework aufgerufen, wenn die vordefinierte ForeColor-Eigenschaftswert geändert hat.  
  
```  
virtual void OnForeColorChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `InvalidateControl`.  
  
 Überschreiben Sie diese Funktion, wenn die Benachrichtigung, nachdem diese Eigenschaft geändert werden soll.  
  
##  <a name="a-nameonfreezeeventsa--colecontrolonfreezeevents"></a><a name="onfreezeevents"></a>COleControl::OnFreezeEvents  
 Nach dem Aufrufen der Container vom Framework aufgerufen **IOleControl:: FreezeEvents**.  
  
```  
virtual void OnFreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Parameter  
 `bFreeze`  
 **True,** Wenn des Steuerelements Ereignisbehandlung fixiert ist andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
 Überschreiben Sie diese Funktion, wenn Sie zusätzliches Verhalten soll, bei der Behandlung von Ereignissen nicht fixiert ist oder fixiert ist.  
  
##  <a name="a-nameongetcolorseta--colecontrolongetcolorset"></a><a name="ongetcolorset"></a>COleControl::OnGetColorSet  
 Vom Framework aufgerufen, wenn der Container aufruft der **IViewObject::GetColorSet** Member-Funktion.  
  
```  
virtual BOOL OnGetColorSet(
    DVTARGETDEVICE* ptd,  
    HDC hicTargetDev,  
    LPLOGPALETTE* ppColorSet);
```  
  
### <a name="parameters"></a>Parameter  
 `ptd`  
 Verweist auf das Zielgerät für das Bild gerendert werden soll. Wenn dieser Wert **NULL**, das Bild für ein Standard-Zielgerät in der Regel ein Anzeigegerät gerendert werden soll.  
  
 `hicTargetDev`  
 Gibt den Informationskontext an auf dem Zielgerät erkennbar `ptd`. Dieser Parameter kann einen Gerätekontext, aber es ist nicht unbedingt. If `ptd` is **NULL**, `hicTargetDev` should also be **NULL**.  
  
 *ppColorSet*  
 Ein Zeiger auf den Speicherort, in dem der Satz von Farben, die verwendet werden sollen kopiert werden soll. Wenn die Funktion nicht die Farbpalette liefert **NULL** zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine gültige Farbpalette zurückgegeben wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Container ruft diese Funktion zum Abrufen der Farben, die zum Zeichnen von OLE-Steuerelement erforderlich sind. Der Container können Farbpaletten, die in Verbindung mit den Farben, die sie die gesamte Farbpalette festgelegt muss abgerufen. Die standardmäßige Implementierung gibt **FALSE**.  
  
 Überschreiben Sie diese Funktion, um spezielle Verarbeitungsschritte Ausführen dieser Anforderung.  
  
##  <a name="a-nameongetcontrolinfoa--colecontrolongetcontrolinfo"></a><a name="ongetcontrolinfo"></a>COleControl::OnGetControlInfo  
 Vom Framework aufgerufen, wenn der Container des Steuerelements Informationen über das Steuerelement angefordert hat.  
  
```  
virtual void OnGetControlInfo(LPCONTROLINFO pControlInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pControlInfo`  
 Zeiger auf eine [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) Struktur ausgefüllt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Information wird in erster Linie eine Beschreibung des Steuerelements mnemonischen Tasten besteht. Die standardmäßige Implementierung füllt `pControlInfo` Standardinformationen.  
  
 Überschreiben Sie diese Funktion, wenn das Steuerelement mnemonische Tasten verarbeiten muss.  
  
##  <a name="a-nameongetdisplaystringa--colecontrolongetdisplaystring"></a><a name="ongetdisplaystring"></a>COleControl::OnGetDisplayString  
 Aufgerufen, um eine Zeichenfolge zu erhalten, die den aktuellen Wert der Eigenschaft identifizierten darstellt `dispid`.  
  
```  
virtual BOOL OnGetDisplayString(
    DISPID dispid,  
    CString& strValue);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 `strValue`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt über die eine Zeichenfolge zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn eine Zeichenfolge zurückgegeben wurden *StrValue;* andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn das Steuerelement verfügt über eine Eigenschaft, deren Wert direkt in eine Zeichenfolge konvertiert werden kann, und den Wert der Eigenschaft in einem Container bereitgestellten Eigenschaftenbrowser angezeigt werden soll.  
  
##  <a name="a-nameongetinplacemenua--colecontrolongetinplacemenu"></a><a name="ongetinplacemenu"></a>COleControl::OnGetInPlaceMenu  
 Vom Framework aufgerufen, wenn das Steuerelement Benutzeroberfläche aktiviert, erhalten Sie im Menü des Containers vorhandenen Menüs zusammengeführt werden sollen.  
  
```  
virtual HMENU OnGetInPlaceMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Steuerelements im Menü oder **NULL** Wenn das Steuerelement keine verfügt. Die standardmäßige Implementierung gibt **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über das Zusammenführen von OLE-Ressourcen finden Sie im Artikel [Menüs und Ressourcen (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="a-nameongetnaturalextenta--colecontrolongetnaturalextent"></a><a name="ongetnaturalextent"></a>COleControl::OnGetNaturalExtent  
 Wird vom Framework als Reaktion auf eines Containers aufgerufen **IViewObjectEx::GetNaturalExtent** Anforderung.  
  
```  
virtual BOOL OnGetNaturalExtent(
    DWORD dwAspect,
    LONG lindex,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="parameters"></a>Parameter  
 `dwAspect`  
 Gibt an, wie das Objekt dargestellt werden soll. Darstellungen enthalten Inhalt, ein Symbol, eine Miniaturansicht oder einem gedruckten Dokument. Gültige Werte stammen aus der Enumeration [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) oder **DVASPECT2**.  
  
 *lindex*  
 Der Teil des Objekts, das von Interesse ist. Derzeit wird nur-1 ist ungültig.  
  
 `ptd`  
 Verweist auf die [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Struktur definiert, das Zielgerät für das die Größe des Objekts zurückgegeben werden soll.  
  
 `hicTargetDev`  
 Der Informationskontext für das Zielgerät erkennbar gibt die `ptd` Parameter aus dem das Objekt Gerätemetrik abrufen und Funktionen des Geräts prüfen kann. Wenn `ptd` ist **NULL**, das Objekt sollte ignoriert den Wert in der `hicTargetDev` Parameter.  
  
 *pExtentInfo*  
 Verweist auf die **DVEXTENTINFO** -Struktur, Größenänderungsdaten angibt. Die **DVEXTENTINFO** Struktur ist:  
  
 `typedef struct  tagExtentInfo`  
  
 `{`  
  
 `UINT cb;`  
  
 `DWORD dwExtentMode;`  
  
 `SIZEL sizelProposed;`  
  
 `}   DVEXTENTINFO;`  
  
 Der Strukturmember `dwExtentMode` kann einen von zwei Werten annehmen:  
  
- **DVEXTENT_CONTENT** Abfragen, wie groß das Steuerelement sein sollte, um genau Inhalt (Snap-Größe)  
  
- **DVEXTENT_INTEGRAL** beim Ändern der Größe, übergeben Sie die vorgeschlagene Größe steuern  
  
 `psizel`  
 Verweist auf die Größe der Daten, die von zurückgegeben werden. Die der zurückgegebenen Größenänderungsdaten werden auf-1 für eine Dimension festgelegt, die nicht angepasst wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn er erfolgreich zurückgibt oder die Größe passt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Größe des Objekts anzeigen, die die vorgeschlagene Größe und Umfang der Modus in am nächsten Zurückgeben der **DVEXTENTINFO** Struktur. Die standardmäßige Implementierung gibt **FALSE** und macht keine Anpassung der Größe.  
  
##  <a name="a-nameongetpredefinedstringsa--colecontrolongetpredefinedstrings"></a><a name="ongetpredefinedstrings"></a>COleControl::OnGetPredefinedStrings  
 Vom Framework aufgerufen wird, erhalten eine Reihe von vordefinierten Zeichenfolgen, die die möglichen Werte für eine Eigenschaft darstellt.  
  
```  
virtual BOOL OnGetPredefinedStrings(
    DISPID dispid,  
    CStringArray* pStringArray,  
    CDWordArray* pCookieArray);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 `pStringArray`  
 Ein Zeichenfolgenarray mit ausgefüllt werden Werte zurückgegeben.  
  
 `pCookieArray`  
 Ein `DWORD` Array zurückgegebenen Werte eingetragen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Elemente hinzugefügt wurden `pStringArray` und `pCookieArray`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn das Steuerelement über eine Eigenschaft mit einem Satz möglicher Werte verfügt, die durch Zeichenfolgen dargestellt werden können. Für jede hinzugefügte Element `pStringArray`, sollten Sie ein entsprechende "Cookie" Element hinzufügen *pCookieArray.* Diese "Cookie" Werte können später übergeben werden, indem das Framework die `COleControl::OnGetPredefinedValue` Funktion.  
  
##  <a name="a-nameongetpredefinedvaluea--colecontrolongetpredefinedvalue"></a><a name="ongetpredefinedvalue"></a>COleControl::OnGetPredefinedValue  
 Aufgerufen, zum Abrufen des Wertes für eine der vordefinierten Zeichenfolgen, die zuvor von einer Überschreibung der zurückgegebenen `COleControl::OnGetPredefinedStrings`.  
  
```  
virtual BOOL OnGetPredefinedValue(
    DISPID dispid,  
    DWORD dwCookie,  
    VARIANT* lpvarOut);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 `dwCookie`  
 Einem Cookiewert, die zuvor von einer Überschreibung der zurückgegebenen `COleControl::OnGetPredefinedStrings`.  
  
 `lpvarOut`  
 Zeiger auf eine **VARIANT** Struktur über die ein Eigenschaftswert zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein Wert zurückgegeben wurden `lpvarOut`; andernfalls 0.  
  
##  <a name="a-nameongetviewextenta--colecontrolongetviewextent"></a><a name="ongetviewextent"></a>COleControl::OnGetViewExtent  
 Wird vom Framework als Reaktion auf eines Containers aufgerufen [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) Anforderung.  
  
```  
virtual BOOL OnGetViewExtent(
    DWORD dwDrawAspect,
    LONG lindex,
    DVTARGETDEVICE* ptd,
    LPSIZEL lpsizel);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDrawAspect*  
 `DWORD`Beschreiben, welches Formular bzw. Aspekt, ist ein Objekt angezeigt werden. Gültige Werte stammen aus der Enumeration [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) oder **DVASPECT2**.  
  
 *lindex*  
 Der Teil des Objekts, das von Interesse ist. Derzeit werden nur –&1; ist gültig.  
  
 `ptd`  
 Verweist auf die [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Struktur definiert, das Zielgerät für das die Größe des Objekts zurückgegeben werden soll.  
  
 *lpsizel*  
 Verweist auf den Speicherort, an die Größe des Objekts zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Erweiterungsinformationen erfolgreich zurückgegeben wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn das Steuerelement zwei Durchläufen Zeichnen verwendet und die deckenden und transparenten Teile unterschiedliche Dimensionen weisen.  
  
##  <a name="a-nameongetviewrecta--colecontrolongetviewrect"></a><a name="ongetviewrect"></a>COleControl::OnGetViewRect  
 Wird vom Framework als Reaktion auf eines Containers aufgerufen **IViewObjectEx::GetRect** Anforderung.  
  
```  
virtual BOOL OnGetViewRect(DWORD dwAspect, LPRECTL pRect);
```  
  
### <a name="parameters"></a>Parameter  
 `dwAspect`  
 `DWORD`Beschreiben, welches Formular bzw. Aspekt, ist ein Objekt angezeigt werden. Gültige Werte stammen aus der Enumeration [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) oder **DVASPECT2**:  
  
- `DVASPECT_CONTENT`Umschließende Rechteck für das gesamte Objekt. Linke obere Ecke am Ursprung befindet und das Ausmaß zurückgegebene Größe des Objekts **GetViewExtent***.*  
  
- **DVASPECT_OPAQUE** Objekte mit einem nicht transparenten rechteckigen Bereich das Rechteck zurück. Andere fehl.  
  
- **DVASPECT_TRANSPARENT** Rechteck für alle Teile von transparent oder unregelmäßig.  
  
 `pRect`  
 Verweist auf die [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) -Struktur und gibt das Rechteck, in dem das Objekt gezeichnet werden soll. Dieser Parameter steuert die Positionierung und Dehnen von des Objekts.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Rechteck auf die das Objekt erfolgreich zurückgegeben wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe des Objekts wird konvertiert, indem `OnGetViewRect` in ein Rechteck, beginnend an einer bestimmten Position (der Standardwert ist der oberen linken Ecke der Anzeige). Überschreiben Sie diese Funktion, wenn das Steuerelement zwei Durchläufen Zeichnen verwendet und die deckenden und transparenten Teile unterschiedliche Dimensionen weisen.  
  
##  <a name="a-nameongetviewstatusa--colecontrolongetviewstatus"></a><a name="ongetviewstatus"></a>COleControl::OnGetViewStatus  
 Wird vom Framework als Reaktion auf eines Containers aufgerufen **IViewObjectEx::GetViewStatus** Anforderung.  
  
```  
virtual DWORD OnGetViewStatus();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der Werte von der **VIEWSTATUS** -Enumeration, wenn erfolgreich, andernfalls 0. Mögliche Werte sind eine beliebige Kombination der folgenden:  
  
 **VIEWSTATUS_OPAQUE**  
 Objekt ist nicht vollständig transparent. Wenn dieses Bit nicht festgelegt ist, enthält das Objekt die transparenten Teile. Dieses Bit gilt nur für Content-bezogenen Aspekte und nicht auf `DVASPECT_ICON` oder `DVASPECT_DOCPRINT`.  
  
 **VIEWSTATUS_SOLIDBKGND**  
 Objekt verfügt über einen undurchsichtigen Hintergrund (besteht eine Volltonfarbe kein Brush-Muster). Dieses Bit hat nur dann, wenn **VIEWSTATUS_OPAQUE** festgelegt ist, und gilt nur für Content-bezogenen Aspekte und nicht auf `DVASPECT_ICON` oder `DVASPECT_DOCPRINT`.  
  
 **VIEWSTATUS_DVASPECTOPAQUE**  
 -Objekt unterstützt **DVASPECT_OPAQUE**. Alle **IViewObjectEx** Methoden, die einen Zeichnung Aspekt wie ein Parameter mit diesem Aspekt aufgerufen werden kann.  
  
 **VIEWSTATUS_DVASPECTTRANSPARENT**  
 -Objekt unterstützt **DVASPECT_TRANSPARENT**. Alle **IViewObjectEx** Methoden, die einen Zeichnung Aspekt wie ein Parameter mit diesem Aspekt aufgerufen werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn das Steuerelement zweistufige Zeichnung verwendet. Die standardmäßige Implementierung gibt **VIEWSTATUS_OPAQUE**.  
  
##  <a name="a-nameonhidetoolbarsa--colecontrolonhidetoolbars"></a><a name="onhidetoolbars"></a>COleControl::OnHideToolBars  
 Wird vom Framework aufgerufen, wenn das Steuerelement der Benutzeroberfläche deaktiviert wird.  
  
```  
virtual void OnHideToolBars();
```  
  
### <a name="remarks"></a>Hinweise  
 Verbergen der Implementierung alle Symbolleisten angezeigt, wenn `OnShowToolbars`.  
  
##  <a name="a-nameoninactivemousemovea--colecontroloninactivemousemove"></a><a name="oninactivemousemove"></a>COleControl::OnInactiveMouseMove  
 Vom Container für die inaktiven Objekt unter dem Mauszeiger auf den Eingang des Namens einer `WM_MOUSEMOVE` Nachricht.  
  
```  
virtual void OnInactiveMouseMove(
    LPCRECT lprcBounds,
    long x,
    long y,
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>Parameter  
 `lprcBounds`  
 Das Objekt, das umschließende Rechteck in Clientkoordinaten des enthaltenden Fensters. Teilt dem Objekt seine genaue Position und Größe auf dem Bildschirm bei der `WM_MOUSEMOVE` Nachricht wurde empfangen.  
  
 *x*  
 Die X-Koordinate der Position des Mauszeigers in Clientkoordinaten des enthaltenden Fensters.  
  
 *y*  
 Die y-Koordinate der Position des Mauszeigers in Clientkoordinaten des enthaltenden Fensters.  
  
 `dwKeyState`  
 Identifiziert den aktuellen Zustand der Tastatur Zusatztasten der Tastatur. Gültige Werte kann eine Kombination der Flags **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_BUTTON**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass Fenster Clientkoordinaten (Pixel) verwendet werden, um die Position des Mauszeigers zu übergeben. Dies wird ermöglicht auch das umschließende Rechteck des Objekts in der gleichen Koordinatensystem übergeben.  
  
##  <a name="a-nameoninactivesetcursora--colecontroloninactivesetcursor"></a><a name="oninactivesetcursor"></a>COleControl::OnInactiveSetCursor  
 Vom Container für die inaktiven Objekt unter dem Mauszeiger auf den Eingang des Namens einer `WM_SETCURSOR` Nachricht.  
  
```  
virtual BOOL OnInactiveSetCursor(
    LPCRECT lprcBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL bSetAlways);
```  
  
### <a name="parameters"></a>Parameter  
 `lprcBounds`  
 Das Objekt, das umschließende Rechteck in Clientkoordinaten des enthaltenden Fensters. Teilt dem Objekt seine genaue Position und Größe auf dem Bildschirm bei der `WM_SETCURSOR` Nachricht wurde empfangen.  
  
 *x*  
 Die X-Koordinate der Position des Mauszeigers in Clientkoordinaten des enthaltenden Fensters.  
  
 *y*  
 Die y-Koordinate der Position des Mauszeigers in Clientkoordinaten des enthaltenden Fensters.  
  
 *dwMouseMsg*  
 Der Bezeichner der Maus-Nachricht, für die ein `WM_SETCURSOR` aufgetreten ist.  
  
 *bSetAlways*  
 Gibt an, ob das Objekt den Cursor festgelegt werden muss. Wenn **TRUE**, das Objekt muss den Cursor; festgelegt, wenn **FALSE**, der Cursor ist nicht verpflichtet, den Cursor zu setzen und sollte zurückgeben **S_FALSE** in diesem Fall.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass Fenster Clientkoordinaten (Pixel) verwendet werden, um die Position des Mauszeigers zu übergeben. Dies wird ermöglicht auch das umschließende Rechteck des Objekts in der gleichen Koordinatensystem übergeben.  
  
##  <a name="a-nameonkeydowneventa--colecontrolonkeydownevent"></a><a name="onkeydownevent"></a>COleControl::OnKeyDownEvent  
 Wird vom Framework aufgerufen, nachdem ein vordefiniertes KeyDown-Ereignis verarbeitet wurde.  
  
```  
virtual void OnKeyDownEvent(
    USHORT nChar,  
    USHORT nShiftState);
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Der Wert der virtuellen Tastencode für die gedrückte Taste. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h  
  
 `nShiftState`  
 Enthält eine Kombination der folgenden Flags:  
  
- **SHIFT_MASK** die UMSCHALTTASTE gedrückt wurde, während der Aktion.  
  
- **CTRL_MASK** die STRG-Taste gedrückt wurde, während der Aktion.  
  
- **ALT_MASK** die ALT-Taste gedrückt wurde, während der Aktion.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn das Steuerelement benötigt Zugriff auf die wichtigsten Informationen, nachdem das Ereignis ausgelöst wurde.  
  
##  <a name="a-nameonkeypresseventa--colecontrolonkeypressevent"></a><a name="onkeypressevent"></a>COleControl::OnKeyPressEvent  
 Vom Framework aufgerufen, nachdem die Stock, KeyPress-Ereignis ausgelöst wurde.  
  
```  
virtual void OnKeyPressEvent(USHORT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Enthält den Wert virtueller Tastencode der gedrückten Taste. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die `nChar` Wert möglicherweise vom Container geändert wurde.  
  
 Überschreiben Sie diese Funktion, wenn nach Eintreten des Ereignisses Benachrichtigung werden soll.  
  
##  <a name="a-nameonkeyupeventa--colecontrolonkeyupevent"></a><a name="onkeyupevent"></a>COleControl::OnKeyUpEvent  
 Wird vom Framework aufgerufen, nachdem ein vordefiniertes KeyDown-Ereignis verarbeitet wurde.  
  
```  
virtual void OnKeyUpEvent(
    USHORT nChar,  
    USHORT nShiftState);
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Der Wert der virtuellen Tastencode für die gedrückte Taste. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h  
  
 `nShiftState`  
 Enthält eine Kombination der folgenden Flags:  
  
- **SHIFT_MASK** die UMSCHALTTASTE gedrückt wurde, während der Aktion.  
  
- **CTRL_MASK** die STRG-Taste gedrückt wurde, während der Aktion.  
  
- **ALT_MASK** die ALT-Taste gedrückt wurde, während der Aktion.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn das Steuerelement benötigt Zugriff auf die wichtigsten Informationen, nachdem das Ereignis ausgelöst wurde.  
  
##  <a name="a-nameonmappropertytopagea--colecontrolonmappropertytopage"></a><a name="onmappropertytopage"></a>COleControl::OnMapPropertyToPage  
 Aufgerufen, um die Klassen-ID einer Eigenschaftenseite zu erhalten, die Bearbeitung der angegebenen Eigenschaft implementiert.  
  
```  
virtual BOOL OnMapPropertyToPage(
    DISPID dispid,  
    LPCLSID lpclsid,  
    BOOL* pbPageOptional);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 `lpclsid`  
 Zeiger auf eine **CLSID** Struktur über die Klassen-ID zurückgegeben wird.  
  
 *pbPageOptional*  
 Gibt einen Indikator dafür, ob für die Verwendung der angegebenen Seite optional ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn eine Klassen-ID zurückgegeben wurden `lpclsid`; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Möglichkeit zum Aufrufen der Eigenschaftenseiten aus Eigenschaftenbrowser des Containers des Steuerelements.  
  
##  <a name="a-nameonmnemonica--colecontrolonmnemonic"></a><a name="onmnemonic"></a>COleControl::OnMnemonic  
 Wird vom Framework aufgerufen, wenn der Container erkannt hat, dass eine mnemonische Taste des OLE-Steuerelements gedrückt wurde.  
  
```  
virtual void OnMnemonic(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Ein Zeiger auf die durch Drücken einer mnemonischen Taste generierte Windows-Meldung.  
  
##  <a name="a-nameonpropertiesa--colecontrolonproperties"></a><a name="onproperties"></a>COleControl::OnProperties  
 Vom Framework aufgerufen, wenn das Steuerelement Eigenschaftenverb vom Container aufgerufen wurde.  
  
```  
virtual BOOL OnProperties(
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMsg`  
 Ein Zeiger auf die Windows-Meldung, die das Verb aufgerufen hat.  
  
 `hWndParent`  
 Ein Handle für das übergeordnete Fenster des Steuerelements.  
  
 `lpRect`  
 Ein Zeiger auf das Rechteck, das das Steuerelement im Container verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung zeigt ein modales Dialogfeld an.  
  
 Diese Funktion können auch dazu führen, dass die Anzeige der Eigenschaftenseiten des Steuerelements. Rufen Sie die `OnProperties` -Funktion übergeben das Handle des Steuerelements übergeordnete Element in der `hWndParent` Parameter. In diesem Fall die Werte der `lpMsg` und `lpRect` Parameter werden ignoriert.  
  
##  <a name="a-nameonqueryhitpointa--colecontrolonqueryhitpoint"></a><a name="onqueryhitpoint"></a>COleControl::OnQueryHitPoint  
 Wird vom Framework als Reaktion auf eines Containers aufgerufen **IViewObjectEx::QueryHitPoint** Anforderung.  
  
```  
virtual BOOL OnQueryHitPoint(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG lCloseHint,
    DWORD* pHitResult);
```  
  
### <a name="parameters"></a>Parameter  
 `dwAspect`  
 Gibt an, wie das Objekt dargestellt wird. Gültige Werte stammen aus der Enumeration [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) oder **DVASPECT2**.  
  
 `pRectBounds`  
 Zeiger auf eine `RECT` -Struktur, die das umschließende Rechteck des Clientbereichs OLE-Steuerelement angibt.  
  
 `ptlLoc`  
 Zeiger auf die **zeigen** Struktur, die Festlegung des auf Treffer überprüft werden soll. Der Punkt wird im OLE Clientkoordinaten Bereich angegeben.  
  
 `lCloseHint`  
 Der Abstand, der definiert, "Schließen" auf den Punkt auf Treffer überprüft.  
  
 `pHitResult`  
 Ein Zeiger auf das Ergebnis der Abfrage drücken. Einer der folgenden Werte:  
  
- **HITRESULT_OUTSIDE** `ptlLoc` außerhalb der OLE-Objekt und nicht geschlossen ist.  
  
- **HITRESULT_TRANSPARENT** *PtlLoc* innerhalb der Grenzen des OLE-Objekts, aber nicht in der Nähe des Abbilds ist. Z. B. ein Punkt in der Mitte eines Kreises transparent sein konnte **HITRESULT_TRANSPARENT**.  
  
- **HITRESULT_CLOSE** `ptlLoc` innerhalb oder außerhalb der OLE-Objekt, aber nahe genug an das Objekt, das in berücksichtigt werden. Eine kleine, dünne oder detaillierte Objekte können diesen Wert verwenden. Auch wenn ein Punkt außerhalb der umgebenden Rechtecks eines Objekts kann weiterhin nahe sein (Dies ist erforderlich für kleine Objekte drücken).  
  
- **HITRESULT_HIT** `ptlLoc` innerhalb des Bilds des Objekts ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Treffer Ergebnis erfolgreich zurückgegeben wird; andernfalls 0. Treffer ist eine Überschneidung mit den Anzeigebereich des OLE-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Fragt ab, ob ein Objekt Anzeigerechteck angegebenen Punkt überschneidet (den Punkt erreicht). `QueryHitPoint`kann überschrieben werden, um Zugriffe für nicht rechteckige Objekte zu testen.  
  
##  <a name="a-nameonqueryhitrecta--colecontrolonqueryhitrect"></a><a name="onqueryhitrect"></a>COleControl::OnQueryHitRect  
 Wird vom Framework als Reaktion auf eines Containers aufgerufen **IViewObjectEx::QueryHitRect** Anforderung.  
  
```  
virtual BOOL OnQueryHitRect(
    DWORD dwAspect,  
    LPCRECT pRectBounds,  
    LPCRECT prcLoc,  
    LONG lCloseHint,  
    DWORD* pHitResult);
```  
  
### <a name="parameters"></a>Parameter  
 `dwAspect`  
 Gibt an, wie das Objekt dargestellt werden soll. Gültige Werte stammen aus der Enumeration [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) oder **DVASPECT2**.  
  
 `pRectBounds`  
 Zeiger auf eine `RECT` -Struktur, die das umschließende Rechteck des Clientbereichs OLE-Steuerelement angibt.  
  
 *prcLoc*  
 Zeiger auf die `RECT` -Struktur und gibt das Rechteck auf Treffer (Überschneidung mit dem Objekt Rechteck), relativ zu der oberen linken Ecke des Objekts überprüft wird.  
  
 `lCloseHint`  
 Nicht verwendet.  
  
 `pHitResult`  
 Ein Zeiger auf das Ergebnis der Abfrage drücken. Einer der folgenden Werte:  
  
- **HITRESULT_OUTSIDE** keine im Rechteck erreicht durch das OLE-Objekt.  
  
- **HITRESULT_HIT** mindestens ein Punkt in dem Rechteck wäre ein Zugriff auf das Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Treffer Ergebnis erfolgreich zurückgegeben wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Fragt ab, ob ein Objekt Anzeigerechteck überschneidet sich mit einem beliebigen Zeitpunkt im angegebenen Rechteck (das Rechteck erreicht). `QueryHitRect`kann überschrieben werden, um Zugriffe für nicht rechteckige Objekte zu testen.  
  
##  <a name="a-nameonrenderdataa--colecontrolonrenderdata"></a><a name="onrenderdata"></a>COleControl::OnRenderData  
 Vom Framework aufgerufen wird zum Abrufen von Daten im angegebenen Format.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Informationen angefordert.  
  
 `lpStgMedium`  
 Verweist auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur, in der die Daten zurückgegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor in das Steuerelement mit platziert die [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) oder [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) Memberfunktionen verzögert zu rendern. Ruft die standardmäßige Implementierung dieser Funktion `OnRenderFileData` oder `OnRenderGlobalData`, wenn das angegebene Speichermedium eine Datei oder einen Speicher ist. Wenn das angeforderte Format ist `CF_METAFILEPICT` oder die permanente Eigenschaft Format festgelegt ist, wird die standardmäßige Implementierung werden die entsprechenden Daten aus und gibt einen Wert ungleich NULL zurück. Andernfalls gibt 0 zurück und führt keine Aktion aus.  
  
 Wenn *LpStgMedium-> Tymed* ist **TYMED_NULL**, **STGMEDIUM** zugeordnet und entsprechend den Angaben von gefüllt werden *LpFormatEtc-> Tymed*. Wenn dies nicht **TYMED_NULL**, **STGMEDIUM** mit Daten ausgefüllt werden.  
  
 Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten sollten Sie stattdessen eine der anderen Versionen dieser Funktion zu überschreiben. Wenn Ihre Daten klein und feste Größe ist, überschreiben `OnRenderGlobalData`. Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter der **FORMATETC** und **STGMEDIUM** Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonrenderfiledataa--colecontrolonrenderfiledata"></a><a name="onrenderfiledata"></a>COleControl::OnRenderFileData  
 Aufgerufen, um die Daten im angegebenen Format abgerufen, wenn das Speichermedium eine Datei ist.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Informationen angefordert.  
  
 `pFile`  
 Verweist auf eine [CFile](../../mfc/reference/cfile-class.md) Objekt, in dem die Daten gerendert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor in das Steuerelement mit platziert die [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion einfach gibt **FALSE**.  
  
 Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten empfiehlt es sich, eine der anderen Versionen dieser Funktion stattdessen überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben `OnRenderData`. Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter der **FORMATETC** -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonrenderglobaldataa--colecontrolonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleControl::OnRenderGlobalData  
 Aufgerufen, um Daten im angegebenen Format abzurufen, wird das angegebene Speichermedium globalen Arbeitsspeicher.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Informationen angefordert.  
  
 `phGlobal`  
 Verweist auf ein Handle für den globalen Arbeitsspeicher, in dem die Daten zurückgegeben werden. Wenn kein Speicher zugewiesen wurde, kann dieser Parameter **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor in das Steuerelement mit platziert die [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion einfach gibt **FALSE**.  
  
 Wenn `phGlobal` ist **NULL**, ein neues `HGLOBAL` zugeordnet und in zurückgegeben werden sollte `phGlobal`. Andernfalls die `HGLOBAL` angegebene `phGlobal` mit Daten gefüllt werden soll. Die Datenmenge der `HGLOBAL` darf sich nicht auf die aktuelle Größe des Speicherblocks. Der Block kann nicht darüber hinaus auf eine größere Größe neu zugewiesen werden.  
  
 Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten sollten Sie stattdessen eine der anderen Versionen dieser Funktion zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben `OnRenderData`. Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter der **FORMATETC** -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonresetstatea--colecontrolonresetstate"></a><a name="onresetstate"></a>COleControl:: OnResetState ein  
 Wird vom Framework aufgerufen, wenn die Eigenschaften des Steuerelements auf ihre Standardwerte festgelegt werden soll.  
  
```  
virtual void OnResetState();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft [DoPropExchange](#dopropexchange), wobei ein `CPropExchange` -Objekt, das bewirkt, dass Eigenschaften auf ihre Standardwerte festgelegt werden.  
  
 Der Steuerelement-Writer kann Initialisierungscode für das OLE-Steuerelement einfügen, in diesem überschrieben. Diese Funktion wird aufgerufen, wenn [IPersistStream:: Load](http://msdn.microsoft.com/library/windows/desktop/ms680568) oder [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms680557) ein Fehler auftritt, oder [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms690234) oder [IPersistStorage::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) aufgerufen wird, ohne zuerst eine **IPersistStream:: Load** oder **IPersistStorage**.  
  
##  <a name="a-nameonsetclientsitea--colecontrolonsetclientsite"></a><a name="onsetclientsite"></a>COleControl:: OnSetClientSite  
 Vom Framework aufgerufen, wenn der Container des Steuerelements aufgerufen hat **IOleControl::SetClientSite** Funktion.  
  
```  
virtual void OnSetClientSite();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `OnSetClientSite` überprüft, ob die Pfadeigenschaften Daten geladen werden, und wenn dies der Fall, ruft `DoDataPathPropExchange`.  
  
 Überschreiben Sie diese Funktion, um spezielle Verarbeitungsschritte Ausführen dieser Benachrichtigung. Insbesondere sollten Außerkraftsetzungen für diese Funktion die Basisklasse aufrufen.  
  
##  <a name="a-nameonsetdataa--colecontrolonsetdata"></a><a name="onsetdata"></a>COleControl::OnSetData  
 Aufgerufen, um die Daten des Steuerelements mit den angegebenen Daten zu ersetzen.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur, die das Format der Daten angibt.  
  
 `lpStgMedium`  
 Zeiger auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur, in dem sich die Daten befinden.  
  
 `bRelease`  
 **True,** , wenn das Steuerelement, das Speichermedium freigeben sollte; **FALSE** , wenn das Steuerelement das Speichermedium nicht freigeben sollte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Daten in der permanenten Eigenschaft Format festgelegt ist, wird die standardmäßige Implementierung der Zustand des Steuerelements entsprechend geändert. Andernfalls wird die standardmäßige Implementierung keine Aktion ausgeführt. Wenn `bRelease` ist **TRUE**, klicken Sie dann auf einen Aufruf von **ReleaseStgMedium** erfolgt; andernfalls nicht.  
  
 Überschreiben Sie diese Funktion, um die Daten des Steuerelements mit den angegebenen Daten zu ersetzen.  
  
 Weitere Informationen finden Sie unter der **FORMATETC** und **STGMEDIUM** Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonsetextenta--colecontrolonsetextent"></a><a name="onsetextent"></a>COleControl::OnSetExtent  
 Vom Framework aufgerufen, wenn die Daten des Steuerelements werden, aufgrund eines Aufrufs von geändert muss [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330).  
  
```  
virtual BOOL OnSetExtent(LPSIZEL lpSizeL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpSizeL`  
 Ein Zeiger auf die **SIZEL** -Struktur, die Ganzzahlen verwendet wird, um die Breite und Höhe des Steuerelements, ausgedrückt in darstellen **HIMETRIC** Einheiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderung akzeptiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung behandelt, die Größe des Steuerelements. Wenn das Steuerelement direkt aktiviert, einen Aufruf in des Containers **OnPosRectChanged** wird hergestellt.  
  
 Überschreiben Sie diese Funktion, um die standardmäßige Größe des Steuerelements zu ändern.  
  
##  <a name="a-nameonsetobjectrectsa--colecontrolonsetobjectrects"></a><a name="onsetobjectrects"></a>COleControl::OnSetObjectRects  
 Aufgerufen, um einen Aufruf zu implementieren [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767).  
  
```  
virtual BOOL OnSetObjectRects(
    LPCRECT lpRectPos,  
    LPCRECT lpRectClip);
```  
  
### <a name="parameters"></a>Parameter  
 *lpRectPos*  
 Ein Zeiger auf einen RECT-Struktur, die neue Position und Größe relativ zu dem Container des Steuerelements angibt.  
  
 `lpRectClip`  
 Ein Zeiger auf eine `RECT` -Struktur, die einen rechteckigen Bereich, das Steuerelement ist für das Ausschneiden, angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Neupositionieren akzeptiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung automatisch behandelt das Neupositionieren und Ändern der Größe des Steuerelementfensters und gibt **TRUE**.  
  
 Überschreiben Sie diese Funktion, um das Standardverhalten dieser Funktion ändern.  
  
##  <a name="a-nameonshowtoolbarsa--colecontrolonshowtoolbars"></a><a name="onshowtoolbars"></a>COleControl::OnShowToolBars  
 Wird vom Framework aufgerufen, wenn das Steuerelement Benutzeroberfläche aktiviert wurde.  
  
```  
virtual void OnShowToolBars();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="a-nameontextchangeda--colecontrolontextchanged"></a><a name="ontextchanged"></a>COleControl::OnTextChanged  
 Wird vom Framework aufgerufen, wenn die vordefinierte Beschriftung oder Text-Eigenschaftswert geändert wurde.  
  
```  
virtual void OnTextChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `InvalidateControl`.  
  
 Überschreiben Sie diese Funktion, wenn die Benachrichtigung, nachdem diese Eigenschaft geändert werden soll.  
  
##  <a name="a-nameonwindowlessmessagea--colecontrolonwindowlessmessage"></a><a name="onwindowlessmessage"></a>COleControl::OnWindowlessMessage  
 Wird vom Framework als Reaktion auf eines Containers aufgerufen **IOleInPlaceObjectWindowless::OnWindowMessage** Anforderung.  
  
```  
virtual BOOL OnWindowlessMessage(
    UINT msg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>Parameter  
 `msg`  
 Nachrichten-ID von Windows zu übergeben.  
  
 `wParam`  
 Von Windows zu übergeben. Gibt zusätzliche Message-spezifische Informationen. Der Inhalt dieses Parameters hängt von den Wert der `msg` Parameter.  
  
 `lParam`  
 Von Windows zu übergeben. Gibt zusätzliche Message-spezifische Informationen. Der Inhalt dieses Parameters hängt von den Wert der `msg` Parameter.  
  
 *plResult*  
 Windows-Ergebniscode. Gibt das Ergebnis der Verarbeitung der Nachricht und hängt von der gesendeten Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verarbeitet Windows-Meldungen für fensterlose Steuerelemente. `COleControl`die `OnWindowlessMessage` für Windows-Nachrichten als Maus und Tastatur Nachrichten verwendet werden soll. `COleControl`bietet [SetCapture](#setcapture) und [SetFocus](#setfocus) speziell für die Erfassung und Tastatur Mausfokus für fensterlose OLE-Objekte zu erhalten.  
  
 Da fensterlose Objekte nicht über ein Fenster verfügen, benötigen sie einen Mechanismus, um die Container-Dispatchmeldungen werden können. Fensterlose OLE-Objekt ruft Nachrichten aus dem zugehörigen Container über die `OnWindowMessage` Methode für die `IOleInPlaceObjectWindowless` Schnittstelle (eine Erweiterung der [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) fensterlose Support). `OnWindowMessage`nimmt nicht an einer `HWND` Parameter.  
  
##  <a name="a-nameparenttoclienta--colecontrolparenttoclient"></a><a name="parenttoclient"></a>COleControl::ParentToClient  
 Übersetzt die Koordinaten der `pPoint` in Clientkoordinaten.  
  
```  
virtual UINT ParentToClient(
    LPCRECT lprcBounds,
    LPPOINT pPoint,
    BOOL bHitTest = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lprcBounds`  
 Ein Zeiger auf die Grenzen des OLE-Steuerelements innerhalb des Containers. Der Client-Bereich jedoch den Bereich des gesamten Steuerelements einschließlich Rahmen und Bildlaufleisten.  
  
 `pPoint`  
 Zeiger auf das übergeordnete Element (Container) zeigen Sie auf die Koordinaten des Clientbereichs des Steuerelements übersetzt werden.  
  
 `bHitTest`  
 Gibt an, ob Treffertests, an dem Punkt ausgeführt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `bHitTest` ist **FALSE**, gibt **HTNOWHERE**. Wenn `bHitTest` ist **TRUE**, gibt der Speicherort an, in dem das übergeordnete Element (Container) zeigen Sie, im Clientbereich des OLE-Steuerelements abgerufen und ist einer der folgenden Maus Treffertest Werte:  
  
- **HTBORDER** im Rahmen eines Fensters, die keinen Rahmen.  
  
- **HTBOTTOM** am horizontalen unteren Rand des Fensters.  
  
- **HTBOTTOMLEFT** In der unteren linken Ecke des Fensters.  
  
- **HTBOTTOMRIGHT** In der unteren rechten Ecke des Fensters.  
  
- **HTCAPTION** In einem Bereich der Titelleiste.  
  
- **HTCLIENT** In einen Clientbereich.  
  
- **HTERROR** auf den Hintergrund oder auf eine Trennlinie zwischen Fenstern (identisch mit **HTNOWHERE** mit dem Unterschied, dass die **DefWndProc** Windows-Funktion erzeugt einen Signalton Fehleranzeige).  
  
- **HTGROWBOX** In einem Größeneinstellungsfeld.  
  
- **HTHSCROLL** In der horizontalen Bildlaufleiste.  
  
- **HTLEFT** am linken Rand des Fensters.  
  
- **HTMAXBUTTON** In ein Maximieren-Schaltfläche.  
  
- **HTMENU** In einem Menü.  
  
- **HTMINBUTTON** In ein Minimieren-Schaltfläche.  
  
- **HTNOWHERE** auf den Hintergrund oder auf eine Trennlinie zwischen Fenstern.  
  
- **HTREDUCE** In ein Minimieren-Schaltfläche.  
  
- **HTRIGHT** In den rechten Rand des Fensters.  
  
- **HTSIZE** In einem Größeneinstellungsfeld (identisch mit **HTGROWBOX**).  
  
- **HTSYSMENU** im eines Steuerelements oder eine Schaltfläche in einem untergeordneten Fenster schließen.  
  
- **HTTOP** In der oberen horizontalen Rand des Fensters.  
  
- **HTTOPLEFT** In der oberen linken Ecke des Fensters.  
  
- **HTTOPRIGHT** In der oberen rechten Ecke des Fensters.  
  
- **HTTRANSPARENT** In einem Fenster, das derzeit von einem anderen Fenster behandelt.  
  
- **HTVSCROLL** auf der vertikalen Bildlaufleiste.  
  
- **HTZOOM** In ein Maximieren-Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Eingabe `pPoint` ist relativ zum Ursprung des übergeordneten Elements (obere linke Ecke des Containers). Bei der Ausgabe `pPoint` ist relativ zum Ursprung des Clientbereichs des OLE-Steuerelements (obere linke Ecke des Clientbereichs des Steuerelements).  
  
##  <a name="a-namepostmodaldialoga--colecontrolpostmodaldialog"></a><a name="postmodaldialog"></a>COleControl::PostModalDialog  
 Zeigt dem Container an, dass ein modales Dialogfeld geschlossen wurde.  
  
```  
void PostModalDialog(HWND hWndParent = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Handle für das übergeordnete Fenster des modalen Dialogfelds.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach jeder modales Dialogfeld angezeigt. Sie müssen diese Funktion aufrufen, sodass der Container alle Fenster der obersten Ebene deaktiviert, kann `PreModalDialog`. Diese Funktion sollte kombiniert werden, mit einem Aufruf von `PreModalDialog`.  
  
##  <a name="a-namepremodaldialoga--colecontrolpremodaldialog"></a><a name="premodaldialog"></a>COleControl::PreModalDialog  
 Benachrichtigt den Container, der ein modales Dialogfeld angezeigt werden.  
  
```  
void PreModalDialog(HWND hWndParent = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Handle für das übergeordnete Fenster des modalen Dialogfelds.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion vor jedem modales Dialogfeld angezeigt. Der Container kann alle übergeordneten Fenster deaktivieren, müssen Sie diese Funktion aufrufen. Nachdem das modale Dialogfeld angezeigt wird, müssen Sie Sie aufrufen `PostModalDialog`.  
  
##  <a name="a-namerecreatecontrolwindowa--colecontrolrecreatecontrolwindow"></a><a name="recreatecontrolwindow"></a>COleControl::RecreateControlWindow  
 Zerstört und neu erstellt das Fenster des Steuerelements.  
  
```  
void RecreateControlWindow();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ist möglicherweise erforderlich, wenn Sie das Fenster Stilbits ändern müssen.  
  
##  <a name="a-namerefresha--colecontrolrefresh"></a><a name="refresh"></a>COleControl::Refresh  
 Erzwingt das Neuzeichnen des OLE-Steuerelements.  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von unterstützt die `COleControl` -Basisklasse als eine vordefinierte Methode namens aktualisieren. Dadurch können Benutzer Ihre OLE-Steuerelements das Steuerelement zu einem bestimmten Zeitpunkt neu aufgebaut werden kann. Weitere Informationen zu dieser Methode finden Sie im Artikel [ActiveX-Steuerelemente: Methoden](../../mfc/mfc-activex-controls-methods.md).  
  
##  <a name="a-namereleasecapturea--colecontrolreleasecapture"></a><a name="releasecapture"></a>COleControl::ReleaseCapture  
 Versionen von Mauseingaben.  
  
```  
BOOL ReleaseCapture();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement gerade das Erfassen von Mauseingaben verfügt, wird die Erfassung freigegeben. Andernfalls hat diese Funktion keine Auswirkung.  
  
##  <a name="a-namereleasedca--colecontrolreleasedc"></a><a name="releasedc"></a>COleControl::ReleaseDC  
 Gibt den Anzeigegerätekontext eines Containers ein fensterloses Steuerelement, das den Gerätekontext für die Verwendung durch andere Programme freigegeben.  
  
```  
int ReleaseDC(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Identifiziert den Gerätekontext Container freigegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Muss die Anwendung aufrufen `ReleaseDC` für jeden Aufruf von [GetDC](#getdc).  
  
##  <a name="a-namereparentcontrolwindowa--colecontrolreparentcontrolwindow"></a><a name="reparentcontrolwindow"></a>COleControl::ReparentControlWindow  
 Legt das übergeordnete Element des Steuerelements fest.  
  
```  
virtual void ReparentControlWindow(
    HWND hWndOuter,  
    HWND hWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 *hWndOuter*  
 Das Handle des Steuerelementfensters.  
  
 `hWndParent`  
 Das Handle des neuen übergeordneten Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um das übergeordnete Element des Steuerelementfensters zurückzusetzen.  
  
##  <a name="a-nameresetstockpropsa--colecontrolresetstockprops"></a><a name="resetstockprops"></a>COleControl::ResetStockProps  
 Initialisiert den Zustand des der `COleControl` vordefinierte Eigenschaften mit ihren Standardwerten.  
  
```  
void ResetStockProps();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaften sind: Darstellung, BackColor, BorderStyle, Beschriftung, aktiviert, Schriftart, ForeColor, hWnd und Text. Eine Beschreibung der Basiseigenschaften, finden Sie unter [ActiveX-Steuerelemente: Hinzufügen vordefinierter Eigenschaften](../../mfc/mfc-activex-controls-adding-stock-properties.md).  
  
 Können Sie ein Steuerelement binäre Initialisierung Leistung verbessern, mithilfe von `ResetStockProps` und `ResetVersion` überschreiben `COleControl::OnResetState`. Siehe das unten aufgeführte Beispiel. Weitere Informationen zum Optimieren der Initialisierung finden Sie unter [ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl&#7;](../../mfc/reference/codesnippet/cpp/colecontrol-class_8.cpp)]  
  
##  <a name="a-nameresetversiona--colecontrolresetversion"></a><a name="resetversion"></a>COleControl::ResetVersion  
 Initialisiert die Versionsnummer an den angegebenen Wert.  
  
```  
void ResetVersion(DWORD dwVersionDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `dwVersionDefault`  
 Die Versionsnummer, die dem Steuerelement zugewiesen werden.  
  
### <a name="remarks"></a>Hinweise  
 Können Sie ein Steuerelement binäre Initialisierung Leistung verbessern, mithilfe von `ResetVersion` und `ResetStockProps` überschreiben `COleControl::OnResetState`. Beispiel finden Sie unter [ResetStockProps](#resetstockprops). Weitere Informationen zum Optimieren der Initialisierung finden Sie unter [ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-namescrollwindowa--colecontrolscrollwindow"></a><a name="scrollwindow"></a>COleControl::ScrollWindow  
 Ermöglicht eine fensterlose OLE-Objekt in seine direkten aktiven Bild auf dem Bildschirm einen Bereich einen Bildlauf durchführen.  
  
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
 Gibt die Menge in Geräteeinheiten, einen vertikalen Bildlauf ausführen. Dieser Parameter muss ein negativer Wert einen Bildlauf nach oben durchführen.  
  
 `lpRect`  
 Verweist auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder RECT-Struktur, die Teil des Clientbereichs des Bildlaufs das OLE-Objekt in Clientkoordinaten des enthaltenden Fensters angibt. Wenn `lpRect` ist **NULL**, wird das gesamte OLE-Objekt-Client-Bereich ein Bildlauf durchgeführt.  
  
 `lpClipRect`  
 Verweist auf eine `CRect` Objekt oder `RECT` Struktur, die das Rechteck auf Clip angibt. Nur Pixel innerhalb des Rechtecks werden durchgeführt. Bits außerhalb des Rechtecks sind nicht betroffen, auch wenn sie in sind die `lpRect` Rechteck. Wenn `lpClipRect` ist **NULL**, ohne Clipping für das Bildlaufrechteck ausgeführt wird.  
  
##  <a name="a-nameselectfontobjecta--colecontrolselectfontobject"></a><a name="selectfontobject"></a>COleControl::SelectFontObject  
 Wählt eine Schriftart in einem Gerätekontext.  
  
```  
CFont* SelectFontObject(
    CDC* pDC,  
    CFontHolder& fontHolder);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf ein Gerätekontextobjekt.  
  
 `fontHolder`  
 Ein Verweis auf die [CFontHolder](../../mfc/reference/cfontholder-class.md) Objekt zurück, die Schriftart ausgewählt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die zuvor ausgewählte Schriftart. Wenn der Aufrufer alle Zeichenoperationen, mit denen abgeschlossen hat *FontHolder,* sollten sie die zuvor ausgewählte Schriftart erneut aktivieren, indem sie als Parameter übergeben [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject).  
  
##  <a name="a-nameselectstockfonta--colecontrolselectstockfont"></a><a name="selectstockfont"></a>COleControl:: SelectStockFont  
 Wählt die vordefinierte Schriftarteigenschaft einen Gerätekontext.  
  
```  
CFont* SelectStockFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Der Gerätekontext, in dem die Schriftart ausgewählt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die zuvor ausgewählte `CFont` Objekt. Verwenden Sie [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) diese Schriftart zurück in den Gerätekontext auswählen, wenn Sie fertig sind.  
  
##  <a name="a-nameserializeextenta--colecontrolserializeextent"></a><a name="serializeextent"></a>COleControl::SerializeExtent  
 Serialisiert bzw. initialisiert den Zustand, der dem Steuerelement zugewiesenen Speicherplatz.  
  
```  
void SerializeExtent(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` Objekt serialisieren in oder aus.  
  
### <a name="remarks"></a>Hinweise  
 Sie können eines Steuerelements binäre Dauerhaftigkeit Leistung verbessern, indem `SerializeExtent`, `SerializeStockProps`, und `SerializeVersion` überschreiben **COleControl::Serialize**. Siehe das unten aufgeführte Beispiel. Weitere Informationen zum Optimieren der Initialisierung finden Sie unter [ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl&#8;](../../mfc/reference/codesnippet/cpp/colecontrol-class_9.cpp)]  
  
##  <a name="a-nameserializestockpropsa--colecontrolserializestockprops"></a><a name="serializestockprops"></a>COleControl::SerializeStockProps  
 Serialisiert bzw. initialisiert den Zustand des der `COleControl` Basiseigenschaften: Darstellung, BackColor, BorderStyle, Beschriftung, aktiviert, Schriftart, ForeColor und Text.  
  
```  
void SerializeStockProps(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` Objekt serialisieren in oder aus.  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Basiseigenschaften, finden Sie unter [ActiveX-Steuerelemente: Hinzufügen vordefinierter Eigenschaften](../../mfc/mfc-activex-controls-adding-stock-properties.md).  
  
 Sie können eines Steuerelements binäre Dauerhaftigkeit Leistung verbessern, indem `SerializeStockProps`, `SerializeExtent`, und `SerializeVersion` überschreiben **COleControl::Serialize**. Ein Beispiel finden Sie den Code am [SerializeExtent](#serializeextent). Weitere Informationen zum Optimieren der Initialisierung finden Sie unter [ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-nameserializeversiona--colecontrolserializeversion"></a><a name="serializeversion"></a>COleControl::SerializeVersion  
 Serialisiert bzw. initialisiert den Zustand des Steuerelements Versionsinformationen.  
  
```  
DWORD SerializeVersion(
    CArchive& ar,
    DWORD dwVersionDefault,
    BOOL bConvert = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` Objekt serialisieren in oder aus.  
  
 `dwVersionDefault`  
 Die aktuelle Versionsnummer des Steuerelements.  
  
 `bConvert`  
 Gibt an, ob Daten dauerhafte in das aktuelle Format konvertiert werden soll, wenn es gespeichert ist, oder im selben Format verwaltet haben, bei der es geladen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Versionsnummer des Steuerelements. Wenn das angegebene Archiv geladen wird, `SerializeVersion` gibt die Version aus diesem Archiv geladen. Andernfalls wird die derzeit geladene Version zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Sie können eines Steuerelements binäre Dauerhaftigkeit Leistung verbessern, indem `SerializeVersion`, `SerializeExtent`, und `SerializeStockProps` überschreiben **COleControl::Serialize**. Ein Beispiel finden Sie den Code am [SerializeExtent](#serializeextent). Weitere Informationen zum Optimieren der Initialisierung finden Sie unter [ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-namesetappearancea--colecontrolsetappearance"></a><a name="setappearance"></a>COleControl::SetAppearance  
 Legt den vordefinierten Darstellung-Eigenschaftswert des Steuerelements fest.  
  
```  
void SetAppearance (short sAppearance);
```  
  
### <a name="parameters"></a>Parameter  
 *sAppearance*  
 Ein **kurze** ( `VT_I2`) für die Darstellung des Steuerelements verwendet werden. Den Wert 0 (null) wird die Darstellung des Steuerelements auf Flach und den Wert 1 wird die Darstellung des Steuerelements auf 3D.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über Basiseigenschaften finden Sie unter [ActiveX-Steuerelemente: Eigenschaften](../../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="a-namesetbackcolora--colecontrolsetbackcolor"></a><a name="setbackcolor"></a>COleControl::SetBackColor  
 Legt den vordefinierten BackColor-Eigenschaftswert des Steuerelements fest.  
  
```  
void SetBackColor(OLE_COLOR dwBackColor);
```  
  
### <a name="parameters"></a>Parameter  
 *dwBackColor*  
 Ein **OLE_COLOR** Wert für Hintergrund Zeichnen des Steuerelements verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Verwendung dieser Eigenschaft und andere verwandte Eigenschaften finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaften](../../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="a-namesetborderstylea--colecontrolsetborderstyle"></a><a name="setborderstyle"></a>COleControl::SetBorderStyle  
 Legt den vordefinierten BorderStyle-Eigenschaftswert des Steuerelements fest.  
  
```  
void SetBorderStyle(short sBorderStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *sBorderStyle*  
 Die neue Rahmenart für das Steuerelement; 0 gibt kein Rahmen an, und 1 gibt einen normalen Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelementfenster anschließend neu erstellt wird und `OnBorderStyleChanged` aufgerufen.  
  
##  <a name="a-namesetcapturea--colecontrolsetcapture"></a><a name="setcapture"></a>COleControl::SetCapture  
 Bewirkt, dass das Fenster des Steuerelements Container besitzt das Erfassen von Mauseingaben im Auftrag des Steuerelements ausführen.  
  
```  
CWnd* SetCapture();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die **CWnd** Window-Objekt, das zuvor Mauseingabe empfangen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement aktiviert und das fensterlose ist, wird diese Funktion Containerfenster besitzt das Erfassen von Mauseingaben im Auftrag des Steuerelements wird das Steuerelement. Andernfalls wird diese Funktion für das Steuerelement selbst besitzt das Erfassen von Mauseingaben wird (wie `CWnd::SetCapture`).  
  
##  <a name="a-namesetcontrolsizea--colecontrolsetcontrolsize"></a><a name="setcontrolsize"></a>COleControl::SetControlSize  
 Legt die Größe des Steuerelementfensters OLE und benachrichtigt den Container, den die Website des Steuerelements geändert wird.  
  
```  
BOOL SetControlSize(int cx, int cy);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Gibt die neue Breite des Steuerelements in Pixel.  
  
 `cy`  
 Gibt die neue Höhe des Steuerelements in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht im Konstruktor des Steuerelements verwendet werden.  
  
 Beachten Sie, dass alle Koordinaten für Windows Steuerelement relativ zu der oberen linken Ecke des Steuerelements.  
  
##  <a name="a-namesetenableda--colecontrolsetenabled"></a><a name="setenabled"></a>COleControl::SetEnabled  
 Legt die Stock Enabled-Eigenschaft auf den Wert des Steuerelements fest.  
  
```  
void SetEnabled(BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnabled`  
 **True,** Wenn das Steuerelement aktiviert, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Festlegen dieser Eigenschaft **OnEnabledChange** aufgerufen wird.  
  
##  <a name="a-namesetfocusa--colecontrolsetfocus"></a><a name="setfocus"></a>COleControl::SetFocus  
 Bewirkt, dass das Fenster des Steuerelements Container, schalten Sie Namen für das Steuerelement den Eingabefokus besitzt.  
  
```  
CWnd* SetFocus();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die **CWnd** Window-Objekt, das den Eingabefokus bisher oder **NULL** , wenn kein solcher Fenster vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement aktiviert und das fensterlose ist, wird diese Funktion des Steuerelements Containerfenster und schalten Sie Namen für das Steuerelement den Eingabefokus besitzt. Der Eingabefokus leitet Tastatureingaben an die Container-Fenster und der Container leitet alle nachfolgenden Tastatur Nachrichten an das OLE-Objekt, das aufgerufen `SetFocus`. Jedes Fenster, die bisher den Eingabefokus verliert er.  
  
 Wenn das Steuerelement nicht fensterlos ist, diese Funktion bewirkt, dass das Steuerelement selbst wird von den Eingabefokus besitzt (wie `CWnd::SetFocus`).  
  
##  <a name="a-namesetfonta--colecontrolsetfont"></a><a name="setfont"></a>COleControl::SetFont  
 Legt die vordefinierte Schriftarteigenschaft des Steuerelements fest.  
  
```  
void SetFont(LPFONTDISP pFontDisp);
```  
  
### <a name="parameters"></a>Parameter  
 *pFontDisp*  
 Ein Zeiger auf eine Schriftart Dispatch-Schnittstelle.  
  
##  <a name="a-namesetforecolora--colecontrolsetforecolor"></a><a name="setforecolor"></a>COleControl::SetForeColor  
 Legt den vordefinierten ForeColor-Eigenschaftswert des Steuerelements fest.  
  
```  
void SetForeColor(OLE_COLOR dwForeColor);
```  
  
### <a name="parameters"></a>Parameter  
 *dwForeColor*  
 Ein **OLE_COLOR** Wert für den Vordergrund Zeichnen des Steuerelements verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Verwendung dieser Eigenschaft und andere verwandte Eigenschaften finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaften](../../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="a-namesetinitialdataformatsa--colecontrolsetinitialdataformats"></a><a name="setinitialdataformats"></a>COleControl::SetInitialDataFormats  
 Aufgerufen, um die Liste der von dem Steuerelement unterstützten Datenformate zu initialisieren.  
  
```  
virtual void SetInitialDataFormats();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung gibt zwei Formate: `CF_METAFILEPICT` und die persistenten Eigenschaft festgelegt.  
  
##  <a name="a-namesetinitialsizea--colecontrolsetinitialsize"></a><a name="setinitialsize"></a>COleControl::SetInitialSize  
 Legt die Größe eines OLE-Steuerelements, wenn erstmals in einem Container angezeigt.  
  
```  
void SetInitialSize(
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Die ursprüngliche Breite des OLE-Steuerelements in Pixel.  
  
 `cy`  
 Die anfängliche Höhe des OLE-Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion im Konstruktor die Anfangsgröße des Steuerelements fest. Die anfängliche Größe wird in Geräteeinheiten oder Pixel gemessen. Es wird empfohlen, dass dieser Aufruf im Konstruktor des Steuerelements vorgenommen werden.  
  
##  <a name="a-namesetmodifiedflaga--colecontrolsetmodifiedflag"></a><a name="setmodifiedflag"></a>COleControl::SetModifiedFlag  
 Ändert den Status eines Steuerelements geänderten.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Der neue Wert für das Steuerelement des Flag geändert. **TRUE** gibt an, dass der Zustand des Steuerelements geändert wurde; **FALSE** gibt an, dass der Zustand des Steuerelements gerade gespeichert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Funktion, wenn eine Änderung auftritt, persistenten Status des Steuerelements auswirken würde. Beispielsweise, wenn der Wert einer permanenten Eigenschaft ändert, rufen Sie diese Funktion mit `bModified` **TRUE**.  
  
##  <a name="a-namesetnotpermitteda--colecontrolsetnotpermitted"></a><a name="setnotpermitted"></a>COleControl::SetNotPermitted  
 Gibt an, dass eine Bearbeiten-Anforderung fehlgeschlagen ist.  
  
```  
void SetNotPermitted();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion beim `BoundPropertyRequestEdit` ein Fehler auftritt. Diese Funktion löst eine Ausnahme vom Typ **COleDispScodeException** an, dass die Set-Operation nicht zugelassen wurde.  
  
##  <a name="a-namesetnotsupporteda--colecontrolsetnotsupported"></a><a name="setnotsupported"></a>COleControl::SetNotSupported  
 Verhindert die Änderung an den Eigenschaftswert eines Steuerelements, durch den Benutzer.  
  
```  
void SetNotSupported();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion anstelle der Set-Funktion einer beliebigen Eigenschaft, die Änderung des Eigenschaftswerts von dem Benutzer des Steuerelements nicht unterstützen. Ein Beispiel wäre eine Eigenschaft, die schreibgeschützt ist.  
  
##  <a name="a-namesetrectincontainera--colecontrolsetrectincontainer"></a><a name="setrectincontainer"></a>COleControl::SetRectInContainer  
 Legt die Koordinaten für das Rechteck des Steuerelements relativ zu dem Container, ausgedrückt in Geräteeinheiten.  
  
```  
BOOL SetRectInContainer(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Ein Zeiger auf ein Rechteck, das Steuerelement neue Koordinaten relativ zu dem Container enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement geöffnet ist, wird es angepasst. andernfalls des Containers **OnPosRectChanged** -Funktion aufgerufen wird.  
  
##  <a name="a-namesettexta--colecontrolsettext"></a><a name="settext"></a>COleControl::SetText  
 Legt den Wert der vordefinierten Beschriftung oder Text-Eigenschaft des Steuerelements.  
  
```  
void SetText(LPCTSTR pszText);
```  
  
### <a name="parameters"></a>Parameter  
 `pszText`  
 Ein Zeiger auf eine Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die Beschriftung und Textfeld Basiseigenschaften beide denselben Wert zugeordnet sind. Dies bedeutet, dass alle Änderungen an einer der Eigenschaften automatisch beide Eigenschaften geändert werden. Im Allgemeinen sollte ein Steuerelement Aktie Beschriftung oder Text-Eigenschaft verwenden, aber nicht beide unterstützen.  
  
##  <a name="a-namethrowerrora--colecontrolthrowerror"></a><a name="throwerror"></a>ThrowError  
 Signalisiert das Auftreten eines Fehlers im Steuerelement.  
  
```  
void ThrowError(
    SCODE sc,  
    UINT nDescriptionID,  
    UINT nHelpID = -1);

 
void ThrowError(
    SCODE sc,  
    LPCTSTR pszDescription = NULL,  
    UINT nHelpID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `sc`  
 Der Statuswert des Codes gemeldet werden. Eine vollständige Liste der möglichen Fehlercodes, finden Sie im Artikel [ActiveX-Steuerelemente: Weiterführende Themen](../../mfc/mfc-activex-controls-advanced-topics.md).  
  
 `nDescriptionID`  
 Die Zeichenfolgenressource-ID der Ausnahme gemeldet werden.  
  
 `nHelpID`  
 Die Hilfe-ID des Themas auf gemeldet werden.  
  
 `pszDescription`  
 Eine Zeichenfolge mit einer Beschreibung der Ausnahme gemeldet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur von innerhalb einer Get- oder Set-Funktion für eine OLE-Eigenschaft oder die Implementierung einer OLE-Automatisierung-Methode aufgerufen werden. Wenn Sie Fehler darauf hinweisen, die zu anderen Zeiten auftreten müssen, sollten Sie die vordefinierte Error-Ereignis auslösen.  
  
##  <a name="a-nametransformcoordsa--colecontroltransformcoords"></a><a name="transformcoords"></a>COleControl::TransformCoords  
 Transformationen Koordinatenwerte zwischen **HIMETRIC** Einheiten und systemeigene Einheiten des Containers.  
  
```  
void TransformCoords(
    POINTL* lpptlHimetric,  
    POINTF* lpptfContainer,  
    DWORD flags);
```  
  
### <a name="parameters"></a>Parameter  
 *lpptlHimetric*  
 Zeiger auf eine **POINTL** -Struktur mit Koordinaten in **HIMETRIC** Einheiten.  
  
 *lpptfContainer*  
 Zeiger auf eine **POINTF** Struktur, die Koordinaten in der Größe des Containers enthält.  
  
 `flags`  
 Eine Kombination der folgenden Werte:  
  
- **XFORMCOORDS_POSITION** einer Position in den Container.  
  
- **XFORMCOORDS_SIZE** eine Größe im Container.  
  
- **XFORMCOORDS_HIMETRICTOCONTAINER** transformieren **HIMETRIC** Einheiten Einheiten für den Container.  
  
- **XFORMCOORDS_CONTAINERTOHIMETRIC** Transformieren des Containers Einheiten **HIMETRIC** Einheiten.  
  
### <a name="remarks"></a>Hinweise  
 Die ersten zwei Flags **XFORMCOORDS_POSITION** und **XFORMCOORDS_SIZE**, anzugeben, ob die Koordinaten als eine Position oder eine Größe behandelt werden sollen. Die übrigen zwei Flags geben die Richtung der Transformation.  
  
##  <a name="a-nametranslatecolora--colecontroltranslatecolor"></a><a name="translatecolor"></a>Memberfunktion COleControl:: TranslateColor  
 Konvertiert einen Farbwert aus der **OLE_COLOR** -Datentyp in der [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Datentyp.  
  
```  
COLORREF TranslateColor(
    OLE_COLOR clrColor,  
    HPALETTE hpal = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `clrColor`  
 Ein **OLE_COLOR** -Datentyp. Weitere Informationen finden Sie unter Windows [OleTranslateColor](http://msdn.microsoft.com/library/windows/desktop/ms694353) Funktion.  
  
 `hpal`  
 Ein Handle für eine optionale Palette; kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein (Rot, Grün, Blau) 32-Bit-RGB-Wert, der dem stabilen definiert Farbe am nächsten gelegenen der `clrColor` -Wert, der das Gerät darstellen kann.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich, um die Vordergrundfarbe und Hintergrundfarbe Basiseigenschaften zu übersetzen **COLORREF** von verwendeten [CDC](../../mfc/reference/cdc-class.md) Memberfunktionen.  
  
##  <a name="a-namewillambientsbevalidduringloada--colecontrolwillambientsbevalidduringload"></a><a name="willambientsbevalidduringload"></a>COleControl::WillAmbientsBeValidDuringLoad  
 Bestimmt, ob das Steuerelement die Werte der Eigenschaften als Standardwerte verwenden soll, wenn sie später in den persistenten Zustand geladen wird.  
  
```  
BOOL WillAmbientsBeValidDuringLoad();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Nonzero gibt an, dass die Ambiente-Eigenschaften gültig sind. Andernfalls werden die Ambiente-Eigenschaften nicht gültig sein.  
  
### <a name="remarks"></a>Hinweise  
 In einige Container des Steuerelements möglicherweise keinen Zugriff auf die ambient-Eigenschaften während des ersten Aufrufs Überschreiben von `COleControl::DoPropExchange`. Dies ist der Fall, wenn der Container ruft [IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) oder [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms680557) vor dem Aufruf [IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) (d. h., wenn er nicht berücksichtigt die **OLEMISC_SETCLIENTSITEFIRST** Statusbit).  
  
##  <a name="a-namewindowproca--colecontrolwindowproc"></a><a name="windowproc"></a>COleControl::WindowProc  
 Stellt ein Windows-Verfahren für ein `COleControl` Objekt.  
  
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
 Der Rückgabewert der Nachricht gesendet.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um bestimmte Nachrichten über das Steuerelement Nachricht Zuordnung weiterleitet.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CIRC3](../../visual-cpp-samples.md)   
 [MFC-Beispiel TESTHELP](../../visual-cpp-samples.md)   
 [COlePropertyPage-Klasse](../../mfc/reference/colepropertypage-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFontHolder-Klasse](../../mfc/reference/cfontholder-class.md)   
 [CPictureHolder-Klasse](../../mfc/reference/cpictureholder-class.md)

