---
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 23c6b0aefae856da449da574669e8475122c7556
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312949"
---
# <a name="macro"></a>MACRO

Markiert einen Makroblock namens *Name* und richtet *Parameter* Platzhalter für Argumente ein, die übergeben werden, wenn das Makro aufgerufen wird.

## <a name="syntax"></a>Syntax

> *Name***Macro** ⟦*Parameter* ⟦ **: req** | : =*default* | *args* **: vararg**⟧... ⟧\
> *Anweisungen*\
⟦**Goto** :*makrolabelid*⟧ \
> ⟦**Exitm**⟧ \
> **ENDM** ⟦*Wert*⟧

## <a name="remarks"></a>Hinweise

Eine Makrofunktion gibt einen *Wert* an die aufrufenden Anweisung zurück.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[Goto (MASM)](goto-masm.md) -\
[ENDM](endm.md) -\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)

