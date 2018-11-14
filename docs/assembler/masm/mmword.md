---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: e4ebaa9d47a569bc9cf7d843d3ddb54ca5d713a0
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328226"
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
    movq     mm0, mmword ptr [ebx]
```