---
title: PROVIDER_COLUMN_ENTRY_LENGTH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_LENGTH macro
ms.assetid: b4a67246-c049-4622-bb65-242cc8cae4be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2aaf2532bc63170940a3526bc34c0763ed0a4aa2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106322"
---
# <a name="providercolumnentrylength"></a>PROVIDER_COLUMN_ENTRY_LENGTH
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name  
, ordinal, size, member )  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Der Spaltenname.  
  
 `ordinal`  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 `size`  
 [in] Die Spaltengröße in Bytes.  
  
 `member`  
 [in] Die Membervariable in `dataClass` zur Speicherung der Spaltendaten.  
  
## <a name="remarks"></a>Hinweise  
 Ermöglicht Ihnen das Festlegen der Größe der Spalte an.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)