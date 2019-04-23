---
title: MakeAndInitialize-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAndInitialize
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
ms.openlocfilehash: 14ae5117194748748ceecf97ac83fc8813bba2d3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037483"
---
# <a name="makeandinitialize-function"></a>MakeAndInitialize-Funktion

Initialisiert die angegebene Windows-Runtime-Klasse. Verwenden Sie diese Funktion, um eine Komponente zu instanziieren, die im Modul definiert ist.

## <a name="syntax"></a>Syntax

```cpp
template <
    typename T,
    typename I,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9>
HRESULT MakeAndInitialize(
    _Outptr_result_nullonfailure_ I** ppvObject,
    TArg1 &&arg1,
    TArg2 &&arg2,
    TArg3 &&arg3,
    TArg4 &&arg4,
    TArg5 &&arg5,
    TArg6 &&arg6,
    TArg7 &&arg7,
    TArg8 &&arg8,
    TArg9 &&arg9) throw()
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

*arg2*<br/>
Argument 2, auf die angegebene Runtime-Klasse übergeben wird.

*arg3*<br/>
Argument 3, das an die angegebene Runtime-Klasse übergeben wird.

*arg4*<br/>
Argument 4, das an die angegebene Runtime-Klasse übergeben wird.

*arg5*<br/>
Argument 5, für die angegebene Runtime-Klasse übergeben wird.

*arg6*<br/>
Argument 6, auf die angegebene Runtime-Klasse übergeben wird.

*arg7*<br/>
Argument 7, das an die angegebene Runtime-Klasse übergeben wird.

*arg8*<br/>
Argument 8, das an die angegebene Runtime-Klasse übergeben wird.

*arg9*<br/>
Argument 9, auf die angegebene Runtime-Klasse übergeben wird.

## <a name="return-value"></a>Rückgabewert

Der HRESULT-Wert.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [How to: Instanziieren von WRL-Komponenten direkt](how-to-instantiate-wrl-components-directly.md) um die Unterschiede zwischen dieser Funktion zu erfahren und [Microsoft::WRL::Make](make-function.md), und ein Beispiel.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)