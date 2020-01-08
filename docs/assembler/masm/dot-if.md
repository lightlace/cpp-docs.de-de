---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 6992ec8b151a83b3f9fa920997845c20caf0476d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317746"
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

Wenn ein [. ](dot-else.md)Andernfalls werden die zugehörigen-Anweisungen ausgeführt, wenn die ursprüngliche Bedingung false lautet. Beachten Sie, dass die Bedingungen zur Laufzeit ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
