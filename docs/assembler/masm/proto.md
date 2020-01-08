---
title: PROTO
ms.date: 12/06/2019
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 3963fa29050653d1706222d33734c4b5f2a17919
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318643"
---
# <a name="proto"></a>PROTO

Prototypen eine Funktion oder Prozedur. Sie können die Funktion, die von der Prototyp-Direktive verwendet wird, mithilfe der Anweisung " [aufrufen](invoke.md) " aufrufen.

## <a name="syntax"></a>Syntax

> *Bezeichnung* **Proto** ⟦*Distance*⟧ ⟦*Language-Type*⟧ ⟦ __,__ ⟦*Parameter*⟧ __:__ *Tag* ... ⟧

### <a name="parameters"></a>Parameters

*Bezeichnung*\
Der Name der Funktion mit prototyptypisierung.

*Distance* (nur 32-Bit-MASM.) \
Optionale Wird in 16-Bit-Speicher Modellen verwendet, um den Standardwert zu überschreiben und **near** -oder **Far** -Aufrufe anzugeben

*Sprachtyp* (nur 32-Bit-MASM.) \
Optionale Legt die Aufruf-und Benennungs Konvention für Prozeduren und öffentliche Symbole fest. Folgende Konventionen werden unterstützt:

- 32-Bit- **flatmodel** : **C**, **StdCall**

- 16-Bit-Modelle: **C**, **Basic**, **Fortran**, **Pascal**, **syscall**, **StdCall**

*Parameter*\
Der optionale Name für einen Funktionsparameter.

*Tag\*
Der Typ eines Funktions Parameters.

Die *Parameter* -und *Tagparameter* können mehrmals, einmal für jedes übergebenen Argument angezeigt werden.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt eine **Proto** -Deklaration für eine Funktion mit dem Namen `addup3`, die einen **near** -Aufruf verwendet, um den Standard-16-Bit-Modell für Prozedur Aufrufe zu überschreiben, und die **C** -Aufruf Konvention für Stapel Parameter und Rückgabewerte verwendet. Es werden zwei Argumente benötigt: ein **Wort** und ein **vararg**.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[. Modell Verweis](dot-model.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
