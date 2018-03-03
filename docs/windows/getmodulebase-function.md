---
title: GetModuleBase-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19f575705b1f8680a68e9100f20be66ca22ec87a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="getmodulebase-function"></a>GetModuleBase-Funktion
Ruft eine [ModuleBase](../windows/modulebase-class.md) Zeiger, der zum Inkrementieren und Dekrementieren den Verweiszähler des ermöglicht eine [RuntimeClass](../windows/runtimeclass-class.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `ModuleBase` Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird intern zum Inkrementieren und Dekrementieren verwendet Verweiszähler des Objekts.  
  
 Sie können diese Funktion verwenden, zum Steuern der Verweiszähler durch Aufrufen von [modulebase:: Incrementobjectcount](../windows/modulebase-incrementobjectcount-method.md) und [modulebase:: Decrementobjectcount](../windows/modulebase-decrementobjectcount-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)