---
title: ALIAS (MASM)
ms.date: 12/17/2019
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 5aef169c5632e74722438c63718ce5b783a8da09
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316602"
---
# <a name="alias"></a>ALIAS

Die **Alias** -Direktive erstellt einen alternativen Namen für eine Funktion.  Auf diese Weise können Sie mehrere Namen für eine Funktion erstellen oder Bibliotheken erstellen, mit denen der Linker (Link. exe) eine alte Funktion einer neuen Funktion zuordnen kann.

## <a name="syntax"></a>Syntax

> **Alias \<** _Alias_ **> = \<** _tatsächlicher Name_ **>**

#### <a name="parameters"></a>Parameters

*tatsächlicher Name*\
Der tatsächliche Name der Funktion oder Prozedur.  Die Klammern sind erforderlich.

*Alias*\
Der Alternative oder Alias Name.  Die Klammern sind erforderlich.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
