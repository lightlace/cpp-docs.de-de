---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 2b91698640e028bf91d822c12b85ded651a04d8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555784"
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