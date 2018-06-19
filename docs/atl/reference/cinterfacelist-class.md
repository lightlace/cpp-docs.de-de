---
title: CInterfaceList Klasse | Microsoft Docs
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
ms.openlocfilehash: 1fc523b1eccc88678cda48a0c7e429ea0fc09f9b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362173"
---
# <a name="cinterfacelist-class"></a>CInterfaceList-Klasse
Diese Klasse bietet Methoden, die hilfreich beim Erstellen einer Liste von COM-Schnittstellenzeigern.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Parameter  
 `I`  
 Eine COM-Schnittstelle, die Angabe des Typs der Zeiger gespeichert werden soll.  
  
 `piid`  
 Ein Zeiger auf die IID der `I`.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Der Konstruktor für die Schnittstellenliste.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt einen Konstruktor und abgeleiteten Methoden zum Erstellen einer Liste von COM-Schnittstellenzeigern. Verwendung [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) Wenn ein Array erforderlich ist.  
  
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
 `nBlockSize`  
 Die Blockgröße hat den Standardwert 10.  
  
### <a name="remarks"></a>Hinweise  
 Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlList-Klasse](../../atl/reference/catllist-class.md)   
 [CComQIPtr-Klasse](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
