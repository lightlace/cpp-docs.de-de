---
title: "COleControl Class"
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
  - "COleControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControl class"
  - "Steuerelemente [MFC], OLE"
  - "Steuerelemente [MFC], windowless"
  - "OLE-Steuerelemente, MFC"
  - "windowless controls"
  - "windowless controls, MFC"
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COleControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein leistungsstarkes Basisklasse zum Entwickeln von OLE\-Steuerelemente.  
  
## Syntax  
  
```  
class COleControl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleControl::COleControl](../Topic/COleControl::COleControl.md)|Erstellt ein `COleControl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleControl::AmbientAppearance](../Topic/COleControl::AmbientAppearance.md)|Ruft die aktuelle Darstellung des Steuerelements ab.|  
|[COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)|Gibt den Wert der Ambienten BackColor\-Eigenschaft zurück.|  
|[COleControl::AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)|Gibt den Namen des Steuerelements zurück, wie vom Container angegeben.|  
|[COleControl::AmbientFont](../Topic/COleControl::AmbientFont.md)|Gibt den Wert der Ambienten Schriftarteigenschaft zurück.|  
|[COleControl::AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)|Gibt den Wert der Ambienten ForeColor\-Eigenschaft zurück.|  
|[COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)|Gibt eher das Gebietsschema des Containers zurück|  
|[COleControl::AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)|Gibt den Typ von Einheiten zurück, die vom Container verwendet werden.|  
|[COleControl::AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)|Bestimmt, ob Ziehpunkte angezeigt werden.|  
|[COleControl::AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)|Bestimmt, ob das Schraffieren angezeigt wird.|  
|[COleControl::AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)|Gibt den Typ der Textausrichtung angegeben durch den Container zurück.|  
|[COleControl::AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)|Bestimmt, ob das Steuerelement auf Benutzeroberflächeaktionen reagiert.|  
|[COleControl::AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)|Bestimmt den Modus des Containers.|  
|[COleControl::BoundPropertyChanged](../Topic/COleControl::BoundPropertyChanged.md)|Benachrichtigt den Container, dass eine gebundene Eigenschaft geändert wurde.|  
|[COleControl::BoundPropertyRequestEdit](../Topic/COleControl::BoundPropertyRequestEdit.md)|Fordert Berechtigung, den Eigenschaftswert zu bearbeiten.|  
|[COleControl::ClientToParent](../Topic/COleControl::ClientToParent.md)|Übersetzt einen Punkt relativ zum Ursprung des Steuerelements einem Punkt relativ zum Ursprung des Containers.|  
|[COleControl::ClipCaretRect](../Topic/COleControl::ClipCaretRect.md)|Passt ein Einfügemarkerechteck, wenn es von einem Steuerelement somit wird.|  
|[COleControl::ControlInfoChanged](../Topic/COleControl::ControlInfoChanged.md)|Rufen Sie diese Funktion nach dem mnemonischen auf, die vom Steuerelement behandelt wird, hat sich geändert.|  
|[COleControl::DisplayError](../Topic/COleControl::DisplayError.md)|Anzeigen vorrätigen Artikel Fehlerereignisse dem Benutzer des Steuerelements.|  
|[COleControl::DoClick](../Topic/COleControl::DoClick.md)|Implementierung der vordefinierten `DoClick`\-Methode.|  
|[COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)|Serialisiert die Eigenschaften eines Objekts `COleControl`.|  
|[COleControl::DoSuperclassPaint](../Topic/COleControl::DoSuperclassPaint.md)|Aktualisiert ein OLE\-Steuerelement neu, das von einem Windows\-Steuerelement erstellt wurde\).|  
|[COleControl::EnableSimpleFrame](../Topic/COleControl::EnableSimpleFrame.md)|Aktiviert einfache Frameunterstützung für ein Steuerelement.|  
|[COleControl::ExchangeExtent](../Topic/COleControl::ExchangeExtent.md)|Serialisiert die Breite und Höhe des Steuerelements.|  
|[COleControl::ExchangeStockProps](../Topic/COleControl::ExchangeStockProps.md)|Serialisiert die Vorrateigenschaften des Steuerelements.|  
|[COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md)|Serialisiert die Versionsnummer des Steuerelements.|  
|[COleControl::FireClick](../Topic/COleControl::FireClick.md)|Löst das vordefinierte `Click`\-Ereignis aus.|  
|[COleControl::FireDblClick](../Topic/COleControl::FireDblClick.md)|Löst das vordefinierte `DblClick`\-Ereignis aus.|  
|[COleControl::FireError](../Topic/COleControl::FireError.md)|Löst das vordefinierte `Error`\-Ereignis aus.|  
|[COleControl::FireEvent](../Topic/COleControl::FireEvent.md)|Löst ein benutzerdefiniertes Ereignis aus.|  
|[COleControl::FireKeyDown](../Topic/COleControl::FireKeyDown.md)|Löst das vordefinierte `KeyDown`\-Ereignis aus.|  
|[COleControl::FireKeyPress](../Topic/COleControl::FireKeyPress.md)|Löst das vordefinierte `KeyPress`\-Ereignis aus.|  
|[COleControl::FireKeyUp](../Topic/COleControl::FireKeyUp.md)|Löst das vordefinierte `KeyUp`\-Ereignis aus.|  
|[COleControl::FireMouseDown](../Topic/COleControl::FireMouseDown.md)|Löst das vordefinierte `MouseDown`\-Ereignis aus.|  
|[COleControl::FireMouseMove](../Topic/COleControl::FireMouseMove.md)|Löst das vordefinierte `MouseMove`\-Ereignis aus.|  
|[COleControl::FireMouseUp](../Topic/COleControl::FireMouseUp.md)|Löst das vordefinierte `MouseUp`\-Ereignis aus.|  
|[COleControl::FireReadyStateChange](../Topic/COleControl::FireReadyStateChange.md)|Löst ein Ereignis wenn die Änderungen des betriebsbereiten Zustand des Steuerelements aus.|  
|[COleControl::GetActivationPolicy](../Topic/COleControl::GetActivationPolicy.md)|Ändert das standardmäßige Aktivierungsverhalten eines Steuerelements, das die `IPointerInactive`\-Schnittstelle unterstützt.|  
|[COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md)|Gibt den Wert der angegebenen Ambient\-Eigenschaft zurück.|  
|[COleControl::GetAppearance](../Topic/COleControl::GetAppearance.md)|Gibt den Wert der vordefinierten Darstellungseigenschaft zurück.|  
|[COleControl::GetBackColor](../Topic/COleControl::GetBackColor.md)|Gibt den Wert der vordefinierten BackColor\-Eigenschaft zurück.|  
|[COleControl::GetBorderStyle](../Topic/COleControl::GetBorderStyle.md)|Gibt den Wert der vordefinierten BorderStyle\-Eigenschaft zurück.|  
|[COleControl::GetCapture](../Topic/COleControl::GetCapture.md)|Bestimmt, ob ein fensterloses, aktiviertes Steuerelementobjekt die Mausauswahl verfügt.|  
|[COleControl::GetClassID](../Topic/COleControl::GetClassID.md)|Ruft die OLE\-Klassen\-ID des Steuerelements ab.|  
|[COleControl::GetClientOffset](../Topic/COleControl::GetClientOffset.md)|Ruft den Unterschied zwischen der linken oberen Ecke des rechteckigen Bereichs des Steuerelements und der linken oberen Ecke des Clientbereichs ab.|  
|[COleControl::GetClientRect](../Topic/COleControl::GetClientRect.md)|Ruft die Größe des Clientbereichs des Steuerelements ab.|  
|[COleControl::GetClientSite](../Topic/COleControl::GetClientSite.md)|Fragt ein Objekt für den Zeiger auf der aktuellen Clientsite innerhalb des Containers ab.|  
|[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)|Ruft die Steuerflagseinstellungen ab.|  
|[COleControl::GetControlSize](../Topic/COleControl::GetControlSize.md)|Gibt die Position und die Größe des OLE\-Steuerelements zurück.|  
|[COleControl::GetDC](../Topic/COleControl::GetDC.md)|Stellt eine Möglichkeit bereit, damit ein fensterloses Steuerelement einen Gerätekontext vom Container abruft.|  
|[COleControl::GetEnabled](../Topic/COleControl::GetEnabled.md)|Gibt den Wert der vordefinierten aktivierten Eigenschaft zurück.|  
|[COleControl::GetExtendedControl](../Topic/COleControl::GetExtendedControl.md)|Ruft einen Zeiger auf einen erweiterten Steuerelementobjekt ab, das dem Container gehört.|  
|[COleControl::GetFocus](../Topic/COleControl::GetFocus.md)|Bestimmt, ob das Steuerelement den Fokus besitzt.|  
|[COleControl::GetFont](../Topic/COleControl::GetFont.md)|Gibt den Wert der vordefinierten Schriftarteigenschaft zurück.|  
|[COleControl::GetFontTextMetrics](../Topic/COleControl::GetFontTextMetrics.md)|Gibt die Metriken `CFontHolder` eines Objekts zurück.|  
|[COleControl::GetForeColor](../Topic/COleControl::GetForeColor.md)|Gibt den Wert der vordefinierten ForeColor\-Eigenschaft zurück.|  
|[COleControl::GetHwnd](../Topic/COleControl::GetHwnd.md)|Gibt den Wert der vordefinierten hWnd Eigenschaft zurück.|  
|[COleControl::GetMessageString](../Topic/COleControl::GetMessageString.md)|Stellt Statusleistentext für ein Menüelement bereit.|  
|[COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md)|Verhindert den Zugriff auf den Eigenschaftswert eines Steuerelements durch den Benutzer.|  
|[COleControl::GetReadyState](../Topic/COleControl::GetReadyState.md)|Gibt den Bereitschaftszustand des Steuerelements zurück.|  
|[COleControl::GetRectInContainer](../Topic/COleControl::GetRectInContainer.md)|Gibt das Rechteck des Steuerelements relativ zu seinem Container zurück.|  
|[COleControl::GetStockTextMetrics](../Topic/COleControl::GetStockTextMetrics.md)|Gibt die Metriken der vordefinierten Schriftarteigenschaft zurück.|  
|[COleControl::GetText](../Topic/COleControl::GetText.md)|Gibt den Wert der vordefinierten Text\- oder Beschriftungseigenschaft zurück.|  
|[COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md)|Überschreiben Sie, um die fensterlose eines Steuerelements zu ermöglichen, ein Ziel von Drag & Drop\-Vorgängen zu sein.|  
|[COleControl::InitializeIIDs](../Topic/COleControl::InitializeIIDs.md)|Das informiert die Basisklasse über die IID, das das Steuerelement verwendet.|  
|[COleControl::InternalGetFont](../Topic/COleControl::InternalGetFont.md)|Gibt ein Objekt `CFontHolder` für die vordefinierte Schriftarteigenschaft zurück.|  
|[COleControl::InternalGetText](../Topic/COleControl::InternalGetText.md)|Ruft die vordefinierte Beschriftungs\- oder Texteigenschaft ab.|  
|[COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md)|Legt den Bereitschaftszustand des Steuerelements fest Betriebsbereit\-Zustandänderung und löst das Ereignis aus.|  
|[COleControl::InvalidateControl](../Topic/COleControl::InvalidateControl.md)|Macht einen Bereich des angezeigten Steuerelements ungültig und wird Neuzeichnen zu werden.|  
|[COleControl::InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)|Löscht den Clientbereich des Containerfensters innerhalb des angegebenen Bereichs ungültig.  Kann verwendet werden, um fensterlose Steuerelemente im Bereich neu zu zeichnen.|  
|[COleControl::IsConvertingVBX](../Topic/COleControl::IsConvertingVBX.md)|Ermöglicht es spezialisierte Laden eines OLE\-Steuerelements.|  
|[COleControl::IsModified](../Topic/COleControl::IsModified.md)|Bestimmt, ob der Steuerelementzustand geändert hat.|  
|[COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md)|Gibt an, ob der Container optimierte Zeichnen für den aktuellen Zeichenvorgang unterstützt.|  
|[COleControl::IsSubclassedControl](../Topic/COleControl::IsSubclassedControl.md)|Aufgerufen, um zu ermitteln, ob das Steuerelement ein Windows\-Steuerelement als Unterklasse verwendet.|  
|[COleControl::Load](../Topic/COleControl::Load.md)|Setzt alle vorherigen asynchronen Daten zurück und initiiert eine neue Auslastung der asynchronen Eigenschaft.|  
|[COleControl::LockInPlaceActive](../Topic/COleControl::LockInPlaceActive.md)|Bestimmt, ob das Steuerelement vom Container deaktiviert werden kann.|  
|[COleControl::OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md)|Aufgerufen, wenn eine Ambient\-Eigenschaft geändert wird.|  
|[COleControl::OnAppearanceChanged](../Topic/COleControl::OnAppearanceChanged.md)|Aufgerufen, wenn die vordefinierte Darstellungseigenschaft geändert wird.|  
|[COleControl::OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md)|Aufgerufen, wenn die Bestand BackColor\-Eigenschaft geändert wird.|  
|[COleControl::OnBorderStyleChanged](../Topic/COleControl::OnBorderStyleChanged.md)|Aufgerufen, wenn die Bestand BorderStyle\-Eigenschaft geändert wird.|  
|[COleControl::OnClick](../Topic/COleControl::OnClick.md)|Aufgerufen, um das Klickereignis vordefinierte auszulösen.|  
|[COleControl::OnClose](../Topic/COleControl::OnClose.md)|Benachrichtigt das Steuerelement, dass `IOleControl::Close` aufgerufen wurde.|  
|[COleControl::OnDoVerb](../Topic/COleControl::OnDoVerb.md)|Aufgerufen, nachdem ein Steuerverb ausgeführt wurde.|  
|[COleControl::OnDraw](../Topic/COleControl::OnDraw.md)|Aufgerufen, wenn ein Steuerelement angefordert wird, sich selbst neu zu entwerfen.|  
|[COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md)|Aufgerufen vom Container, wenn ein Steuerelement angefordert wird, die mit einem Metadateigerätekontexts neu zu zeichnen.|  
|[COleControl::OnEdit](../Topic/COleControl::OnEdit.md)|Aufgerufen vom Container zu Benutzeroberfläche können Sie ein OLE\-Steuerelement.|  
|[COleControl::OnEnabledChanged](../Topic/COleControl::OnEnabledChanged.md)|Aufgerufen, wenn die vordefinierte aktivierte Eigenschaft geändert wird.|  
|[COleControl::OnEnumVerbs](../Topic/COleControl::OnEnumVerbs.md)|Aufgerufen vom Container, um die Verben eines Steuerelements aufzulisten.|  
|[COleControl::OnEventAdvise](../Topic/COleControl::OnEventAdvise.md)|Aufgerufen, wenn Ereignishandler von einem Steuerelement verbunden oder getrennt werden.|  
|[COleControl::OnFontChanged](../Topic/COleControl::OnFontChanged.md)|Aufgerufen, wenn die vordefinierte Schriftarteigenschaft geändert wird.|  
|[COleControl::OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md)|Aufgerufen, wenn die Bestand ForeColor\-Eigenschaft geändert wird.|  
|[COleControl::OnFreezeEvents](../Topic/COleControl::OnFreezeEvents.md)|Aufgerufen, wenn die Ereignisse eines Steuerelements fixiert und seine Fixierung nicht aufgehoben werden.|  
|[COleControl::OnGetColorSet](../Topic/COleControl::OnGetColorSet.md)|Benachrichtigt das Steuerelement, dass `IOleObject::GetColorSet` aufgerufen wurde.|  
|[COleControl::OnGetControlInfo](../Topic/COleControl::OnGetControlInfo.md)|Stellt mnemonische Informationen an den Container bereit.|  
|[COleControl::OnGetDisplayString](../Topic/COleControl::OnGetDisplayString.md)|Aufgerufen, erhält eine Zeichenfolge, um eines Eigenschaftswerts darzustellen.|  
|[COleControl::OnGetInPlaceMenu](../Topic/COleControl::OnGetInPlaceMenu.md)|Zeigt das Handle des Steuerelements an, das dem Containermenü zusammengeführt wird.|  
|[COleControl::OnGetNaturalExtent](../Topic/COleControl::OnGetNaturalExtent.md)|Überschreiben Sie, um die Anzeigengröße des Steuerelements abzurufen am ehesten dem vorgeschlagenen Größen\- und Wertebereichsmodus.|  
|[COleControl::OnGetPredefinedStrings](../Topic/COleControl::OnGetPredefinedStrings.md)|EINGABETASTE reiht die Darstellung von möglichen Werten für eine Eigenschaft auf.|  
|[COleControl::OnGetPredefinedValue](../Topic/COleControl::OnGetPredefinedValue.md)|Gibt den Wert entsprechend einer vordefinierten Zeichenfolge zurück.|  
|[COleControl::OnGetViewExtent](../Topic/COleControl::OnGetViewExtent.md)|Überschreiben Sie, um die Größe der Anzeigebereiche des Steuerelements abzurufen \(kann verwendet werden, um in zwei Durchläufenzeichnung\) zu aktivieren.|  
|[COleControl::OnGetViewRect](../Topic/COleControl::OnGetViewRect.md)|Überschreiben Sie, um die Größe des Steuerelements in ein Rechteck zu konvertieren, die an einer bestimmten Position beginnt.|  
|[COleControl::OnGetViewStatus](../Topic/COleControl::OnGetViewStatus.md)|Überschreiben Sie, um das Anzeigen des Steuerelements abzurufen.|  
|[COleControl::OnHideToolBars](../Topic/COleControl::OnHideToolBars.md)|Aufgerufen vom Container, wenn das Steuerelement deaktiviertes Benutzeroberfläche ist.|  
|[COleControl::OnInactiveMouseMove](../Topic/COleControl::OnInactiveMouseMove.md)|Überschreibung für das den Container für das inaktive Steuerelement unter den `WM_MOUSEMOVE`\-Mauszeigerdispatch\-Meldungen an das Steuerelement.|  
|[COleControl::OnInactiveSetCursor](../Topic/COleControl::OnInactiveSetCursor.md)|Überschreibung für das den Container für das inaktive Steuerelement unter den `WM_SETCURSOR`\-Mauszeigerdispatch\-Meldungen an das Steuerelement.|  
|[COleControl::OnKeyDownEvent](../Topic/COleControl::OnKeyDownEvent.md)|Aufgerufen, nachdem das vordefinierte KeyDown\-Ereignis ausgelöst wurde.|  
|[COleControl::OnKeyPressEvent](../Topic/COleControl::OnKeyPressEvent.md)|Aufgerufen, nachdem das Bestand KeyPress\-Ereignis ausgelöst wurde.|  
|[COleControl::OnKeyUpEvent](../Topic/COleControl::OnKeyUpEvent.md)|Aufgerufen, nachdem das Bestand KeyUp\-Ereignis ausgelöst wurde.|  
|[COleControl::OnMapPropertyToPage](../Topic/COleControl::OnMapPropertyToPage.md)|Gibt an, das für Bearbeitung verwendeten Eigenschaftenseite, einer Eigenschaft.|  
|[COleControl::OnMnemonic](../Topic/COleControl::OnMnemonic.md)|Aufgerufen, wenn eine mnemonische Taste des Steuerelements gedrückt wurde.|  
|[COleControl::OnProperties](../Topic/COleControl::OnProperties.md)|Aufgerufen, wenn das "Eigenschaft" Verb des Steuerelements aufgerufen wurde.|  
|[COleControl::OnQueryHitPoint](../Topic/COleControl::OnQueryHitPoint.md)|Abzufragen Überschreibung ob Anzeigenüberschneidungen eines Steuerelements ein angegebenen Punkt.|  
|[COleControl::OnQueryHitRect](../Topic/COleControl::OnQueryHitRect.md)|Abzufragen Überschreibung, ob die Anzeige eines Steuerelements entweder sich Punkt in einem angegebenen Rechteck schneidet.|  
|[COleControl::OnRenderData](../Topic/COleControl::OnRenderData.md)|Aufgerufen durch das Framework, um Daten im angegebenen Format abzurufen.|  
|[COleControl::OnRenderFileData](../Topic/COleControl::OnRenderFileData.md)|Aufgerufen durch das Framework, um Daten aus einer Datei im angegebenen Format abzurufen.|  
|[COleControl::OnRenderGlobalData](../Topic/COleControl::OnRenderGlobalData.md)|Aufgerufen durch das Framework, um Daten aus dem globalen Arbeitsspeicher im angegebenen Format abzurufen.|  
|[COleControl::OnResetState](../Topic/COleControl::OnResetState.md)|Setzt die Eigenschaften eines Steuerelements auf die Standardwerte zurück.|  
|[COleControl::OnSetClientSite](../Topic/COleControl::OnSetClientSite.md)|Benachrichtigt das Steuerelement, dass `IOleControl::SetClientSite` aufgerufen wurde.|  
|[COleControl::OnSetData](../Topic/COleControl::OnSetData.md)|Ersetzt die Daten des Steuerelements durch einen anderen Wert.|  
|[COleControl::OnSetExtent](../Topic/COleControl::OnSetExtent.md)|Aufgerufen nach dem Wertebereich des Steuerelements hat sich geändert.|  
|[COleControl::OnSetObjectRects](../Topic/COleControl::OnSetObjectRects.md)|Aufgerufen, nachdem die Dimensionen des Steuerelements geändert wurden.|  
|[COleControl::OnShowToolBars](../Topic/COleControl::OnShowToolBars.md)|Aufgerufen, wenn das Steuerelement Benutzeroberfläche aktiviert war.|  
|[COleControl::OnTextChanged](../Topic/COleControl::OnTextChanged.md)|Aufgerufen, wenn die vordefinierte Text\- oder Beschriftungseigenschaft geändert wird.|  
|[COleControl::OnWindowlessMessage](../Topic/COleControl::OnWindowlessMessage.md)|Prozessfenstermeldungen \(außer Maus\- und Tastaturmeldungen\) für fensterlose Steuerelemente.|  
|[COleControl::ParentToClient](../Topic/COleControl::ParentToClient.md)|Übersetzt einen Punkt relativ zum Ursprung des Containers zu einem Punkt im Verhältnis zu dem Ursprung des Steuerelements.|  
|[COleControl::PostModalDialog](../Topic/COleControl::PostModalDialog.md)|Benachrichtigt den Container, dass ein modales Dialogfeld geschlossen wurde.|  
|[COleControl::PreModalDialog](../Topic/COleControl::PreModalDialog.md)|Benachrichtigt den Container, dass ein modales Dialogfeld im Begriff ist angezeigt werden.|  
|[COleControl::RecreateControlWindow](../Topic/COleControl::RecreateControlWindow.md)|Zerstört und erstellt das Fenster des Steuerelements neu.|  
|[COleControl::Refresh](../Topic/COleControl::Refresh.md)|Erzwingt ein Neu streichung der Darstellung eines Steuerelements.|  
|[COleControl::ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)|Befreit Mausauswahl.|  
|[COleControl::ReleaseDC](../Topic/COleControl::ReleaseDC.md)|Gibt den Anzeigegerätenkontext eines Containers fensterlose eines Steuerelements frei.|  
|[COleControl::ReparentControlWindow](../Topic/COleControl::ReparentControlWindow.md)|Setzt das übergeordnete Element des Steuerfensters zurück.|  
|[COleControl::ResetStockProps](../Topic/COleControl::ResetStockProps.md)|Initialisiert `COleControl` Vorrateigenschaften mit ihren Standardwerten.|  
|[COleControl::ResetVersion](../Topic/COleControl::ResetVersion.md)|Initialisiert die Versionsnummer zu einem angegebenen Wert.|  
|[COleControl::ScrollWindow](../Topic/COleControl::ScrollWindow.md)|Ermöglicht einem fensterlose Steuerelement, um einen Bereich innerhalb des direkt aktiven Bilder auf der Anzeige liegen.|  
|[COleControl::SelectFontObject](../Topic/COleControl::SelectFontObject.md)|Wählt eine benutzerdefinierte Schriftarteigenschaft in einen Gerätekontext aus.|  
|[COleControl::SelectStockFont](../Topic/COleControl::SelectStockFont.md)|Wählt die vordefinierte Schriftarteigenschaft in einen Gerätekontext aus.|  
|[COleControl::SerializeExtent](../Topic/COleControl::SerializeExtent.md)|Serialisiert oder initialisiert den Bildbereich für das Steuerelement.|  
|[COleControl::SerializeStockProps](../Topic/COleControl::SerializeStockProps.md)|Serialisiert oder initialisiert die `COleControl` Vorrateigenschaften.|  
|[COleControl::SerializeVersion](../Topic/COleControl::SerializeVersion.md)|Serialisiert oder initialisiert die Versionsinformationen des Steuerelements.|  
|[COleControl::SetAppearance](../Topic/COleControl::SetAppearance.md)|Legt den Wert der vordefinierten Darstellungseigenschaft fest.|  
|[COleControl::SetBackColor](../Topic/COleControl::SetBackColor.md)|Legt den Wert der vordefinierten BackColor\-Eigenschaft fest.|  
|[COleControl::SetBorderStyle](../Topic/COleControl::SetBorderStyle.md)|Legt den Wert der vordefinierten BorderStyle\-Eigenschaft fest.|  
|[COleControl::SetCapture](../Topic/COleControl::SetCapture.md)|Veranlasst das Containerfenster des Steuerelements, die Mausauswahl im Namen des Steuerelements in Besitz zu akzeptieren.|  
|[COleControl::SetControlSize](../Topic/COleControl::SetControlSize.md)|Legt die Position und die Größe des OLE\-Steuerelements fest.|  
|[COleControl::SetEnabled](../Topic/COleControl::SetEnabled.md)|Legt den Wert der vordefinierten aktivierten Eigenschaft fest.|  
|[COleControl::SetFocus](../Topic/COleControl::SetFocus.md)|Veranlasst das Containerfenster des Steuerelements, den Eingabefokus im Namen des Steuerelements in Besitz zu akzeptieren.|  
|[COleControl::SetFont](../Topic/COleControl::SetFont.md)|Legt den Wert der vordefinierten Schriftarteigenschaft fest.|  
|[COleControl::SetForeColor](../Topic/COleControl::SetForeColor.md)|Legt den Wert der vordefinierten ForeColor\-Eigenschaft fest.|  
|[COleControl::SetInitialSize](../Topic/COleControl::SetInitialSize.md)|Legt die Größe eines OLE\-Steuerelements fest, wenn Sie zuerst in einem Container angezeigt werden.|  
|[COleControl::SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md)|Ändert den geänderten Zustand eines Steuerelements.|  
|[COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md)|Gibt an, dass eine Bearbeitungsanforderung fehlgeschlagen ist.|  
|[COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md)|Verhindert Änderung auf den Eigenschaftswert eines Steuerelements durch den Benutzer.|  
|[COleControl::SetRectInContainer](../Topic/COleControl::SetRectInContainer.md)|Legt das Rechteck des Steuerelements relativ zu seinem Container fest.|  
|[COleControl::SetText](../Topic/COleControl::SetText.md)|Legt den Wert der vordefinierten Text\- oder Beschriftungseigenschaft fest.|  
|[COleControl::ThrowError](../Topic/COleControl::ThrowError.md)|signalisiert, dass ein Fehler in einem OLE\-Steuerelement aufgetreten ist.|  
|[COleControl::TransformCoords](../Topic/COleControl::TransformCoords.md)|Transformiert Koordinatenwerte zwischen einem Container und dem Steuerelement.|  
|[COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md)|Konvertiert einen Wert **OLE\_COLOR** zu einem **COLORREF**\-Wert.|  
|[COleControl::WillAmbientsBeValidDuringLoad](../Topic/COleControl::WillAmbientsBeValidDuringLoad.md)|Bestimmt, ob Ambient\-Eigenschaften nächsten das Steuerelement wird geladen verfügbar sind.|  
|[COleControl::WindowProc](../Topic/COleControl::WindowProc.md)|Enthält eine Windows\-Prozedur für ein Objekt `COleControl` vor.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleControl::DrawContent](../Topic/COleControl::DrawContent.md)|Aufgerufen vom Framework, wenn die Darstellung des Steuerelements aktualisiert werden muss.|  
|[COleControl::DrawMetafile](../Topic/COleControl::DrawMetafile.md)|Aufgerufen vom Framework, wenn der Metadateigerätekontext verwendet wird.|  
|[COleControl::IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md)|Ermöglicht Automatisierungsmethodenaufruf.|  
|[COleControl::SetInitialDataFormats](../Topic/COleControl::SetInitialDataFormats.md)|Aufgerufen vom Framework, um die Liste der Datenformaten zu initialisieren vom Steuerelement unterstützt wird.|  
  
## Hinweise  
 Ist von `CWnd`, erbt diese Klasse die gesamte Funktionalität eines Windows\-Fensterobjekts sowie Einzelheiten der zusätzlichen Funktionen zu OLE, wie Auslösen von Ereignissen und der Möglichkeit, Methoden und Eigenschaften zu unterstützen.  
  
 OLE\-Steuerelemente können sich in OLE\-Containeranwendungen eingefügt werden und mit dem Container kommunizieren, indem sie eine bidirektionale System von Auslösen von Ereignissen verwenden und Methoden und Eigenschaften zum Container verfügbar machen.  Beachten Sie, dass Standard\-OLE\-Container nur die grundlegende Funktionalität eines OLE\-Steuerelements unterstützen.  Sie ist nicht möglich, erweiterte Funktionen eines OLE\-Steuerelements zu unterstützen.  Auslösen von Ereignissen treten auf, wenn Ereignisse an den Container aufgrund bestimmter Aktionen gesendet werden, die im \- Steuerelement stattfinden.  Dagegen ist der Container das Steuerelement kommunizieren, indem er einen Satz verfügbar gemachten Methoden abgerufen werden und Eigenschaften, die Memberfunktionen und Datenmember von eine C\+\+\-Datei analog sind, Klasse.  Dieser Ansatz ermöglicht es dem Entwickler, die Darstellung des Steuerelements zu steuern und den Container zu benachrichtigen, wenn bestimmte Aktionen auftreten.  
  
## Fensterlose Steuerelemente  
 OLE\-Steuerelemente können ohne ein Fenster verwendete direkt aktiviertes sein.  Fensterlose Steuerelemente weisen erhebliche Vorteile:  
  
-   Fensterlose Steuerelemente können transparent und nicht\-rechteckig sein  
  
-   Fensterlose Steuerelemente verringern außerdem Erstellungszeit des Objekts  
  
 Steuerelemente erfordern kein Fenster.  Dienste, die ein Fenster bietet, können über ein einzelnes freigegebenes Fenster \(normalerweise den Container\) und ein Bit des Weiterleitens des Codes leicht bereitgestellt werden.  Ein Fenster zu ändern ist meistens eine unnötige Schwierigkeit auf dem Objekt.  
  
 Wenn fensterlose Aktivierung verwendet wird, ist der Container \(der ein Fenster hat\), zum Bereitstellen von Diensten verantwortlich, die andernfalls vom eigenen Fenster des Steuerelements bereitgestellt worden wären.  Wenn das Steuerelement, den Tastaturfokus abfragen, die Mausauswahl abzufragen oder zum Abrufen eines Gerätekontext, diese Vorgänge vom Container verwaltet werden.  Der Aufruf `COleControl`[FensterlosVorgang Memberfunktionen](assetId:///e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) diese Vorgänge auf den Container.  
  
 Wenn fensterlose Aktivierung aktiviert ist, stellen die Containerdelegat\-Eingabemeldungen zu `IOleInPlaceObjectWindowless` des Steuerelements auf \(eine Erweiterung von [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) für fensterlose Unterstützung\).  Die `COleControl`\-Implementierung dieser Schnittstelle leitet diese Meldungen durch die Meldungszuordnung des Steuerelements weiter nach, die Mauskoordinaten entsprechend anpassen.  Sie können diese Meldungen wie gewöhnliche Fenstermeldungen verarbeiten, indem Sie die entsprechenden Einträgen zur Meldungszuordnung hinzufügen.  
  
 In einem fensterlose Steuerelement sollten Sie die `COleControl`\-Memberfunktionen anstelle entsprechender `CWnd`\-Memberfunktionen oder ihrer verwandten Windows\-API\-Funktionen immer verwenden.  
  
 OLE\-Steuerelement\-Objekte können das Fenster auch erstellen, wenn sie aktiv sind, aber der Arbeitsaufwand, der für den INACTIVEACTIVE\-Übergang benötigt wird, wechselt und die Geschwindigkeit des Übergangs wird unten.  Es gibt Fälle, wenn dies ein Problem ist: Betrachten Sie als Beispiel ein Raster von Textfeldern.  Wenn Cursoring auf ab und über die Spalte, jedes Steuerelement direkt aktiviert werden muss und anschließend deaktiviert.  Die Geschwindigkeit des inaktiven\/aktiven Übergangs beeinflusst direkt die Bildlaufgeschwindigkeit.  
  
 Weitere Informationen über das Entwickeln eines OLE\-Steuerelement\-Frameworks, finden Sie in Artikel [MFC\-ActiveX\-Steuerelemente](../../mfc/mfc-activex-controls.md) und [Übersicht: Erstellen eines MFC\-ActiveX\-Steuerelement\-Programms](../../mfc/reference/mfc-activex-control-wizard.md).  Informationen zum Optimieren von OLE\-Steuerelementen, einschließlich der fensterlose Steuerelemente und flimmerfreien, finden Sie unter [MFC\-ActiveX\-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `COleControl`  
  
## Anforderungen  
 **Header:**  afxctl.h  
  
## Siehe auch  
 [MFC überprüft CIRC3](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel TESTHELP](../../top/visual-cpp-samples.md)   
 [COlePropertyPage Class](../../mfc/reference/colepropertypage-class.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)   
 [CPictureHolder Class](../../mfc/reference/cpictureholder-class.md)