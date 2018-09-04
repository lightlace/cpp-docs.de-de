---
title: IF (MASM) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca0cce834924f7fc147b1ef301d5bd345dfd2973
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685306"
---
# <a name="if-masm"></a>IF (MASM)

Gewährt der Assembly des *Ifstatements* Wenn *expression1* true (ungleich) oder *Elseifstatements* Wenn *expression1* ist "false" (0) und *expression2* ist "true".

## <a name="syntax"></a>Syntax

> IF *expression1*<br/>
> *ifstatements*<br/>
> [[ELSEIF *expression2*<br/>
> *Elseifstatements*]]<br/>
> [[ELSE<br/>
> *Elsestatements*]]<br/>
> ENDIF

## <a name="remarks"></a>Hinweise

Die folgenden Anweisungen können als Ersatz für [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, und **ELSEIFNDEF** . Optional, assembliert *Elsestatements* , wenn der vorherige Ausdruck falsch ist. Beachten Sie, dass die Assembly zum Zeitpunkt der Ausdrücke ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>