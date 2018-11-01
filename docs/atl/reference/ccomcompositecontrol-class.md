---
title: CComCompositeControl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
ms.openlocfilehash: 370f0bb2fc76e1377dce6ae4616861085ad44562
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429041"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl-Klasse

Diese Klasse stellt die Methoden erforderlich, um ein zusammengesetztes Steuerelement zu implementieren.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das zusammengesetzte Steuerelement unterstützt werden soll.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Der Konstruktor.|
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[:: AdviseSinkMap](#advisesinkmap)|Rufen Sie diese Methode oder alle Steuerelemente, die durch das zusammengesetzte Steuerelement gehostet abzumelden.|
|[CComCompositeControl::CalcExtent](#calcextent)|Rufen Sie diese Methode, um die Größe in HIMETRIC-Einheiten der Dialogfeldressource zum Hosten des zusammengesetzten Steuerelements zu berechnen.|
|[CComCompositeControl::Create](#create)|Diese Methode wird aufgerufen, um die Steuerelementfenster für das zusammengesetzte Steuerelement zu erstellen.|
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Rufen Sie diese Methode, um das Fenster des Steuerelements zu erstellen und zu beraten alle gehosteten Steuerelements.|
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Rufen Sie diese Methode, um die Hintergrundfarbe des zusammengesetzten Steuerelements mit der Hintergrundfarbe des Containers festgelegt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Der Hintergrundpinsel.|
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Das Handle des Fensters, das gerade den Fokus besitzt.|

## <a name="remarks"></a>Hinweise

Abgeleitete Klassen von Klasse `CComCompositeControl` erben die Funktionalität eines zusammengesetzten ActiveX-Steuerelements. ActiveX-Steuerelemente, die von abgeleiteten `CComCompositeControl` von ein Standarddialogfeld gehostet werden. Diese Arten von Steuerelementen sind zusammengesetzte Steuerelemente wird aufgerufen, da sie andere Steuerelemente (systemeigene Windows-Steuerelemente und ActiveX-Steuerelemente) hosten können.

`CComCompositeControl` identifiziert die Ressource beim Erstellen des zusammengesetzten Steuerelements anhand der für einen enumerierten Datenmember in der untergeordneten Klasse an. Das Element IDD dieser untergeordneten Klasse wird auf die Ressourcen-ID der Dialogfeldressource festgelegt, der als das Fenster des Steuerelements verwendet wird. Folgendes ist ein Beispiel für das Datenelement, das von die Klasse abgeleitet `CComCompositeControl` sollten enthalten, um die Ressource, die für das Fenster des Steuerelements verwendet werden zu identifizieren:

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
>  Zusammengesetzte Steuerelemente werden immer im Fenstermodus, obwohl sie Fensterlose Steuerelemente enthalten können.

Ein Steuerelement implementiert, indem eine `CComCompositeControl`-abgeleitete Klasse verfügt über Standardverhalten integriert. Wenn das Steuerelement den Fokus erhält, durch Sie wird im Registerkartenformat in einer Anwendung, nach Drücken der TAB-Taste führt dazu, dass den Fokus auf das zusammengesetzte Steuerelement enthaltenen Steuerelemente, und klicken Sie dann aus der zusammengesetzten Steuerelements und dem nächsten Element in durchlaufen werden die die Aktivierreihenfolge des Containers. Die Aktivierreihenfolge des den gehosteten Steuerelementen richtet sich nach der Dialogfeldressource und bestimmt die Reihenfolge, in die TAB-Taste erfolgt.

> [!NOTE]
>  In der Reihenfolge für Accelerators ordnungsgemäß funktioniert mit einer `CComCompositeControl`, es ist notwendig, laden eine Zugriffstastentabelle, wie das Steuerelement erstellt wurde, übergeben Sie das Handle und die Anzahl von Schnellinfos wieder [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), und Zerstören Sie schließlich in der Tabelle auf, wenn das Steuerelement freigegeben wird.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="advisesinkmap"></a>  :: AdviseSinkMap

Rufen Sie diese Methode oder alle Steuerelemente, die durch das zusammengesetzte Steuerelement gehostet abzumelden.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parameter

*bAdvise*<br/>
True, wenn alle Steuerelemente sind, darüber informiert zu werden. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

|||
|-|-|
|S_OK  |Alle Steuerelemente im Ereignisprotokoll Sink-Zuordnung verbunden oder getrennt von ihrer Ereignisquelle erfolgreich waren.|
|E_FAIL  |Nicht alle Steuerelemente im Ereignisprotokoll Sink-Zuordnung verbunden oder getrennt von ihrer Ereignisquelle wurde erfolgreich sein kann.|
|E_POINTER  |Dieser Fehler in der Regel gibt an, ein Problem mit einem Eintrag in die Senke-ereigniszuordnung des Steuerelements oder ein Problem mit einem Vorlagenargument verwendet eine `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse.|
|CONNECT_E_ADVISELIMIT  |Der Verbindungspunkt hat bereits die maximale Anzahl von Verbindungen erreicht und kann nicht mehr annehmen.|
|CONNECT_E_CANNOTCONNECT  |Die Senke unterstützt nicht die von diesem Verbindungspunkt erforderliche Schnittstelle.|
|CONNECT_E_NOCONNECTION  |Der Cookiewert stellt keine gültige Verbindung dar. Dieser Fehler in der Regel gibt an, ein Problem mit einem Eintrag in die Senke-ereigniszuordnung des Steuerelements oder ein Problem mit einem Vorlagenargument verwendet eine `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse.|

### <a name="remarks"></a>Hinweise

Die grundlegende Implementierung dieser Methode durchsucht die Einträge in der ereignismeldung Sink-Zuordnung. Anschließend weist oder hebt Anweisungen für die Verbindungspunkte, die COM-Objekte, die von der Senke ereigniszuordnung der Senke Einträge beschrieben. Diese Membermethode auch ist es erforderlich, die eine Instanz die abgeleitete Klasse erbt `IDispEventImpl` für jedes Steuerelement in der Senke-Zuordnung, die empfohlen oder abzumelden sein.

##  <a name="calcextent"></a>  CComCompositeControl::CalcExtent

Rufen Sie diese Methode, um die Größe in HIMETRIC-Einheiten der Dialogfeldressource zum Hosten des zusammengesetzten Steuerelements zu berechnen.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Ein Verweis auf eine `SIZE` Struktur, die von dieser Methode gefüllt werden.

### <a name="return-value"></a>Rückgabewert

True, wenn das Steuerelement von einem Dialogfeld gehostet wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Die Größe wird zurückgegeben, der *Größe* Parameter.

##  <a name="create"></a>  CComCompositeControl::Create

Diese Methode wird aufgerufen, um die Steuerelementfenster für das zusammengesetzte Steuerelement zu erstellen.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das übergeordnete Fenster des Steuerelements.

*rcPos*<br/>
Reserviert.

*dwInitParam*<br/>
Die Daten während der steuerelementerstellung das Steuerelement übergeben werden soll. Die Daten zu übergeben, als *DwInitParam* als der LPARAM-Parameter, der angezeigt wird der [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) -Nachricht, die an das zusammengesetzte Steuerelement gesendet wird, wenn sie erstellt wird.

### <a name="return-value"></a>Rückgabewert

Ein Handle für das Dialogfeld für die neu erstellte zusammengesetztes Steuerelement.

### <a name="remarks"></a>Hinweise

Diese Methode wird in der Regel während der direkten Aktivierung des Steuerelements aufgerufen.

##  <a name="ccomcompositecontrol"></a>  CComCompositeControl::CComCompositeControl

Der Konstruktor.

```
CComCompositeControl();
```

### <a name="remarks"></a>Hinweise

Initialisiert die [CComCompositeControl::m_hbrBackground](#m_hbrbackground) und [CComCompositeControl::m_hWndFocus](#m_hwndfocus) Datenmember auf NULL.

##  <a name="dtor"></a>  CComCompositeControl:: ~ CComCompositeControl

Der Destruktor.

```
~CComCompositeControl();
```

### <a name="remarks"></a>Hinweise

Löscht das Hintergrund-Objekt, falls vorhanden.

##  <a name="createcontrolwindow"></a>  CComCompositeControl::CreateControlWindow

Rufen Sie diese Methode, um das Fenster des Steuerelements zu erstellen und alle gehosteten Steuerelemente empfehlen.

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das übergeordnete Fenster des Steuerelements.

*rcPos*<br/>
Das Positionsrechteck des zusammengesetzten Steuerelements in Client-Koordinaten relativ zum *hWndParent*.

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle an das Dialogfeld für die neu erstellte zusammengesetzten Steuerelements zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [CComCompositeControl::Create](#create) und [:: AdviseSinkMap](#advisesinkmap).

##  <a name="m_hbrbackground"></a>  CComCompositeControl::m_hbrBackground

Der Hintergrundpinsel.

```
HBRUSH m_hbrBackground;
```

##  <a name="m_hwndfocus"></a>  CComCompositeControl::m_hWndFocus

Das Handle des Fensters, das gerade den Fokus besitzt.

```
HWND m_hWndFocus;
```

##  <a name="setbackgroundcolorfromambient"></a>  CComCompositeControl::SetBackgroundColorFromAmbient

Rufen Sie diese Methode, um die Hintergrundfarbe des zusammengesetzten Steuerelements mit der Hintergrundfarbe des Containers festgelegt.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
