---
title: IWorkerThreadClient-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86e35910469128ecaf38751d6db73094adf3422e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884723"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient-Schnittstelle
`IWorkerThreadClient` ist die Schnittstelle implementiert, die von Clients von der [CWorkerThread](../../atl/reference/cworkerthread-class.md) Klasse.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|["CloseHandle"](#closehandle)|Implementieren Sie diese Methode, um das Handle, das diesem Objekt zugeordneten zu schließen.|  
|[Führen Sie](#execute)|Implementieren Sie diese Methode, um Code auszuführen, wenn das diesem Objekt zugeordnete Handle signalisiert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Implementieren Sie diese Schnittstelle, wenn Sie über Code verfügen, die auf einem Arbeitsthread als Reaktion auf ein Handle signalisiert ausführen muss.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlutil.h"  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 Implementieren Sie diese Methode, um das Handle, das diesem Objekt zugeordneten zu schließen.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>Parameter  
 *hHandle*  
 Das Handle geschlossen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle, das an diese Methode übergeben wurde bereits zugeordnet. dieses Objekt durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 Implementieren Sie diese Methode, um Code auszuführen, wenn das diesem Objekt zugeordnete Handle signalisiert wird.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Parameter  
 *dwParam*  
 Der Benutzerparameter.  
  
 *hObject*  
 Das Handle, das signalisiert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle und die DWORD/Zeiger an diese Methode übergeben wurden zuvor mit diesem Objekt durch einen Aufruf von verknüpften [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CWorkerThread-Klasse](../../atl/reference/cworkerthread-class.md)
