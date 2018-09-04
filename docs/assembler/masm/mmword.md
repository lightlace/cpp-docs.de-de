---
title: DIE MMWORD | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7314c6d0861195e312c7f72481d2e195e041965d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679233"
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