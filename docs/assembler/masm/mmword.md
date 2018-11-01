---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: 1205338f9140c74a3a6e0b4bce57983edc80862e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541117"
---
# <a name="mmword"></a>MMWORD

Für 64-Bit-multimediaoperanden MMX- und SSE (XMM)-Anweisungen verwendet.

## <a name="syntax"></a>Syntax

> MMWORD

## <a name="remarks"></a>Hinweise

`MMWORD` ist ein Typ.  Vor dem MMWORD MASM hinzugefügt wird kann entsprechende Funktionalität mit erreicht wurden:

```asm
    mov mm0, qword ptr [ebx]
```

Zwar beide Anweisungen für 64-Bit-Operanden funktionieren `QWORD` ist der Typ für 64-Bit-Ganzzahlen ohne Vorzeichen und `MMWORD` ist der Typ für einen 64-Bit-multimedia-Wert.

`MMWORD` Dient zum Darstellen des gleichen Typs wie [__m64](../../cpp/m64.md).

## <a name="example"></a>Beispiel

```asm
    movq     mm0, mmword ptr [ebx]
```