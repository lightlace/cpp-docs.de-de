---
title: IF1 und IF2
ms.date: 11/21/2019
f1_keywords:
- IF2
- IF1
helpviewer_keywords:
- IF2 directive
- IF2 directive
ms.assetid: a0f75564-b51b-4e39-ad3b-f7421e7ecad6
ms.openlocfilehash: 60f8b0dcedb61ac06de929aff300845e342d7cfc
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317317"
---
# <a name="if1-and-if2"></a>IF1 und IF2

Der **IF1** -Block wird bei der ersten Assembly ausgewertet.

Der **IF2** -Block wird für jeden assemblydurchlauf ausgewertet, wenn die **Option: SETIF2** **true**ist.

## <a name="syntax"></a>Syntax

> **IF1;;**

> **IF2;;**

## <a name="remarks"></a>Hinweise

Die gesamte [Syntax finden Sie](if-masm.md) unter.

Anders als bei Version 5,1 führen MASM 6,1 und höher den größten Teil der Arbeit am ersten Durchlauf aus und führen dann so viele nachfolgende Übergängen aus, wie erforderlich. Im Gegensatz dazu wird MASM 5,1 immer in zwei Quell Durchläufen assembliert. Daher müssen Sie möglicherweise einige Pass-abhängige Konstrukte unter MASM 6,1 und höher überarbeiten oder löschen.

### <a name="two-pass-directives"></a>Two-Pass-Direktiven

Um Kompatibilität zu gewährleisten, unterstützen MASM 6,1 und höher 5,1-Direktiven, die auf zwei Durchgänge verweisen Hierzu gehören **. ERR1**, **. ERR2**, **IF1**, **IF2**, **ELSEIF1**und **ELSEIF2**. Für Second-Pass-Konstrukte müssen Sie die [Option SETIF2](option-masm.md)angeben. Ohne die **Option SETIF2**, **IF2** und **. ERR2** -Direktiven verursachen einen Fehler:

```output
.ERR2 not allowed : single-pass assembler
```

MASM 6,1 und höher verarbeiten die First-Pass-Konstrukte anders. Die wird behandelt **. ERR1** -Direktive als **. Err**und die **IF1** -Direktive wie **if**.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
