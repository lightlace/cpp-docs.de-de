---
title: _bstr_t::GetBSTR | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a62cd1c08409fb5915ebf42fa118c1e6124e29f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071860"
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