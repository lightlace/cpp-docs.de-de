---
title: Klasse CInterfaceList | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 50d86163080c5a0d0a7bb9ed6d77a40ac73722e7
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cinterfacelist-class"></a>CInterfaceList-Klasse
Diese Klasse enthält Methoden, die hilfreich beim Erstellen einer Liste von COM-Schnittstellenzeigern.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Parameter  
 `I`  
 Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.  
  
 `piid`  
 Ein Zeiger auf die ID der `I`.  
  
## <a name="members"></a>Mitglieder  
  
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
  
##  <a name="cinterfacelist"></a>CInterfaceList::CInterfaceList  
 Der Konstruktor für die Schnittstellenliste.  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Blockgröße hat den Standardwert 10.  
  
### <a name="remarks"></a>Hinweise  
 Die Blockgröße ist ein Maß für die Menge des Arbeitsspeichers, wenn ein neues Element erforderlich ist. Größere Blöcke reduziert Aufrufe an Arbeitsspeicher, aber mehr Ressourcen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlList-Klasse](../../atl/reference/catllist-class.md)   
 [CComQIPtr-Klasse](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

