---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 83c9ff588e2fe273e24e1d0b1c16517c5eee3365
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703776"
---
# <a name="if-32-bit-masm"></a>. IF (32-Bit-MASM)

Generiert Code, der `condition1` testet (z. b. ax > 7), und führt die *Anweisungen* aus, wenn diese Bedingung erfüllt ist. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> . Wenn Bedingung1<br/>
> Anweisungen<br/>
> [[. Elseif Bedingung2<br/>
> Anweisungen]]<br/>
> [[. Woanders<br/>
> Anweisungen]]<br/>
> .ENDIF

## <a name="remarks"></a>Hinweise

Wenn ein [. ](../../assembler/masm/dot-else.md)Andernfalls werden die zugehörigen-Anweisungen ausgeführt, wenn die ursprüngliche Bedingung false lautet. Beachten Sie, dass die Bedingungen zur Laufzeit ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>