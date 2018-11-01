---
title: malloc-Ausrichtung
ms.date: 11/04/2016
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
ms.openlocfilehash: 436033d4e99d42d0a1a9366377f928bc402ac974
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533548"
---
# <a name="malloc-alignment"></a>malloc-Ausrichtung

["malloc"](../c-runtime-library/reference/malloc.md) ist immer, den Speicher zurück, die passend ausgerichtet ist, für das Speichern eines beliebigen Objekts, die eine grundlegende Ausrichtung und die hinsichtlich der Menge des Arbeitsspeichers unterbringen konnten, die zugeordnet wird. Ein *grundlegende Ausrichtung* ist eine Ausrichtung, die kleiner oder gleich der größten Ausrichtung, die von der Implementierung ohne Ausrichtungsspezifikation unterstützt wird. (In Visual C++ ist dies die Ausrichtung, die für einen `double` oder 8 Bytes erforderlich ist. In einem Code, der auf 64-Bit-Plattformen ausgerichtet ist, sind es 16 Bytes.) Beispielsweise kann eine Vier-Byte-Speicherbelegung an einer Begrenzung ausgerichtet werden, die ein Objekt unterstützt, das maximal vier Byte groß ist.

Visual C++ unterstützt Typen mit *über eine erweiterte Ausrichtung*, welche sind auch bekannt als *über-ausgerichtete* Typen. Beispielsweise die SSE-Typen [__m128](../cpp/m128.md) und `__m256`, sowie Typen, die mithilfe von deklariert werden `__declspec(align( n ))` , in denen `n` ist größer als 8, verfügen über eine erweiterte Ausrichtung. Eine Speicherausrichtung an einer Grenze, die für ein Objekt geeignet ist, das eine erweiterte Ausrichtung erfordert, wird von `malloc` nicht gewährleistet. Um Arbeitsspeicher für über-ausgerichtete Typen zuzuordnen, verwenden Sie [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) und verwandte Funktionen.

## <a name="see-also"></a>Siehe auch

[Verwendung von Stapeln](../build/stack-usage.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)