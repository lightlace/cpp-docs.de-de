---
title: .PUSHFRAME
ms.date: 08/30/2018
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: b0f047278f6250d5ef359f7992df4ea23f4bbd9b
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398047"
---
# <a name="pushframe"></a>.PUSHFRAME

Generiert einen `UWOP_PUSH_MACHFRAME` Entladungs Code Eintrag. Wenn der optionale *Code* angegeben wird, erhält der Entladungs Code Eintrag einen Modifizierer von 1. Andernfalls ist der-Modifizierer 0.

## <a name="syntax"></a>Syntax

> **. PushFrame** ⟦*Code*⟧;;

## <a name="remarks"></a>Hinweise

. Mithilfe von PushFrame können Benutzer von ml64. exe angeben, wie sich eine Frame Funktion entlädt und nur innerhalb des Prologs zulässig ist, der von der [proc](../../assembler/masm/proc.md) Frame-Deklaration zum reicht [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. **. Dem PushFrame** sollten Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
