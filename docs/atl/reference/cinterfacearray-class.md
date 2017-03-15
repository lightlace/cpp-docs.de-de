---
title: Klasse CInterfaceArray | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CInterfaceArray
- CInterfaceArray
- ATL::CInterfaceArray
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: 18
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a2a99eb3cff4f2381d4c58e4d1a7aaa167e83896
ms.lasthandoff: 02/24/2017

---
# <a name="cinterfacearray-class"></a>CInterfaceArray-Klasse
Diese Klasse enthält Methoden, die hilfreich beim Erstellen eines Arrays von COM-Schnittstellenzeigern.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Der Konstruktor für das Array der Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt einen Konstruktor und abgeleiteten Methoden zum Erstellen eines Arrays von COM-Schnittstellenzeigern. Verwendung [CInterfaceList](../../atl/reference/cinterfacelist-class.md) Wenn eine Liste erforderlich ist.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="a-namecinterfacearraya--cinterfacearraycinterfacearray"></a><a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray  
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

