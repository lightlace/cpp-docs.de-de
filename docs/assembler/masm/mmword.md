---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: d4378c1435df09f249fe7f55dabd4bd0f43f6100
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397177"
---
# <a name="mmword"></a>MMWORD

Wird für 64-Bit-Multimedia-Operanden mit MMX-und SSE (XMM)-Anweisungen verwendet.

## <a name="syntax"></a>Syntax

> **MMWORD**

## <a name="remarks"></a>Hinweise

**MMWORD** ist ein-Typ.  Vor dem Hinzufügen von **MMWORD** zu MASM konnte eine entsprechende Funktionalität mit folgenden Funktionen erzielt werden:

```asm
    mov mm0, qword ptr [ebx]
```

Obwohl beide Anweisungen auf 64-Bit-Operanden funktionieren, ist **QWORD** der Typ für 64-Bit-Ganzzahlen ohne Vorzeichen und **MMWORD** ist der Typ für einen multimediawert von 64-Bit.

**MMWORD** soll denselben Typ wie [__m64](../../cpp/m64.md)darstellen.

## <a name="example"></a>Beispiel

```asm
    movq     mm0, mmword ptr [ebx]
```
