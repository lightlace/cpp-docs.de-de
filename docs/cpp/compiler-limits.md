---
title: Compiler-Grenzen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 01260500a564e6cb18b4477a423ce1ef70444201
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402184"
---
# <a name="compiler-limits"></a>Compiler-Grenzen
Der C++-Standard empfiehlt Grenzen für verschiedene Sprachkonstrukte. Es folgt eine Liste von Fällen, bei denen der Visual C++-Compiler keine empfohlenen Limits implementiert. Die erste Nummer ist das im ISO C++ 11-Standard (INCITS/ISO/IEC 14882-2011[2012], Anhang B) definierte Limit, und die zweite Nummer ist das von Visual C++ implementierte Limit:  
  
-   Schachtelungsebenen von verbundanweisungen, iterationssteuerungsstrukturen und Auswahl Steuerungsstrukturen - C++-standard: 256, Visual C++-Compiler: abhängig von der Kombination von geschachtelten Anweisungen, typischerweise jedoch zwischen 100 und 110 ist.  
  
-   Parameter in einer Makrodefinition - C++-standard: 256, Visual C++-Compiler: 127.  
  
-   Argumente in einem Makroaufruf - C++-standard: 256, Visual C++-Compiler 127.  
  
-   Zeichen in einem Zeichen string-literal oder breiten Zeichenfolgenliteral (nach Verkettung) - C++-Standard: 65536, Visual C++-Compiler: 65535 Einzelbytezeichen, einschließlich des NULL-Abschlusszeichens, und 32767 Doppelbytezeichen, einschließlich des NULL-Terminators.  
  
-   Ebenen der geschachtelten Klasse, Struktur oder union-Definitionen in einer einzelnen `struct-declaration-list` -C++-Standard: 256, Visual C++-Compiler: 16.  
  
-   Memberinitialisierer in einer Konstruktordefinition – C++-standard: 6144, Visual C++-Compiler: mindestens 6144.  
  
-   Bereichsqualifikationen eines einzigen Bezeichners - C++-standard: 256, Visual C++-Compiler: 127.  
  
-   Geschachtelte **"extern"** Spezifikationen - C++-standard: 1024, Visual C++-Compiler: 9 (ohne Berücksichtigung der impliziten **"extern"** Spezifikation im globalen Gültigkeitsbereich oder 10, wenn Sie den impliziten zählen **"extern"**  -Spezifikation im globalen Bereich...  
  
-   Vorlagenargumente in einer Vorlagendeklaration - C++-standard: 1024, Visual C++-Compiler: 2046.  
  
## <a name="see-also"></a>Siehe auch  
 [Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md)