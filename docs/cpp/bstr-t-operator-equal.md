---
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 97f0100d8a34253f3a1375d34b887d3d31a77f43
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432577"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =

**Microsoft-spezifisch**

Weist einem vorhandenen `_bstr_t`-Objekt einen neuen Wert zu.

## <a name="syntax"></a>Syntax

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>Parameter

*s1*<br/>
Ein `_bstr_t`-Objekt, das einem vorhandenen `_bstr_t`-Objekt zugewiesen werden soll.

*s2*<br/>
Eine Multibyte-Zeichenfolge, die einem vorhandenen `_bstr_t` Objekt zugewiesen werden soll.

*s3*<br/>
Eine Unicode-Zeichenfolge, die einem vorhandenen `_bstr_t` Objekt zugewiesen werden soll.

*var*<br/>
Ein `_variant_t`-Objekt, das einem vorhandenen `_bstr_t`-Objekt zugewiesen werden soll.

**Ende Microsoft-spezifisch**

## <a name="example"></a>Beispiel

Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein Beispiel der Verwendung von **Operator =**.

## <a name="see-also"></a>Siehe auch

[_bstr_t-Klasse](../cpp/bstr-t-class.md)