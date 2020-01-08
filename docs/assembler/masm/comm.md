---
title: COMM
ms.date: 12/06/2019
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: 0ea02806cae3295af0846baa6c4e9049d54c271b
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75315172"
---
# <a name="comm"></a>COMM

Erstellt eine kommunale Variable mit den in der *Definition*angegebenen Attributen.

## <a name="syntax"></a>Syntax

> **Comm** - *Definition* ⟦ __,__ *Definition* ... ⟧

## <a name="remarks"></a>Hinweise

Die kommunalen Variablen werden vom Linker zugewiesen und können nicht initialisiert werden. Dies bedeutet, dass Sie nicht von dem Speicherort oder der Reihenfolge dieser Variablen abhängig sein können.

Jede *Definition* weist die folgende Form auf:

⟦*Language-Type*⟧ ⟦**near** | **Far**⟧ _Label_ **:** _Type_⟦ **:** _count_⟧

Die *Sprachtyp-* , **near**-und **Far** -Argumente sind nur in 32-Bit-MASM gültig.

Der optionale *Sprachtyp* legt die Benennungs Konventionen für den folgenden Namen fest. Sie überschreibt alle Sprachen, die von angegeben werden **. Model** -Direktive. Das optionale **near** -oder **Far** -überschreiben das aktuelle Speichermodell. Die *Bezeichnung ist der* Name der Variablen. Der *Typ* kann ein beliebiger Typspezifizierer ([Byte](byte-masm.md), [Word](word.md)usw.) oder eine ganze Zahl sein, die die Anzahl von Bytes angibt. Der optionale *Zähler* gibt die Anzahl der Elemente im deklarierten Datenobjekt an. Die Standard *Anzahl* ist 1.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein Array von 512 Byte-Elementen erstellt:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
