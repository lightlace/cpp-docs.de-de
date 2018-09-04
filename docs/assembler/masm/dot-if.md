---
title: . IF | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7bd5ba5821b4dcfb2d088e31816f50540445018
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691543"
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