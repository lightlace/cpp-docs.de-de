---
title: .IF
ms.date: 08/30/2018
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: cf9c594d843c937dd2191bee2a7cebadbc615c82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185266"
---
# <a name="if"></a>.IF

Generiert Code, der testet `condition1` (z. B. AX-> 7) und führt die *Anweisungen* , wenn die Bedingung erfüllt ist.

## <a name="syntax"></a>Syntax

> . IF-Bedingung 1<br/>
> Anweisungen<br/>
> [[. ELSEIF Bedingung2<br/>
> Anweisungen]]<br/>
> [[.ELSE<br/>
> Anweisungen]]<br/>
> .ENDIF

## <a name="remarks"></a>Hinweise

Wenn eine [. ANDERE](../../assembler/masm/dot-else.md) folgt, die Anweisungen ausgeführt werden, wenn Sie den ursprünglichen Zustand auf "false" festgelegt wurde. Beachten Sie, dass die Bedingungen zur Laufzeit ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>