---
title: Make-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
dev_langs:
- C++
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5dab76460dcbbb70f55dac864292ad9a6f1fca99
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607819"
---
# <a name="make-function"></a>Make-Funktion

Initialisiert die angegebene Windows-Runtime-Klasse. Verwenden Sie diese Funktion, um eine Komponente zu instanziieren, die im Modul definiert ist.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8,
   TArg9 &&arg9
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3
);
template <
   typename T,
   typename TArg1,
   typename TArg2
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2
);
template <
   typename T,
   typename TArg1
>
ComPtr<T> Make(
   TArg1 &&arg1
);
template <
   typename T
>
ComPtr<T> Make();
```

### <a name="parameters"></a>Parameter

*T*  
Eine benutzerdefinierte-Klasse, die von erbt `WRL::RuntimeClass`.

*TArg1*  
Typ des Arguments 1, der auf die angegebene Runtime-Klasse übergeben wird.

*TArg2*  
Typ des Arguments, 2, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg3*  
Typ des Arguments, 3, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg4*  
Typ des Arguments, 4, der auf die angegebene Runtime-Klasse übergeben wird.

*TArg5*  
Typ des Arguments, 5, der auf die angegebene Runtime-Klasse übergeben wird.

*TArg6*  
Typ des Arguments, 6, die an die angegebene Runtime-Klasse übergeben wird.

*TArg7*  
Typ des Arguments, 7, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg8*  
Typ des Arguments, 8, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg9*  
Typ des Arguments, 9, die an die angegebene Runtime-Klasse übergeben wird.

*arg1*  
Argument 1, das an die angegebene Runtime-Klasse übergeben wird.

*Arg2*  
Argument 2, auf die angegebene Runtime-Klasse übergeben wird.

*Arg3*  
Argument 3, das an die angegebene Runtime-Klasse übergeben wird.

*Arg4*  
Argument 4, das an die angegebene Runtime-Klasse übergeben wird.

*Arg5*  
Argument 5, für die angegebene Runtime-Klasse übergeben wird.

*Arg6*  
Argument 6, auf die angegebene Runtime-Klasse übergeben wird.

*Arg7*  
Argument 7, das an die angegebene Runtime-Klasse übergeben wird.

*Arg8*  
Argument 8, das an die angegebene Runtime-Klasse übergeben wird.

*Arg9*  
Argument 9, auf die angegebene Runtime-Klasse übergeben wird.

## <a name="return-value"></a>Rückgabewert

Ein `ComPtr<T>` -Objekt, wenn erfolgreich; andernfalls **"nullptr"**.

## <a name="remarks"></a>Hinweise

Finden Sie unter [Vorgehensweise: WRL-Komponenten direkt instanziieren](../windows/how-to-instantiate-wrl-components-directly.md) um die Unterschiede zwischen dieser Funktion zu erfahren und [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md), und ein Beispiel.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)