---
title: .IF
ms.date: 08/30/2018
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: cf9c594d843c937dd2191bee2a7cebadbc615c82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483637"
---
# <a name="if"></a>.IF

Generiert Code, der testet `condition1` (z. B. AX-> 7) und führt die *Anweisungen* , wenn die Bedingung erfüllt ist.

## <a name="syntax"></a>Syntax

> . IF-Bedingung 1<br/>
> Anweisungen<br/>
> [[. ELSEIF Bedingung2<br/>
> Anweisungen]]<br/>
> [[. ANDERE<br/>
> Anweisungen]]<br/>
> .ENDIF

## <a name="remarks"></a>Hinweise

Wenn eine [. ANDERE](../../assembler/masm/dot-else.md) folgt, die Anweisungen ausgeführt werden, wenn Sie den ursprünglichen Zustand auf "false" festgelegt wurde. Beachten Sie, dass die Bedingungen zur Laufzeit ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>