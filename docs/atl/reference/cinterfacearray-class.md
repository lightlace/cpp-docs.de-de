---
title: CInterfaceArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c33e0783acfba1b460894ac8f5dde80e61780762
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882713"
---
# <a name="cinterfacearray-class"></a>CInterfaceArray-Klasse
Diese Klasse stellt nützliche Methoden aus, wenn Sie ein Array von COM-Schnittstellenzeiger zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Parameter  
 *I*  
 Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.  
  
 *piid*  
 Ein Zeiger auf die IID der *ich*.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Der Konstruktor für das schnittstellenarray.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt einen Konstruktor und die abgeleiteten Methoden zum Erstellen eines Arrays von COM-Schnittstellenzeiger. Verwendung [CInterfaceList](../../atl/reference/cinterfacelist-class.md) Wenn eine Liste erforderlich ist.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="cinterfacearray"></a>  CInterfaceArray::CInterfaceArray  
 Der Konstruktor.  
  
```
CInterfaceArray() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert den intelligenten Zeiger-Array.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlArray-Klasse](../../atl/reference/catlarray-class.md)   
 [CComQIPtr-Klasse](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
