---
title: PROVIDER_COLUMN_ENTRY_WSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_WSTR
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_WSTR macro
ms.assetid: 70630bd5-d782-473b-9777-aebbbf5321c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: faa6630d8821065d056e922dbf4790265d2497f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104073"
---
# <a name="providercolumnentrywstr"></a>PROVIDER_COLUMN_ENTRY_WSTR
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Der Spaltenname.  
  
 `ordinal`  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 `member`  
 [in] Die Membervariable in der Data-Klasse, die die Daten speichert.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro aus, wenn die Spaltendaten ist eine Null-terminierte Unicode-Zeichenfolge, [DBTYPE_WSTR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)