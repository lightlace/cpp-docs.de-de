---
title: MakeAndInitialize-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAndInitialize
dev_langs: C++
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f759a71117d00e5f01f2f0f53f93fef2ba47a4fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="makeandinitialize-function"></a>MakeAndInitialize-Funktion
Initialisiert die angegebene Windows-Runtime-Klasse. Verwenden Sie diese Funktion, eine Komponente zu instanziieren, die im selben Modul definiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <typename T, typename I,   
typename TArg1,   
typename TArg2,   
typename TArg3,   
typename TArg4,   
typename TArg5,   
typename TArg6,   
typename TArg7,   
typename TArg8,   
typename TArg9> HRESULT MakeAndInitialize(_Outptr_result_nullonfailure_ I** ppvObject, TArg1 &&arg1, TArg2 &&arg2, TArg3 &&arg3, TArg4 &&arg4, TArg5 &&arg5, TArg6 &&arg6, TArg7 &&arg7, TArg8 &&arg8, TArg9 &&arg9) throw()  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine benutzerdefinierte Klasse, die erbt `WRL::RuntimeClass`.  
  
 `TArg1`  
 Typ des Arguments 1, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `TArg2`  
 Typ des Arguments 2, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `TArg3`  
 Typ des Arguments 3, die an die angegebene Runtime-Klasse übergeben wird.  
  
 `TArg4`  
 Typ des Arguments 4, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `TArg5`  
 Typ des Arguments 5, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `TArg6`  
 Typ des Arguments 6, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `TArg7`  
 Typ des Arguments 7, die an die angegebene Runtime-Klasse übergeben wird.  
  
 `TArg8`  
 Typ des Arguments 8, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `TArg9`  
 Typ des Arguments 9, die an die angegebene Runtime-Klasse übergeben wird.  
  
 `arg1`  
 Argument 1, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `arg2`  
 Argument 2, das an die angegebene Runtime-Klasse übergeben wird.  
  
 `arg3`  
 Argument 3, das an die angegebene Runtime-Klasse übergeben wird.  
  
 `arg4`  
 Argument 4, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `arg5`  
 Argument 5, der auf dem angegebenen Common Language Runtime-Klasse übergeben wird.  
  
 `arg6`  
 Argument 6, das an die angegebene Runtime-Klasse übergeben wird.  
  
 `arg7`  
 Argument 7, das an die angegebene Runtime-Klasse übergeben wird.  
  
 `arg8`  
 Argument 8, das an die angegebene Runtime-Klasse übergeben wird.  
  
 `arg9`  
 Argument 9, die an die angegebene Runtime-Klasse übergeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT`-Wert.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Vorgehensweise: WRL-Komponenten direkt instanziieren](../windows/how-to-instantiate-wrl-components-directly.md) um die Unterschiede zwischen dieser Funktion zu erfahren und [Microsoft::WRL::Make](../windows/make-function.md), und ein Beispiel.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)