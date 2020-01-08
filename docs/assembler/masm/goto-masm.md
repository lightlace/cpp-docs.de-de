---
title: GOTO (MASM)
ms.date: 12/16/2019
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: f198658f9a4b85e0b5ec9b7a0c122241e57286f6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317278"
---
# <a name="goto"></a>GOTO

Überträgt die Assembly an die Zeile, die mit **:** _Macrolabel_gekennzeichnet ist.

## <a name="syntax"></a>Syntax

> **Goto** *makrolabel*

## <a name="remarks"></a>Hinweise

**Goto** ist nur innerhalb von [Makros](macro.md), [for](for-masm.md)-, [FORC](forc.md)-, [Repeat](repeat.md)-und [while](while-masm.md) -Blöcken zulässig. Das *Makro Label* -Ziel muss die einzige Anweisung in der Zeile sein, und es muss ein vorangestelltem Doppelpunkt vorangestellt sein.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
