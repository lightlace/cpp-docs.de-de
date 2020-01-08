---
title: LOCAL (MASM)
ms.date: 12/16/2019
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 2bef6b26f1b922be6512bd6ebe8e0b2627e86f45
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317148"
---
# <a name="local"></a>LOCAL

In der ersten Direktive definiert **local** innerhalb eines Makros Bezeichnungen, die für jede Instanz des Makros eindeutig sind.

## <a name="syntax"></a>Syntax

> **Local** *localId* ⟦, *localId* ... ⟧
>
> **Local** *LabelId* ⟦ __\[__ *count* __]__ ⟧ ⟦ __:__ *qualifiedtype*⟧ ⟦ __,__ *LabelId* ⟦ __\[__ *count* __]__ ⟧ ⟦*qualifiedtype*⟧... ⟧

## <a name="remarks"></a>Hinweise

In der zweiten-Direktive erstellt in einer Prozedur Definition (**proc**) in der **lokalen** Prozedur Stapel basierte Variablen, die für die Dauer der Prozedur vorhanden sind. Die *LabelId* kann eine einfache Variable oder ein Array mit *count* -Elementen sein, wobei *count* ein konstanter Ausdruck ist.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
