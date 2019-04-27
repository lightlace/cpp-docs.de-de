---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 2b91698640e028bf91d822c12b85ded651a04d8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203063"
---
# <a name="if-masm"></a>IF (MASM)

Gewährt der Assembly des *Ifstatements* Wenn *expression1* true (ungleich) oder *Elseifstatements* Wenn *expression1* ist "false" (0) und *expression2* ist "true".

## <a name="syntax"></a>Syntax

> IF *expression1*<br/>
> *ifstatements*<br/>
> [[ELSEIF *expression2*<br/>
> *elseifstatements*]]<br/>
> [[ELSE<br/>
> *elsestatements*]]<br/>
> ENDIF

## <a name="remarks"></a>Hinweise

Die folgenden Anweisungen können als Ersatz für [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI**, **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, und **ELSEIFNDEF**. Optional, assembliert *Elsestatements* , wenn der vorherige Ausdruck falsch ist. Beachten Sie, dass die Assembly zum Zeitpunkt der Ausdrücke ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>