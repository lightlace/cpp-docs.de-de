---
title: CAtlFileMapping Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 524e5d9c7cef5bcff0d72ddf1225ef79b1b26d64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping-Klasse
Diese Klasse stellt eine Speicherabbilddatei, die Methoden der Umwandlungsoperatoren hinzugefügt [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten, die für die Cast-Operator verwendet.  
  
## <a name="members"></a>Member  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Ermöglicht die implizite Konvertierung von `CAtlFileMapping` -Objekte `T` **\***.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse fügt einem einzelnen Umwandlungsoperator damit können die implizite Konvertierung des `CAtlFileMapping` -Objekte `T` **\***. Andere Member werden von der Basisklasse bereitgestellt [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlfile.h  
  
##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *  
 Ermöglicht die implizite Konvertierung von `CAtlFileMapping` -Objekte `T` **\***.  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `T` **\*** Zeiger am Anfang der Speicherabbilddatei.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) und den zurückgegebenen Zeiger als interpretiert eine `T` **\*** , in denen *T* ist der Typ, der als Vorlage verwendet die Parameter dieser Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlFileMappingBase-Klasse](../../atl/reference/catlfilemappingbase-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
