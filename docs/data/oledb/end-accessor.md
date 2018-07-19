---
title: END_ACCESSOR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- END_ACCESSOR
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f7bab52df0ed05886933a3df827fae5198651b39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099237"
---
# <a name="endaccessor"></a>END_ACCESSOR
Markiert das Ende eines Eintrags Accessor.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
END_ACCESSOR()  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Für mehrere Accessoren für ein Rowset, müssen Sie angeben `BEGIN_ACCESSOR_MAP` und Verwenden der `BEGIN_ACCESSOR` -Makro für jede einzelne Zugriffsmethode. Das `BEGIN_ACCESSOR` -Makro wird mit dem `END_ACCESSOR` -Makro abgeschlossen. Die `BEGIN_ACCESSOR_MAP` Makro erfolgt mit der `END_ACCESSOR_MAP` Makro.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)