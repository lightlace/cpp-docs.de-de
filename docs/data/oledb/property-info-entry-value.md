---
title: PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROPERTY_INFO_ENTRY_VALUE
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY_VALUE macro
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbd216a3358385a0a0c1c61e8e3f31a1fd3c8946
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104658"
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