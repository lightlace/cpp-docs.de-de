---
title: Klasse CAtlFileMapping | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlFileMapping<T>
- ATL.CAtlFileMapping
- ATL::CAtlFileMapping
- CAtlFileMapping
- ATL.CAtlFileMapping<T>
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 2693647af904eab1ed0f84bc406bc1207d4a9b8c
ms.lasthandoff: 02/24/2017

---
# <a name="catlfilemapping-class"></a>CAtlFileMapping-Klasse
Diese Klasse stellt eine Speicherabbilddatei, die Methoden der Umwandlungsoperatoren hinzugefügt [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten, die für die Cast-Operator verwendet.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Ermöglicht die implizite Konvertierung von `CAtlFileMapping` Objekte `T` ** \* **.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse fügt einem einzelnen Umwandlungsoperator um ermöglichen die implizite Konvertierung des `CAtlFileMapping` Objekte `T` ** \* **. Andere Member werden von der Basisklasse bereitgestellt [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlfile.h  
  
##  <a name="a-nameoperatortstara--catlfilemappingoperator-t"></a><a name="operator_t_star"></a>CAtlFileMapping::operator T *  
 Ermöglicht die implizite Konvertierung von `CAtlFileMapping` Objekte `T` ** \* **.  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `T` ** \* ** Zeiger am Anfang der Datei mit zugewiesenem Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) und interpretiert die zurückgegebenen Zeiger als ein `T` ** \* ** , *T* wird als Vorlagenparameter dieser Klasse verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlFileMappingBase-Klasse](../../atl/reference/catlfilemappingbase-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

