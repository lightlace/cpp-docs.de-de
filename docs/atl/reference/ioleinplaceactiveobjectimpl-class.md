---
title: IOleInPlaceActiveObjectImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e74df913b22684a61ab4f45ade561e55db18544
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044508"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl-Klasse

Diese Klasse stellt Methoden für die Unterstützung der Kommunikation zwischen einem in-Place-Steuerelement und seinem Container.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IOleInPlaceActiveObjectImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Können kontextbezogene Hilfe an. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Ermöglicht Dialogfelder ohne Modus. Es gibt S_OK zurück, die ATL-Implementierung.|
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Ruft einen Fensterhandle ab.|
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Benachrichtigt das Steuerelement aus, wenn das Dokumentfenster des Containers aktiviert oder deaktiviert wird. Es gibt S_OK zurück, die ATL-Implementierung.|
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Benachrichtigt das Steuerelement aus, wenn der obersten Ebene Rahmenfenster des Containers aktiviert oder deaktiviert ist. Gibt zurück, die ATL-Implementierung|
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Benachrichtigt, dass der Rahmen Ändern der Größe muss das Steuerelement. Es gibt S_OK zurück, die ATL-Implementierung.|
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Verarbeitet die Tastenkombinations-menünachrichten aus dem Container. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Die [IOleInPlaceActiveObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceactiveobject) Schnittstelle unterstützt die Kommunikation zwischen einem in-Place-Steuerelement und seinem Container, z. B. den aktiven Status des Steuerelements und die Container kommuniziert und informiert das Steuerelement muss zum Ändern der Größe sich selbst. Klasse `IOleInPlaceActiveObjectImpl` stellt eine Standardimplementierung von `IOleInPlaceActiveObject` und unterstützt `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceActiveObjectImpl::ContextSensitiveHelp

Können kontextbezogene Hilfe an.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleWindow::ContextSensitiveHelp](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) in das Windows SDK.

##  <a name="enablemodeless"></a>  IOleInPlaceActiveObjectImpl::EnableModeless

Ermöglicht Dialogfelder ohne Modus.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) in das Windows SDK.

##  <a name="getwindow"></a>  IOleInPlaceActiveObjectImpl::GetWindow

Der Container ruft diese Funktion rufen Sie das Fensterhandle des Steuerelements.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Hinweise

Einige Container funktioniert nicht mit einem Steuerelement, die fensterlose, selbst wenn sie derzeit im Fenstermodus ist. In ATLs-Implementierung Wenn die `CComControl::m_bWasOnceWindowless` -Datenmember ist "true", die Funktion gibt E_FAIL zurück. Andernfalls gilt: Wenn \* *Phwnd* ist nicht NULL, `GetWindow` weist *Phwnd* in der Steuerelementklasse-Datenmember `m_hWnd` und gibt S_OK zurück.

Finden Sie unter [IOleWindow::GetWindow](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-getwindow) in das Windows SDK.

##  <a name="ondocwindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnDocWindowActivate

Benachrichtigt das Steuerelement aus, wenn das Dokumentfenster des Containers aktiviert oder deaktiviert wird.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) in das Windows SDK.

##  <a name="onframewindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnFrameWindowActivate

Benachrichtigt das Steuerelement aus, wenn der obersten Ebene Rahmenfenster des Containers aktiviert oder deaktiviert ist.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) in das Windows SDK.

##  <a name="resizeborder"></a>  IOleInPlaceActiveObjectImpl::ResizeBorder

Benachrichtigt, dass der Rahmen Ändern der Größe muss das Steuerelement.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) in das Windows SDK.

##  <a name="translateaccelerator"></a>  IOleInPlaceActiveObjectImpl::TranslateAccelerator

Verarbeitet die Tastenkombinations-menünachrichten aus dem Container.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Rückgabewert

Diese Methode unterstützt die folgenden Rückgabewerte:

S_OK, wenn die Nachricht erfolgreich übersetzt wurde.

S_FALSE, wenn die Nachricht nicht übersetzt wurde.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleInPlaceActiveObject:: TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX-Steuerelemente Schnittstellen](/windows/desktop/com/activex-controls-interfaces)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
