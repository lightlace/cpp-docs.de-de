---
title: IRunnableObjectImpl-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 2a98456d3d7d0d2e4600267a81151c44e38993c5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885580"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl-Klasse
Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IRunnableObjectImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Gibt die CLSID des Steuerelements ausgeführt. Die ATL-Implementierung wird von der CLSID auf GUID_NULL und gibt E_UNEXPECTED zurück.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Bestimmt, ob das Steuerelement ausgeführt wird. Die ATL-Implementierung gibt "true" zurück.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Sperrt das Steuerelement in den ausgeführten Status an. Es gibt S_OK zurück, die ATL-Implementierung.|  
|[IRunnableObjectImpl::Run](#run)|Erzwingt, dass das Steuerelement ausgeführt. Es gibt S_OK zurück, die ATL-Implementierung.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Gibt an, dass das Steuerelement eingebettet ist. Es gibt S_OK zurück, die ATL-Implementierung.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) Schnittstelle ermöglicht einem Container, zu bestimmen, ob ein Steuerelement ausgeführt wird, ausführen oder Sperren es in den ausgeführten Zustand erzwingen. Klasse `IRunnableObjectImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.  
  
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
 Der ATL-Implementierung legt \* *LpClsid* GUID_NULL und gibt E_UNEXPECTED zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) in das Windows SDK.  
  
##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning  
 Bestimmt, ob das Steuerelement ausgeführt wird.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ATL-Implementierung gibt "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) in das Windows SDK.  
  
##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning  
 Sperrt das Steuerelement in den ausgeführten Status an.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Es gibt S_OK zurück, die ATL-Implementierung.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) in das Windows SDK.  
  
##  <a name="run"></a>  IRunnableObjectImpl::Run  
 Erzwingt, dass das Steuerelement ausgeführt.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Es gibt S_OK zurück, die ATL-Implementierung.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) in das Windows SDK.  
  
##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject  
 Gibt an, dass das Steuerelement eingebettet ist.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Es gibt S_OK zurück, die ATL-Implementierung.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
