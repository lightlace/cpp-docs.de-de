---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: cea3404e0732cb0e16b3fa9199ce95e3dfcc23f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386147"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR

**Microsoft-spezifisch**

Zeigt auf den Anfang des `BSTR`, das vom `_bstr_t` umschlossen ist.

## <a name="syntax"></a>Syntax

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Rückgabewert

Der Anfang des `BSTR`, der vom `_bstr_t` umschlossen ist.

## <a name="remarks"></a>Hinweise

**GetBSTR** wirkt sich auf alle `_bstr_t` Objekte die Freigabe einer `BSTR`. Mehr als eine `_bstr_t` können Freigeben einer `BSTR` durch die Verwendung des Kopierkonstruktors und **Operator =**.

## <a name="example"></a>Beispiel

Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein Beispiel mit **GetBSTR**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_bstr_t-Klasse](../cpp/bstr-t-class.md)