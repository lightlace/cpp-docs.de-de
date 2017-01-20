---
title: "CComControlBase Class"
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
  - "CComControlBase"
  - "ATL.CComControlBase"
  - "ATL::CComControlBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComControlBase class"
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CComControlBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL\-Steuerelementen bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class ATL_NO_VTABLE CComControlBase  
  
```  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](../Topic/CComControlBase::AppearanceType.md)|Überschreiben Sie, wenn die `m_nAppearance` Vorrateigenschaft nicht vom Typ `short` ist.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](../Topic/CComControlBase::CComControlBase.md)|Der \-Konstruktor.|  
|[CComControlBase::~CComControlBase](../Topic/CComControlBase::~CComControlBase.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](../Topic/CComControlBase::ControlQueryInterface.md)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComControlBase::DoesVerbActivate](../Topic/CComControlBase::DoesVerbActivate.md)|Überprüft, ob der `iVerb`\-Parameter durch `IOleObjectImpl::DoVerb` verwendete, entweder aktiviert die Benutzeroberfläche des Steuerelements \(`iVerb` entspricht `OLEIVERB_UIACTIVATE`\), definiert die Aktion, wenn der Benutzer auf das Steuerelement \(`iVerb` entspricht `OLEIVERB_PRIMARY`\), doppelklicken, wird das Steuerelement \(`iVerb` entspricht `OLEIVERB_SHOW`\) oder aktiviert das Steuerelement \(`iVerb` entspricht **OLEIVERB\_INPLACEACTIVATE**\).|  
|[CComControlBase::DoesVerbUIActivate](../Topic/CComControlBase::DoesVerbUIActivate.md)|Überprüft, ob der `iVerb`\-Parameter, der von `IOleObjectImpl::DoVerb` verwendet wird, die Benutzeroberfläche des Steuerelements wird zu aktivieren und gibt **TRUE** zurück.|  
|[CComControlBase::DoVerbProperties](../Topic/CComControlBase::DoVerbProperties.md)|Zeigt die Eigenschaftenseiten des Steuerelements an.|  
|[CComControlBase::FireViewChange](../Topic/CComControlBase::FireViewChange.md)|Rufen Sie diese Methode auf, um den Container mitzuteilen, dass das Steuerelement neu zu zeichnen, oder benachrichtigen Sie die registrierten Advise\-Senken, dass die Ansicht des Steuerelements geändert hat.|  
|[CComControlBase::GetAmbientAppearance](../Topic/CComControlBase::GetAmbientAppearance.md)|Ruft **DISPID\_AMBIENT\_APPEARANCE**, die aktuelle Darstellungseinstellung für das Steuerelement ab: Ebene 0 für und 1 für 3D.|  
|[CComControlBase::GetAmbientAutoClip](../Topic/CComControlBase::GetAmbientAutoClip.md)|Ruft **DISPID\_AMBIENT\_AUTOCLIP** ab, ein Flag, ob der Container automatische Clipping des Kontrollanzeigebereichs unterstützt.|  
|[CComControlBase::GetAmbientBackColor](../Topic/CComControlBase::GetAmbientBackColor.md)|Ruft **DISPID\_AMBIENT\_BACKCOLOR**, die eine Hintergrundfarbe für alle Steuerelemente ab, definiert vom Container.|  
|[CComControlBase::GetAmbientCharSet](../Topic/CComControlBase::GetAmbientCharSet.md)|Ruft **DISPID\_AMBIENT\_CHARSET**, den Ambienten Zeichensatz für alle Steuerelemente ab, definiert vom Container.|  
|[CComControlBase::GetAmbientCodePage](../Topic/CComControlBase::GetAmbientCodePage.md)|Ruft **DISPID\_AMBIENT\_CODEPAGE**, den Ambienten Zeichensatz für alle Steuerelemente ab, definiert vom Container.|  
|[CComControlBase::GetAmbientDisplayAsDefault](../Topic/CComControlBase::GetAmbientDisplayAsDefault.md)|Ruft **DISPID\_AMBIENT\_DISPLAYASDEFAULT**, ein Flag ab, das **TRUE** ist, wenn der Container das Steuerelement in dieser Website markiert wurde, um eine Standardschaltfläche zu sein, daher sollte ein Schaltflächen\-Steuerelement mit stärkeren Frame sich selbst zeichnen.|  
|[CComControlBase::GetAmbientDisplayName](../Topic/CComControlBase::GetAmbientDisplayName.md)|Ruft **DISPID\_AMBIENT\_DISPLAYNAME**, den Namen ab, der den Container zum Steuerelement angegeben hat.|  
|[CComControlBase::GetAmbientFont](../Topic/CComControlBase::GetAmbientFont.md)|Ruft einen Zeiger auf die Ambienten `IFont`\-Schnittstelle des Containers ab.|  
|[CComControlBase::GetAmbientFontDisp](../Topic/CComControlBase::GetAmbientFontDisp.md)|Ruft einen Zeiger auf die Ambienten **IFontDisp** Dispatchschnittstelle des Containers ab.|  
|[CComControlBase::GetAmbientForeColor](../Topic/CComControlBase::GetAmbientForeColor.md)|Ruft **DISPID\_AMBIENT\_FORECOLOR**, die eine Vordergrundfarbe für alle Steuerelemente ab, definiert vom Container.|  
|[CComControlBase::GetAmbientLocaleID](../Topic/CComControlBase::GetAmbientLocaleID.md)|Ruft **DISPID\_AMBIENT\_LOCALEID**, den Bezeichner der Sprache ab, die vom Container verwendet wird.|  
|[CComControlBase::GetAmbientMessageReflect](../Topic/CComControlBase::GetAmbientMessageReflect.md)|Ruft **DISPID\_AMBIENT\_MESSAGEREFLECT** ab, ein Flag, ob der Container Fenstermeldungen \(z `WM_DRAWITEM`\) als Ereignisse empfangen möchte.|  
|[CComControlBase::GetAmbientPalette](../Topic/CComControlBase::GetAmbientPalette.md)|Ruft **DISPID\_AMBIENT\_PALETTE** ab, verwendet, um auf `HPALETTE` des Containers zuzugreifen.|  
|[CComControlBase::GetAmbientProperty](../Topic/CComControlBase::GetAmbientProperty.md)|Ruft die Containereigenschaft ab, die von `id` angegeben wird.|  
|[CComControlBase::GetAmbientRightToLeft](../Topic/CComControlBase::GetAmbientRightToLeft.md)|Ruft **DISPID\_AMBIENT\_RIGHTTOLEFT** ab, in die die Richtung angezeigt wird vom Container erfüllen.|  
|[CComControlBase::GetAmbientScaleUnits](../Topic/CComControlBase::GetAmbientScaleUnits.md)|Ruft **DISPID\_AMBIENT\_SCALEUNITS**, die Ambienten Einheiten des Containers \(wie Zoll oder Zentimeter\) zum Bezeichnen von Anzeigen ab.|  
|[CComControlBase::GetAmbientShowGrabHandles](../Topic/CComControlBase::GetAmbientShowGrabHandles.md)|Ruft **DISPID\_AMBIENT\_SHOWGRABHANDLES**, ein Flag, das angibt, ob der Container das Steuerelement an Anzeigenziehpunkten sich zulässt, wenn aktiv.|  
|[CComControlBase::GetAmbientShowHatching](../Topic/CComControlBase::GetAmbientShowHatching.md)|Ruft **DISPID\_AMBIENT\_SHOWHATCHING** ab, ein Flag, ob der Container dem Steuerelement ermöglicht, um mit einer Schraffur anzuzeigen, wenn die Benutzeroberfläche aktiv ist.|  
|[CComControlBase::GetAmbientSupportsMnemonics](../Topic/CComControlBase::GetAmbientSupportsMnemonics.md)|Ruft **DISPID\_AMBIENT\_SUPPORTSMNEMONICS** ab, ein Flag, ob der Container Tastaturmnemotechnik unterstützt.|  
|[CComControlBase::GetAmbientTextAlign](../Topic/CComControlBase::GetAmbientTextAlign.md)|Ruft **DISPID\_AMBIENT\_TEXTALIGN**, die Textausrichtung ab, die vom Container bevorzugt wird: 0 für allgemeine Ausrichtung \(Zahlen berichtigen, der mehr übrig Text\), 1 für linke Ausrichtung, 2 für und 3 für Ausrichtung mittlere rechte Ausrichtung.|  
|[CComControlBase::GetAmbientTopToBottom](../Topic/CComControlBase::GetAmbientTopToBottom.md)|Ruft **DISPID\_AMBIENT\_TOPTOBOTTOM** ab, in die die Richtung angezeigt wird vom Container erfüllen.|  
|[CComControlBase::GetAmbientUIDead](../Topic/CComControlBase::GetAmbientUIDead.md)|Ruft **DISPID\_AMBIENT\_UIDEAD** ab, ein Flag, ob der Container das Steuerelement auf Benutzeroberflächeaktionen reagieren wünscht.|  
|[CComControlBase::GetAmbientUserMode](../Topic/CComControlBase::GetAmbientUserMode.md)|Ruft **DISPID\_AMBIENT\_USERMODE** ab, ein Flag, ob der Container Ausführmodus \(**TRUE**\) oder im Entwurfsmodus \(**FALSE**\) ist.|  
|[CComControlBase::GetDirty](../Topic/CComControlBase::GetDirty.md)|Gibt den Wert des Datenmembers `m_bRequiresSave` zurück.|  
|[CComControlBase::GetZoomInfo](../Topic/CComControlBase::GetZoomInfo.md)|Ruft die x und die y\-Werte des Zählers und des Nenners des Zoomfaktors für ein Steuerelement ab, das für die direkte Bearbeitung aktiviert ist.|  
|[CComControlBase::InPlaceActivate](../Topic/CComControlBase::InPlaceActivate.md)|Bewirkt das Steuerelement für den Übergang vom inaktiven Zustand zu, was Zustand das Verb in `iVerb` angibt.|  
|[CComControlBase::InternalGetSite](../Topic/CComControlBase::InternalGetSite.md)|Rufen Sie diese Methode auf, um die Steuerungssite für einen Zeiger auf die identifizierten Schnittstelle abzufragen.|  
|[CComControlBase::OnDraw](../Topic/CComControlBase::OnDraw.md)|Überschreiben Sie diese Methode, um das Steuerelement zu zeichnen.|  
|[CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)|Standard **OnDrawAdvanced**  bereitet einen normalisierten Gerätekontext zum Zeichnen vor, ruft `OnDraw`\-Methode der Steuerklasse auf.|  
|[CComControlBase::OnKillFocus](../Topic/CComControlBase::OnKillFocus.md)|Überprüft, ob das Steuerelement direkt aktiviert und gültigen Steuerungssite hat, dann informiert den Container, dass das Steuerelement den Fokus verloren hat.|  
|[CComControlBase::OnMouseActivate](../Topic/CComControlBase::OnMouseActivate.md)|Überprüft, ob das Benutzeroberfläche im Benutzermodus ist, dann kann das Steuerelement.|  
|[CComControlBase::OnPaint](../Topic/CComControlBase::OnPaint.md)|Bereitet den Container für das Zeichnen vor, ruft den Clientbereich des Steuerelements ab, ruft die `OnDraw`\-Methode der Steuerelementklasse auf.|  
|[CComControlBase::OnSetFocus](../Topic/CComControlBase::OnSetFocus.md)|Überprüft, ob das Steuerelement direkt aktiviert und gültigen Steuerungssite hat, dann informiert den Container, den das Steuerelement den Fokus erhalten hat.|  
|[CComControlBase::PreTranslateAccelerator](../Topic/CComControlBase::PreTranslateAccelerator.md)|Überschreiben Sie diese Methode, um eigene Zugriffstastenhandler bereitzustellen.|  
|[CComControlBase::SendOnClose](../Topic/CComControlBase::SendOnClose.md)|Benachrichtigt alle Advise\-Senken, die mit dem Advise\-Halter registriert werden, dass das Steuerelement geschlossen wurde.|  
|[CComControlBase::SendOnDataChange](../Topic/CComControlBase::SendOnDataChange.md)|Benachrichtigt alle Advise\-Senken, die mit dem Advise\-Halter registriert werden, dass die Steuerelementdaten geändert haben.|  
|[CComControlBase::SendOnRename](../Topic/CComControlBase::SendOnRename.md)|Benachrichtigt alle Advise\-Senken, die mit dem Advise\-Halter registriert werden, dass das Steuerelement einen neuen Moniker verfügt.|  
|[CComControlBase::SendOnSave](../Topic/CComControlBase::SendOnSave.md)|Benachrichtigt alle Advise\-Senken, die mit dem Advise\-Halter registriert werden, dass das Steuerelement gespeichert wurde.|  
|[CComControlBase::SendOnViewChange](../Topic/CComControlBase::SendOnViewChange.md)|Benachrichtigt alle registrierten Advise\-Senken, dass die Ansicht des Steuerelements geändert hat.|  
|[CComControlBase::SetControlFocus](../Topic/CComControlBase::SetControlFocus.md)|Setzt oder entfernt den Tastaturfokus in oder aus dem Steuerelement.|  
|[CComControlBase::SetDirty](../Topic/CComControlBase::SetDirty.md)|Legt den Datenmember `m_bRequiresSave` zum Wert in `bDirty` fest.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComControlBase::m\_bAutoSize](../Topic/CComControlBase::m_bAutoSize.md)|Das Flag, das das Steuerelement angibt, kann keine andere Größe aufweisen.|  
|[CComControlBase::m\_bDrawFromNatural](../Topic/CComControlBase::m_bDrawFromNatural.md)|Kennzeichnen Sie das Angeben von diesem `IDataObjectImpl::GetData` und `CComControlBase::GetZoomInfo` sollte die der Steuerelementgröße von `m_sizeNatural` statt von `m_sizeExtent` festlegen.|  
|[CComControlBase::m\_bDrawGetDataInHimetric](../Topic/CComControlBase::m_bDrawGetDataInHimetric.md)|Kennzeichnen Sie das Angeben von diesem `IDataObjectImpl::GetData` sollte HIMETRIC\-Einheiten und keine Pixel beim Zeichnen verwenden.|  
|[CComControlBase::m\_bInPlaceActive](../Topic/CComControlBase::m_bInPlaceActive.md)|Das Flag, das das Steuerelement angibt, kann direkt aktiviert.|  
|[CComControlBase::m\_bInPlaceSiteEx](../Topic/CComControlBase::m_bInPlaceSiteEx.md)|Das Flag, das den Container angibt, unterstützt die **IOleInPlaceSiteEx**\-Schnittstelle und \-steuerocx96 Funktionen, wie fensterlose und flimmerfreie Steuerelemente.|  
|[CComControlBase::m\_bNegotiatedWnd](../Topic/CComControlBase::m_bNegotiatedWnd.md)|Kennzeichnen Sie das angibt, ob das Steuerelement mit dem Container über die Features des Steuerelements OCX96 \(z flimmerfreie und fensterlose Steuerelemente\) ausgehandelt hat und ob das Steuerelement mit Fenster oder fensterlos ist.|  
|[CComControlBase::m\_bRecomposeOnResize](../Topic/CComControlBase::m_bRecomposeOnResize.md)|Das Flag, das das Steuerelement angibt, möchte seine Darstellung neu anordnen, wenn der Container die Anzeigengröße des Steuerelements ändert.|  
|[CComControlBase::m\_bRequiresSave](../Topic/CComControlBase::m_bRequiresSave.md)|Das Flag, das das Steuerelement angibt, wurde geändert, seit der zuletzt gespeichert wurde.|  
|[CComControlBase::m\_bResizeNatural](../Topic/CComControlBase::m_bResizeNatural.md)|Das Flag, das das Steuerelement angibt, möchte den natürlichen Wertebereich \(die unskalierte physische Größe\) Größe ändern wenn der Container die Anzeigengröße des Steuerelements ändert.|  
|[CComControlBase::m\_bUIActive](../Topic/CComControlBase::m_bUIActive.md)|Kennzeichnen Sie das Angeben der Benutzeroberfläche des Steuerelements, wie Menüs und Symbolleisten, ist aktiv.|  
|[CComControlBase::m\_bUsingWindowRgn](../Topic/CComControlBase::m_bUsingWindowRgn.md)|Das Flag, das das Steuerelement angibt, verwendet den Container\-angegebenen Fensterbereich.|  
|[CComControlBase::m\_bWasOnceWindowless](../Topic/CComControlBase::m_bWasOnceWindowless.md)|Das Flag, das angibt, welches Steuerelement betraf fensterlos, ist jedoch möglicherweise jetzt fensterlos.|  
|[CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md)|Das Flag, das das Steuerelement angibt, sollte mit Fenster sein, wenn der Container fensterlose Steuerelemente unterstützt.|  
|[CComControlBase::m\_bWndLess](../Topic/CComControlBase::m_bWndLess.md)|Das Flag, das das Steuerelement angibt, ist fensterlos.|  
|[CComControlBase::m\_hWndCD](../Topic/CComControlBase::m_hWndCD.md)|Enthält einen Verweis auf das Fensterhandle, das dem Steuerelement zugeordnet ist.|  
|[CComControlBase::m\_nFreezeEvents](../Topic/CComControlBase::m_nFreezeEvents.md)|Eine Anzahl der Häufigkeit der Container hat die Ereignisse \(abgelehnt, Ereignisse zu akzeptieren\) ohne ein dazwischenliegendes Tauwetter von Ereignissen \(Übernahme von Ereignissen\) fixiert.|  
|[CComControlBase::m\_rcPos](../Topic/CComControlBase::m_rcPos.md)|Die Position in Pixel des Steuerelements, ausgedrückt in den Koordinaten des Containers.|  
|[CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md)|Der Umfang eines Steuerelements in den HIMETRIC\-Einheiten \(jede Einheit ist 0,01 mm\), für eine bestimmte Anzeige.|  
|[CComControlBase::m\_sizeNatural](../Topic/CComControlBase::m_sizeNatural.md)|Die physische Größe des Steuerelements in der HIMETRIC\-Einheiten \(jede Einheit ist 0,01 mm\).|  
|[CComControlBase::m\_spAdviseSink](../Topic/CComControlBase::m_spAdviseSink.md)|Ein direkten Zeiger zur Advise\-Verbindung im Container \( [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) des Containers\).|  
|[CComControlBase::m\_spAmbientDispatch](../Topic/CComControlBase::m_spAmbientDispatch.md)|Ein `CComDispatchDriver`\-Objekt, das Sie die Eigenschaften des Containers durch einen Zeiger `IDispatch` abrufen und festlegen können.|  
|[CComControlBase::m\_spClientSite](../Topic/CComControlBase::m_spClientSite.md)|Ein Zeiger auf die Clientsite des Steuerelements innerhalb des Containers.|  
|[CComControlBase::m\_spDataAdviseHolder](../Topic/CComControlBase::m_spDataAdviseHolder.md)|Stellt ein Mittel eines Standards bereit, um Advise\-Verbindungen zwischen Datenobjekten und Advise\-Senken aufzunehmen.|  
|[CComControlBase::m\_spInPlaceSite](../Topic/CComControlBase::m_spInPlaceSite.md)|Ein Zeiger auf [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461) oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)\-Schnittstellenzeiger des Containers.|  
|[CComControlBase::m\_spOleAdviseHolder](../Topic/CComControlBase::m_spOleAdviseHolder.md)|Stellt eine Standardimplementierung einer Methode, Advise\-Verbindungen anzuhalten bereit.|  
  
## Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL\-Steuerelementen bereit.  [CComControl\-Klasse](../../atl/reference/ccomcontrol-class.md) wird von abgeleitet `CComControlBase`.  Wenn Sie ein Standardsteuerelement oder DHTML\-Steuerelement mit dem ATL\-Steuerelement\-Assistenten erstellen, berechnet der Assistent automatisch die Klasse von `CComControlBase`.  
  
 Weitere Informationen zum Erstellen eines Steuerelements, finden Sie unter [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).  Weitere Informationen zu den ATL\-Projekt\-Assistenten, finden Sie im Artikel [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
## Anforderungen  
 **Header:** atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)