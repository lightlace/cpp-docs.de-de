---
title: Ioleinplaceobjectwindowlessimpl-Klasse
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
ms.openlocfilehash: fdd660daae109ac2a656519131dd9869ceaeaf4e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495750"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>Ioleinplaceobjectwindowlessimpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt Methoden bereit, die einem fensterlosen Steuerelement ermöglichen, Fenster Meldungen zu empfangen und an Drag & Drop-Vorgängen teilzunehmen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IOleInPlaceObjectWindowlessImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Aktiviert die kontextbezogene Hilfe. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Stellt die `IDropTarget` Schnittstelle für ein direkt aktives, fensterloses Objekt bereit, das Drag & Drop unterstützt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Ruft ein Fenster Handle ab.|
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Deaktiviert eine aktive direkte Steuerung.|
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Sendet eine Nachricht aus dem Container an ein fensterloses Steuerelement, das direkt aktiv ist.|
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Reaktiviert ein zuvor deaktiviertes Steuerelement. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Gibt an, welcher Teil der direkten Steuerung sichtbar ist.|
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Deaktiviert und entfernt die Benutzeroberfläche, die die direkte Aktivierung unterstützt.|

## <a name="remarks"></a>Hinweise

Die [IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) -Schnittstelle verwaltet die erneute Aktivierung und die wieder Aktivierung von direkten Steuerelementen und bestimmt, wie viel von dem Steuerelement sichtbar sein sollte. Die [IOleInPlaceObjectWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) -Schnittstelle ermöglicht einem fensterlosen Steuerelement das Empfangen von Fenster Meldungen und die Teilnahme an Drag & Drop-Vorgängen. Die `IOleInPlaceObjectWindowlessImpl` -Klasse stellt eine Standard `IOleInPlaceObject` Implementierung `IOleInPlaceObjectWindowless` von und `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="contextsensitivehelp"></a>Ioleinplaceobjectwindowlessimpl:: ContextSensitiveHelp

Gibt E_NOTIMPL zurück.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) im Windows SDK.

##  <a name="getdroptarget"></a>Ioleinplaceobjectwindowlessimpl:: getdroptarget

Gibt E_NOTIMPL zurück.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IOleInPlaceObjectWindowless:: getdroptarget](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) .

##  <a name="getwindow"></a>Ioleinplaceobjectwindowlessimpl:: GetWindow

Der Container ruft diese Funktion auf, um das Fenster Handle des Steuer Elements zu erhalten.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Hinweise

Einige Container funktionieren nicht mit einem Steuerelement, das fensterloser ist, auch wenn es aktuell Fenster ist. Wenn in der ATL-Implementierung der Datenmember `m_bWasOnceWindowless` der Steuerelement Klasse true ist, gibt die Funktion E_FAIL zurück. Wenn *phwnd* andernfalls nicht NULL ist, `GetWindow` wird *phwnd* auf das Datenmember `m_hWnd` der Steuerelement Klasse festgelegt \* und S_OK zurückgegeben.

Siehe [IOleWindow:: GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) in der Windows SDK.

##  <a name="inplacedeactivate"></a>Ioleinplaceobjectwindowlessimpl:: inplacedeaktivierungs

Wird vom Container aufgerufen, um ein direktes aktives Steuerelement zu deaktivieren.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>Hinweise

Diese Methode führt eine vollständige oder partielle Deaktivierung in Abhängigkeit vom Zustand des Steuer Elements aus. Bei Bedarf wird die Benutzeroberfläche des Steuer Elements deaktiviert, und das Fenster des Steuer Elements wird ggf. zerstört. Der Container wird benachrichtigt, dass das Steuerelement nicht mehr aktiv ist. Die `IOleInPlaceUIWindow` Schnittstelle, die vom Container zum Aushandeln von Menüs und Rahmen Bereich verwendet wird, wird freigegeben.

Weitere Informationen finden Sie unter [IOleInPlaceObject:: inplacedeaktivierungs](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) in der Windows SDK.

##  <a name="onwindowmessage"></a>Ioleinplaceobjectwindowlessimpl:: onwindowmessage

Sendet eine Nachricht von einem Container an ein fensterloses Steuerelement, das direkt aktiv ist.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleInPlaceObjectWindowless:: onwindowmessage](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) in der Windows SDK.

##  <a name="reactivateandundo"></a>Ioleinplaceobjectwindowlessimpl:: reactivateandundo

Gibt E_NOTIMPL zurück.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleInPlaceObject:: reactivateandundo](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) in der Windows SDK.

##  <a name="setobjectrects"></a>Ioleinplaceobjectwindowlessimpl:: Log-jectrects

Wird vom Container aufgerufen, um das Steuerelement darüber zu informieren, dass seine Größe und/oder Position geändert wurde.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>Hinweise

Aktualisiert den `m_rcPos` Datenmember des Steuer Elements und die Steuerelement Anzeige. Es wird nur der Teil des Steuer Elements angezeigt, der den Clip Bereich überschneidet. Wenn die Anzeige eines Steuer Elements zuvor abgeschnitten wurde, das Clipping jedoch entfernt wurde, kann diese Funktion aufgerufen werden, um eine vollständige Ansicht des Steuer Elements neu zu zeichnen.

Weitere Informationen finden Sie im Windows SDK unter [IOleInPlaceObject:: SetObjectRects](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) .

##  <a name="uideactivate"></a>Ioleinplaceobjectwindowlessimpl:: uideaktivierungs

Deaktiviert und entfernt die Benutzeroberfläche des Steuer Elements, das die direkte Aktivierung unterstützt.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>Hinweise

Legt den Datenmember `m_bUIActive` der Steuerelement Klasse auf false fest. Die ATL-Implementierung dieser Funktion gibt immer S_OK zurück.

Weitere Informationen finden Sie im Windows SDK unter [IOleInPlaceObject:: uideaktivierungs](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) .

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
