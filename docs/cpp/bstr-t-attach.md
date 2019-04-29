---
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: 8601ebbea6a9ab837c07518b018e83e8c0df226d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385062"
---
# <a name="bstrtattach"></a>_bstr_t::Attach

**Microsoft-spezifisch**

Verknüpft einen `_bstr_t`-Wrapper mit einem `BSTR`.

## <a name="syntax"></a>Syntax

```
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>Parameter

*s*<br/>
Eine `BSTR`-Variable, die `_bstr_t` zugeordnet oder zugewiesen werden soll.

## <a name="remarks"></a>Hinweise

Wenn `_bstr_t` zuvor an einen anderen `BSTR` angefügt war, bereinigt `_bstr_t` die `BSTR`-Ressource, wenn keine anderen `_bstr_t`-Variablen den `BSTR` verwenden.

## <a name="example"></a>Beispiel

Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein Beispiel mit **Anfügen**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_bstr_t-Klasse](../cpp/bstr-t-class.md)