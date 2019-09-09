---
title: Ununnableobjectimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
ms.openlocfilehash: 6b1af7c21c6f5028ad6d3a228cb22650fa3cef42
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495668"
---
# <a name="irunnableobjectimpl-class"></a>Ununnableobjectimpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt eine Standard Implementierung der [ununnableobject](/windows/win32/api/objidl/nn-objidl-irunnableobject) -Schnittstelle bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IRunnableObjectImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Gibt die CLSID des laufenden Steuer Elements zurück. Die ATL-Implementierung legt die CLSID auf GUID_NULL fest und gibt E_UNEXPECTED zurück.|
|[IRunnableObjectImpl::IsRunning](#isrunning)|Bestimmt, ob das Steuerelement ausgeführt wird. Die ATL-Implementierung gibt true zurück.|
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Sperrt das Steuerelement in den Zustand "wird ausgeführt". Die ATL-Implementierung gibt S_OK zurück.|
|[IRunnableObjectImpl::Run](#run)|Erzwingt, dass das Steuerelement ausgeführt wird. Die ATL-Implementierung gibt S_OK zurück.|
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Gibt an, dass das Steuerelement eingebettet ist. Die ATL-Implementierung gibt S_OK zurück.|

## <a name="remarks"></a>Hinweise

Mit der [ununnableobject](/windows/win32/api/objidl/nn-objidl-irunnableobject) -Schnittstelle kann ein Container ermitteln, ob ein Steuerelement ausgeführt wird, die Ausführung erzwingen oder es in den Zustand "wird ausgeführt" sperren. Die `IRunnableObjectImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstelle `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="getrunningclass"></a>Ununnableobjectimpl:: getrunningclass

Gibt die CLSID des laufenden Steuer Elements zurück.

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>Rückgabewert

Die ATL-Implementierung \* legt *lpclsid* auf GUID_NULL fest und gibt E_UNEXPECTED zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter " [unnableobject:: getrunningclass](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass) ".

##  <a name="isrunning"></a>Ununnableobjectimpl:: IsRunning

Bestimmt, ob das Steuerelement ausgeführt wird.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>Rückgabewert

Die ATL-Implementierung gibt true zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [ununnableobject:: IsRunning](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning) in der Windows SDK.

##  <a name="lockrunning"></a>Ununnableobjectimpl:: lockrunning

Sperrt das Steuerelement in den Zustand "wird ausgeführt".

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>Rückgabewert

Die ATL-Implementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere [Informationen](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning) finden Sie in der Windows SDK.

##  <a name="run"></a>"Ununnableobjectimpl:: Run"

Erzwingt, dass das Steuerelement ausgeführt wird.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>Rückgabewert

Die ATL-Implementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [ununnableobject:: Run](/windows/win32/api/objidl/nf-objidl-irunnableobject-run) im Windows SDK.

##  <a name="setcontainedobject"></a>Ununnableobjectimpl:: setcontainedobject

Gibt an, dass das Steuerelement eingebettet ist.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>Rückgabewert

Die ATL-Implementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [ununnableobject:: setcontainedobject](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
