---
title: 'CUtlProps:: IsValidValue | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
dev_langs:
- C++
helpviewer_keywords:
- IsValidValue method
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0a37f0e0e9d415f9b7c78c8a619fd7fd66d24f28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101964"
---
# <a name="cutlpropsisvalidvalue"></a>CUtlProps::IsValidValue
Verwendet, um einen Wert vor dem Festlegen einer Eigenschaft zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>Parameter  
 `iCurSet`  
 Der Index im Array Eigenschaftensatz; 0 (null), wenn nur eine Eigenschaft festgelegt ist.  
  
 `pDBProp`  
 Die Eigenschafts-ID und den neuen Wert in einem [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Der Standardrückgabewert ist `S_OK`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie alle Überprüfungsroutinen, die auf einem Wert ausgeführt wird, die Sie verwenden haben, um eine Eigenschaft festgelegt werden soll, sollten Sie diese Funktion überschrieben. Sie können z. B. überprüfen **DBPROP_AUTH_PASSWORD** für eine Kennworttabelle, um einen gültigen Wert zu bestimmen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CUtlProps-Klasse](../../data/oledb/cutlprops-class.md)