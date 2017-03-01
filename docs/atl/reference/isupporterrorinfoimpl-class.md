---
title: Klasse ISupportErrorInfoImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::ISupportErrorInfoImpl<piid>
- ATL::ISupportErrorInfoImpl
- ISupportErrorInfoImpl
- ATL.ISupportErrorInfoImpl<piid>
- ATL.ISupportErrorInfoImpl
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
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
ms.openlocfilehash: 320cb27d1d22a5e4240861c934e9bcfabd731bad
ms.lasthandoff: 02/24/2017

---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl-Klasse
Diese Klasse enthält die standardmäßige Implementierung der [ISupportErrorInfo-Schnittstelle](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) und kann verwendet werden, wenn nur eine einzige Schnittstelle Fehler für ein Objekt generiert.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>Parameter  
 `piid`  
 Ein Zeiger auf eine Schnittstelle, unterstützt die IID [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Gibt an, ob die Schnittstelle identifizierte `riid` unterstützt die [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ISupportErrorInfo-Schnittstelle](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) wird sichergestellt, dass die Fehlerinformationen an den Client zurückgegeben werden kann. Objekten, **IErrorInfo** müssen implementieren **ISupportErrorInfo**.  
  
 Klasse `ISupportErrorInfoImpl` stellt eine Standardimplementierung der **ISupportErrorInfo** und kann verwendet werden, wenn nur eine einzige Schnittstelle Fehler für ein Objekt generiert. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#48;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-nameinterfacesupportserrorinfoa--isupporterrorinfoimplinterfacesupportserrorinfo"></a><a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 Gibt an, ob die Schnittstelle identifizierte `riid` unterstützt die [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) Schnittstelle.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ISupportErrorInfo:: InterfaceSupportsErrorInfo](http://msdn.microsoft.com/en-us/a54ef18d-ee3f-4483-ac4a-99d758f0960a) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetsizea--ithreadpoolconfiggetsize"></a><a name="getsize"></a>IThreadPoolConfig::GetSize  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Parameter  
 `pnNumThreads`  
 [out] Die Adresse der Variablen, die bei Erfolg, die Anzahl der Threads im Pool empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#134;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
##  <a name="a-namegettimeouta--ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool, bis ein Thread warten soll beendet.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Parameter  
 `pdwMaxWait`  
 [out] Die Adresse der Variablen, die bei Erfolg die maximale Zeit in Millisekunden, die der Threadpool warten soll, bis ein Thread erhält beendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="a-namesetsizea--ithreadpoolconfigsetsize"></a><a name="setsize"></a>IThreadPoolConfig::SetSize  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Parameter  
 `nNumThreads`  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn `nNumThreads` ist negativ, der Absolute Wert multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
 Wenn `nNumThreads` NULL ist, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="a-namesettimeouta--ithreadpoolconfigsettimeout"></a><a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMaxWait`  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

