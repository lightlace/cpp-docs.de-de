---
title: -Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
dev_langs:
- C++
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6109bfaf29ee26053bc1dcbb5af8f56a0612215
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcontrolbase-class"></a>-Klasse
Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](#appearancetype)|Überschreiben, wenn Ihre `m_nAppearance` Systemeigenschaft ist nicht vom Typ `short`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](#ccomcontrolbase)|Der Konstruktor.|  
|[CComControlBase:: ~ CComControlBase](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Überprüft, ob die `iVerb` vom verwendeter Parameter `IOleObjectImpl::DoVerb` entweder aktiviert das Steuerelement-Benutzeroberfläche ( `iVerb` gleich `OLEIVERB_UIACTIVATE`), definiert die Aktion ausgeführt, wenn der Benutzer das Steuerelement doppelklickt ( `iVerb` gleich `OLEIVERB_PRIMARY`), zeigt das Steuerelement ( `iVerb` gleich `OLEIVERB_SHOW`), oder das Steuerelement aktiviert ( `iVerb` gleich **OLEIVERB_INPLACEACTIVATE**).|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Überprüft, ob die `iVerb` vom verwendeter Parameter `IOleObjectImpl::DoVerb` bewirkt, dass das Steuerelement-Benutzeroberfläche zu aktivieren, und gibt **"true"**.|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|Zeigt die Eigenschaftenseiten für das Steuerelement.|  
|[CComControlBase::FireViewChange](#fireviewchange)|Rufen Sie diese Methode zum Erkennen des Containers kann das Steuerelement neu gezeichnet werden, oder benachrichtigen Sie die registrierten Advise-senken, die Ansicht des Steuerelements geändert wurde.|  
|[CComControlBase](#getambientappearance)|Ruft ab **DISPID_AMBIENT_APPEARANCE**, die aktuelle Darstellung, die für das Steuerelement festlegen: 0 für flache und 1 für 3D.|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Ruft ab **DISPID_AMBIENT_AUTOCLIP**und ein Kennzeichen, das angibt, ob der Container automatische Clipping bei den Anzeigebereich des Steuerelements unterstützt.|  
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Ruft ab **DISPID_AMBIENT_BACKCOLOR**, die Ambiente-Hintergrundfarbe für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Ruft ab **DISPID_AMBIENT_CHARSET**, die ambient-Zeichensatz für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Ruft ab **DISPID_AMBIENT_CODEPAGE**, die ambient-Zeichensatz für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase:: GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Ruft ab **DISPID_AMBIENT_DISPLAYASDEFAULT**, ein Flag, das **"true"** Wenn der Container das Steuerelement an diesem Standort zu einer Standardschaltfläche markiert wurde, und daher ein Schaltflächen-Steuerelement sollte zeichnen sich selbst bei einem Dicker Frame.|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Ruft ab **DISPID_AMBIENT_DISPLAYNAME**, den Namen der Container für das Steuerelement angegeben hat.|  
|[CComControlBase::GetAmbientFont](#getambientfont)|Ruft ein Zeiger auf den Container des ambient `IFont` Schnittstelle.|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Ruft ein Zeiger auf den Container des ambient **IFontDisp** Dispatch-Schnittstelle.|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Ruft ab **DISPID_AMBIENT_FORECOLOR**, die Ambiente-Farbe für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Ruft ab **DISPID_AMBIENT_LOCALEID**, den Bezeichner der vom Container verwendeten Sprache.|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Ruft ab **DISPID_AMBIENT_MESSAGEREFLECT**, ein Flag, der angibt, ob der Container fenstermeldungen empfangen will (z. B. `WM_DRAWITEM`) als Ereignisse.|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Ruft ab **DISPID_AMBIENT_PALETTE**, mit denen Zugriff auf den Container `HPALETTE`.|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Ruft die Containereigenschaft, die vom angegebenen `id`.|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|Ruft ab **DISPID_AMBIENT_RIGHTTOLEFT**, der die Richtung, in dem Inhalte vom Container angezeigt wird.|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Ruft ab **DISPID_AMBIENT_SCALEUNITS**, des Containers ambient Einheiten (z. B. Zoll oder Zentimeter) für die Bezeichnung angezeigt.|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Ruft ab **DISPID_AMBIENT_SHOWGRABHANDLES**und ein Kennzeichen, das angibt, ob der Container die im Steuerelement anzuzeigende Ziehpunkte für sich selbst bei Aktivierung kann.|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Ruft ab **DISPID_AMBIENT_SHOWHATCHING**und ein Kennzeichen, das angibt, ob der Container kann das Steuerelement selbst mit einer Schraffur angezeigt, wenn der UI aktiv ist.|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Ruft ab **DISPID_AMBIENT_SUPPORTSMNEMONICS**und ein Kennzeichen, das angibt, ob der Container mnemonisches unterstützt.|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Ruft ab **DISPID_AMBIENT_TEXTALIGN**, die vom Container bevorzugte Ausrichtung des Texts: 0 für die allgemeine Ausrichtung (Zahlen, Text rechts nach links), 1 für die linksbündige Ausrichtung, 2 für zentrieren und 3 für rechtsbündige Ausrichtung.|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|Ruft ab **DISPID_AMBIENT_TOPTOBOTTOM**, der die Richtung, in dem Inhalte vom Container angezeigt wird.|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Ruft ab **DISPID_AMBIENT_UIDEAD**und ein Kennzeichen, das angibt, ob der Container das Steuerelement auf der Benutzeroberfläche Aktionen reagieren möchte.|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Ruft ab **DISPID_AMBIENT_USERMODE**und ein Kennzeichen, das angibt, ob der Container im Ausführungsmodus befindet ( **"true"**) oder Entwurfsmodus ( **"false"**).|  
|[CComControlBase::GetDirty](#getdirty)|Gibt den Wert der Datenmember `m_bRequiresSave`.|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|Ruft ab, der x- und y-Achse Werte der Zähler und Nenner, der den Zoomfaktor für ein Steuerelement für aktiviert direktes Bearbeiten.|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|Bewirkt den Übergang des Steuerelements aus dem inaktiven Zustand in den gewünschten das Verb im Status `iVerb` angibt.|  
|[CComControlBase::InternalGetSite](#internalgetsite)|Rufen Sie diese Methode, um die Website des Steuerelements für einen Zeiger auf die angegebene Schnittstelle abzufragen.|  
|[CComControlBase:: OnDraw](#ondraw)|Überschreiben Sie diese Methode, um das Steuerelement gezeichnet werden soll.|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Die Standardeinstellung **OnDrawAdvanced** bereitet einen normalisierten Gerätekontext für das Zeichnen, dann ruft der Steuerelementklasse `OnDraw` Methode.|  
|[CComControlBase::OnKillFocus](#onkillfocus)|Überprüft, dass das Steuerelement in-Place aktiv ist und verfügt über eine gültige Steuerelementsite und informiert dem Container, dass das Steuerelement den Fokus verloren hat.|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Überprüft, dass die Benutzeroberfläche im Benutzermodus ist, und das Steuerelement aktiviert.|  
|[CComControlBase::OnPaint](#onpaint)|Bereitet den Container für das Pixelbild, ruft Clientbereich des Steuerelements ab und ruft dann die Steuerelementklasse `OnDraw` Methode.|  
|[CComControlBase::OnSetFocus](#onsetfocus)|Überprüft, dass das Steuerelement in-Place aktiv ist und verfügt über eine gültige Steuerelementsite und das Container das Steuerelement informiert den Fokus gewonnen hat.|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Überschreiben Sie diese Methode, um eine eigene Tastatur Accelerator Handler bereitstellen.|  
|[CComControlBase::SendOnClose](#sendonclose)|Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, dass das Steuerelement geschlossen wurde.|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, den die Steuerelementdaten geändert wurde.|  
|[CComControlBase::SendOnRename](#sendonrename)|Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, dass das Steuerelement einen neuen Moniker verfügt.|  
|[CComControlBase::SendOnSave](#sendonsave)|Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, den das Steuerelement gespeichert wurde.|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Benachrichtigt, dass alle registrierten Advise-Senken, die Ansicht des Steuerelements geändert wurde.|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Legt fest, oder den Tastaturfokus zu oder aus dem Steuerelement entfernt.|  
|[CComControlBase::SetDirty](#setdirty)|Legt den Datenmember `m_bRequiresSave` auf den Wert in `bDirty`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|Ein Flag, der angibt, das Steuerelement kann eine beliebige andere Größe sein.|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Flag zeigt an, dass `IDataObjectImpl::GetData` und `CComControlBase::GetZoomInfo` fest, dass die Steuerelementgröße auf `m_sizeNatural` anstatt von `m_sizeExtent`.|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Gibt an, dass Flag `IDataObjectImpl::GetData` die zu verwendende HIMETRIC-Einheiten und nicht Pixel beim Zeichnen.|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Ein Flag, der angibt, dass das Steuerelement in-Place aktiv ist.|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Ein Flag, der angibt, die Container unterstützt die **IOleInPlaceSiteEx** Schnittstelle und OCX96 steuern Sie Features, wie z. B. fensterlose und flimmerfreier Steuerelemente.|  
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Ein Flag, der angibt, und zwar unabhängig davon, ob das Steuerelement mit dem Container zur Unterstützung von Funktionen (z. B. flimmerfreier und Fensterlose Steuerelemente) OCX96 ausgehandelt wurde, und gibt an, ob das Steuerelement im Fenstermodus oder fensterlose ist.|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Ein Flag, der angibt, dass möchte, dass das Steuerelement seine Darstellung neu aufzubauen, wenn der Container die Größe der Anzeige des Steuerelements ändert.|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Ein Flag zeigt an, dass das Steuerelement geändert hat, seit es zuletzt gespeichert wurde.|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Kennzeichnung des Steuerelements sein natürliche Wertebereich (seiner nicht skalierten physischen Größe) ändern möchte, wenn der Container des Steuerelements Anzeigegröße ändert.|  
|[CComControlBase::m_bUIActive](#m_buiactive)|Flag, das das Steuerelement-Benutzeroberfläche, z. B. Menüs und Symbolleisten, die angibt, ist aktiv.|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Ein Flag, der angibt, dass das Steuerelement den Container bereitgestellte Fensterbereich verwendet.|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Ein Flag, der angibt, das Steuerelement fensterlose, wurde jedoch möglicherweise nicht oder nicht komplett fensterlose jetzt.|  
|[CComControlBase](#m_bwindowonly)|Ein Flag zeigt an, dass das Steuerelement Fensterfunktionen, sein sollte, auch wenn der Container Fensterlose Steuerelemente unterstützt.|  
|[CComControlBase::m_bWndLess](#m_bwndless)|Ein Flag, der angibt, dass das Steuerelement fensterlose ist.|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|Enthält einen Verweis auf das Fensterhandle des Steuerelements zugeordnet.|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Die Anzahl, wie oft der Container hat Ereignisse (Ereignisse akzeptieren verweigert) ohne einen zwischenzeitlichen Entsperren von Ereignissen (akzeptieren von Ereignissen) fixiert.|  
|[CComControlBase::m_rcPos](#m_rcpos)|Die Position in Pixel des Steuerelements, ausgedrückt in die Koordinaten des Containers.|  
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Das Ausmaß des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter) für eine bestimmte Darstellung.|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|Die physische Größe des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter).|  
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Direkten Zeiger auf die Advise-Verbindung für den Container (des Containers [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Ein `CComDispatchDriver` Objekt, mit dem Sie abrufen und Festlegen von Containereigenschaften über eine `IDispatch` Zeiger.|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|Ein Zeiger auf das Steuerelement Clientstandort innerhalb des Containers.|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Stellt ein Standard bedeutet, dass für die bereitzustellenden Advise-Verbindungen zwischen Datenobjekte advise-Empfänger bereit.|  
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Ein Zeiger auf des Containers [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) Schnittstellenzeiger auf.|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Stellt eine Standardimplementierung von eine Möglichkeit, Advise-Verbindungen aufzunehmen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen. [CComControl Klasse](../../atl/reference/ccomcontrol-class.md) leitet sich von `CComControlBase`. Wenn Sie über ein Standardsteuerelement oder DHTML-Steuerelement, mit der ATL-Steuerelement-Assistenten erstellen, leiten der Assistent automatisch eine Klasse von `CComControlBase`.  
  
 Weitere Informationen zum Erstellen eines Steuerelements finden Sie unter der [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="appearancetype"></a>CComControlBase::AppearanceType  
 Überschreiben, wenn Ihre **M_nAppearance** Systemeigenschaft ist nicht vom Typ **kurze**.  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>Hinweise  
 ATL-Steuerelement-Assistent fügt **M_nAppearance** SKU-Eigenschaft vom Typ short. Überschreiben Sie `AppearanceType` , wenn Sie einen anderen Datentyp verwenden.  
  
##  <a name="ccomcontrolbase"></a>CComControlBase::CComControlBase  
 Der Konstruktor.  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 Das Handle für das Fenster, das dem Steuerelement zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die Größe des Steuerelements zu 5080 X 5080 HIMETRIC-Einheiten (2 "X 2") und initialisiert die `CComControlBase` Datenmember Werte **NULL** oder **"false"**.  
  
##  <a name="dtor"></a>CComControlBase:: ~ CComControlBase  
 Der Destruktor.  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement im Fenstermodus, `~CComControlBase` zerstört er durch den Aufruf [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682).  
  
##  <a name="controlqueryinterface"></a>CComControlBase::ControlQueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 Die GUID der Schnittstelle angefordert wird.  
  
 `ppv`  
 Ein Zeiger auf den Schnittstellenzeiger, der durch `iid`, oder **NULL** , wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Nur behandelt Schnittstellen in der COM-Zuordnungstabelle.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate  
 Überprüft, ob die `iVerb` vom verwendeter Parameter `IOleObjectImpl::DoVerb` entweder aktiviert das Steuerelement-Benutzeroberfläche ( `iVerb` gleich `OLEIVERB_UIACTIVATE`), definiert die Aktion ausgeführt, wenn der Benutzer das Steuerelement doppelklickt ( `iVerb` gleich `OLEIVERB_PRIMARY`), zeigt das Steuerelement ( `iVerb` gleich `OLEIVERB_SHOW`), oder das Steuerelement aktiviert ( `iVerb` gleich **OLEIVERB_INPLACEACTIVATE**).  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Wert, der angibt, die Aktion, die von `DoVerb`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn `iVerb` gleich `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, oder **OLEIVERB_INPLACEACTIVATE**ist, andernfalls gibt **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um eine eigene Aktivierung Verb definieren überschreiben.  
  
##  <a name="doesverbuiactivate"></a>CComControlBase::DoesVerbUIActivate  
 Überprüft, ob die `iVerb` vom verwendeter Parameter `IOleObjectImpl::DoVerb` bewirkt, dass das Steuerelement-Benutzeroberfläche zu aktivieren, und gibt **"true"**.  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Wert, der angibt, die Aktion, die von `DoVerb`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn `iVerb` gleich `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, oder **OLEIVERB_INPLACEACTIVATE**. Andernfalls der Methodenrückgabe **"false"**.  
  
##  <a name="doverbproperties"></a>CComControlBase::DoVerbProperties  
 Zeigt die Eigenschaftenseiten für das Steuerelement.  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 Reserviert.  
  
 *hwndParent*  
 Das Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>CComControlBase::FireViewChange  
 Rufen Sie diese Methode zum Erkennen des Containers kann das Steuerelement neu gezeichnet werden, oder benachrichtigen Sie die registrierten Advise-senken, die Ansicht des Steuerelements geändert wurde.  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement aktiv ist (die Steuerelement-Klassendatenmember [CComControlBase::m_bInPlaceActive](#m_binplaceactive) ist **"true"**), benachrichtigt dem Container, dass das gesamte Steuerelement neu gezeichnet werden soll. Wenn das Steuerelement aktiv ist, wird darauf hingewiesen, das Steuerelement des registriert advise-Empfänger (über die Control-Klassendatenmember [CComControlBase::m_spAdviseSink](#m_spadvisesink)), die Ansicht des Steuerelements geändert wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>CComControlBase  
 Ruft ab **DISPID_AMBIENT_APPEARANCE**, die aktuelle Darstellung, die für das Steuerelement festlegen: 0 für flache und 1 für 3D.  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>Parameter  
 `nAppearance`  
 Die Eigenschaft **DISPID_AMBIENT_APPEARANCE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip  
 Ruft ab **DISPID_AMBIENT_AUTOCLIP**und ein Kennzeichen, das angibt, ob der Container automatische Clipping bei den Anzeigebereich des Steuerelements unterstützt.  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>Parameter  
 *bAutoClip*  
 Die Eigenschaft **DISPID_AMBIENT_AUTOCLIP**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientbackcolor"></a>CComControlBase::GetAmbientBackColor  
 Ruft ab **DISPID_AMBIENT_BACKCOLOR**, die Ambiente-Hintergrundfarbe für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>Parameter  
 *Hintergrundfarbe*  
 Die Eigenschaft **DISPID_AMBIENT_BACKCOLOR**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientcharset"></a>CComControlBase::GetAmbientCharSet  
 Ruft ab **DISPID_AMBIENT_CHARSET**, die ambient-Zeichensatz für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrCharSet*  
 Die Eigenschaft **DISPID_AMBIENT_CHARSET**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage  
 Ruft ab **DISPID_AMBIENT_CODEPAGE**, die ambient-Codepage für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>Parameter  
 *ulCodePage*  
 Die Eigenschaft **DISPID_AMBIENT_CODEPAGE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientdisplayasdefault"></a>CComControlBase:: GetAmbientDisplayAsDefault  
 Ruft ab **DISPID_AMBIENT_DISPLAYASDEFAULT**, ein Flag, das **"true"** Wenn der Container das Steuerelement an diesem Standort zu einer Standardschaltfläche markiert wurde, und daher ein Schaltflächen-Steuerelement sollte zeichnen sich selbst bei einem Dicker Frame.  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `bDisplayAsDefault`  
 Die Eigenschaft **DISPID_AMBIENT_DISPLAYASDEFAULT**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientdisplayname"></a>CComControlBase::GetAmbientDisplayName  
 Ruft ab **DISPID_AMBIENT_DISPLAYNAME**, den Namen der Container für das Steuerelement angegeben hat.  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrDisplayName*  
 Die Eigenschaft **DISPID_AMBIENT_DISPLAYNAME**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientfont"></a>CComControlBase::GetAmbientFont  
 Ruft ein Zeiger auf den Container des ambient `IFont` Schnittstelle.  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>Parameter  
 `ppFont`  
 Ein Zeiger auf den Container des ambient [IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673) Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft **NULL**, wird der Zeiger **NULL**. Wenn der Zeiger nicht **NULL**, der Aufrufer muss die Zeiger freizugeben.  
  
##  <a name="getambientfontdisp"></a>CComControlBase::GetAmbientFontDisp  
 Ruft ein Zeiger auf den Container des ambient **IFontDisp** Dispatch-Schnittstelle.  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>Parameter  
 `ppFont`  
 Ein Zeiger auf den Container des ambient [IFontDisp](http://msdn.microsoft.com/library/windows/desktop/ms692695) Dispatch-Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft **NULL**, wird der Zeiger **NULL**. Wenn der Zeiger nicht **NULL**, der Aufrufer muss die Zeiger freizugeben.  
  
##  <a name="getambientforecolor"></a>CComControlBase::GetAmbientForeColor  
 Ruft ab **DISPID_AMBIENT_FORECOLOR**, die Ambiente-Farbe für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>Parameter  
 *Vordergrundfarbe*  
 Die Eigenschaft **DISPID_AMBIENT_FORECOLOR**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientlocaleid"></a>CComControlBase::GetAmbientLocaleID  
 Ruft ab **DISPID_AMBIENT_LOCALEID**, den Bezeichner der vom Container verwendeten Sprache.  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>Parameter  
 `lcid`  
 Die Eigenschaft **DISPID_AMBIENT_LOCALEID**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement kann diesen Bezeichner verwenden, seine Benutzeroberfläche für unterschiedliche Sprachen angepasst werden kann.  
  
##  <a name="getambientmessagereflect"></a>CComControlBase::GetAmbientMessageReflect  
 Ruft ab **DISPID_AMBIENT_MESSAGEREFLECT**, ein Flag, der angibt, ob der Container fenstermeldungen empfangen will (z. B. `WM_DRAWITEM`) als Ereignisse.  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>Parameter  
 `bMessageReflect`  
 Die Eigenschaft **DISPID_AMBIENT_MESSAGEREFLECT**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientpalette"></a>CComControlBase::GetAmbientPalette  
 Ruft ab **DISPID_AMBIENT_PALETTE**, mit denen Zugriff auf den Container `HPALETTE`.  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `hPalette`  
 Die Eigenschaft **DISPID_AMBIENT_PALETTE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientproperty"></a>CComControlBase::GetAmbientProperty  
 Ruft die Containereigenschaft, die vom angegebenen `dispid`.  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Der Bezeichner für die Containereigenschaft abgerufen werden sollen.  
  
 `var`  
 Die Variable zum Empfangen von der Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 ATL stellt eine Reihe von Hilfsfunktionen zum Abrufen von Eigenschaften, z. B. [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Wenn keine geeignete Methode verfügbar ist, verwenden Sie `GetAmbientProperty`.  
  
##  <a name="getambientrighttoleft"></a>CComControlBase::GetAmbientRightToLeft  
 Ruft ab **DISPID_AMBIENT_RIGHTTOLEFT**, der die Richtung, in dem Inhalte vom Container angezeigt wird.  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>Parameter  
 *bRightToLeft*  
 Die Eigenschaft **DISPID_AMBIENT_RIGHTTOLEFT**. Legen Sie auf **"true"** Wenn Inhalt, von rechts nach links angezeigt wird, **"false"** falls er links nach rechts angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientscaleunits"></a>CComControlBase::GetAmbientScaleUnits  
 Ruft ab **DISPID_AMBIENT_SCALEUNITS**, des Containers ambient Einheiten (z. B. Zoll oder Zentimeter) für die Bezeichnung angezeigt.  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrScaleUnits*  
 Die Eigenschaft **DISPID_AMBIENT_SCALEUNITS**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientshowgrabhandles"></a>CComControlBase::GetAmbientShowGrabHandles  
 Ruft ab **DISPID_AMBIENT_SHOWGRABHANDLES**und ein Kennzeichen, das angibt, ob der Container die im Steuerelement anzuzeigende Ziehpunkte für sich selbst bei Aktivierung kann.  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>Parameter  
 *bShowGrabHandles*  
 Die Eigenschaft **DISPID_AMBIENT_SHOWGRABHANDLES**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientshowhatching"></a>CComControlBase::GetAmbientShowHatching  
 Ruft ab **DISPID_AMBIENT_SHOWHATCHING**und ein Kennzeichen, das angibt, ob der Container kann das Steuerelement selbst mit einer Schraffur angezeigt, wenn das Steuerelement-Benutzeroberfläche aktiv ist.  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>Parameter  
 *bShowHatching*  
 Die Eigenschaft **DISPID_AMBIENT_SHOWHATCHING**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMnemonics  
 Ruft ab **DISPID_AMBIENT_SUPPORTSMNEMONICS**und ein Kennzeichen, das angibt, ob der Container mnemonisches unterstützt.  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>Parameter  
 *bSupportsMnemonics*  
 Die Eigenschaft **DISPID_AMBIENT_SUPPORTSMNEMONICS**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambienttextalign"></a>CComControlBase::GetAmbientTextAlign  
 Ruft ab **DISPID_AMBIENT_TEXTALIGN**, die vom Container bevorzugte Ausrichtung des Texts: 0 für die allgemeine Ausrichtung (Zahlen, Text rechts nach links), 1 für die linksbündige Ausrichtung, 2 für zentrieren und 3 für rechtsbündige Ausrichtung.  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>Parameter  
 *nTextAlign*  
 Die Eigenschaft **DISPID_AMBIENT_TEXTALIGN**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getambienttoptobottom"></a>CComControlBase::GetAmbientTopToBottom  
 Ruft ab **DISPID_AMBIENT_TOPTOBOTTOM**, der die Richtung, in dem Inhalte vom Container angezeigt wird.  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>Parameter  
 *bTopToBottom*  
 Die Eigenschaft **DISPID_AMBIENT_TOPTOBOTTOM**. Legen Sie auf **"true"** Wenn Text angezeigt wird, oben nach unten, **"false"** falls er angezeigt wird von unten nach oben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientuidead"></a>CComControlBase::GetAmbientUIDead  
 Ruft ab **DISPID_AMBIENT_UIDEAD**und ein Kennzeichen, das angibt, ob der Container das Steuerelement auf der Benutzeroberfläche Aktionen reagieren möchte.  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>Parameter  
 *bUIDead*  
 Die Eigenschaft **DISPID_AMBIENT_UIDEAD**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn **"true"**, das Steuerelement nicht reagieren soll. Dieses Flag gilt unabhängig von der **DISPID_AMBIENT_USERMODE** Flag. Finden Sie unter [CComControlBase::GetAmbientUserMode](#getambientusermode).  
  
##  <a name="getambientusermode"></a>CComControlBase::GetAmbientUserMode  
 Ruft ab **DISPID_AMBIENT_USERMODE**und ein Kennzeichen, das angibt, ob der Container im Ausführungsmodus befindet ( **"true"**) oder Entwurfsmodus ( **"false"**).  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>Parameter  
 `bUserMode`  
 Die Eigenschaft **DISPID_AMBIENT_USERMODE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="getdirty"></a>CComControlBase::GetDirty  
 Gibt den Wert der Datenmember `m_bRequiresSave`.  
  
```
BOOL GetDirty();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der Datenmember [M_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird festgelegt, mit [CComControlBase::SetDirty](#setdirty).  
  
##  <a name="getzoominfo"></a>CComControlBase::GetZoomInfo  
 Ruft ab, der x- und y-Achse Werte der Zähler und Nenner, der den Zoomfaktor für ein Steuerelement für aktiviert direktes Bearbeiten.  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parameter  
 `di`  
 Die Struktur, die des Zoomfaktor Zähler und Nenner enthalten soll. Weitere Informationen finden Sie unter [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).  
  
### <a name="remarks"></a>Hinweise  
 Der Zoomfaktor wird der Anteil des Steuerelements natürliche Größe auf seine aktuellen Block.  
  
##  <a name="inplaceactivate"></a>CComControlBase::InPlaceActivate  
 Bewirkt den Übergang des Steuerelements aus dem inaktiven Zustand in den gewünschten das Verb im Status `iVerb` angibt.  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Wert, der angibt, die Aktion, die von [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).  
  
 *prcPosRect*  
 Ein Zeiger auf die Position des direkten-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Vor der Aktivierung diese Methode überprüft, ob das Steuerelement verfügt über eine Client-Website, überprüft, wie viel des Steuerelements sichtbar ist, und ruft die Position des Steuerelements in das übergeordnete Fenster. Nachdem das Steuerelement aktiviert ist, wird diese Methode aktiviert das Steuerelement-Benutzeroberfläche und weist den Container aus, um das Steuerelement sichtbar zu machen.  
  
 Diese Methode ruft auch ab einem `IOleInPlaceSite`, **IOleInPlaceSiteEx**, oder **IOleInPlaceSiteWindowless** Schnittstellenzeiger für das Steuerelement und speichert ihn in der Steuerelementklasse Datenmember [CComControlBase::m_spInPlaceSite](#m_spinplacesite). Die Steuerelement-Klassendatenmember [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless), und [ CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) auf "true" entsprechend festgelegt werden.  
  
##  <a name="internalgetsite"></a>CComControlBase::InternalGetSite  
 Rufen Sie diese Methode, um die Website des Steuerelements für einen Zeiger auf die angegebene Schnittstelle abzufragen.  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>Parameter  
 `riid`  
 Die IID des Schnittstellenzeigers, die zurückgegeben werden sollen `ppUnkSite`.  
  
 `ppUnkSite`  
 Adresse der Zeigervariablen, die den Schnittstellenzeiger in angeforderte empfängt `riid`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Standort auf die angeforderte Schnittstelle unterstützt `riid`, die Zeiger zurückgegeben wird, mithilfe von `ppUnkSite`. Andernfalls `ppUnkSite` auf NULL festgelegt ist.  
  
##  <a name="m_bautosize"></a>CComControlBase::m_bAutoSize  
 Ein Flag, der angibt, das Steuerelement kann eine beliebige andere Größe sein.  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag aktiviert ist, indem `IOleObjectImpl::SetExtent` und **"true"**, bewirkt, dass die Funktion zurückgibt **E_FAIL**.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Wenn Sie beim Hinzufügen der **Automatische Größe der** option die [Basiseigenschaften](../../atl/reference/stock-properties-atl-control-wizard.md) der ATL-Steuerelement-Assistent, den Assistenten auf der Registerkarte dieses Datenelement in der Steuerelementklasse erstellt, erstellt automatisch PUT- und get-Methoden für die Eigenschaft , und unterstützt [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Container automatisch zu benachrichtigen, wenn die Eigenschaft ändert.  
  
##  <a name="m_bdrawfromnatural"></a>CComControlBase::m_bDrawFromNatural  
 Flag zeigt an, dass `IDataObjectImpl::GetData` und `CComControlBase::GetZoomInfo` fest, dass die Steuerelementgröße auf `m_sizeNatural` anstatt von `m_sizeExtent`.  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric  
 Gibt an, dass Flag `IDataObjectImpl::GetData` die zu verwendende HIMETRIC-Einheiten und nicht Pixel beim Zeichnen.  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Jeder logischen Einheit der HIMETRIC ist 0,01 Millimeter.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_binplaceactive"></a>CComControlBase::m_bInPlaceActive  
 Ein Flag, der angibt, dass das Steuerelement in-Place aktiv ist.  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Dies bedeutet, dass das Steuerelement sichtbar ist und das Fenster, sofern vorhanden, sichtbar ist, ist aber seine Menüs und Symbolleisten nicht aktiv sein. Die `m_bUIActive` Flag gibt an, das Steuerelement-Benutzeroberfläche, z. B. Menüs, auch aktiv ist.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_binplacesiteex"></a>CComControlBase::m_bInPlaceSiteEx  
 Ein Flag, der angibt, die Container unterstützt die **IOleInPlaceSiteEx** Schnittstelle und OCX96 steuern Sie Features, wie z. B. fensterlose und flimmerfreier Steuerelemente.  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Das Datenelement `m_spInPlaceSite` verweist auf eine [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) -Schnittstelle, abhängig vom Wert der `m_bWndLess` und `m_bInPlaceSiteEx` Flags. (Das Datenelement `m_bNegotiatedWnd` muss **"true"** für die `m_spInPlaceSite` Zeiger gültig ist.)  
  
 Wenn `m_bWndLess` ist **"false"** und `m_bInPlaceSiteEx` ist **"true"**, `m_spInPlaceSite` ist ein **IOleInPlaceSiteEx** Schnittstellenzeiger auf. Finden Sie unter [M_spInPlaceSite](#m_spinplacesite) für eine Tabelle mit den Beziehungen zwischen diesen drei Datenmember.  
  
##  <a name="m_bnegotiatedwnd"></a>CComControlBase::m_bNegotiatedWnd  
 Ein Flag, der angibt, und zwar unabhängig davon, ob das Steuerelement mit dem Container zur Unterstützung von Funktionen (z. B. flimmerfreier und Fensterlose Steuerelemente) OCX96 ausgehandelt wurde, und gibt an, ob das Steuerelement im Fenstermodus oder fensterlose ist.  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Die `m_bNegotiatedWnd` Flag muss **"true"** für die `m_spInPlaceSite` Zeiger gültig ist.  
  
##  <a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize  
 Ein Flag, der angibt, dass möchte, dass das Steuerelement seine Darstellung neu aufzubauen, wenn der Container die Größe der Anzeige des Steuerelements ändert.  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Dieses Flag aktiviert ist, indem [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) und **"true"**, `SetExtent` benachrichtigt den Container der Änderungen an. Wenn dieses Flag festgelegt ist, die **OLEMISC_RECOMPOSEONRESIZE** bit in der [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Enumeration sollte auch festgelegt werden.  
  
##  <a name="m_brequiressave"></a>CComControlBase::m_bRequiresSave  
 Ein Flag zeigt an, dass das Steuerelement geändert hat, seit es zuletzt gespeichert wurde.  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der `m_bRequiresSave` kann festgelegt werden, mit [CComControlBase::SetDirty](#setdirty) und mit abgerufene [CComControlBase::GetDirty](#getdirty).  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural  
 Kennzeichnung des Steuerelements sein natürliche Wertebereich (seiner nicht skalierten physischen Größe) ändern möchte, wenn der Container des Steuerelements Anzeigegröße ändert.  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag aktiviert ist, indem `IOleObjectImpl::SetExtent` und, falls **"true"**, übergeben Sie die Größe in `SetExtent` zugewiesen `m_sizeNatural`.  
  
 Übergeben Sie die Größe in `SetExtent` ist immer zugewiesen `m_sizeExtent`, unabhängig von den Wert des `m_bResizeNatural`.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_buiactive"></a>CComControlBase::m_bUIActive  
 Flag, das das Steuerelement-Benutzeroberfläche, z. B. Menüs und Symbolleisten, die angibt, ist aktiv.  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_bInPlaceActive` Flag gibt an, dass das Steuerelement aktiv ist, aber nicht seine Benutzeroberfläche aktiv ist.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn  
 Ein Flag, der angibt, dass das Steuerelement den Container bereitgestellte Fensterbereich verwendet.  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless  
 Ein Flag, der angibt, das Steuerelement fensterlose, wurde jedoch möglicherweise nicht oder nicht komplett fensterlose jetzt.  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bwindowonly"></a>CComControlBase  
 Ein Flag zeigt an, dass das Steuerelement Fensterfunktionen, sein sollte, auch wenn der Container Fensterlose Steuerelemente unterstützt.  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bwndless"></a>CComControlBase::m_bWndLess  
 Ein Flag, der angibt, dass das Steuerelement fensterlose ist.  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Das Datenelement `m_spInPlaceSite` verweist auf eine [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) -Schnittstelle, abhängig vom Wert der `m_bWndLess` und [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) Flags. (Das Datenelement [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) muss **"true"** für die [CComControlBase::m_spInPlaceSite](#m_spinplacesite) Zeiger gültig ist.)  
  
 Wenn `m_bWndLess` ist **"true"**, `m_spInPlaceSite` ist ein **IOleInPlaceSiteWindowless** Schnittstellenzeiger auf. Finden Sie unter [CComControlBase::m_spInPlaceSite](#m_spinplacesite) für eine Tabelle, die die vollständige Beziehung zwischen diesen Datenmembern anzeigt.  
  
##  <a name="m_hwndcd"></a>CComControlBase::m_hWndCD  
 Enthält einen Verweis auf das Fensterhandle des Steuerelements zugeordnet.  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents  
 Die Anzahl, wie oft der Container hat Ereignisse (Ereignisse akzeptieren verweigert) ohne einen zwischenzeitlichen Entsperren von Ereignissen (akzeptieren von Ereignissen) fixiert.  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_rcpos"></a>CComControlBase::m_rcPos  
 Die Position in Pixel des Steuerelements, ausgedrückt in die Koordinaten des Containers.  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_sizeextent"></a>CComControlBase::m_sizeExtent  
 Das Ausmaß des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter) für eine bestimmte Darstellung.  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Diese Größe wird durch die Anzeige skaliert. Physische Größe des Steuerelements wird angegeben, der `m_sizeNatural` -Datenmember "und" korrigiert wird.  
  
 Sie können die Größe in Pixel mit den globalen Funktion konvertieren [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_sizenatural"></a>CComControlBase::m_sizeNatural  
 Die physische Größe des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter).  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Diese Größe fest, während die Größe in `m_sizeExtent` durch die Anzeige skaliert wird.  
  
 Sie können die Größe in Pixel mit den globalen Funktion konvertieren [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_spadvisesink"></a>CComControlBase::m_spAdviseSink  
 Direkten Zeiger auf die Advise-Verbindung für den Container (des Containers [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch  
 Ein `CComDispatchDriver` Objekt, mit dem Sie das Abrufen und Festlegen der Eigenschaften eines Objekts über eine `IDispatch` Zeiger.  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_spclientsite"></a>CComControlBase::m_spClientSite  
 Ein Zeiger auf das Steuerelement Clientstandort innerhalb des Containers.  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder  
 Stellt ein Standard bedeutet, dass für die bereitzustellenden Advise-Verbindungen zwischen Datenobjekte advise-Empfänger bereit.  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Ein Datenobjekt ist ein Steuerelement, die Daten übertragen werden kann und mit einer Implementierung ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421), deren Methoden geben Sie das Medium Format und die Übertragung der Daten.  
  
 Die Schnittstelle `m_spDataAdviseHolder` implementiert die [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) und [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) Methoden, um festzustellen, und löschen die Advise-Verbindungen auf den Container. Der Container des Steuerelements muss eine Advise-Senke implementieren, durch die Unterstützung der [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle.  
  
##  <a name="m_spinplacesite"></a>CComControlBase::m_spInPlaceSite  
 Ein Zeiger auf des Containers [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) Schnittstellenzeiger auf.  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Die `m_spInPlaceSite` Zeiger gilt nur, wenn die [M_bNegotiatedWnd](#m_bnegotiatedwnd) Flag ist **"true"**.  
  
 Die folgende Tabelle zeigt, wie die `m_spInPlaceSite` Zeigertyp hängt die [M_bWndLess](#m_bwndless) und [M_bInPlaceSiteEx](#m_binplacesiteex) Datenmember Flags:  
  
|M_spInPlaceSite Typ|M_bWndLess Wert|M_bInPlaceSiteEx Wert|  
|---------------------------|-----------------------|-----------------------------|  
|**IOleInPlaceSiteWindowless**|**"TRUE"**|**"True"** oder **"false"**|  
|**IOleInPlaceSiteEx**|**"FALSE"**|**"TRUE"**|  
|`IOleInPlaceSite`|**"FALSE"**|**"FALSE"**|  
  
##  <a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder  
 Stellt eine Standardimplementierung von eine Möglichkeit, Advise-Verbindungen aufzunehmen.  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da er in einer Union in der Basisklasse deklariert ist.  
  
 Die Schnittstelle `m_spOleAdviseHolder` implementiert die [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) und [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) Methoden, um festzustellen, und löschen die Advise-Verbindungen auf den Container. Der Container des Steuerelements muss eine Advise-Senke implementieren, durch die Unterstützung der [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle.  
  
##  <a name="ondraw"></a>CComControlBase:: OnDraw  
 Überschreiben Sie diese Methode, um das Steuerelement gezeichnet werden soll.  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parameter  
 `di`  
 Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) -Struktur, die zeichnen Informationen wie z. B. der Draw-Aspekt der Begrenzungen des Steuerelements, und gibt an, ob die Zeichnung optimiert ist oder nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung `OnDraw` löscht den Gerätekontext wiederhergestellt oder wird keine Aktion ausgeführt, je nach in festgelegten Flags [CComControlBase::OnDrawAdvanced](#ondrawadvanced).  
  
 Ein `OnDraw` Methode wird automatisch bei der Erstellung des Steuerelements mit der ATL-Steuerelement-Assistent für die Steuerelementklasse hinzugefügt. Der Assistent standardmäßig `OnDraw` zeichnet ein Rechteck mit der Bezeichnung "ATL 8.0".  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CComControlBase](#getambientappearance).  
  
##  <a name="ondrawadvanced"></a>CComControlBase::OnDrawAdvanced  
 Die Standardeinstellung `OnDrawAdvanced` bereitet einen normalisierten Gerätekontext für das Zeichnen, dann ruft der Steuerelementklasse `OnDraw` Methode.  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parameter  
 `di`  
 Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) -Struktur, die zeichnen Informationen wie z. B. der Draw-Aspekt der Begrenzungen des Steuerelements, und gibt an, ob die Zeichnung optimiert ist oder nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie den Gerätekontext, der vom Container übergeben werden, ohne ihn zu normalisieren annehmen möchten.  
  
 Finden Sie unter [CComControlBase:: OnDraw](#ondraw) Weitere Details.  
  
##  <a name="onkillfocus"></a>CComControlBase::OnKillFocus  
 Überprüft, dass das Steuerelement in-Place aktiv ist und verfügt über eine gültige Steuerelementsite und informiert dem Container, dass das Steuerelement den Fokus verloren hat.  
  
```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parameter  
 `nMsg`  
 Reserviert.  
  
 `wParam`  
 Reserviert.  
  
 `lParam`  
 Reserviert.  
  
 `bHandled`  
 Flag, die angibt, ob die fenstermeldung erfolgreich behandelt wurde. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
##  <a name="onmouseactivate"></a>CComControlBase::OnMouseActivate  
 Überprüft, dass die Benutzeroberfläche im Benutzermodus ist, und das Steuerelement aktiviert.  
  
```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parameter  
 `nMsg`  
 Reserviert.  
  
 `wParam`  
 Reserviert.  
  
 `lParam`  
 Reserviert.  
  
 `bHandled`  
 Flag, die angibt, ob die fenstermeldung erfolgreich behandelt wurde. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
##  <a name="onpaint"></a>CComControlBase::OnPaint  
 Bereitet den Container für das Pixelbild, ruft Clientbereich des Steuerelements ab und ruft dann die Steuerelementklasse `OnDrawAdvanced` Methode.  
  
```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```  
  
### <a name="parameters"></a>Parameter  
 `nMsg`  
 Reserviert.  
  
 `wParam`  
 Eine vorhandene HDC.  
  
 `lParam`  
 Reserviert.  
  
 `lResult`  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 (null) zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `wParam` ist ungleich NULL, `OnPaint` wird angenommen, sie enthält eine gültige HDC und verwendet ihn anstelle von [CComControlBase::m_hWndCD](#m_hwndcd).  
  
##  <a name="onsetfocus"></a>CComControlBase::OnSetFocus  
 Überprüft, dass das Steuerelement in-Place aktiv ist und verfügt über eine gültige Steuerelementsite und das Container das Steuerelement informiert den Fokus gewonnen hat.  
  
```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parameter  
 `nMsg`  
 Reserviert.  
  
 `wParam`  
 Reserviert.  
  
 `lParam`  
 Reserviert.  
  
 `bHandled`  
 Flag, die angibt, ob die fenstermeldung erfolgreich behandelt wurde. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung für den Container an, dass das Steuerelement den Fokus erhalten hat.  
  
##  <a name="pretranslateaccelerator"></a>CComControlBase::PreTranslateAccelerator  
 Überschreiben Sie diese Methode, um eine eigene Tastatur Accelerator Handler bereitstellen.  
  
```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Reserviert.  
  
 *hRet*  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Standardmäßig gibt **"false"**.  
  
##  <a name="sendonclose"></a>CComControlBase::SendOnClose  
 Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, dass das Steuerelement geschlossen wurde.  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung, dass das Steuerelement die Advise-Senken geschlossen wurde.  
  
##  <a name="sendondatachange"></a>CComControlBase::SendOnDataChange  
 Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, den die Steuerelementdaten geändert wurde.  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *ADVF*  
 Empfehlen von Flags, die angeben, wie der Aufruf von [IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283) erfolgt. Werte reichen von der [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742) Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="sendonrename"></a>CComControlBase::SendOnRename  
 Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, dass das Steuerelement einen neuen Moniker verfügt.  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>Parameter  
 *PMK*  
 Ein Zeiger auf den neuen Moniker des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung, die der Moniker des Steuerelements geändert wurde.  
  
##  <a name="sendonsave"></a>CComControlBase::SendOnSave  
 Benachrichtigt alle Advise Ereignissenken registriert die Advise-Inhaber, den das Steuerelement gespeichert wurde.  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung, dass das Steuerelement seine Daten gerade gespeichert wurde.  
  
##  <a name="sendonviewchange"></a>CComControlBase::SendOnViewChange  
 Benachrichtigt, dass alle registrierten Advise-Senken, die Ansicht des Steuerelements geändert wurde.  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>Parameter  
 `dwAspect`  
 Der Aspekt oder die Ansicht des Steuerelements.  
  
 *lindex*  
 Der Teil der Sicht, die geändert wurde. Nur-1 ist gültig.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 `SendOnViewChange`Aufrufe [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337). Der einzige Wert, der *Lindex* derzeit unterstützt ist-1 und gibt an, dass die komplette Ansicht von Interesse sind.  
  
##  <a name="setcontrolfocus"></a>CComControlBase::SetControlFocus  
 Legt fest, oder den Tastaturfokus zu oder aus dem Steuerelement entfernt.  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>Parameter  
 *bGrab*  
 Wenn **"true"**, legt den Tastaturfokus an das aufrufende Steuerelement. Wenn **"false"**, aus dem aufrufenden Steuerelement den Tastaturfokus entfernt, sofern es den Fokus besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn das Steuerelement erfolgreich den Fokus erhält, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Für ein Steuerelement mit Fenster, die Windows-API-Funktion [SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312) aufgerufen wird. Für ein fensterloses Steuerelement [IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745) aufgerufen wird. Über diesen Aufruf ein fensterloses Steuerelement den Tastaturfokus erhält und auf Windows-Nachrichten reagieren kann.  
  
##  <a name="setdirty"></a>CComControlBase::SetDirty  
 Legt den Datenmember `m_bRequiresSave` auf den Wert in `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Parameter  
 `bDirty`  
 Wert des Datenmembers [CComControlBase::m_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Hinweise  
 **SetDirty(TRUE)** sollte aufgerufen werden, um zu kennzeichnen, dass das Steuerelement geändert hat, seit es zuletzt gespeichert wurde. Der Wert der `m_bRequiresSave` wird abgerufen, mit [CComControlBase::GetDirty](#getdirty).  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
