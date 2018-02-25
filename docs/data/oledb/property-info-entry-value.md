---
title: PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- PROPERTY_INFO_ENTRY_VALUE
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY_VALUE macro
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8adb8fb0c2978bdf5886d47fa0ee33cba8f8fbe4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="propertyinfoentryvalue"></a>PROPERTY_INFO_ENTRY_VALUE
Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID  
, value )  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwPropID*  
 [in] Ein [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) -Wert, der in Verbindung mit dem GUID-Eigenschaftensatz verwendet werden kann, um eine Eigenschaft zu identifizieren.  
  
 *Wert*  
 [in] Der Eigenschaftswert von Typ `DWORD`.  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Makro können Sie den Wert der Eigenschaft vom Typ direkt angeben `DWORD`. Für die Eigenschaft in ATLDB definierten Standardwert fest. H verwenden [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Verwenden Sie zum Festlegen der Wert, der Flags und der Optionen für die Eigenschaft [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).  
  
## <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)