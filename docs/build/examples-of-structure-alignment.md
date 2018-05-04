---
title: Beispiele für die Strukturausrichtung | Microsoft Docs
ms.custom: ''
ms.date: 03/26/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structure alignment
- examples [C++], structure alignment
ms.assetid: 03d137bf-5cc4-472e-9583-6498f2534199
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9c4e8cb27d02777e40af56217bd82dec6e647b6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="examples-of-structure-alignment"></a>Beispiele für die Strukturausrichtung

Die folgenden vier Beispielen jedes deklarieren, dass eine ausgerichteten Struktur oder Union und die entsprechenden Zahlen veranschaulichen das Layout, Struktur oder Union im Arbeitsspeicher. Jede Spalte in der Abbildung steht ein Byte des Arbeitsspeichers und der Wert in der Spalte an der Verschiebung von Bytes. Der Name in der zweiten Zeile jeder Abbildung entspricht dem Namen einer Variablen in der Deklaration. Die schattierten Spalten anzugeben, dass die Auffüllung, die zum Erreichen der angegebenen Ausrichtung erforderlich ist.

## <a name="example-1"></a>Beispiel 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD-Konvertierungsbeispiel](../build/media/vcamd_conv_ex_1_block.png "vcAmd_conv_ex_1")

## <a name="example-2"></a>Beispiel 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD-Konvertierungsbeispiel](../build/media/vcamd_conv_ex_2_block.png "vcAmd_conv_ex_2")

## <a name="example-3"></a>Beispiel 3

```C
// Total size = 22 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD-Konvertierungsbeispiel](../build/media/vcamd_conv_ex_3_block.png "vcAmd_conv_ex_3")

## <a name="example-4"></a>Beispiel 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD-Konvertierungsbeispiel](../build/media/vcamd_conv_ex_4_block.png "vcAmd_conv_ex_4")

## <a name="see-also"></a>Siehe auch

[Typen und Speicher](../build/types-and-storage.md)<br/>
