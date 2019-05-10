---
title: Compiler-Grenzen
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: 9663da06c97886ef1cd20ca2928944795b39dc18
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222192"
---
# <a name="compiler-limits"></a>Compiler-Grenzen

Der C++-Standard empfiehlt Grenzen für verschiedene Sprachkonstrukte. Im folgenden finden eine Liste der Fälle, in denen Microsoft C++ -Compiler wird keine empfohlenen Limits implementiert. Die erste Zahl ist die Grenze, die der ISO-Datei besteht C++ 11-standard (INCITS/ISO/IEC 14882-2011 [2012], Anhang B) und die zweite Zahl liegt die Beschränkung, die von Microsoft implementiert C++ Compiler:

- Schachtelungsebenen von verbundanweisungen, iterationssteuerungsstrukturen und auswahlsteuerungsstrukturen - C++ standard: 256, Microsoft C++ Compiler: abhängig von der Kombination von geschachtelten Anweisungen, typischerweise jedoch zwischen 100 und 110 ist.

- Parameter in einer Makrodefinition - C++ standard: 256, Microsoft C++ Compiler: 127.

- Argumente in einem Makroaufruf - C++ standard: 256, Microsoft C++ Compiler 127.

- Zeichen in einem Zeichen string-literal oder breiten Zeichenfolgenliteral (nach Verkettung) - C++ standard: 65536, Microsoft C++ Compiler: 65535 Einzelbytezeichen, einschließlich des NULL-Abschlusszeichens, und 32767 Doppelbytezeichen, einschließlich des NULL-Terminators.

- Ebenen der geschachtelten Klasse, Struktur oder union-Definitionen in einer einzelnen `struct-declaration-list` - C++ standard: 256, Microsoft C++ Compiler: 16.

- Memberinitialisierer in einer Konstruktordefinition – C++ standard: 6144, Microsoft C++ Compiler: mindestens 6144.

- Bereichsqualifikationen eines einzigen Bezeichners - C++ standard: 256, Microsoft C++ Compiler: 127.

- Geschachtelte **"extern"** Spezifikationen - C++ standard: 1024, Microsoft C++ Compiler: 9 (ohne Berücksichtigung der impliziten **"extern"** Spezifikation im globalen Gültigkeitsbereich oder 10, wenn Sie den impliziten zählen **"extern"** -Spezifikation im globalen Bereich.

- Vorlagenargumente in einer Vorlagendeklaration - C++ standard: 1024, Microsoft C++ Compiler: 2046.

## <a name="see-also"></a>Siehe auch

[Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md)