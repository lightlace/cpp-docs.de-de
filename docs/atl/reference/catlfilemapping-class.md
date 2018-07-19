---
title: CAtlFileMapping-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 17f4735b56d6d15dfe3740c0dad727765e0eb84b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882304"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping-Klasse
Diese Klasse stellt eine Speicherabbilddatei, die Methoden der Cast-Operator hinzugefügt [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Der Typ der Daten, die für die Cast-Operator verwendet werden soll.  
  
## <a name="members"></a>Member  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Ermöglicht die implizite Konvertierung von `CAtlFileMapping` Objekte `T` **\***.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse fügt einen einzelne Cast-Operator, um ermöglichen die implizite Konvertierung des `CAtlFileMapping` Objekte `T` **\***. Andere Mitglieder werden bereitgestellt, von der Basisklasse, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlfile.h  
  
##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *  
 Ermöglicht die implizite Konvertierung von `CAtlFileMapping` Objekte `T` **\***.  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `T` **\*** Zeiger am Anfang der Datei mit zugewiesenem Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) und interpretiert die zurückgegebenen Zeiger als einen `T` **\*** , in denen *T* ist der Typ, der als Vorlage verwendet die Parameter dieser Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlFileMappingBase-Klasse](../../atl/reference/catlfilemappingbase-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
