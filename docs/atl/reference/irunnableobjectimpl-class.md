---
title: Klasse IRunnableObjectImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a9b2698c195ac5bd709e6d40d3c30008d3fa26d4
ms.lasthandoff: 02/24/2017

---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl-Klasse
Diese Klasse implementiert **IUnknown** und enthält die standardmäßige Implementierung der [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IRunnableObjectImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Gibt die CLSID des Steuerelements ausgeführt. Die ATL-Implementierung wird die CLSID auf `GUID_NULL` und gibt **E_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Bestimmt, ob das Steuerelement ausgeführt wird. Der ATL-Implementierung zurückgegeben **TRUE**.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Sperren das Steuerelement in den ausgeführten Status. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IRunnableObjectImpl::Run](#run)|Erzwingt, dass das Steuerelement ausgeführt. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Gibt an, dass das Steuerelement eingebettet ist. Der ATL-Implementierung zurückgegeben `S_OK`.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) Schnittstelle ermöglicht einen Container zu bestimmen, ob ein Steuerelement ausgeführt wird, auszuführen oder zu schützen, in den ausgeführten Status zu erzwingen. Klasse `IRunnableObjectImpl` bietet eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass  
 Gibt die CLSID des Steuerelements ausgeführt.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der ATL-Implementierung legt \* *LpClsid* auf `GUID_NULL` und gibt **E_UNEXPECTED**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isrunning"></a>IRunnableObjectImpl::IsRunning  
 Bestimmt, ob das Steuerelement ausgeführt wird.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der ATL-Implementierung zurückgegeben **TRUE**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="lockrunning"></a>IRunnableObjectImpl::LockRunning  
 Sperren das Steuerelement in den ausgeführten Status.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der ATL-Implementierung zurückgegeben `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="run"></a>IRunnableObjectImpl::Run  
 Erzwingt, dass das Steuerelement ausgeführt.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der ATL-Implementierung zurückgegeben `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedObject  
 Gibt an, dass das Steuerelement eingebettet ist.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der ATL-Implementierung zurückgegeben `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

