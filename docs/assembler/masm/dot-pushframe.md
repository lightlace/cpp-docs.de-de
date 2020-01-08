---
title: .PUSHFRAME
description: Beschreibt die. PushFrame-MASM-Direktive, mit der angegeben wird, wie eine Frame Funktion entladen werden soll.
ms.date: 12/06/2019
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 0aaec119d26d87fddb1eba505458da1250a5926e
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317577"
---
# <a name="pushframe"></a>.PUSHFRAME

Generiert einen `UWOP_PUSH_MACHFRAME` Entladungs Code Eintrag. Wenn das optionale **Code** Schlüsselwort angegeben wird, erhält der Entladungs Code Eintrag einen Modifizierer von 1. Andernfalls ist der-Modifizierer 0.

## <a name="syntax"></a>Syntax

> **. PushFrame** ⟦**Code**⟧;;

## <a name="remarks"></a>Hinweise

. Mithilfe von PushFrame können Benutzer von ml64. exe angeben, wie sich eine Frame Funktion entlädt. Es ist nur innerhalb des Prologs zulässig, der sich von der [proc](proc.md) Frame-Deklaration zum erstreckt [. ENDPROLOG](dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. **. Dem PushFrame** sollten Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es empfiehlt sich, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
