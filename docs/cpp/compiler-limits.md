---
title: Compiler-Grenzen
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: a0c6041d326982dc9807355733cf714dcfa62ca8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399160"
---
# <a name="compiler-limits"></a>Compiler-Grenzen

Der C++-Standard empfiehlt Grenzen für verschiedene Sprachkonstrukte. Es folgt eine Liste von Fällen, bei denen der Visual C++-Compiler keine empfohlenen Limits implementiert. Die erste Nummer ist das im ISO C++ 11-Standard (INCITS/ISO/IEC 14882-2011[2012], Anhang B) definierte Limit, und die zweite Nummer ist das von Visual C++ implementierte Limit:

- Schachtelungsebenen von verbundanweisungen, iterationssteuerungsstrukturen und auswahlsteuerungsstrukturen - C++ standard: 256, Visual C++ Compiler: abhängig von der Kombination von geschachtelten Anweisungen, typischerweise jedoch zwischen 100 und 110 ist.

- Parameter in einer Makrodefinition - C++ standard: 256, Visual C++ Compiler: 127.

- Argumente in einem Makroaufruf - C++ standard: 256, Visual C++ Compiler 127.

- Zeichen in einem Zeichen string-literal oder breiten Zeichenfolgenliteral (nach Verkettung) - C++ standard: 65536, Visual C++ Compiler: 65535 Einzelbytezeichen, einschließlich des NULL-Abschlusszeichens, und 32767 Doppelbytezeichen, einschließlich des NULL-Terminators.

- Ebenen der geschachtelten Klasse, Struktur oder union-Definitionen in einer einzelnen `struct-declaration-list` - C++ standard: 256, Visual C++ Compiler: 16.

- Memberinitialisierer in einer Konstruktordefinition – C++ standard: 6144, Visual C++ Compiler: mindestens 6144.

- Bereichsqualifikationen eines einzigen Bezeichners - C++ standard: 256, Visual C++ Compiler: 127.

- Geschachtelte **"extern"** Spezifikationen - C++ standard: 1024, Visual C++ Compiler: 9 (ohne Berücksichtigung der impliziten **"extern"** Spezifikation im globalen Gültigkeitsbereich oder 10, wenn Sie den impliziten zählen **"extern"** -Spezifikation im globalen Bereich.

- Vorlagenargumente in einer Vorlagendeklaration - C++ standard: 1024, Visual C++ Compiler: 2046.

## <a name="see-also"></a>Siehe auch

[Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md)