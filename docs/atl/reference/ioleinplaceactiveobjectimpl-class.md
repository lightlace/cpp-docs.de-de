---
title: Ioleinplaceactiveobjectimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: f52638c8a28652cc958ebb3d774319ab37a3c46d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495757"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>Ioleinplaceactiveobjectimpl-Klasse

Diese Klasse stellt Methoden zur Unterstützung der Kommunikation zwischen einer direkten Steuerung und deren Container bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IOleInPlaceActiveObjectImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Aktiviert die kontextbezogene Hilfe. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Aktiviert Dialogfelder ohne Modus. Die ATL-Implementierung gibt S_OK zurück.|
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Ruft ein Fenster Handle ab.|
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Benachrichtigt das-Steuerelement, wenn das Dokument Fenster des Containers aktiviert oder deaktiviert wird. Die ATL-Implementierung gibt S_OK zurück.|
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Benachrichtigt das-Steuerelement, wenn das Rahmen Fenster der obersten Ebene des Containers aktiviert oder deaktiviert wird. Die ATL-Implementierung gibt zurück.|
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Informiert das Steuerelement, dass es die Größe seines Rahmens ändern muss. Die ATL-Implementierung gibt S_OK zurück.|
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Verarbeitet Menü Zugriffstasten-Meldungen aus dem Container. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Die [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) -Schnittstelle unterstützt die Kommunikation zwischen einem direkten Steuerelement und seinem Container. Wenn Sie z. b. den aktiven Zustand des Steuer Elements und des Containers übermitteln und das Steuerelement darüber informieren, muss seine Größe geändert werden. Die `IOleInPlaceActiveObjectImpl` -Klasse stellt eine Standard `IOleInPlaceActiveObject` Implementierung von `IUnknown` bereit und unterstützt das Senden von Informationen an das dumpgerät in Debugbuilds.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="contextsensitivehelp"></a>Ioleinplaceactiveobjectimpl:: ContextSensitiveHelp

Aktiviert die kontextbezogene Hilfe.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) im Windows SDK.

##  <a name="enablemodeless"></a>Ioleinplaceactiveobjectimpl:: enablemodeless

Aktiviert Dialogfelder ohne Modus.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IOleInPlaceActiveObject:: enablemodeless](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) .

##  <a name="getwindow"></a>Ioleinplaceactiveobjectimpl:: GetWindow

Der Container ruft diese Funktion auf, um das Fenster Handle des Steuer Elements zu erhalten.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Hinweise

Einige Container funktionieren nicht mit einem Steuerelement, das fensterloser ist, auch wenn es aktuell Fenster ist. Wenn der Datenmember in der ATL `CComControl::m_bWasOnceWindowless` -Implementierung den Wert true hat, gibt die Funktion E_FAIL zurück. Wenn \* *phwnd* andernfalls nicht NULL ist, `GetWindow` wird *phwnd* dem Datenmember `m_hWnd` der Steuerelement Klasse zugewiesen und S_OK zurückgegeben.

Siehe [IOleWindow:: GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) in der Windows SDK.

##  <a name="ondocwindowactivate"></a>Ioleinplaceactiveobjectimpl:: ondocwindowaktivierungs

Benachrichtigt das-Steuerelement, wenn das Dokument Fenster des Containers aktiviert oder deaktiviert wird.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleInPlaceActiveObject:: ondocwindowaktivierungs](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) in der Windows SDK.

##  <a name="onframewindowactivate"></a>Ioleinplaceactiveobjectimpl:: onframewindowaktivierungs

Benachrichtigt das-Steuerelement, wenn das Rahmen Fenster der obersten Ebene des Containers aktiviert oder deaktiviert wird.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleInPlaceActiveObject:: onframewindowaktivierungs](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) in der Windows SDK.

##  <a name="resizeborder"></a>Ioleinplaceactiveobjectimpl:: resizeborder

Informiert das Steuerelement, dass es die Größe seines Rahmens ändern muss.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleInPlaceActiveObject:: resizeborder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) in der Windows SDK.

##  <a name="translateaccelerator"></a>Ioleinplaceactiveobjectimpl:: TranslateAccelerator

Verarbeitet Menü Zugriffstasten-Meldungen aus dem Container.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Rückgabewert

Diese Methode unterstützt die folgenden Rückgabewerte:

S_OK, wenn die Nachricht erfolgreich übersetzt wurde.

S_FALSE, wenn die Meldung nicht übersetzt wurde.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IOleInPlaceActiveObject:: TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) .

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX-Steuerelement Schnittstellen](/windows/win32/com/activex-controls-interfaces)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
