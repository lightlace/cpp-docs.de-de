---
title: CUtlProps-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- CUtlProps class
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b39edb002c254f5d122d574ac389c2fd4df8b38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cutlprops-class"></a>CUtlProps-Klasse
Eigenschaften für eine Vielzahl von OLE DB-Schnittstellen implementiert (z. B. `IDBProperties`, `IDBProperties`, und `IRowsetInfo`).  
  
## <a name="syntax"></a>Syntax

```cpp
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse enthält die `BEGIN_PROPSET_MAP`.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|Ruft eine Eigenschaft aus einer Eigenschaft ab.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Verwendet, um einen Wert vor dem Festlegen einer Eigenschaft zu überprüfen.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Verarbeitet Anforderungen für eine optionale Schnittstelle, wenn ein Consumer eine Methode für ein Objekt erstellen Schnittstelle aufruft.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Wird aufgerufen, nach dem Festlegen einer Eigenschaft für die verkettete Eigenschaften zu behandeln.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Festlegen einer Eigenschaft in einem Eigenschaftensatz.|  
  
## <a name="remarks"></a>Hinweise  
 Die meisten dieser Klasse ist ein Implementierungsdetail.  
  
 `CUtlProps` enthält zwei Member zum Festlegen von Eigenschaften intern: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) und [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Weitere Informationen über die Makros in einer Eigenschaft Set-Zuordnung verwendet, finden Sie unter [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) und [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)