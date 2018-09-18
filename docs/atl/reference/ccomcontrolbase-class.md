---
title: CComControlBase-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18666cc619796bc7ee0216eb9cdf020bd8d8a6f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035746"
---
# <a name="ccomcontrolbase-class"></a>CComControlBase-Klasse

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::AppearanceType](#appearancetype)|Überschreiben, wenn Ihre `m_nAppearance` Systemeigenschaft ist nicht vom Typ **kurze**.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::CComControlBase](#ccomcontrolbase)|Der Konstruktor.|
|[CComControlBase:: ~ CComControlBase](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Überprüft, ob die *iVerb* vom verwendeter Parameter `IOleObjectImpl::DoVerb` entweder die Benutzeroberfläche des Steuerelements aktiviert (*iVerb* OLEIVERB_UIACTIVATE entspricht), definiert die Aktion ausgeführt, wenn der Benutzer doppelklickt der Steuerelement (*iVerb* OLEIVERB_PRIMARY entspricht), zeigt das Steuerelement (*iVerb* OLEIVERB_SHOW entspricht), oder das Steuerelement aktiviert (*iVerb* OLEIVERB entspricht _INPLACEACTIVATE).|
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Überprüft, ob die *iVerb* vom verwendeter Parameter `IOleObjectImpl::DoVerb` bewirkt, dass Sie in der Benutzeroberfläche des Steuerelements zu aktivieren, und gibt TRUE zurück.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|Zeigt die Eigenschaftenseiten des Steuerelements.|
|[CComControlBase::FireViewChange](#fireviewchange)|Rufen Sie diese Methode zum Teilen Sie des Containers an das Steuerelement neu gezeichnet werden soll, oder benachrichtigen Sie die registrierten Advise-senken, die Ansicht des Steuerelements geändert wurde.|
|[CComControlBase](#getambientappearance)|Ruft die DISPID_AMBIENT_APPEARANCE, die aktuelle Darstellung, die Einstellung für das Steuerelement ab: 0 für flache und 1 für 3D.|
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Ruft die DISPID_AMBIENT_AUTOCLIP, ein Flag, der angibt, ob der Container unterstützt die automatische Clipping bei den Anzeigebereich des Steuerelements ab.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Ruft ab die DISPID_AMBIENT_BACKCOLOR, die ambient-Hintergrundfarbe für alle Steuerelemente, die vom Container definiert.|
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Ruft ab, DISPID_AMBIENT_CHARSET, die ambient-Zeichensatz für alle Steuerelemente, die vom Container definiert.|
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Ruft ab, DISPID_AMBIENT_CODEPAGE, die ambient-Zeichensatz für alle Steuerelemente, die vom Container definiert.|
|[CComControlBase:: GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Ruft ab die DISPID_AMBIENT_DISPLAYASDEFAULT, ein Flag, das TRUE ist, wenn der Container verfügt über das Steuerelement an diesem Standort eine Standardschaltfläche werden markiert, und daher ein Schaltflächen-Steuerelement selbst mit einem breiteren Rahmen zeichnen soll.|
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Ruft ab die DISPID_AMBIENT_DISPLAYNAME, den Namen, der Container für das Steuerelement angegeben wurde.|
|[CComControlBase::GetAmbientFont](#getambientfont)|Ruft ein Zeiger auf den Container dem ambient `IFont` Schnittstelle.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Ruft ein Zeiger auf den Container dem ambient `IFontDisp` Dispatch-Schnittstellen.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Ruft ab die DISPID_AMBIENT_FORECOLOR, die ambient-Vordergrundfarbe für alle Steuerelemente, die vom Container definiert.|
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Ruft die DISPID_AMBIENT_LOCALEID, den Bezeichner der vom Container verwendeten Sprache ab.|
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Ruft ab die DISPID_AMBIENT_MESSAGEREFLECT, ein Flag, der angibt, ob der Container fenstermeldungen (z. B. WM_DRAWITEM) als Ereignisse empfangen werden sollen.|
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Ruft die DISPID_AMBIENT_PALETTE, für den Zugriff auf den Container HPALETTE ab.|
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Ruft ab, die Containereigenschaft, die anhand des *Id*.|
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|Ruft die DISPID_AMBIENT_RIGHTTOLEFT, die Richtung, in dem Inhalt, durch den Container angezeigt wird, ab.|
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Ruft ab die DISPID_AMBIENT_SCALEUNITS, des Containers ambient-Einheiten (z. B. Zoll oder Zentimeter) für die Bezeichnung zeigt.|
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Ruft ab, DISPID_AMBIENT_SHOWGRABHANDLES, ein Flag, der angibt, ob der Container das Steuerelement zum Anzeigen der Ziehpunkte für sich selbst beim active zulässt.|
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Ruft ab die DISPID_AMBIENT_SHOWHATCHING, ein Flag, der angibt, ob der Container kann das Steuerelement selbst mit einer Schraffur angezeigt, wenn die Benutzeroberfläche aktiv ist.|
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Ruft ab die DISPID_AMBIENT_SUPPORTSMNEMONICS, ein Flag, der angibt, ob der Container Tastatur mnemonische Zeichen unterstützt.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Ruft DISPID_AMBIENT_TEXTALIGN, die Ausrichtung des Texts, die vom Container bevorzugt: 0 für die allgemeine Ausrichtung (Zahlen, Text rechts nach links), 1 für die linksbündige Ausrichtung, 2 für die Ausrichtung zentriert und 3 für Rechts-Ausrichtung.|
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|Ruft die DISPID_AMBIENT_TOPTOBOTTOM, die Richtung, in dem Inhalt, durch den Container angezeigt wird, ab.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Ruft ab die DISPID_AMBIENT_UIDEAD, ein Flag, der angibt, ob der Container das Steuerelement auf der Benutzeroberfläche Aktionen reagieren möchte.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Ruft ab die DISPID_AMBIENT_USERMODE, ein Flag, das angibt, ob der Container im Ausführungsmodus (TRUE) oder Entwurfsmodus (FALSE) ist.|
|[CComControlBase::GetDirty](#getdirty)|Gibt den Wert des Datenmembers `m_bRequiresSave`.|
|[CComControlBase::GetZoomInfo](#getzoominfo)|Ruft ab, der x- und y die Werte der Zähler und Nenner der Zoomfaktor für ein Steuerelement, für die aktiviert direkte Bearbeitung.|
|[CComControlBase::InPlaceActivate](#inplaceactivate)|Bewirkt, dass das Steuerelement für den Übergang von den inaktiven Status, was das Verb im Status *iVerb* angibt.|
|[CComControlBase::InternalGetSite](#internalgetsite)|Rufen Sie diese Methode, um die Website des Steuerelements für einen Zeiger auf die angegebene Schnittstelle Abfragen.|
|[CComControlBase:: OnDraw](#ondraw)|Überschreiben Sie diese Methode, um Ihr Steuerelement zu zeichnen.|
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Der Standardwert `OnDrawAdvanced` bereitet einen normalisierten Gerätekontext zum Zeichnen, und klicken Sie dann ruft der Steuerelementklasse `OnDraw` Methode.|
|[CComControlBase::OnKillFocus](#onkillfocus)|Überprüft, dass das Steuerelement direkt aktiv ist und verfügt über ein gültiges Steuerelement-Standort, und informiert dem Container, dass das Steuerelement den Fokus verloren hat.|
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Überprüft, dass die Benutzeroberfläche im Benutzermodus ist, wird das Steuerelement aktiviert.|
|[CComControlBase::OnPaint](#onpaint)|Wird der Container zum Zeichnen vorbereitet, ruft der Clientbereich des Steuerelements ab und ruft dann der Control-Klasse `OnDraw` Methode.|
|[CComControlBase::OnSetFocus](#onsetfocus)|Überprüft, dass das Steuerelement direkt aktiv ist und verfügt über ein gültiges Steuerelement-Standort, und den Container dem Steuerelement informiert den Fokus hat wurde hinzugefügt.|
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Überschreiben Sie diese Methode, um Ihre eigenen Tastatur Accelerator-Handler bereitstellen.|
|[CComControlBase::SendOnClose](#sendonclose)|Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, dass das Steuerelement geschlossen wurde.|
|[CComControlBase::SendOnDataChange](#sendondatachange)|Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, den die Daten des Steuerelements geändert wurde.|
|[CComControlBase::SendOnRename](#sendonrename)|Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, dass das Steuerelement über einen neuen Moniker verfügt.|
|[CComControlBase::SendOnSave](#sendonsave)|Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, den das Steuerelement gespeichert wurde.|
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Benachrichtigt, dass alle registrierten Advise-Senken, die Ansicht des Steuerelements geändert wurde.|
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Legt fest oder den Tastaturfokus zu oder aus dem Steuerelement entfernt.|
|[CComControlBase::SetDirty](#setdirty)|Legt den Datenmember `m_bRequiresSave` mit dem Wert im *bDirty*.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::m_bAutoSize](#m_bautosize)|Flag zum angeben, das Steuerelement kann eine beliebige andere Größe sein.|
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Flag gibt an, dass `IDataObjectImpl::GetData` und `CComControlBase::GetZoomInfo` sollte die Steuerelementgröße auf festgelegt `m_sizeNatural` anstatt von `m_sizeExtent`.|
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Flag gibt an, dass `IDataObjectImpl::GetData` sollten verwenden HIMETRIC-Einheiten und nicht in Pixel zeichnen.|
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Flag zum angeben, dass das Steuerelement direkt aktiv ist.|
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Flag zum angeben, die Container unterstützt die `IOleInPlaceSiteEx` -Schnittstelle und OCX96 steuern Sie Features, wie z. B. fensterlose und flimmerfrei Steuerelemente.|
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Flag zum angeben, unabhängig davon, ob das Steuerelement mit dem Container über die Unterstützung von Funktionen (z. B. flimmerfreie und Fensterlose Steuerelemente) OCX96 ausgehandelt wurde, und gibt an, ob das Steuerelement im Fenstermodus oder fensterlose ist.|
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Flag zum angeben, dass möchte, dass das Steuerelement die Präsentation neu anzuordnen, wenn der Container des Steuerelements Größe ändert.|
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Flag zum angeben, dass das Steuerelement seit der letzten Speicherung geändert hat.|
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Flag zum Angeben der möchte, dass des Steuerelements den natürlichen Umfang (die physische Größe) Ändern der Größe, wenn der Container des Steuerelements Größe ändert.|
|[CComControlBase::m_bUIActive](#m_buiactive)|Flag zum angeben, die Benutzeroberfläche des Steuerelements, z. B. Menüs und Symbolleisten, ist aktiv.|
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Flag zum angeben, dass das Steuerelement den Container bereitgestellten Fensterbereich verwendet.|
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Flag zum angeben, das Steuerelement wurde fensterlose, aber möglicherweise oder möglicherweise nicht fensterlos jetzt.|
|[CComControlBase](#m_bwindowonly)|Flag zum angeben, dass das Steuerelement im Fenstermodus, sein, auch wenn der Container Fensterlose Steuerelemente unterstützt.|
|[CComControlBase::m_bWndLess](#m_bwndless)|Flag zum angeben, dass das Steuerelement fensterlose ist.|
|[CComControlBase::m_hWndCD](#m_hwndcd)|Enthält einen Verweis auf das Fensterhandle, das dem Steuerelement zugeordnet.|
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Die Anzahl wie oft der Container hat Ereignisse (Ereignisse akzeptieren abgelehnt) ohne einen zwischenzeitlichen Entsperren von Ereignissen (Annahme von Ereignissen) fixiert.|
|[CComControlBase::m_rcPos](#m_rcpos)|Die Position in Pixel des Steuerelements, ausgedrückt in die Koordinaten des Containers.|
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Der Umfang des Steuerelements in HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter) für einen Bildschirm.|
|[CComControlBase::m_sizeNatural](#m_sizenatural)|Die physische Größe des Steuerelements in HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter).|
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Einen direkten Zeiger auf die Advise-Verbindung für den Container (des Containers [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink)).|
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Ein `CComDispatchDriver` -Objekt, das ermöglicht Ihnen das Abrufen und Festlegen von Eigenschaften des Containers, über eine `IDispatch` Zeiger.|
|[CComControlBase::m_spClientSite](#m_spclientsite)|Ein Zeiger auf Client-Standort innerhalb des Containers des Steuerelements.|
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Stellt ein Standard-Umgebung für die bereitzustellenden Advise-Verbindungen zwischen Datenobjekten advise-senken.|
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Ein Zeiger auf des Containers [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), oder [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) Schnittstellenzeiger auf.|
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Stellt eine Standardimplementierung von eine Möglichkeit zum Speichern der Advise-Verbindungen bereit.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen. [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md) leitet sich von `CComControlBase`. Wenn Sie über ein Standardsteuerelement oder DHTML-Steuerelement, mit dem ATL-Steuerelement-Assistenten erstellen, der Assistent wird automatisch Ableiten der Klasse aus `CComControlBase`.

Weitere Informationen zum Erstellen eines Steuerelements finden Sie unter den [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="appearancetype"></a>  CComControlBase::AppearanceType

Überschreiben, wenn Ihre `m_nAppearance` Systemeigenschaft ist nicht vom Typ **kurze**.

```
typedef short AppearanceType;
```

### <a name="remarks"></a>Hinweise

Der ATL-Steuerelement-Assistent fügt `m_nAppearance` vordefinierte Eigenschaft vom Typ short. Außer Kraft setzen `AppearanceType` Wenn Sie einen anderen Datentyp verwenden.

##  <a name="ccomcontrolbase"></a>  CComControlBase::CComControlBase

Der Konstruktor.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Das Handle für das Fenster, das dem Steuerelement zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

Initialisiert die Größe des Steuerelements zu 5080 X 5080 HIMETRIC-Einheiten (2 "X 2") und initialisiert die `CComControlBase` Datenmemberwerte auf NULL oder "false".

##  <a name="dtor"></a>  CComControlBase:: ~ CComControlBase

Der Destruktor.

```
~CComControlBase();
```

### <a name="remarks"></a>Hinweise

Wenn das Steuerelement im Fenstermodus, `~CComControlBase` zerstört es durch Aufrufen von [DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow).

##  <a name="controlqueryinterface"></a>  CComControlBase::ControlQueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>Parameter

*IID*<br/>
Die GUID der Schnittstelle angefordert wird.

*ppv*<br/>
Ein Zeiger auf den Schnittstellenzeiger vom *Iid*, oder NULL, wenn die Schnittstelle nicht gefunden wird.

### <a name="remarks"></a>Hinweise

behandelt nur Schnittstellen in der COM-Zuordnungstabelle.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

##  <a name="doesverbactivate"></a>  CComControlBase::DoesVerbActivate

Überprüft, ob die *iVerb* vom verwendeter Parameter `IOleObjectImpl::DoVerb` entweder die Benutzeroberfläche des Steuerelements aktiviert (*iVerb* OLEIVERB_UIACTIVATE entspricht), definiert die Aktion ausgeführt, wenn der Benutzer doppelklickt der Steuerelement (*iVerb* OLEIVERB_PRIMARY entspricht), zeigt das Steuerelement (*iVerb* OLEIVERB_SHOW entspricht), oder das Steuerelement aktiviert (*iVerb* OLEIVERB entspricht _INPLACEACTIVATE).

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Wert, der angibt, der Aktion, die durch erfolgen `DoVerb`.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn *iVerb* gleich OLEIVERB_UIACTIVATE OLEIVERB_PRIMARY, OLEIVERB_SHOW oder OLEIVERB_INPLACEACTIVATE zurückgegeben; andernfalls "false".

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um eigene Aktivierung Verb definieren überschreiben.

##  <a name="doesverbuiactivate"></a>  CComControlBase::DoesVerbUIActivate

Überprüft, ob die *iVerb* vom verwendeter Parameter `IOleObjectImpl::DoVerb` bewirkt, dass Sie in der Benutzeroberfläche des Steuerelements zu aktivieren, und gibt TRUE zurück.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Wert, der angibt, der Aktion, die durch erfolgen `DoVerb`.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn *iVerb* gleich OLEIVERB_UIACTIVATE OLEIVERB_PRIMARY, OLEIVERB_SHOW oder OLEIVERB_INPLACEACTIVATE. Andernfalls gibt die Methode "false" zurück.

##  <a name="doverbproperties"></a>  CComControlBase::DoVerbProperties

Zeigt die Eigenschaftenseiten des Steuerelements.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
Reserviert.

*hwndParent*<br/>
Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

##  <a name="fireviewchange"></a>  CComControlBase::FireViewChange

Rufen Sie diese Methode zum Teilen Sie des Containers an das Steuerelement neu gezeichnet werden soll, oder benachrichtigen Sie die registrierten Advise-senken, die Ansicht des Steuerelements geändert wurde.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Wenn das Steuerelement aktiv ist (die Steuerelement-Klassendatenmember [CComControlBase::m_bInPlaceActive](#m_binplaceactive) ist "true"), benachrichtigt Sie den Container, dass das gesamte Steuerelement neu gezeichnet werden soll. Wenn das Steuerelement inaktiv ist, benachrichtigt das Steuerelement der registrierten advise-senken (über die Control-Klassendatenmember [CComControlBase::m_spAdviseSink](#m_spadvisesink)), das des Steuerelements geändert hat.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

##  <a name="getambientappearance"></a>  CComControlBase

Ruft die DISPID_AMBIENT_APPEARANCE, die aktuelle Darstellung, die Einstellung für das Steuerelement ab: 0 für flache und 1 für 3D.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>Parameter

*nAppearance*<br/>
Die DISPID_AMBIENT_APPEARANCE-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

##  <a name="getambientautoclip"></a>  CComControlBase::GetAmbientAutoClip

Ruft die DISPID_AMBIENT_AUTOCLIP, ein Flag, der angibt, ob der Container unterstützt die automatische Clipping bei den Anzeigebereich des Steuerelements ab.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>Parameter

*bAutoClip*<br/>
Die DISPID_AMBIENT_AUTOCLIP-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientbackcolor"></a>  CComControlBase::GetAmbientBackColor

Ruft ab die DISPID_AMBIENT_BACKCOLOR, die ambient-Hintergrundfarbe für alle Steuerelemente, die vom Container definiert.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>Parameter

*Hintergrundfarbe*<br/>
Die DISPID_AMBIENT_BACKCOLOR-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientcharset"></a>  CComControlBase::GetAmbientCharSet

Ruft ab, DISPID_AMBIENT_CHARSET, die ambient-Zeichensatz für alle Steuerelemente, die vom Container definiert.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>Parameter

*bstrCharSet*<br/>
Die DISPID_AMBIENT_CHARSET-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="getambientcodepage"></a>  CComControlBase::GetAmbientCodePage

Ruft ab die DISPID_AMBIENT_CODEPAGE, die ambient-Codepage für alle Steuerelemente, die vom Container definiert.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>Parameter

*ulCodePage*<br/>
Die DISPID_AMBIENT_CODEPAGE-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="getambientdisplayasdefault"></a>  CComControlBase:: GetAmbientDisplayAsDefault

Ruft ab die DISPID_AMBIENT_DISPLAYASDEFAULT, ein Flag, das TRUE ist, wenn der Container verfügt über das Steuerelement an diesem Standort eine Standardschaltfläche werden markiert, und daher ein Schaltflächen-Steuerelement selbst mit einem breiteren Rahmen zeichnen soll.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>Parameter

*bDisplayAsDefault*<br/>
Die DISPID_AMBIENT_DISPLAYASDEFAULT-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientdisplayname"></a>  CComControlBase::GetAmbientDisplayName

Ruft ab die DISPID_AMBIENT_DISPLAYNAME, den Namen, der Container für das Steuerelement angegeben wurde.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>Parameter

*bstrDisplayName*<br/>
Die DISPID_AMBIENT_DISPLAYNAME-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientfont"></a>  CComControlBase::GetAmbientFont

Ruft ein Zeiger auf den Container dem ambient `IFont` Schnittstelle.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>Parameter

*ppFont*<br/>
Ein Zeiger auf den Container dem ambient [IFont](/windows/desktop/api/ocidl/nn-ocidl-ifont) Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Wenn die Eigenschaft NULL ist, ist der Zeiger NULL. Wenn der Zeiger nicht NULL ist, muss der Aufrufer den Zeiger freigeben.

##  <a name="getambientfontdisp"></a>  CComControlBase::GetAmbientFontDisp

Ruft ein Zeiger auf den Container dem ambient `IFontDisp` Dispatch-Schnittstellen.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parameter

*ppFont*<br/>
Ein Zeiger auf den Container dem ambient [IFontDisp](https://msdn.microsoft.com/library/windows/desktop/ms692695) Dispatch-Schnittstellen.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Wenn die Eigenschaft NULL ist, ist der Zeiger NULL. Wenn der Zeiger nicht NULL ist, muss der Aufrufer den Zeiger freigeben.

##  <a name="getambientforecolor"></a>  CComControlBase::GetAmbientForeColor

Ruft ab die DISPID_AMBIENT_FORECOLOR, die ambient-Vordergrundfarbe für alle Steuerelemente, die vom Container definiert.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>Parameter

*Vordergrundfarbe*<br/>
Die DISPID_AMBIENT_FORECOLOR-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientlocaleid"></a>  CComControlBase::GetAmbientLocaleID

Ruft die DISPID_AMBIENT_LOCALEID, den Bezeichner der vom Container verwendeten Sprache ab.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>Parameter

*lcid*<br/>
Die DISPID_AMBIENT_LOCALEID-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Das Steuerelement kann diesen Bezeichner verwenden, Anpassen die Benutzeroberfläche in verschiedenen Sprachen.

##  <a name="getambientmessagereflect"></a>  CComControlBase::GetAmbientMessageReflect

Ruft die DISPID_AMBIENT_MESSAGEREFLECT, ein Flag, der angibt, ob der Container fenstermeldungen empfangen werden sollen (z. B. `WM_DRAWITEM`) als Ereignisse.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>Parameter

*bMessageReflect*<br/>
Die DISPID_AMBIENT_MESSAGEREFLECT-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientpalette"></a>  CComControlBase::GetAmbientPalette

Ruft die DISPID_AMBIENT_PALETTE, für den Zugriff auf den Container HPALETTE ab.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>Parameter

*hPalette*<br/>
Die DISPID_AMBIENT_PALETTE-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientproperty"></a>  CComControlBase::GetAmbientProperty

Ruft ab, die Containereigenschaft, die anhand des *Dispid*.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Der Bezeichner für die Containereigenschaft abgerufen werden sollen.

*var*<br/>
Die Variable zum Empfangen der Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

ATL stellt eine Reihe von Hilfsfunktionen zum Abrufen der bestimmte Eigenschaften, z. B. [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Wenn keine passende Methode verfügbar ist, verwenden Sie `GetAmbientProperty`.

##  <a name="getambientrighttoleft"></a>  CComControlBase::GetAmbientRightToLeft

Ruft die DISPID_AMBIENT_RIGHTTOLEFT, die Richtung, in dem Inhalt, durch den Container angezeigt wird, ab.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>Parameter

*bRightToLeft*<br/>
Die DISPID_AMBIENT_RIGHTTOLEFT-Eigenschaft. Legen Sie auf "true", wenn Inhalt von rechts nach links, "false" angezeigt wird, wenn sie nach rechts nach links angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="getambientscaleunits"></a>  CComControlBase::GetAmbientScaleUnits

Ruft ab die DISPID_AMBIENT_SCALEUNITS, des Containers ambient-Einheiten (z. B. Zoll oder Zentimeter) für die Bezeichnung zeigt.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>Parameter

*bstrScaleUnits*<br/>
Die DISPID_AMBIENT_SCALEUNITS-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientshowgrabhandles"></a>  CComControlBase::GetAmbientShowGrabHandles

Ruft ab, DISPID_AMBIENT_SHOWGRABHANDLES, ein Flag, der angibt, ob der Container das Steuerelement zum Anzeigen der Ziehpunkte für sich selbst beim active zulässt.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>Parameter

*bShowGrabHandles*<br/>
Die DISPID_AMBIENT_SHOWGRABHANDLES-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientshowhatching"></a>  CComControlBase::GetAmbientShowHatching

Ruft ab die DISPID_AMBIENT_SHOWHATCHING, ein Flag, der angibt, ob der Container kann das Steuerelement selbst mit einer Schraffur angezeigt, wenn das Steuerelement der Benutzeroberfläche aktiv ist.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>Parameter

*bShowHatching*<br/>
Die DISPID_AMBIENT_SHOWHATCHING-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambientsupportsmnemonics"></a>  CComControlBase::GetAmbientSupportsMnemonics

Ruft ab die DISPID_AMBIENT_SUPPORTSMNEMONICS, ein Flag, der angibt, ob der Container Tastatur mnemonische Zeichen unterstützt.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>Parameter

*bSupportsMnemonics*<br/>
Die DISPID_AMBIENT_SUPPORTSMNEMONICS-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambienttextalign"></a>  CComControlBase::GetAmbientTextAlign

Ruft DISPID_AMBIENT_TEXTALIGN, die Ausrichtung des Texts, die vom Container bevorzugt: 0 für die allgemeine Ausrichtung (Zahlen, Text rechts nach links), 1 für die linksbündige Ausrichtung, 2 für die Ausrichtung zentriert und 3 für Rechts-Ausrichtung.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>Parameter

*nTextAlign*<br/>
Die DISPID_AMBIENT_TEXTALIGN-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getambienttoptobottom"></a>  CComControlBase::GetAmbientTopToBottom

Ruft die DISPID_AMBIENT_TOPTOBOTTOM, die Richtung, in dem Inhalt, durch den Container angezeigt wird, ab.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>Parameter

*bTopToBottom*<br/>
Die DISPID_AMBIENT_TOPTOBOTTOM-Eigenschaft. Auf "true" festgelegt werden, wenn der Text angezeigt wird von oben nach unten, "false" ist dies angezeigt, nach unten nach oben.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="getambientuidead"></a>  CComControlBase::GetAmbientUIDead

Ruft ab die DISPID_AMBIENT_UIDEAD, ein Flag, der angibt, ob der Container das Steuerelement auf der Benutzeroberfläche Aktionen reagieren möchte.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>Parameter

*bUIDead*<br/>
Die DISPID_AMBIENT_UIDEAD-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

True gibt an, soll das Steuerelement nicht reagieren. Dieses Flag gilt unabhängig von der DISPID_AMBIENT_USERMODE-Flag. Finden Sie unter [CComControlBase::GetAmbientUserMode](#getambientusermode).

##  <a name="getambientusermode"></a>  CComControlBase::GetAmbientUserMode

Ruft ab die DISPID_AMBIENT_USERMODE, ein Flag, das angibt, ob der Container im Ausführungsmodus (TRUE) oder Entwurfsmodus (FALSE) ist.

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>Parameter

*bUserMode*<br/>
Die DISPID_AMBIENT_USERMODE-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="getdirty"></a>  CComControlBase::GetDirty

Gibt den Wert des Datenmembers `m_bRequiresSave`.

```
BOOL GetDirty();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert des Datenmembers [M_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Hinweise

Dieser Wert wird festgelegt, mit [CComControlBase::SetDirty](#setdirty).

##  <a name="getzoominfo"></a>  CComControlBase::GetZoomInfo

Ruft ab, der x- und y die Werte der Zähler und Nenner der Zoomfaktor für ein Steuerelement, für die aktiviert direkte Bearbeitung.

```
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parameter

*Dependency Injection*<br/>
Die Struktur, die Zähler und Nenner des Zoomfaktor enthält. Weitere Informationen finden Sie unter [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).

### <a name="remarks"></a>Hinweise

Der Zoomfaktor ist der Anteil der Größe des Steuerelements in der aktuellen Umfang.

##  <a name="inplaceactivate"></a>  CComControlBase::InPlaceActivate

Bewirkt, dass das Steuerelement für den Übergang von den inaktiven Status, was das Verb im Status *iVerb* angibt.

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Wert, der angibt, der Aktion, die durch erfolgen [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).

*prcPosRect*<br/>
Zeiger auf die Position des direktes-Steuerelements.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Vor der Aktivierung überprüft diese Methode an, dass das Steuerelement verfügt über einen Clientstandort, überprüft, wie viel des Steuerelements sichtbar ist und ruft die Position des Steuerelements im übergeordneten Fenster ab. Nachdem das Steuerelement aktiviert ist, wird diese Methode wird die Benutzeroberfläche des Steuerelements aktiviert und weist den Container aus, um das Steuerelement sichtbar zu machen.

Diese Methode ruft auch ab einem `IOleInPlaceSite`, `IOleInPlaceSiteEx`, oder `IOleInPlaceSiteWindowless` Schnittstellenzeiger für das Steuerelement und speichert sie in der Steuerelementklasse Datenmember [CComControlBase::m_spInPlaceSite](#m_spinplacesite). Die Steuerelement-Klassendatenmember [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless), und [ CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) auf "true" entsprechend festgelegt werden.

##  <a name="internalgetsite"></a>  CComControlBase::InternalGetSite

Rufen Sie diese Methode, um die Website des Steuerelements für einen Zeiger auf die angegebene Schnittstelle Abfragen.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Die IID des Schnittstellenzeigers, die zurückgegeben werden sollen *PpUnkSite*.

*ppUnkSite*<br/>
Adresse der Zeigervariablen, die die im angeforderten Schnittstellenzeiger empfängt *Riid*.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Wenn der Standort über die Schnittstelle, die im angeforderten unterstützt *Riid*, die Zeiger zurückgegeben von *PpUnkSite*. Andernfalls *PpUnkSite* auf NULL festgelegt ist.

##  <a name="m_bautosize"></a>  CComControlBase::m_bAutoSize

Flag zum angeben, das Steuerelement kann eine beliebige andere Größe sein.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>Hinweise

Dieses Flag aktiviert ist, indem `IOleObjectImpl::SetExtent` und, wenn "true" bewirkt, dass die Funktion E_FAIL zurück.

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Wenn Sie beim Hinzufügen der **Größe automatisch anpassen** option die [Basiseigenschaften](../../atl/reference/stock-properties-atl-control-wizard.md) der ATL-Steuerelement-Assistent, den Assistenten auf der Registerkarte erstellt automatisch dieses Datenelement in der Steuerelementklasse, put erstellt und get-Methoden für die Eigenschaft , und unterstützt [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Container automatisch benachrichtigt, wenn die Eigenschaft geändert.

##  <a name="m_bdrawfromnatural"></a>  CComControlBase::m_bDrawFromNatural

Flag gibt an, dass `IDataObjectImpl::GetData` und `CComControlBase::GetZoomInfo` sollte die Steuerelementgröße auf festgelegt `m_sizeNatural` anstatt von `m_sizeExtent`.

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_bdrawgetdatainhimetric"></a>  CComControlBase::m_bDrawGetDataInHimetric

Flag gibt an, dass `IDataObjectImpl::GetData` sollten verwenden HIMETRIC-Einheiten und nicht in Pixel zeichnen.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>Hinweise

Jede logische HIMETRIC-Einheit ist 0,01 Millimeter.

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_binplaceactive"></a>  CComControlBase::m_bInPlaceActive

Flag zum angeben, dass das Steuerelement direkt aktiv ist.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>Hinweise

Dies bedeutet, dass das Steuerelement sichtbar ist und das Fenster, falls vorhanden, ist sichtbar, aber seine Menüs und Symbolleisten nicht aktiv sein. Die `m_bUIActive` Flag gibt an, auch des Steuerelements-Benutzeroberfläche, z. B. Menüs, aktiv ist.

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_binplacesiteex"></a>  CComControlBase::m_bInPlaceSiteEx

Flag zum angeben, die Container unterstützt die `IOleInPlaceSiteEx` -Schnittstelle und OCX96 steuern Sie Features, wie z. B. fensterlose und flimmerfrei Steuerelemente.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Das Datenelement `m_spInPlaceSite` verweist auf eine [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), oder [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) -Schnittstelle, abhängig vom Wert der `m_bWndLess` und `m_bInPlaceSiteEx` Flags. (Der den Datenmember `m_bNegotiatedWnd` muss "true" für die `m_spInPlaceSite` Zeiger gültig ist.)

Wenn `m_bWndLess` ist "false" und `m_bInPlaceSiteEx` ist "true", `m_spInPlaceSite` ist ein `IOleInPlaceSiteEx` Schnittstellenzeiger auf. Finden Sie unter [M_spInPlaceSite](#m_spinplacesite) für eine Tabelle mit den Beziehungen zwischen diesen drei Datenmember.

##  <a name="m_bnegotiatedwnd"></a>  CComControlBase::m_bNegotiatedWnd

Flag zum angeben, unabhängig davon, ob das Steuerelement mit dem Container über die Unterstützung von Funktionen (z. B. flimmerfreie und Fensterlose Steuerelemente) OCX96 ausgehandelt wurde, und gibt an, ob das Steuerelement im Fenstermodus oder fensterlose ist.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Die `m_bNegotiatedWnd` Flag muss "true" werden für die `m_spInPlaceSite` Zeiger gültig ist.

##  <a name="m_brecomposeonresize"></a>  CComControlBase::m_bRecomposeOnResize

Flag zum angeben, dass möchte, dass das Steuerelement die Präsentation neu anzuordnen, wenn der Container des Steuerelements Größe ändert.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Dieses Flag aktiviert ist, indem [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) und, falls "true" `SetExtent` benachrichtigt den Container der Änderungen anzeigen. Wenn dieses Flag festgelegt ist, wird die OLEMISC_RECOMPOSEONRESIZE in bit der [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Enumeration muss auch festgelegt werden.

##  <a name="m_brequiressave"></a>  CComControlBase::m_bRequiresSave

Flag zum angeben, dass das Steuerelement seit der letzten Speicherung geändert hat.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>Hinweise

Der Wert des `m_bRequiresSave` kann festgelegt werden, mit [CComControlBase::SetDirty](#setdirty) und abgerufene mit [CComControlBase::GetDirty](#getdirty).

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_bresizenatural"></a>  CComControlBase::m_bResizeNatural

Flag zum Angeben der möchte, dass des Steuerelements den natürlichen Umfang (die physische Größe) Ändern der Größe, wenn der Container des Steuerelements Größe ändert.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>Hinweise

Dieses Flag aktiviert ist, indem `IOleObjectImpl::SetExtent` und, wenn "true", wird die Größe in übergeben `SetExtent` zugewiesen `m_sizeNatural`.

Übergeben Sie die Größe in `SetExtent` ist immer zugewiesen `m_sizeExtent`, unabhängig vom Wert der `m_bResizeNatural`.

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_buiactive"></a>  CComControlBase::m_bUIActive

Flag zum angeben, die Benutzeroberfläche des Steuerelements, z. B. Menüs und Symbolleisten, ist aktiv.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>Hinweise

Die `m_bInPlaceActive` Flag gibt an, dass das Steuerelement aktiv, aber nicht, die die Benutzeroberfläche aktiv ist.

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_busingwindowrgn"></a>  CComControlBase::m_bUsingWindowRgn

Flag zum angeben, dass das Steuerelement den Container bereitgestellten Fensterbereich verwendet.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_bwasoncewindowless"></a>  CComControlBase::m_bWasOnceWindowless

Flag zum angeben, das Steuerelement wurde fensterlose, aber möglicherweise oder möglicherweise nicht fensterlos jetzt.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_bwindowonly"></a>  CComControlBase

Flag zum angeben, dass das Steuerelement im Fenstermodus, sein, auch wenn der Container Fensterlose Steuerelemente unterstützt.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_bwndless"></a>  CComControlBase::m_bWndLess

Flag zum angeben, dass das Steuerelement fensterlose ist.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Das Datenelement `m_spInPlaceSite` verweist auf eine [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), oder [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) -Schnittstelle, abhängig vom Wert der `m_bWndLess` und [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) Flags. (Der den Datenmember [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) muss "true" für die [CComControlBase::m_spInPlaceSite](#m_spinplacesite) Zeiger gültig ist.)

Wenn `m_bWndLess` ist "true", `m_spInPlaceSite` ist ein `IOleInPlaceSiteWindowless` Schnittstellenzeiger auf. Finden Sie unter [CComControlBase::m_spInPlaceSite](#m_spinplacesite) für eine Tabelle, die die vollständige Beziehung zwischen diesen Datenmembern anzeigt.

##  <a name="m_hwndcd"></a>  CComControlBase::m_hWndCD

Enthält einen Verweis auf das Fensterhandle, das dem Steuerelement zugeordnet.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_nfreezeevents"></a>  CComControlBase::m_nFreezeEvents

Die Anzahl wie oft der Container hat Ereignisse (Ereignisse akzeptieren abgelehnt) ohne einen zwischenzeitlichen Entsperren von Ereignissen (Annahme von Ereignissen) fixiert.

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_rcpos"></a>  CComControlBase::m_rcPos

Die Position in Pixel des Steuerelements, ausgedrückt in die Koordinaten des Containers.

```
RECT m_rcPos;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_sizeextent"></a>  CComControlBase::m_sizeExtent

Der Umfang des Steuerelements in HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter) für einen Bildschirm.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Diese Größe wird durch die Anzeige skaliert. Physische Größe des Steuerelements angegeben ist, der `m_sizeNatural` -Datenmember und wurde behoben.

Sie können die Größe in Pixeln mit der globalen Funktion konvertieren [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).

##  <a name="m_sizenatural"></a>  CComControlBase::m_sizeNatural

Die physische Größe des Steuerelements in HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter).

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Dieser Größe wurde behoben, bei der die Größe in `m_sizeExtent` die Anzeige skaliert wird.

Sie können die Größe in Pixeln mit der globalen Funktion konvertieren [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).

##  <a name="m_spadvisesink"></a>  CComControlBase::m_spAdviseSink

Einen direkten Zeiger auf die Advise-Verbindung für den Container (des Containers [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink)).

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_spambientdispatch"></a>  CComControlBase::m_spAmbientDispatch

Ein `CComDispatchDriver` -Objekt, das ermöglicht Ihnen das Abrufen und Festlegen der Eigenschaften eines Objekts über eine `IDispatch` Zeiger.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_spclientsite"></a>  CComControlBase::m_spClientSite

Ein Zeiger auf Client-Standort innerhalb des Containers des Steuerelements.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

##  <a name="m_spdataadviseholder"></a>  CComControlBase::m_spDataAdviseHolder

Stellt ein Standard-Umgebung für die bereitzustellenden Advise-Verbindungen zwischen Datenobjekten advise-senken.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Ein Datenobjekt ist ein Steuerelement, das Daten übertragen werden kann, und implementiert [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject), deren Methoden geben Sie das Medium Format und die Übertragung der Daten.

Die Schnittstelle `m_spDataAdviseHolder` implementiert die [IDataObject::DAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise) und [IDataObject::DUnadvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dunadvise) Methoden zum Einrichten und die Advise-Verbindungen auf den Container löschen. Der Container des Steuerelements muss eine Advise-Senke implementieren, durch die Unterstützung der [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) Schnittstelle.

##  <a name="m_spinplacesite"></a>  CComControlBase::m_spInPlaceSite

Ein Zeiger auf des Containers [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), oder [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) Schnittstellenzeiger auf.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Die `m_spInPlaceSite` Zeiger gilt nur, wenn die [M_bNegotiatedWnd](#m_bnegotiatedwnd) Flag ist "true".

Die folgende Tabelle zeigt, wie die `m_spInPlaceSite` Zeigertyp hängt von der [M_bWndLess](#m_bwndless) und [M_bInPlaceSiteEx](#m_binplacesiteex) Data-Member-Flags:

|M_spInPlaceSite Typ|M_bWndLess Wert|M_bInPlaceSiteEx Wert|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|true|"True" oder "false"|
|`IOleInPlaceSiteEx`|false|true|
|`IOleInPlaceSite`|false|false|

##  <a name="m_spoleadviseholder"></a>  CComControlBase::m_spOleAdviseHolder

Stellt eine Standardimplementierung von eine Möglichkeit zum Speichern der Advise-Verbindungen bereit.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenelement in der Steuerelementklasse verwenden zu können, müssen Sie es als Datenmember in der Steuerelementklasse deklarieren. Die Steuerelementklasse wird dieses Datenelement nicht von der Basisklasse erben, da es in einer Union in der Basisklasse deklariert ist.

Die Schnittstelle `m_spOleAdviseHolder` implementiert die [IOleObject::Advise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise) und [IOleObject::Unadvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-unadvise) Methoden zum Einrichten und die Advise-Verbindungen auf den Container löschen. Der Container des Steuerelements muss eine Advise-Senke implementieren, durch die Unterstützung der [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) Schnittstelle.

##  <a name="ondraw"></a>  CComControlBase:: OnDraw

Überschreiben Sie diese Methode, um Ihr Steuerelement zu zeichnen.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parameter

*Dependency Injection*<br/>
Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) Struktur, zeichnen Informationen wie z. B. den Draw-Aspekt der Begrenzungen des Steuerelements, und gibt an, ob das Zeichnen optimiert ist oder nicht.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Der Standardwert `OnDraw` löscht den Gerätekontext wiederhergestellt oder hat keine Auswirkungen, je nachdem in festgelegten Flags [CComControlBase::OnDrawAdvanced](#ondrawadvanced).

Ein `OnDraw` Methode wird automatisch der Steuerelement-Klasse hinzugefügt, wenn Sie das Steuerelement mit dem ATL-Steuerelement-Assistenten erstellen. Des Assistenten standardmäßig `OnDraw` zeichnet ein Rechteck mit der Bezeichnung "ATL 8.0".

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CComControlBase](#getambientappearance).

##  <a name="ondrawadvanced"></a>  CComControlBase::OnDrawAdvanced

Der Standardwert `OnDrawAdvanced` bereitet einen normalisierten Gerätekontext zum Zeichnen, und klicken Sie dann ruft der Steuerelementklasse `OnDraw` Methode.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parameter

*Dependency Injection*<br/>
Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) Struktur, zeichnen Informationen wie z. B. den Draw-Aspekt der Begrenzungen des Steuerelements, und gibt an, ob das Zeichnen optimiert ist oder nicht.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, wenn Sie den vom Container übergeben werden, ohne ihn zu normalisieren Gerätekontext akzeptieren möchten.

Finden Sie unter [CComControlBase:: OnDraw](#ondraw) Weitere Details.

##  <a name="onkillfocus"></a>  CComControlBase::OnKillFocus

Überprüft, dass das Steuerelement direkt aktiv ist und verfügt über ein gültiges Steuerelement-Standort, und informiert dem Container, dass das Steuerelement den Fokus verloren hat.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam-Parameter*<br/>
Reserviert.

*lParam*<br/>
Reserviert.

*bHandled*<br/>
Flag, die angibt, ob die fenstermeldung wurde erfolgreich verarbeitet wurde. Der Standardwert ist "false".

### <a name="return-value"></a>Rückgabewert

Gibt immer 1 zurück.

##  <a name="onmouseactivate"></a>  CComControlBase::OnMouseActivate

Überprüft, dass die Benutzeroberfläche im Benutzermodus ist, wird das Steuerelement aktiviert.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam-Parameter*<br/>
Reserviert.

*lParam*<br/>
Reserviert.

*bHandled*<br/>
Flag, die angibt, ob die fenstermeldung wurde erfolgreich verarbeitet wurde. Der Standardwert ist "false".

### <a name="return-value"></a>Rückgabewert

Gibt immer 1 zurück.

##  <a name="onpaint"></a>  CComControlBase::OnPaint

Wird der Container zum Zeichnen vorbereitet, ruft der Clientbereich des Steuerelements ab und ruft dann der Control-Klasse `OnDrawAdvanced` Methode.

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam-Parameter*<br/>
Eine vorhandene HDC.

*lParam*<br/>
Reserviert.

*lResult*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt immer 0 (null) zurück.

### <a name="remarks"></a>Hinweise

Wenn *wParam* ist nicht NULL, `OnPaint` wird vorausgesetzt, dass es enthält eine gültige HDC verwendet ihn anstelle von [CComControlBase::m_hWndCD](#m_hwndcd).

##  <a name="onsetfocus"></a>  CComControlBase::OnSetFocus

Überprüft, dass das Steuerelement direkt aktiv ist und verfügt über ein gültiges Steuerelement-Standort, und den Container dem Steuerelement informiert den Fokus hat wurde hinzugefügt.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam-Parameter*<br/>
Reserviert.

*lParam*<br/>
Reserviert.

*bHandled*<br/>
Flag, die angibt, ob die fenstermeldung wurde erfolgreich verarbeitet wurde. Der Standardwert ist "false".

### <a name="return-value"></a>Rückgabewert

Gibt immer 1 zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung an den Container, dass das Steuerelement den Fokus erhalten hat.

##  <a name="pretranslateaccelerator"></a>  CComControlBase::PreTranslateAccelerator

Überschreiben Sie diese Methode, um Ihre eigenen Tastatur Accelerator-Handler bereitstellen.

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
Reserviert.

*hRet*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Standardmäßig wird FALSE zurückgegeben.

##  <a name="sendonclose"></a>  CComControlBase::SendOnClose

Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, dass das Steuerelement geschlossen wurde.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung, dass das Steuerelement die Advise-Senken geschlossen wurde.

##  <a name="sendondatachange"></a>  CComControlBase::SendOnDataChange

Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, den die Daten des Steuerelements geändert wurde.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>Parameter

*ADVF*<br/>
Empfehlen von Flags, die angeben, wie der Aufruf von [IAdviseSink::OnDataChange](/windows/desktop/api/objidl/nf-objidl-iadvisesink-ondatachange) erfolgt. Werte reichen von der [ADVF](/windows/desktop/api/objidl/ne-objidl-tagadvf) Enumeration.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="sendonrename"></a>  CComControlBase::SendOnRename

Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, dass das Steuerelement über einen neuen Moniker verfügt.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>Parameter

*PMK*<br/>
Zeiger auf den neuen Moniker des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung, die der Moniker des Steuerelements geändert wurde.

##  <a name="sendonsave"></a>  CComControlBase::SendOnSave

Benachrichtigt alle Advise-Senken registriert mit der Advise-Inhaber, den das Steuerelement gespeichert wurde.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung, dass das Steuerelement seine Daten einfach gespeichert wurde.

##  <a name="sendonviewchange"></a>  CComControlBase::SendOnViewChange

Benachrichtigt, dass alle registrierten Advise-Senken, die Ansicht des Steuerelements geändert wurde.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>Parameter

*dwAspect*<br/>
Der Aspekt oder die Ansicht des Steuerelements.

*lindex*<br/>
Der Teil der Sicht, die geändert wurde. Es ist nur-1 gültig.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

`SendOnViewChange` Aufrufe [IAdviseSink::OnViewChange](/windows/desktop/api/objidl/nf-objidl-iadvisesink-onviewchange). Der einzige Wert, der *Lindex* ist-1 gibt an, dass die gesamte Ansicht von Interesse ist derzeit nicht unterstützt.

##  <a name="setcontrolfocus"></a>  CComControlBase::SetControlFocus

Legt fest oder den Tastaturfokus zu oder aus dem Steuerelement entfernt.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>Parameter

*bGrab*<br/>
True gibt an, legt den Tastaturfokus an das aufrufende Steuerelement fest. False gibt an, entfernt den Tastaturfokus des aufrufenden-Steuerelements, vorausgesetzt es den Fokus besitzt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Steuerelement erfolgreich den Fokus erhält. andernfalls "false".

### <a name="remarks"></a>Hinweise

Für ein Steuerelement mit Fenster, die Windows-API-Funktion [SetFocus](https://msdn.microsoft.com/library/windows/desktop/ms646312) aufgerufen wird. Bei einem fensterlosen Steuerelement [IOleInPlaceSiteWindowless::SetFocus](/windows/desktop/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) aufgerufen wird. Durch diesen Aufruf ein fensterloses Steuerelement den Tastaturfokus erhält und auf Windows-Meldungen reagieren kann.

##  <a name="setdirty"></a>  CComControlBase::SetDirty

Legt den Datenmember `m_bRequiresSave` mit dem Wert im *bDirty*.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parameter

*bDirty*<br/>
Der Wert des Datenmembers [CComControlBase::m_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Hinweise

`SetDirty(TRUE)` sollte aufgerufen werden, um zu kennzeichnen, dass das Steuerelement seit der letzten Speicherung geändert hat. Der Wert des `m_bRequiresSave` wird abgerufen, mit [CComControlBase::GetDirty](#getdirty).

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
