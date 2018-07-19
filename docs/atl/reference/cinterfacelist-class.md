---
title: CInterfaceList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33cfcc072e000bc903cceb4ac5551071e35610d9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884375"
---
# <a name="cinterfacelist-class"></a>CInterfaceList-Klasse
Diese Klasse stellt nützliche Methoden aus, wenn Sie eine Liste der COM-Schnittstellenzeiger zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Der Konstruktor für die Schnittstellenliste.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt einen Konstruktor und die abgeleiteten Methoden zum Erstellen einer Liste von COM-Schnittstellenzeiger. Verwendung [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) Wenn ein Array erforderlich ist.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="cinterfacelist"></a>  CInterfaceList::CInterfaceList  
 Der Konstruktor für die Schnittstellenliste.  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nBlockSize*  
 Die Blockgröße hat den Standardwert 10.  
  
### <a name="remarks"></a>Hinweise  
 Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlList-Klasse](../../atl/reference/catllist-class.md)   
 [CComQIPtr-Klasse](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
