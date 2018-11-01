---
title: Make-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
ms.openlocfilehash: 94468e35abc8bb53f4b01b4295478e8d9c52ddb0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501334"
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

*T*<br/>
Eine benutzerdefinierte-Klasse, die von erbt `WRL::RuntimeClass`.

*TArg1*<br/>
Typ des Arguments 1, der auf die angegebene Runtime-Klasse übergeben wird.

*TArg2*<br/>
Typ des Arguments, 2, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg3*<br/>
Typ des Arguments, 3, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg4*<br/>
Typ des Arguments, 4, der auf die angegebene Runtime-Klasse übergeben wird.

*TArg5*<br/>
Typ des Arguments, 5, der auf die angegebene Runtime-Klasse übergeben wird.

*TArg6*<br/>
Typ des Arguments, 6, die an die angegebene Runtime-Klasse übergeben wird.

*TArg7*<br/>
Typ des Arguments, 7, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg8*<br/>
Typ des Arguments, 8, das auf die angegebene Runtime-Klasse übergeben wird.

*TArg9*<br/>
Typ des Arguments, 9, die an die angegebene Runtime-Klasse übergeben wird.

*arg1*<br/>
Argument 1, das an die angegebene Runtime-Klasse übergeben wird.

*Arg2*<br/>
Argument 2, auf die angegebene Runtime-Klasse übergeben wird.

*Arg3*<br/>
Argument 3, das an die angegebene Runtime-Klasse übergeben wird.

*Arg4*<br/>
Argument 4, das an die angegebene Runtime-Klasse übergeben wird.

*Arg5*<br/>
Argument 5, für die angegebene Runtime-Klasse übergeben wird.

*Arg6*<br/>
Argument 6, auf die angegebene Runtime-Klasse übergeben wird.

*Arg7*<br/>
Argument 7, das an die angegebene Runtime-Klasse übergeben wird.

*Arg8*<br/>
Argument 8, das an die angegebene Runtime-Klasse übergeben wird.

*Arg9*<br/>
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