---
title: BEGIN_PROPERTY_SET_EX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_PROPERTY_SET_EX
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_PROPERTY_SET_EX macro
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 239ee5810b0ebf46e01c9c97b01a36fdca4a1392
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093099"
---
# <a name="beginpropertysetex"></a>BEGIN_PROPERTY_SET_EX
Legen Sie der Anfang einer Eigenschaft in einer Eigenschaft markiert Zuordnung festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
BEGIN_PROPERTY_SET_EX(guid  
, flags )  
```  
  
#### <a name="parameters"></a>Parameter  
 `guid`  
 [in] Die GUID-Eigenschaft.  
  
 `flags`  
 [in] **UPROPSET_HIDDEN** für eine beliebige Eigenschaftensätze nicht verfügbar zu machen, möchten oder **UPROPSET_PASSTHROUGH** für einen Anbieter Verfügbarmachen von Eigenschaften, die außerhalb des Bereichs des Anbieters definiert.  
  
## <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)