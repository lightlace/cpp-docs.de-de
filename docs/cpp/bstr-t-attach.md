---
title: _bstr_t::Attach | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1eddbc7a01be66430759bb84c3ce6d840f37d098
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111211"
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