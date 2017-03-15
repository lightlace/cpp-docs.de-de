---
title: IWorkerThreadClient Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IWorkerThreadClient
- ATL::IWorkerThreadClient
- IWorkerThreadClient
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2127d13dc11edb353ef27396f3457dd9abdc4a99
ms.lasthandoff: 02/24/2017

---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient-Schnittstelle
`IWorkerThreadClient`ist die Schnittstelle implementiert, die von Clients von der [CWorkerThread](../../atl/reference/cworkerthread-class.md) Klasse.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|["CloseHandle"](#closehandle)|Implementieren Sie diese Methode, um das diesem Objekt zugeordnete Handle zu schließen.|  
|[Ausführen](#execute)|Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordnete signalisiert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Implementieren Sie diese Schnittstelle, wenn Sie über Code verfügen, die in Reaktion auf ein Handle signalisiert einem Arbeitsthread ausgeführt werden muss.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="a-nameclosehandlea--iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 Implementieren Sie diese Methode, um das diesem Objekt zugeordnete Handle zu schließen.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>Parameter  
 *hHandle*  
 Das Handle geschlossen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das an diese Methode übergebene Handle wurde zuvor mit diesem Objekt verknüpften durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung von `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities&#135;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="a-nameexecutea--iworkerthreadclientexecute"></a><a name="execute"></a>IWorkerThreadClient::Execute  
 Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordnete signalisiert wird.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `dwParam`  
 Der Benutzerparameter.  
  
 `hObject`  
 Das Handle, das signalisiert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle und DWORD/Zeiger an diese Methode übergebenen wurden zuvor mit diesem Objekt verknüpften durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung von `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities&#136;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CWorkerThread-Klasse](../../atl/reference/cworkerthread-class.md)

