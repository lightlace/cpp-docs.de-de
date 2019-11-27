---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e8213052dce8d84d62f90d4bc2653435c2b31434
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398221"
---
# <a name="if-32-bit-masm"></a>. IF (32-Bit-MASM)

Generiert Code, der *Bedingung1* testet (z. b. ax > 7) und führt die *Anweisungen* aus, wenn diese Bedingung erfüllt ist. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> **. Wenn** *Bedingung1*\
> *Anweisungen*\
> ⟦ **. Elseif** *Bedingung2*\
> *Anweisungen*⟧ \
> ⟦ **. Else** -\
> *Anweisungen*⟧ \
> **.ENDIF**

## <a name="remarks"></a>Hinweise

Wenn ein [. ](../../assembler/masm/dot-else.md)Andernfalls werden die zugehörigen-Anweisungen ausgeführt, wenn die ursprüngliche Bedingung false lautet. Beachten Sie, dass die Bedingungen zur Laufzeit ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
