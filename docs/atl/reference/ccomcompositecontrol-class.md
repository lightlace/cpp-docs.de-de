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
ms.openlocfilehash: b57eaf105bfca1a49d53b5e5e99969b0fa2fc82f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497336"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl-Klasse

Diese Klasse stellt die Methoden bereit, die zum Implementieren eines zusammengesetzten Steuer Elements erforderlich sind.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Ihre Klasse, abgeleitet von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), sowie von anderen Schnittstellen, die Sie für Ihr zusammengesetztes Steuerelement unterstützen möchten.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Der Konstruktor.|
|[CComCompositeControl::~CComCompositeControl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Mit dieser Methode können Sie alle Steuerelemente, die vom zusammengesetzten Steuerelement gehostet werden, informieren oder deren Empfehlung deaktivieren|
|[CComCompositeControl::CalcExtent](#calcextent)|Mit dieser Methode können Sie die Größe in den HIMETRIC-Einheiten der Dialog Ressource berechnen, die zum Hosten des zusammengesetzten Steuer Elements verwendet wird.|
|[CComCompositeControl::Create](#create)|Diese Methode wird aufgerufen, um das Steuerelement Fenster für das zusammengesetzte Steuerelement zu erstellen.|
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Rufen Sie diese Methode auf, um das Steuerelement Fenster zu erstellen und alle gehosteten Steuerelemente zu|
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Mit dieser Methode können Sie die Hintergrundfarbe des zusammengesetzten Steuer Elements mit der Hintergrundfarbe des Containers festlegen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Der Hintergrund Pinsel.|
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Das Handle des Fensters, das derzeit den Fokus besitzt.|

## <a name="remarks"></a>Hinweise

Von der-Klasse `CComCompositeControl` abgeleitete Klassen erben die Funktionalität eines zusammengesetzten ActiveX-Steuer Elements. Von abgeleitete `CComCompositeControl` ActiveX-Steuerelemente werden von einem Standard Dialogfeld gehostet. Diese Steuerelement Typen werden als zusammengesetzte Steuerelemente bezeichnet, da Sie andere Steuerelemente (systemeigene Windows-Steuerelemente und ActiveX-Steuerelemente) hosten können.

`CComCompositeControl`Gibt die für die Erstellung des zusammengesetzten Steuer Elements zu verwendende Dialog Ressource an, indem nach einem enumerierten Datenmember in der untergeordneten Klasse gesucht wird. Das IDD-Element dieser untergeordneten Klasse ist auf die Ressourcen-ID der Dialogfeld Ressource festgelegt, die als Fenster des Steuer Elements verwendet wird. Im folgenden finden Sie ein Beispiel für den Datenmember, den die von `CComCompositeControl` abgeleitete Klasse enthalten sollte, um die für das Fenster des Steuer Elements zu verwendende Dialog Ressource zu identifizieren:

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
>  Zusammengesetzte Steuerelemente sind immer Fenster Steuerelemente, obwohl Sie Fensterlose Steuerelemente enthalten können.

Ein-Steuerelement, `CComCompositeControl`das von einer von abgeleiteten Klasse implementiert wird, verfügt über ein in integriertes Standardverhalten. Wenn das Steuerelement den Fokus erhält, indem es in einer enthaltenden Anwendung als Registerkarte verwendet wird, führt die durch Drücken der Tab-Taste dazu, dass der Fokus durch alle enthaltenen Steuerelemente des zusammengesetzten Steuer Elements, dann vom zusammengesetzten Steuerelement bis zum nächsten Element im Aktivier Reihenfolge des Containers. Die Aktivier Reihenfolge der gehosteten Steuerelemente wird von der Dialogfeld Ressource bestimmt und bestimmt die Reihenfolge, in der Tabulatoren ausgeführt werden.

> [!NOTE]
>  Damit Accelerators ordnungsgemäß mit einem `CComCompositeControl`funktionieren, muss bei der Erstellung des Steuer Elements eine Zugriffstasten Tabelle geladen, das Handle und die Anzahl von Accelerators zurück an [iolecontrolimpl:: GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)übergeben und schließlich die Tabelle zerstört werden. Wenn das Steuerelement freigegeben wird.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="advisesinkmap"></a>CComCompositeControl:: AdviseSinkMap

Mit dieser Methode können Sie alle Steuerelemente, die vom zusammengesetzten Steuerelement gehostet werden, informieren oder deren Empfehlung deaktivieren

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parameter

*bAdvise*<br/>
True, wenn alle Steuerelemente empfohlen werden sollen. andernfalls false.

### <a name="return-value"></a>Rückgabewert

|||
|-|-|
|S_OK  |Alle Steuerelemente in der Ereignis Senke-Zuordnung waren erfolgreich verbunden oder von ihrer Ereignis Quelle getrennt.|
|E_FAIL  |Nicht alle Steuerelemente in der Ereignis Senk Karte können erfolgreich verbunden oder von ihrer Ereignis Quelle getrennt werden.|
|E_POINTER  |Dieser Fehler weist normalerweise auf ein Problem mit einem Eintrag in der Ereignis sendermap des Steuer Elements oder auf ein Problem mit einem `IDispEventImpl` in `IDispEventSimpleImpl` einer-oder-Basisklasse verwendeten Vorlagen Argument hin.|
|CONNECT_E_ADVISELIMIT  |Der Verbindungspunkt hat das Limit von Verbindungen bereits erreicht und kann nicht mehr akzeptiert werden.|
|CONNECT_E_CANNOTCONNECT  |Die Senke unterstützt nicht die für diesen Verbindungspunkt erforderliche Schnittstelle.|
|CONNECT_E_NOCONNECTION  |Der Cookie-Wert stellt keine gültige Verbindung dar. Dieser Fehler weist normalerweise auf ein Problem mit einem Eintrag in der Ereignis sendermap des Steuer Elements oder auf ein Problem mit einem `IDispEventImpl` in `IDispEventSimpleImpl` einer-oder-Basisklasse verwendeten Vorlagen Argument hin.|

### <a name="remarks"></a>Hinweise

Die Basis Implementierung dieser Methode durchsucht die Einträge in der Ereignis Senke-Zuordnung. Anschließend werden die Verbindungspunkte für die COM-Objekte, die durch die Senke-Einträge der Ereignis Senke beschrieben werden, von der Ereignis Senke benachrichtigt oder Diese Member-Methode basiert auch darauf, dass die abgeleitete Klasse von einer Instanz von `IDispEventImpl` für jedes Steuerelement in der Senke-Zuordnung erbt, das empfohlen oder nicht empfohlen wird.

##  <a name="calcextent"></a>CComCompositeControl:: calcblock

Mit dieser Methode können Sie die Größe in den HIMETRIC-Einheiten der Dialog Ressource berechnen, die zum Hosten des zusammengesetzten Steuer Elements verwendet wird.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Ein Verweis auf eine `SIZE` -Struktur, die von dieser Methode aufgefüllt werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Steuerelement von einem Dialogfeld gehostet wird. andernfalls false.

### <a name="remarks"></a>Hinweise

Die Größe wird im *size* -Parameter zurückgegeben.

##  <a name="create"></a>CComCompositeControl:: Create

Diese Methode wird aufgerufen, um das Steuerelement Fenster für das zusammengesetzte Steuerelement zu erstellen.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das übergeordnete Fenster des Steuer Elements.

*rcPos*<br/>
Reserviert.

*dwInitParam*<br/>
An das Steuerelement bei der Erstellung des Steuer Elements zu über gebenden Daten. Die als *dwinitparam* übergebenen Daten werden als lParam-Parameter der [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) -Nachricht angezeigt, die beim Erstellen an das zusammengesetzte Steuerelement gesendet wird.

### <a name="return-value"></a>Rückgabewert

Ein Handle für das neu erstellte zusammengesetzte Steuerelement Dialogfeld.

### <a name="remarks"></a>Hinweise

Diese Methode wird in der Regel während der direkten Aktivierung des Steuer Elements aufgerufen.

##  <a name="ccomcompositecontrol"></a>CComCompositeControl:: CComCompositeControl

Der Konstruktor.

```
CComCompositeControl();
```

### <a name="remarks"></a>Hinweise

Initialisiert die Datenmember " [CComCompositeControl:: m_hbrBackground](#m_hbrbackground) " und " [CComCompositeControl:: m_hWndFocus](#m_hwndfocus) " in NULL.

##  <a name="dtor"></a>CComCompositeControl:: ~ CComCompositeControl

Der Destruktor.

```
~CComCompositeControl();
```

### <a name="remarks"></a>Hinweise

Löscht das Hintergrund Objekt, falls es vorhanden ist.

##  <a name="createcontrolwindow"></a>CComCompositeControl:: kreatecontrolwindow

Rufen Sie diese Methode auf, um das Steuerelement Fenster zu erstellen und alle gehosteten Steuerelemente zu

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das übergeordnete Fenster des Steuer Elements.

*rcPos*<br/>
Das Positions Rechteck des zusammengesetzten Steuer Elements in Client Koordinaten relativ zu *hwndParent*.

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle für das neu erstellte zusammengesetzte Steuerelement-Dialogfeld zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [CComCompositeControl:: Create](#create) und [CComCompositeControl:: AdviseSinkMap](#advisesinkmap)auf.

##  <a name="m_hbrbackground"></a>CComCompositeControl:: m_hbrBackground

Der Hintergrund Pinsel.

```
HBRUSH m_hbrBackground;
```

##  <a name="m_hwndfocus"></a>CComCompositeControl:: m_hWndFocus

Das Handle des Fensters, das derzeit den Fokus besitzt.

```
HWND m_hWndFocus;
```

##  <a name="setbackgroundcolorfromambient"></a>CComCompositeControl:: setbackgroundcolorfromambient

Mit dieser Methode können Sie die Hintergrundfarbe des zusammengesetzten Steuer Elements mit der Hintergrundfarbe des Containers festlegen.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
