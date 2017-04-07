---
title: -Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 20
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
ms.openlocfilehash: 988528a3658dee930df2cac6fd1a4add87302509
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontrolbase-class"></a>-Klasse
Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Überprüft, ob die `iVerb` verwendeten Parameter `IOleObjectImpl::DoVerb` entweder die Benutzeroberfläche des Steuerelements aktiviert ( `iVerb` gleich `OLEIVERB_UIACTIVATE`), definiert die Aktion ausgeführt, wenn der Benutzer auf das Steuerelement doppelklickt ( `iVerb` gleich `OLEIVERB_PRIMARY`), zeigt das Steuerelement ( `iVerb` gleich `OLEIVERB_SHOW`), oder aktiviert das Steuerelement ( `iVerb` gleich **OLEIVERB_INPLACEACTIVATE**).|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Überprüft, ob die `iVerb` verwendeten Parameter `IOleObjectImpl::DoVerb` bewirkt, dass das Steuerelement der Benutzeroberfläche aktiviert, und gibt **TRUE**.|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|Zeigt die Eigenschaftenseiten für das Steuerelement.|  
|[CComControlBase::FireViewChange](#fireviewchange)|Rufen Sie diese Methode, um den Container an das Steuerelement neu gezeichnet mitzuteilen, oder benachrichtigen Sie die registrierten Advise-senken, die Ansicht des Steuerelements geändert wurde.|  
|[CComControlBase](#getambientappearance)|Ruft **DISPID_AMBIENT_APPEARANCE**, die aktuelle Darstellung für das Steuerelement festlegen: 0 für flache und 1 für 3D.|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Ruft **DISPID_AMBIENT_AUTOCLIP**, ein Flag gibt an, ob der Container automatische Abschneiden des Anzeigebereichs Steuerelement unterstützt.|  
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Ruft **DISPID_AMBIENT_BACKCOLOR**, die ambient-Hintergrundfarbe für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Ruft **DISPID_AMBIENT_CHARSET**, der der Zeichensatz für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Ruft **DISPID_AMBIENT_CODEPAGE**, der der Zeichensatz für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase:: GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Ruft **DISPID_AMBIENT_DISPLAYASDEFAULT**, ein **TRUE** Wenn der Container das Steuerelement an diesem Standort eine Standardschaltfläche werden markiert wurde und daher ein Schaltflächen-Steuerelement selbst mit einem breiteren Rahmen zeichnen soll.|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Ruft **DISPID_AMBIENT_DISPLAYNAME**, den Namen der Container für das Steuerelement angegeben hat.|  
|[CComControlBase::GetAmbientFont](#getambientfont)|Ruft ein Zeiger auf den Container des ambient `IFont` Schnittstelle.|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Ruft ein Zeiger auf den Container des ambient **IFontDisp** Dispatch-Schnittstellen.|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Ruft **DISPID_AMBIENT_FORECOLOR**, die ambient-Vordergrundfarbe für alle Steuerelemente, die vom Container definiert.|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Ruft **DISPID_AMBIENT_LOCALEID**, den Bezeichner der vom Container verwendeten Sprache.|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Ruft **DISPID_AMBIENT_MESSAGEREFLECT**, ein Flag, der angibt, ob der Container Fensternachrichten empfangen möchte (z. B. `WM_DRAWITEM`) als Ereignisse.|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Ruft **DISPID_AMBIENT_PALETTE**, mit denen Sie Zugriff auf den Container `HPALETTE`.|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Ruft die angegebenen Containereigenschaft `id`.|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|Ruft **DISPID_AMBIENT_RIGHTTOLEFT**, die Richtung, in dem Inhalte vom Container angezeigt wird.|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Ruft **DISPID_AMBIENT_SCALEUNITS**, des Containers ambient Einheiten (z. B. Zoll oder Zentimeter) zum Beschriften von angezeigt.|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Ruft **DISPID_AMBIENT_SHOWGRABHANDLES**, ein Flag gibt an, ob der Container des Steuerelements anzuzeigenden Ziehpunkte für sich selbst beim active zulässt.|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Ruft **DISPID_AMBIENT_SHOWHATCHING**, ein Flag gibt an, ob der Container ermöglicht, dass das Steuerelement selbst mit einer Schraffur an, wenn die Benutzeroberfläche aktiv ist.|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Ruft **DISPID_AMBIENT_SUPPORTSMNEMONICS**, ein Flag gibt an, ob der Container mnemonisches unterstützt.|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Ruft **DISPID_AMBIENT_TEXTALIGN**, die Ausrichtung des Texts bevorzugten vom Container: 0 für die allgemeine Ausrichtung (Zahlen, Text rechts nach links), 1 für linksbündig, 2 für zentrierte Ausrichtung und 3 für rechtsbündige Ausrichtung.|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|Ruft **DISPID_AMBIENT_TOPTOBOTTOM**, die Richtung, in dem Inhalte vom Container angezeigt wird.|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Ruft **DISPID_AMBIENT_UIDEAD**, ein Flag gibt an, ob der Container des Steuerelements auf der Benutzeroberfläche Aktionen reagieren möchte.|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Ruft **DISPID_AMBIENT_USERMODE**, ein Flag, der angibt, ob der Container im Ausführungsmodus ist ( **TRUE**) oder Entwurfsmodus ( **FALSE**).|  
|[CComControlBase::GetDirty](#getdirty)|Gibt den Wert eines Datenelements `m_bRequiresSave`.|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|Ruft die x- und y Werte der Zähler und Nenner für den Zoomfaktor für ein Steuerelement, für die aktiviert direkte Bearbeitung.|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|Bewirkt, dass das Steuerelement für den Übergang vom inaktiven Status, was das Verb im Zustand `iVerb` angibt.|  
|[CComControlBase::InternalGetSite](#internalgetsite)|Rufen Sie diese Methode, um die Website des Steuerelements für einen Zeiger auf die angegebene Schnittstelle Abfragen.|  
|[CComControlBase:: OnDraw](#ondraw)|Überschreiben Sie diese Methode zum Zeichnen des Steuerelements.|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Die Standardeinstellung **OnDrawAdvanced** bereitet einen normalisierten Gerätekontext für das Zeichnen, dann ruft der Steuerelementklasse `OnDraw` Methode.|  
|[CComControlBase::OnKillFocus](#onkillfocus)|Überprüft, ob das Steuerelement direkt aktiv ist und verfügt über eine gültige Steuerelement-Website, Container teilt mit, dass das Steuerelement den Fokus verloren hat.|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Überprüft, ob die Benutzeroberfläche im Benutzermodus ist, dann wird das Steuerelement aktiviert.|  
|[CComControlBase::OnPaint](#onpaint)|Bereitet den Container für das Pixelbild, ruft der Clientbereich des Steuerelements ab und ruft dann der Control-Klasse `OnDraw` Methode.|  
|[CComControlBase::OnSetFocus](#onsetfocus)|Überprüft, ob das Steuerelement direkt aktiv ist und verfügt über eine gültige Steuerelement-Website, informiert das Container des Steuerelements den Fokus hat gewonnen werden.|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Überschreiben Sie diese Methode, um eigene Accelerator Handler bereitstellen.|  
|[CComControlBase::SendOnClose](#sendonclose)|Benachrichtigt alle Advise-Senken der Advise-Inhaber, dass das Steuerelement geschlossen wurde registriert.|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|Benachrichtigt alle Advise-Senken registriert den Inhaber der anweisen, den die Daten des Steuerelements geändert wurde.|  
|[CComControlBase::SendOnRename](#sendonrename)|Benachrichtigt alle Advise-Senken, dass das Steuerelement einen neuen Moniker hat der Inhaber der Advise registriert.|  
|[CComControlBase::SendOnSave](#sendonsave)|Benachrichtigt alle Advise-Senken registriert den Inhaber der anweisen, den das Steuerelement gespeichert wurde.|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Benachrichtigt alle registrierten Advise-Senken, die Ansicht des Steuerelements geändert wurde.|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Legt fest oder den Tastaturfokus in oder aus dem Steuerelement entfernt.|  
|[CComControlBase::SetDirty](#setdirty)|Legt das Datenelement `m_bRequiresSave` mit dem Wert im `bDirty`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|Zeigt an, das Steuerelement kann eine beliebige andere Größe sein.|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Flag zeigt an, dass `IDataObjectImpl::GetData` und `CComControlBase::GetZoomInfo` fest, dass die Größe von `m_sizeNatural` anstatt von `m_sizeExtent`.|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Flag zeigt an, dass `IDataObjectImpl::GetData` verwende HIMETRIC-Einheiten und nicht in Pixel zeichnen.|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Ein Flag, der angibt, dass das Steuerelement direkt aktiv ist.|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Zeigt an, die Container unterstützt die **IOleInPlaceSiteEx** -Schnittstelle und OCX96 Funktionen, z. B. fensterlose und flimmerfreie Steuerelemente zu steuern.|  
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Ein Flag, der angibt, ob das Steuerelement mit dem Container über die Unterstützung für OCX96 Funktionen (z. B. flimmerfreie und Fensterlose Steuerelemente) ausgehandelt wurde, und gibt an, ob das Steuerelement im Fenstermodus oder fensterlose ist.|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Zeigt an, dass möchte, dass das Steuerelement seine Darstellung neu aufzubauen, wenn der Container die Größe des Steuerelements angezeigt wird.|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Ein Flag, der angibt, dass das Steuerelement geändert wurde, seit es zuletzt gespeichert wurde.|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Kennzeichnung möchte, dass das Steuerelement Größe seiner natürlichen Ausdehnung (der nicht skalierten physischen Größe), wenn der Container des Steuerelements Größe ändert.|  
|[CComControlBase::m_bUIActive](#m_buiactive)|Flag zur Angabe des Steuerelements-Benutzeroberfläche, z. B. Menüs und Symbolleisten, ist aktiv.|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Ein Flag, der angibt, dass das Steuerelement den Container bereitgestellten Fensterbereich verwendet wird.|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Zeigt an, das Steuerelement wurde fensterlose, jedoch möglicherweise oder sind möglicherweise nicht fensterlos jetzt.|  
|[CComControlBase](#m_bwindowonly)|Ein Flag, der angibt, dass das Steuerelement im Fenstermodus, sein sollte, selbst wenn der Container Fensterlose Steuerelemente unterstützt.|  
|[CComControlBase::m_bWndLess](#m_bwndless)|Ein Flag, der angibt, dass das Steuerelement fensterlose ist.|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|Enthält einen Verweis auf das Fensterhandle, das dem Steuerelement zugeordnet.|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Anzahl die Anzahl der Container hat Ereignisse (abgelehnt hat Ereignisse) ohne eine Beteiligte Entsperren von Ereignissen (Annahme) fixiert.|  
|[CComControlBase::m_rcPos](#m_rcpos)|Die Position in Pixel des Steuerelements, ausgedrückt in die Koordinaten des Containers.|  
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Der Umfang des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter) für einen Bildschirm.|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|Die physische Größe des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter).|  
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Direkten Zeiger auf die Advise-Verbindung für den Container (der Containers [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Ein `CComDispatchDriver` Objekt, mit dem Sie das Abrufen und Festlegen der Container-Eigenschaften über einen `IDispatch` Zeiger.|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|Ein Zeiger auf Site innerhalb des Containers des Steuerelements.|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Stellt ein Standard-Umgebung Advise-Verbindungen zwischen Datenobjekte und advise-senken.|  
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Ein Zeiger auf des Containers [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) -Schnittstellenzeiger.|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Stellt eine standardmäßige Implementierung der Advise-Verbindungen speichern können.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen. [CComControl Klasse](../../atl/reference/ccomcontrol-class.md) leitet sich von `CComControlBase`. Wenn Sie ein Standardsteuerelement oder DHTML-Steuerelement, mit der ATL-Steuerelement-Assistenten erstellen, leiten der Assistent automatisch eine Klasse von `CComControlBase`.  
  
 Weitere Informationen zum Erstellen eines Steuerelements finden Sie unter der [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen über ATL-Projekt-Assistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="appearancetype"></a>CComControlBase::AppearanceType  
 Überschreiben, wenn Ihre **M_nAppearance** Systemeigenschaft ist nicht vom Typ **kurze**.  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>Hinweise  
 Der ATL-Steuerelement-Assistent fügt **M_nAppearance** stock-Eigenschaft vom Typ short. Überschreiben Sie `AppearanceType` , wenn Sie einen anderen Datentyp verwenden.  
  
##  <a name="ccomcontrolbase"></a>CComControlBase::CComControlBase  
 Der Konstruktor.  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 Das Handle für das Fenster, das dem Steuerelement zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die Größe 5080 X 5080 HIMETRIC-Einheiten (2 "X 2") und initialisiert die `CComControlBase` -Datenmember Werte **NULL** oder **FALSE**.  
  
##  <a name="dtor"></a>CComControlBase:: ~ CComControlBase  
 Der Destruktor.  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement im Fenstermodus, `~CComControlBase` zerstört es durch Aufrufen von [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682).  
  
##  <a name="controlqueryinterface"></a>CComControlBase::ControlQueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 Die GUID der angeforderten Schnittstelle.  
  
 `ppv`  
 Ein Zeiger auf den Schnittstellenzeiger vom `iid`, oder **NULL** Wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Behandelt nur Schnittstellen im COM-Zuordnungstabelle.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#15;](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate  
 Überprüft, ob die `iVerb` verwendeten Parameter `IOleObjectImpl::DoVerb` entweder die Benutzeroberfläche des Steuerelements aktiviert ( `iVerb` gleich `OLEIVERB_UIACTIVATE`), definiert die Aktion ausgeführt, wenn der Benutzer auf das Steuerelement doppelklickt ( `iVerb` gleich `OLEIVERB_PRIMARY`), zeigt das Steuerelement ( `iVerb` gleich `OLEIVERB_SHOW`), oder aktiviert das Steuerelement ( `iVerb` gleich **OLEIVERB_INPLACEACTIVATE**).  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Wert, der die Aktion, die von `DoVerb`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** Wenn `iVerb` gleich `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, oder **OLEIVERB_INPLACEACTIVATE**ist, andernfalls gibt **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um eigene Aktivierung Verb zu definieren, überschreiben.  
  
##  <a name="doesverbuiactivate"></a>CComControlBase::DoesVerbUIActivate  
 Überprüft, ob die `iVerb` verwendeten Parameter `IOleObjectImpl::DoVerb` bewirkt, dass das Steuerelement der Benutzeroberfläche aktiviert, und gibt **TRUE**.  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Wert, der die Aktion, die von `DoVerb`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** Wenn `iVerb` gleich `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, oder **OLEIVERB_INPLACEACTIVATE**. Die Methode andernfalls **FALSE**.  
  
##  <a name="doverbproperties"></a>CComControlBase::DoVerbProperties  
 Zeigt die Eigenschaftenseiten für das Steuerelement.  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 Reserviert.  
  
 *hwndParent*  
 Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM NR.&19;](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM&20;](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>CComControlBase::FireViewChange  
 Rufen Sie diese Methode, um den Container an das Steuerelement neu gezeichnet mitzuteilen, oder benachrichtigen Sie die registrierten Advise-senken, die Ansicht des Steuerelements geändert wurde.  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement aktiv ist (das Steuerelement eine Datenmember [CComControlBase::m_bInPlaceActive](#m_binplaceactive) ist **TRUE**), zeigt dem Container an, dass das gesamte Steuerelement neu gezeichnet werden soll. Wenn das Steuerelement nicht aktiv ist, benachrichtigt das Steuerelement registriert die advise-senken (über das Steuerelement eine Datenmember [CComControlBase::m_spAdviseSink](#m_spadvisesink)), die Ansicht des Steuerelements geändert hat.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&21;](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>CComControlBase  
 Ruft **DISPID_AMBIENT_APPEARANCE**, die aktuelle Darstellung für das Steuerelement festlegen: 0 für flache und 1 für 3D.  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>Parameter  
 `nAppearance`  
 Die Eigenschaft **DISPID_AMBIENT_APPEARANCE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#22;](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip  
 Ruft **DISPID_AMBIENT_AUTOCLIP**, ein Flag gibt an, ob der Container automatische Abschneiden des Anzeigebereichs Steuerelement unterstützt.  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>Parameter  
 *bAutoClip*  
 Die Eigenschaft **DISPID_AMBIENT_AUTOCLIP**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientbackcolor"></a>CComControlBase::GetAmbientBackColor  
 Ruft **DISPID_AMBIENT_BACKCOLOR**, die ambient-Hintergrundfarbe für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>Parameter  
 *BackColor*  
 Die Eigenschaft **DISPID_AMBIENT_BACKCOLOR**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientcharset"></a>CComControlBase::GetAmbientCharSet  
 Ruft **DISPID_AMBIENT_CHARSET**, der der Zeichensatz für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrCharSet*  
 Die Eigenschaft **DISPID_AMBIENT_CHARSET**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage  
 Ruft **DISPID_AMBIENT_CODEPAGE**, die der Codepage für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>Parameter  
 *ulCodePage*  
 Die Eigenschaft **DISPID_AMBIENT_CODEPAGE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientdisplayasdefault"></a>CComControlBase:: GetAmbientDisplayAsDefault  
 Ruft **DISPID_AMBIENT_DISPLAYASDEFAULT**, ein **TRUE** Wenn der Container das Steuerelement an diesem Standort eine Standardschaltfläche werden markiert wurde und daher ein Schaltflächen-Steuerelement selbst mit einem breiteren Rahmen zeichnen soll.  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `bDisplayAsDefault`  
 Die Eigenschaft **DISPID_AMBIENT_DISPLAYASDEFAULT**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientdisplayname"></a>CComControlBase::GetAmbientDisplayName  
 Ruft **DISPID_AMBIENT_DISPLAYNAME**, den Namen der Container für das Steuerelement angegeben hat.  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrDisplayName*  
 Die Eigenschaft **DISPID_AMBIENT_DISPLAYNAME**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientfont"></a>CComControlBase::GetAmbientFont  
 Ruft ein Zeiger auf den Container des ambient `IFont` Schnittstelle.  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>Parameter  
 `ppFont`  
 Ein Zeiger auf den Container des ambient [IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673) Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft **NULL**, der Zeiger **NULL**. Wenn der Zeiger nicht **NULL**, der Aufrufer muss den Zeiger freigeben.  
  
##  <a name="getambientfontdisp"></a>CComControlBase::GetAmbientFontDisp  
 Ruft ein Zeiger auf den Container des ambient **IFontDisp** Dispatch-Schnittstellen.  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>Parameter  
 `ppFont`  
 Ein Zeiger auf den Container des ambient [IFontDisp](http://msdn.microsoft.com/library/windows/desktop/ms692695) Dispatch-Schnittstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft **NULL**, der Zeiger **NULL**. Wenn der Zeiger nicht **NULL**, der Aufrufer muss den Zeiger freigeben.  
  
##  <a name="getambientforecolor"></a>CComControlBase::GetAmbientForeColor  
 Ruft **DISPID_AMBIENT_FORECOLOR**, die ambient-Vordergrundfarbe für alle Steuerelemente, die vom Container definiert.  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>Parameter  
 *Vordergrundfarbe*  
 Die Eigenschaft **DISPID_AMBIENT_FORECOLOR**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientlocaleid"></a>CComControlBase::GetAmbientLocaleID  
 Ruft **DISPID_AMBIENT_LOCALEID**, den Bezeichner der vom Container verwendeten Sprache.  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>Parameter  
 `lcid`  
 Die Eigenschaft **DISPID_AMBIENT_LOCALEID**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement kann diesen Bezeichner zum Anpassen der Benutzeroberfläche in verschiedenen Sprachen verwenden.  
  
##  <a name="getambientmessagereflect"></a>CComControlBase::GetAmbientMessageReflect  
 Ruft **DISPID_AMBIENT_MESSAGEREFLECT**, ein Flag, der angibt, ob der Container Fensternachrichten empfangen möchte (z. B. `WM_DRAWITEM`) als Ereignisse.  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>Parameter  
 `bMessageReflect`  
 Die Eigenschaft **DISPID_AMBIENT_MESSAGEREFLECT**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientpalette"></a>CComControlBase::GetAmbientPalette  
 Ruft **DISPID_AMBIENT_PALETTE**, mit denen Sie Zugriff auf den Container `HPALETTE`.  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `hPalette`  
 Die Eigenschaft **DISPID_AMBIENT_PALETTE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientproperty"></a>CComControlBase::GetAmbientProperty  
 Ruft die angegebenen Containereigenschaft `dispid`.  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Der Bezeichner der Containereigenschaft abgerufen werden soll.  
  
 `var`  
 Variable, die die Eigenschaft empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 ATL gab eine Reihe von Hilfsfunktionen zum Abrufen von Eigenschaften, z. B. [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Wenn keine geeignete Methode verfügbar ist, verwenden Sie `GetAmbientProperty`.  
  
##  <a name="getambientrighttoleft"></a>CComControlBase::GetAmbientRightToLeft  
 Ruft **DISPID_AMBIENT_RIGHTTOLEFT**, die Richtung, in dem Inhalte vom Container angezeigt wird.  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>Parameter  
 *bRightToLeft*  
 Die Eigenschaft **DISPID_AMBIENT_RIGHTTOLEFT**. Legen Sie auf **TRUE** Wenn Inhalt, von rechts nach links angezeigt wird, **FALSE** Wenn sie links nach rechts angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientscaleunits"></a>CComControlBase::GetAmbientScaleUnits  
 Ruft **DISPID_AMBIENT_SCALEUNITS**, des Containers ambient Einheiten (z. B. Zoll oder Zentimeter) zum Beschriften von angezeigt.  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrScaleUnits*  
 Die Eigenschaft **DISPID_AMBIENT_SCALEUNITS**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientshowgrabhandles"></a>CComControlBase::GetAmbientShowGrabHandles  
 Ruft **DISPID_AMBIENT_SHOWGRABHANDLES**, ein Flag gibt an, ob der Container des Steuerelements anzuzeigenden Ziehpunkte für sich selbst beim active zulässt.  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>Parameter  
 *bShowGrabHandles*  
 Die Eigenschaft **DISPID_AMBIENT_SHOWGRABHANDLES**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientshowhatching"></a>CComControlBase::GetAmbientShowHatching  
 Ruft **DISPID_AMBIENT_SHOWHATCHING**, ein Flag gibt an, ob der Container ermöglicht, dass das Steuerelement selbst mit einer Schraffur an, wenn das Steuerelement-Benutzeroberfläche aktiviert ist.  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>Parameter  
 *bShowHatching*  
 Die Eigenschaft **DISPID_AMBIENT_SHOWHATCHING**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMnemonics  
 Ruft **DISPID_AMBIENT_SUPPORTSMNEMONICS**, ein Flag gibt an, ob der Container mnemonisches unterstützt.  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>Parameter  
 *bSupportsMnemonics*  
 Die Eigenschaft **DISPID_AMBIENT_SUPPORTSMNEMONICS**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambienttextalign"></a>CComControlBase::GetAmbientTextAlign  
 Ruft **DISPID_AMBIENT_TEXTALIGN**, die Ausrichtung des Texts bevorzugten vom Container: 0 für die allgemeine Ausrichtung (Zahlen, Text rechts nach links), 1 für linksbündig, 2 für zentrierte Ausrichtung und 3 für rechtsbündige Ausrichtung.  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>Parameter  
 *nTextAlign*  
 Die Eigenschaft **DISPID_AMBIENT_TEXTALIGN**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getambienttoptobottom"></a>CComControlBase::GetAmbientTopToBottom  
 Ruft **DISPID_AMBIENT_TOPTOBOTTOM**, die Richtung, in dem Inhalte vom Container angezeigt wird.  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>Parameter  
 *bTopToBottom*  
 Die Eigenschaft **DISPID_AMBIENT_TOPTOBOTTOM**. Legen Sie auf **TRUE** Wenn Text angezeigt wird, von oben nach unten, **FALSE** Wenn es angezeigt wird von unten nach oben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getambientuidead"></a>CComControlBase::GetAmbientUIDead  
 Ruft **DISPID_AMBIENT_UIDEAD**, ein Flag gibt an, ob der Container des Steuerelements auf der Benutzeroberfläche Aktionen reagieren möchte.  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>Parameter  
 *bUIDead*  
 Die Eigenschaft **DISPID_AMBIENT_UIDEAD**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn **TRUE**, das Steuerelement nicht reagieren soll. Dieser Parameter gilt unabhängig von der **DISPID_AMBIENT_USERMODE** Flag. Finden Sie unter [CComControlBase::GetAmbientUserMode](#getambientusermode).  
  
##  <a name="getambientusermode"></a>CComControlBase::GetAmbientUserMode  
 Ruft **DISPID_AMBIENT_USERMODE**, ein Flag, der angibt, ob der Container im Ausführungsmodus ist ( **TRUE**) oder Entwurfsmodus ( **FALSE**).  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>Parameter  
 `bUserMode`  
 Die Eigenschaft **DISPID_AMBIENT_USERMODE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
##  <a name="getdirty"></a>CComControlBase::GetDirty  
 Gibt den Wert eines Datenelements `m_bRequiresSave`.  
  
```
BOOL GetDirty();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert eines Datenelements [M_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird festgelegt, mit [CComControlBase::SetDirty](#setdirty).  
  
##  <a name="getzoominfo"></a>CComControlBase::GetZoomInfo  
 Ruft die x- und y Werte der Zähler und Nenner für den Zoomfaktor für ein Steuerelement, für die aktiviert direkte Bearbeitung.  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parameter  
 `di`  
 Die Struktur, die des Zoomfaktor Zähler und Nenner enthalten. Weitere Informationen finden Sie unter [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).  
  
### <a name="remarks"></a>Hinweise  
 Der Zoomfaktor ist der Anteil der natürlichen Größe des Steuerelements, in seiner aktuellen Ausdehnung.  
  
##  <a name="inplaceactivate"></a>CComControlBase::InPlaceActivate  
 Bewirkt, dass das Steuerelement für den Übergang vom inaktiven Status, was das Verb im Zustand `iVerb` angibt.  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Wert, der die Aktion, die von [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).  
  
 *prcPosRect*  
 Ein Zeiger auf die Position des Steuerelements an.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Vor der Aktivierung überprüft diese Methode, dass das Steuerelement verfügt über eine Client-Website überprüft, wie viel des Steuerelements sichtbar ist, und die Position des Steuerelements im übergeordneten Fenster ruft. Nachdem das Steuerelement aktiviert ist, wird diese Methode wird die Benutzeroberfläche des Steuerelements aktiviert und weist den Container an das Steuerelement sichtbar zu machen.  
  
 Diese Methode ruft auch eine `IOleInPlaceSite`, **IOleInPlaceSiteEx**, oder **IOleInPlaceSiteWindowless** -Schnittstellenzeiger für das Steuerelement und speichert ihn in der Steuerelementklasse Datenmember [CComControlBase::m_spInPlaceSite](#m_spinplacesite). Die Steuerelement-Klassendatenmember [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless), und [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) auf "true" entsprechend festgelegt werden.  
  
##  <a name="internalgetsite"></a>CComControlBase::InternalGetSite  
 Rufen Sie diese Methode, um die Website des Steuerelements für einen Zeiger auf die angegebene Schnittstelle Abfragen.  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>Parameter  
 `riid`  
 Die IID des Schnittstellenzeigers, die zurückgegeben werden sollen `ppUnkSite`.  
  
 `ppUnkSite`  
 Adresse der Zeigervariablen, die den Schnittstellenzeiger, der im angeforderten empfängt `riid`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Standort über die Schnittstelle im angeforderten unterstützt `riid`, der Zeiger wird zurückgegeben, mit der `ppUnkSite`. Andernfalls `ppUnkSite` auf NULL festgelegt ist.  
  
##  <a name="m_bautosize"></a>CComControlBase::m_bAutoSize  
 Zeigt an, das Steuerelement kann eine beliebige andere Größe sein.  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag wird von überprüft `IOleObjectImpl::SetExtent` und **TRUE**, bewirkt, dass die Funktion zurückgeben **E_FAIL**.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Wenn Sie Hinzufügen der **Automatische Größe** auf die option der [Basiseigenschaften](../../atl/reference/stock-properties-atl-control-wizard.md) Registerkarte des ATL-Steuerelement-Assistenten, der Assistent erstellt dieses Datenelement in der Steuerelementklasse, erstellt automatisch put und get-Methoden für die Eigenschaft und unterstützt [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Container automatisch benachrichtigt, wenn die Eigenschaft geändert wird.  
  
##  <a name="m_bdrawfromnatural"></a>CComControlBase::m_bDrawFromNatural  
 Flag zeigt an, dass `IDataObjectImpl::GetData` und `CComControlBase::GetZoomInfo` fest, dass die Größe von `m_sizeNatural` anstatt von `m_sizeExtent`.  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric  
 Flag zeigt an, dass `IDataObjectImpl::GetData` verwende HIMETRIC-Einheiten und nicht in Pixel zeichnen.  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Jede logische Einheit von HIMETRIC ist 0,01 Millimeter.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_binplaceactive"></a>CComControlBase::m_bInPlaceActive  
 Ein Flag, der angibt, dass das Steuerelement direkt aktiv ist.  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Dies bedeutet, dass das Steuerelement sichtbar ist und das Fenster ggf. sichtbar ist, ist aber Menüs und Symbolleisten nicht aktiv sein. Die `m_bUIActive` -Flag gibt an, das Steuerelement-Benutzeroberfläche, z. B. Menüs, auch aktiv ist.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_binplacesiteex"></a>CComControlBase::m_bInPlaceSiteEx  
 Zeigt an, die Container unterstützt die **IOleInPlaceSiteEx** -Schnittstelle und OCX96 Funktionen, z. B. fensterlose und flimmerfreie Steuerelemente zu steuern.  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Das Datenelement `m_spInPlaceSite` verweist auf eine [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) -Schnittstelle, abhängig vom Wert der `m_bWndLess` und `m_bInPlaceSiteEx` Flags. (Das Datenelement `m_bNegotiatedWnd` muss **TRUE** für die `m_spInPlaceSite` Zeiger gültig ist.)  
  
 Wenn `m_bWndLess` ist **FALSE** und `m_bInPlaceSiteEx` ist **TRUE**, `m_spInPlaceSite` ist ein **IOleInPlaceSiteEx** -Schnittstellenzeiger. Finden Sie unter [M_spInPlaceSite](#m_spinplacesite) für eine Tabelle mit den Beziehungen zwischen diesen drei Datenmember.  
  
##  <a name="m_bnegotiatedwnd"></a>CComControlBase::m_bNegotiatedWnd  
 Ein Flag, der angibt, ob das Steuerelement mit dem Container über die Unterstützung für OCX96 Funktionen (z. B. flimmerfreie und Fensterlose Steuerelemente) ausgehandelt wurde, und gibt an, ob das Steuerelement im Fenstermodus oder fensterlose ist.  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Die `m_bNegotiatedWnd` Flag muss **TRUE** für die `m_spInPlaceSite` Zeiger gültig ist.  
  
##  <a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize  
 Zeigt an, dass möchte, dass das Steuerelement seine Darstellung neu aufzubauen, wenn der Container die Größe des Steuerelements angezeigt wird.  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Dieses Flag wird von überprüft [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) und **TRUE**, `SetExtent` benachrichtigt den Container der Ansicht geändert wird. Wenn dieses Flag festgelegt ist, die **OLEMISC_RECOMPOSEONRESIZE** bit in der [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Enumeration muss auch festgelegt werden.  
  
##  <a name="m_brequiressave"></a>CComControlBase::m_bRequiresSave  
 Ein Flag, der angibt, dass das Steuerelement geändert wurde, seit es zuletzt gespeichert wurde.  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der `m_bRequiresSave` kann festgelegt werden, mit [CComControlBase::SetDirty](#setdirty) und mit abgerufene [CComControlBase::GetDirty](#getdirty).  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural  
 Kennzeichnung möchte, dass das Steuerelement Größe seiner natürlichen Ausdehnung (der nicht skalierten physischen Größe), wenn der Container des Steuerelements Größe ändert.  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag wird von überprüft `IOleObjectImpl::SetExtent` und **TRUE**, übergeben Sie die Größe in `SetExtent` zugewiesen ist `m_sizeNatural`.  
  
 Übergeben Sie die Größe in `SetExtent` wird immer zugewiesen `m_sizeExtent`, unabhängig vom Wert der `m_bResizeNatural`.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_buiactive"></a>CComControlBase::m_bUIActive  
 Flag zur Angabe des Steuerelements-Benutzeroberfläche, z. B. Menüs und Symbolleisten, ist aktiv.  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_bInPlaceActive` Flag gibt an, dass das Steuerelement aktiv ist, aber nicht die Benutzeroberfläche ist aktiv.  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn  
 Ein Flag, der angibt, dass das Steuerelement den Container bereitgestellten Fensterbereich verwendet wird.  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless  
 Zeigt an, das Steuerelement wurde fensterlose, jedoch möglicherweise oder sind möglicherweise nicht fensterlos jetzt.  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bwindowonly"></a>CComControlBase  
 Ein Flag, der angibt, dass das Steuerelement im Fenstermodus, sein sollte, selbst wenn der Container Fensterlose Steuerelemente unterstützt.  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_bwndless"></a>CComControlBase::m_bWndLess  
 Ein Flag, der angibt, dass das Steuerelement fensterlose ist.  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Das Datenelement `m_spInPlaceSite` verweist auf eine [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) -Schnittstelle, abhängig vom Wert der `m_bWndLess` und [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) Flags. (Das Datenelement [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) muss **TRUE** für die [CComControlBase::m_spInPlaceSite](#m_spinplacesite) Zeiger gültig ist.)  
  
 Wenn `m_bWndLess` ist **TRUE**, `m_spInPlaceSite` ist ein **IOleInPlaceSiteWindowless** -Schnittstellenzeiger. Finden Sie unter [CComControlBase::m_spInPlaceSite](#m_spinplacesite) für eine Tabelle, die die vollständige Beziehung zwischen diesen Datenmembern anzeigt.  
  
##  <a name="m_hwndcd"></a>CComControlBase::m_hWndCD  
 Enthält einen Verweis auf das Fensterhandle, das dem Steuerelement zugeordnet.  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents  
 Anzahl die Anzahl der Container hat Ereignisse (abgelehnt hat Ereignisse) ohne eine Beteiligte Entsperren von Ereignissen (Annahme) fixiert.  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_rcpos"></a>CComControlBase::m_rcPos  
 Die Position in Pixel des Steuerelements, ausgedrückt in die Koordinaten des Containers.  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_sizeextent"></a>CComControlBase::m_sizeExtent  
 Der Umfang des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter) für einen Bildschirm.  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Diese Größe skaliert wird angezeigt. Physikalische Größe des Steuerelements wird angegeben, der `m_sizeNatural` -Datenmember und wird.  
  
 Sie können die Größe in Pixel mit der globalen Funktion konvertieren [AtlHiMetricToPixel](http://msdn.microsoft.com/library/00c3af58-7298-4082-9a2e-5b68a8cec6fd).  
  
##  <a name="m_sizenatural"></a>CComControlBase::m_sizeNatural  
 Die physische Größe des Steuerelements in HIMETRIC-Einheiten (à 0,01 Millimeter).  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Diese Größe ist festgelegt, während die Größe in `m_sizeExtent` ist abhängig von der Anzeige.  
  
 Sie können die Größe in Pixel mit der globalen Funktion konvertieren [AtlHiMetricToPixel](http://msdn.microsoft.com/library/00c3af58-7298-4082-9a2e-5b68a8cec6fd).  
  
##  <a name="m_spadvisesink"></a>CComControlBase::m_spAdviseSink  
 Direkten Zeiger auf die Advise-Verbindung für den Container (der Containers [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch  
 Ein `CComDispatchDriver` Objekt, mit dem Sie das Abrufen und Festlegen der Eigenschaften eines Objekts über eine `IDispatch` Zeiger.  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_spclientsite"></a>CComControlBase::m_spClientSite  
 Ein Zeiger auf Site innerhalb des Containers des Steuerelements.  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
##  <a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder  
 Stellt ein Standard-Umgebung Advise-Verbindungen zwischen Datenobjekte und advise-senken.  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Ein Objekt ist ein Steuerelement, die Daten übertragen werden kann, und implementiert [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), deren Methoden geben Sie das Medium Format und die Übertragung der Daten.  
  
 Die Schnittstelle `m_spDataAdviseHolder` implementiert die [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) und [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) Methoden zum Einrichten und Advise-Verbindungen auf den Container löschen. Der Container des Steuerelements muss eine Advise-Senke implementieren, durch die Unterstützung der [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle.  
  
##  <a name="m_spinplacesite"></a>CComControlBase::m_spInPlaceSite  
 Ein Zeiger auf des Containers [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), oder [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) -Schnittstellenzeiger.  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Die `m_spInPlaceSite` Zeiger gilt nur, wenn der [M_bNegotiatedWnd](#m_bnegotiatedwnd) Flag ist **TRUE**.  
  
 Die folgende Tabelle zeigt, wie die `m_spInPlaceSite` Zeigertyp hängt von der [M_bWndLess](#m_bwndless) und [M_bInPlaceSiteEx](#m_binplacesiteex) Datenmember Flags:  
  
|M_spInPlaceSite Typ|M_bWndLess Wert|M_bInPlaceSiteEx Wert|  
|---------------------------|-----------------------|-----------------------------|  
|**IOleInPlaceSiteWindowless**|**"TRUE"**|**True,** oder **FALSE**|  
|**IOleInPlaceSiteEx**|**FALSE**|**"TRUE"**|  
|`IOleInPlaceSite`|**FALSE**|**FALSE**|  
  
##  <a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder  
 Stellt eine standardmäßige Implementierung der Advise-Verbindungen speichern können.  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Um dieses Datenelement innerhalb eine Klasse zu verwenden, müssen Sie es als Datenmember in eine Klasse deklarieren. Eine Klasse erbt nicht dieses Datenelement aus der Basisklasse, da es in einer Union in der Basisklasse deklariert ist.  
  
 Die Schnittstelle `m_spOleAdviseHolder` implementiert die [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) und [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) Methoden zum Einrichten und Advise-Verbindungen auf den Container löschen. Der Container des Steuerelements muss eine Advise-Senke implementieren, durch die Unterstützung der [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle.  
  
##  <a name="ondraw"></a>CComControlBase:: OnDraw  
 Überschreiben Sie diese Methode zum Zeichnen des Steuerelements.  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parameter  
 `di`  
 Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) -Struktur, die Zeichnung wie der Draw-Aspekt der Grenzen des Steuerelements Informationen, und gibt an, ob das Zeichnen optimiert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung `OnDraw` löscht den Gerätekontext wiederhergestellt oder wird keine Aktion ausgeführt, je nachdem in festgelegten Flags [CComControlBase::OnDrawAdvanced](#ondrawadvanced).  
  
 Eine `OnDraw` Methode wird automatisch auf eine Klasse hinzugefügt, wenn Sie das Steuerelement mit der ATL-Steuerelement-Assistenten erstellen. Der Assistent standardmäßig `OnDraw` zeichnet ein Rechteck mit der Bezeichnung "ATL 8.0".  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CComControlBase](#getambientappearance).  
  
##  <a name="ondrawadvanced"></a>CComControlBase::OnDrawAdvanced  
 Die Standardeinstellung `OnDrawAdvanced` bereitet einen normalisierten Gerätekontext für das Zeichnen, dann ruft der Steuerelementklasse `OnDraw` Methode.  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parameter  
 `di`  
 Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) -Struktur, die Zeichnung wie der Draw-Aspekt der Grenzen des Steuerelements Informationen, und gibt an, ob das Zeichnen optimiert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie den Gerätekontext, der vom Container übergeben, ohne ihn zu normalisieren übernehmen möchten.  
  
 Finden Sie unter [CComControlBase:: OnDraw](#ondraw) für weitere Details.  
  
##  <a name="onkillfocus"></a>CComControlBase::OnKillFocus  
 Überprüft, ob das Steuerelement direkt aktiv ist und verfügt über eine gültige Steuerelement-Website, Container teilt mit, dass das Steuerelement den Fokus verloren hat.  
  
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
 Flag, die angibt, ob die Meldung erfolgreich verarbeitet wurde. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
##  <a name="onmouseactivate"></a>CComControlBase::OnMouseActivate  
 Überprüft, ob die Benutzeroberfläche im Benutzermodus ist, dann wird das Steuerelement aktiviert.  
  
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
 Flag, die angibt, ob die Meldung erfolgreich verarbeitet wurde. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
##  <a name="onpaint"></a>CComControlBase::OnPaint  
 Bereitet den Container für das Pixelbild, ruft der Clientbereich des Steuerelements ab und ruft dann der Control-Klasse `OnDrawAdvanced` Methode.  
  
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
 Gibt immer&0; (null) zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `wParam` ist nicht NULL, `OnPaint` nimmt er enthält eine gültige HDC und verwendet ihn statt des [CComControlBase::m_hWndCD](#m_hwndcd).  
  
##  <a name="onsetfocus"></a>CComControlBase::OnSetFocus  
 Überprüft, ob das Steuerelement direkt aktiv ist und verfügt über eine gültige Steuerelement-Website, informiert das Container des Steuerelements den Fokus hat gewonnen werden.  
  
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
 Flag, die angibt, ob die Meldung erfolgreich verarbeitet wurde. Die Standardeinstellung ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung an den Container an, dass das Steuerelement den Fokus erhalten hat.  
  
##  <a name="pretranslateaccelerator"></a>CComControlBase::PreTranslateAccelerator  
 Überschreiben Sie diese Methode, um eigene Accelerator Handler bereitstellen.  
  
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
 Standardmäßig gibt **FALSE**.  
  
##  <a name="sendonclose"></a>CComControlBase::SendOnClose  
 Benachrichtigt alle Advise-Senken der Advise-Inhaber, dass das Steuerelement geschlossen wurde registriert.  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung, dass das Steuerelement die Advise-Senken geschlossen wurde.  
  
##  <a name="sendondatachange"></a>CComControlBase::SendOnDataChange  
 Benachrichtigt alle Advise-Senken registriert den Inhaber der anweisen, den die Daten des Steuerelements geändert wurde.  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *ADVF*  
 Empfehlen Sie Flags geben an, wie der Aufruf von [IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283) erfolgt. Die Werte reichen von der [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742) Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="sendonrename"></a>CComControlBase::SendOnRename  
 Benachrichtigt alle Advise-Senken, dass das Steuerelement einen neuen Moniker hat der Inhaber der Advise registriert.  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>Parameter  
 *PMK*  
 Ein Zeiger auf die neuen Moniker des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung, die der Moniker des Steuerelements geändert wurde.  
  
##  <a name="sendonsave"></a>CComControlBase::SendOnSave  
 Benachrichtigt alle Advise-Senken registriert den Inhaber der anweisen, den das Steuerelement gespeichert wurde.  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sendet eine Benachrichtigung, dass das Steuerelement seine Daten einfach gespeichert wurde.  
  
##  <a name="sendonviewchange"></a>CComControlBase::SendOnViewChange  
 Benachrichtigt alle registrierten Advise-Senken, die Ansicht des Steuerelements geändert wurde.  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>Parameter  
 `dwAspect`  
 Der Aspekt oder die Ansicht des Steuerelements.  
  
 *lindex*  
 Der Teil der Ansicht, die geändert wurde. Nur-1 ist ungültig.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 `SendOnViewChange`Aufrufe [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337). Der einzige Wert, der *Lindex* derzeit unterstützt ist-1 und gibt an, dass die gesamte Ansicht von Interesse ist.  
  
##  <a name="setcontrolfocus"></a>CComControlBase::SetControlFocus  
 Legt fest oder den Tastaturfokus in oder aus dem Steuerelement entfernt.  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>Parameter  
 *bGrab*  
 Wenn **TRUE**, legt den Tastaturfokus auf das aufrufende Steuerelement. Wenn **FALSE**, den Tastaturfokus des aufrufenden Steuerelements entfernt, sofern es den Fokus besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** , wenn das Steuerelement erfolgreich den Fokus erhält, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Für ein Fenstersteuerelement, die Windows-API-Funktion [SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312) aufgerufen wird. Für ein fensterloses Steuerelement [IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745) aufgerufen wird. Durch diesen Aufruf wird ein fensterloses Steuerelement den Tastaturfokus erhält und auf Windows-Meldungen reagieren kann.  
  
##  <a name="setdirty"></a>CComControlBase::SetDirty  
 Legt das Datenelement `m_bRequiresSave` mit dem Wert im `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Parameter  
 `bDirty`  
 Wert des Datenmembers [CComControlBase::m_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Hinweise  
 **SetDirty(TRUE)** aufgerufen werden, um zu kennzeichnen, dass das Steuerelement geändert wurde, seit es zuletzt gespeichert wurde. Der Wert der `m_bRequiresSave` wird abgerufen, mit [CComControlBase::GetDirty](#getdirty).  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

