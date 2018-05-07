---
title: PROPERTY_INFO_ENTRY | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROPERTY_INFO_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY macro
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2603d3257edad6e90357c425a8b5aef60af611dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="propertyinfoentry"></a>PROPERTY_INFO_ENTRY
Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
PROPERTY_INFO_ENTRY(dwPropID)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwPropID*  
 [in] Ein [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) -Wert, der in Verbindung mit dem GUID-Eigenschaftensatz verwendet werden kann, um eine Eigenschaft zu identifizieren.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro legt den Wert der Eigenschaft vom Typ `DWORD` auf einen in ATLDB.H definierten Standardwert fest. Verwenden Sie [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md), um die Eigenschaft auf einen Wert Ihrer Wahl festzulegen. Zum gleichzeitigen Festlegen von [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) und [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) für die Eigenschaft verwenden Sie [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md), um die Eigenschaft auf einen Wert Ihrer Wahl festzulegen.  
  
## <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)