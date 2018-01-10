---
title: 'CUtlProps:: IsValidValue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
dev_langs: C++
helpviewer_keywords: IsValidValue method
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 06193b8c560c5ac6006698813222e698a98bccc3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropsisvalidvalue"></a>CUtlProps::IsValidValue
Verwendet, um einen Wert vor dem Festlegen einer Eigenschaft zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
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