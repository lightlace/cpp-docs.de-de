---
title: IRunnableObjectImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a08fec0fd38e30729c9131def1831e5e5d8f633e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl-Klasse
Diese Klasse implementiert **IUnknown** und stellt eine Standardimplementierung von der [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IRunnableObjectImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Gibt die CLSID des Steuerelements ausgeführt. Die ATL-Implementierung wird die CLSID auf `GUID_NULL` und gibt **E_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Bestimmt, ob das Steuerelement ausgeführt wird. Gibt die ATL-Implementierung **"true"**.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Sperren das Steuerelement in den Ausführungsstatus. Gibt die ATL-Implementierung `S_OK`.|  
|[IRunnableObjectImpl::Run](#run)|Erzwingt, dass das Steuerelement ausführen. Gibt die ATL-Implementierung `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Gibt an, dass das Steuerelement eingebettet ist. Gibt die ATL-Implementierung `S_OK`.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) Schnittstelle ermöglicht, einen Container zu bestimmen, ob ein Steuerelement ausgeführt wird, die ihn zwingen, ausführen oder in den Ausführungsstatus zu sperren. Klasse `IRunnableObjectImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass  
 Gibt die CLSID des Steuerelements ausgeführt.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Legt die ATL-Implementierung \* *LpClsid* auf `GUID_NULL` und gibt **E_UNEXPECTED**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) im Windows SDK.  
  
##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning  
 Bestimmt, ob das Steuerelement ausgeführt wird.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ATL-Implementierung **"true"**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) im Windows SDK.  
  
##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning  
 Sperren das Steuerelement in den Ausführungsstatus.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ATL-Implementierung `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) im Windows SDK.  
  
##  <a name="run"></a>  IRunnableObjectImpl::Run  
 Erzwingt, dass das Steuerelement ausführen.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ATL-Implementierung `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) im Windows SDK.  
  
##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject  
 Gibt an, dass das Steuerelement eingebettet ist.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ATL-Implementierung `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
