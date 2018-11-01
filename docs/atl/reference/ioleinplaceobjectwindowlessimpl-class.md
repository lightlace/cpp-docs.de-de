---
title: IOleInPlaceObjectWindowlessImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
ms.openlocfilehash: a83fbed524c55c6bc98aa25caa17b80c1e5f89f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592126"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl-Klasse

Diese Klasse implementiert `IUnknown` und bietet Methoden, die ein fensterloses Steuerelement, um fenstermeldungen zu empfangen und zur Teilnahme an Drag & Drop-Vorgänge zu ermöglichen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IOleInPlaceObjectWindowlessImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Können kontextbezogene Hilfe an. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Stellt die `IDropTarget` Schnittstelle für ein direktes aktiven, fensterlosen Objekt, das per Drag & drop unterstützt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Ruft einen Fensterhandle ab.|
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Ein aktives Steuerelement des direktes wird deaktiviert.|
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Sendet eine Nachricht aus dem Container an einem fensterlosen Steuerelement, das direkt aktiv ist.|
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Reaktiviert eine zuvor deaktivierte Steuerelement an. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Gibt an, welcher Teil des direktes Steuerelements sichtbar ist.|
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Deaktiviert und entfernt die Benutzeroberfläche, die direkte Aktivierung unterstützt.|

## <a name="remarks"></a>Hinweise

Die [IOleInPlaceObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceobject) Schnittstelle verwaltet die Aktivierung und Deaktivierung des direktes steuert und bestimmt, wie viel des Steuerelements sichtbar sein soll. Die [IOleInPlaceObjectWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) Schnittstelle ermöglicht es ein fensterloses Steuerelement, um fenstermeldungen zu empfangen und zur Teilnahme an Drag & Drop-Vorgänge. Klasse `IOleInPlaceObjectWindowlessImpl` stellt eine Standardimplementierung von `IOleInPlaceObject` und `IOleInPlaceObjectWindowless` und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp

Gibt E_NOTIMPL zurück.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleWindow::ContextSensitiveHelp](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) in das Windows SDK.

##  <a name="getdroptarget"></a>  IOleInPlaceObjectWindowlessImpl::GetDropTarget

Gibt E_NOTIMPL zurück.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleInPlaceObjectWindowless::GetDropTarget](/windows/desktop/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) in das Windows SDK.

##  <a name="getwindow"></a>  IOleInPlaceObjectWindowlessImpl::GetWindow

Der Container ruft diese Funktion rufen Sie das Fensterhandle des Steuerelements.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Hinweise

Einige Container funktioniert nicht mit einem Steuerelement, die fensterlose, selbst wenn sie derzeit im Fenstermodus ist. In ATLs-Implementierung Wenn die Control-Klasse-Datenmember `m_bWasOnceWindowless` ist "true", die Funktion gibt E_FAIL zurück. Andernfalls gilt: Wenn *Phwnd* ist nicht NULL, `GetWindow` legt diese fest \* *Phwnd* in der Steuerelementklasse-Datenmember `m_hWnd` und gibt S_OK zurück.

Finden Sie unter [IOleWindow::GetWindow](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-getwindow) in das Windows SDK.

##  <a name="inplacedeactivate"></a>  IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate

Wird aufgerufen, durch den Container ein direktes aktives Steuerelement deaktivieren.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>Hinweise

Diese Methode führt eine vollständige oder partielle Deaktivierung je nach Zustand des Steuerelements. Bei Bedarf Benutzeroberfläche des Steuerelements wird deaktiviert, und das Fenster des Steuerelements, sofern vorhanden, zerstört wird. Der Container mitgeteilt, dass das Steuerelement nicht mehr aktiv, vorhanden ist. Die `IOleInPlaceUIWindow` Schnittstelle, die vom Container verwendet werden, zum Aushandeln von Menüs und border Speicherplatz wird freigegeben.

Finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) in das Windows SDK.

##  <a name="onwindowmessage"></a>  IOleInPlaceObjectWindowlessImpl::OnWindowMessage

Sendet eine Nachricht aus einem Container an einem fensterlosen Steuerelement, das direkt aktiv ist.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleInPlaceObjectWindowless::OnWindowMessage](/windows/desktop/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) in das Windows SDK.

##  <a name="reactivateandundo"></a>  IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo

Gibt E_NOTIMPL zurück.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleInPlaceObject::ReactivateAndUndo](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) in das Windows SDK.

##  <a name="setobjectrects"></a>  IOleInPlaceObjectWindowlessImpl::SetObjectRects

Wird aufgerufen, durch den Container informiert das Steuerelement, das die Größe und/oder Position geändert hat.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>Hinweise

Updates des Steuerelements `m_rcPos` Datenmember und der Steuerelementanzeige. Nur der Teil des Steuerelements, das die Clip-Bereich überschneidet wird angezeigt. Wenn die Anzeige eines Steuerelements wurde zuvor abgeschnitten, aber das Clipping entfernt wurde, kann diese Funktion aufgerufen werden, um eine vollständige Ansicht des Steuerelements neu zu zeichnen.

Finden Sie unter [IOleInPlaceObject::SetObjectRects](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) in das Windows SDK.

##  <a name="uideactivate"></a>  IOleInPlaceObjectWindowlessImpl::UIDeactivate

Deaktiviert und entfernt das Steuerelement der Benutzeroberfläche, die direkte Aktivierung unterstützt.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>Hinweise

Legt die Control-Klasse-Datenmember `m_bUIActive` auf "false". Die ATL-Implementierung dieser Funktion stets gibt S_OK zurück.

Finden Sie unter [IOleInPlaceObject::UIDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
