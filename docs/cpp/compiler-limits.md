---
title: Compiler-Grenzen | Microsoft Docs
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
ms.openlocfilehash: bc7cd26add0a46bab8df7669fb6dfb6060b0010e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-limits"></a>Compiler-Grenzen
Der C++-Standard empfiehlt Grenzen für verschiedene Sprachkonstrukte. Es folgt eine Liste von Fällen, bei denen der Visual C++-Compiler keine empfohlenen Limits implementiert. Die erste Nummer ist das im ISO C++ 11-Standard (INCITS/ISO/IEC 14882-2011[2012], Anhang B) definierte Limit, und die zweite Nummer ist das von Visual C++ implementierte Limit:  
  
-   Schachteln von Ebenen von verbundanweisungen, Iteration Steuerungsstrukturen und Auswahl Steuerelementstrukturen - C++-standard: 256, Visual C++-Compiler: die Kombination von Anweisungen, die geschachtelt sind, doch im Allgemeinen zwischen 100 und 110 abhängig.  
  
-   Parameter in einer Makrodefinition - C++-standard: 256, Visual C++-Compiler: 127.  
  
-   Argumente in einem Makroaufruf - C++-standard: 256, Visual C++-Compiler 127.  
  
-   Zeichen in einem Zeichen string-literal oder breiten Zeichenfolgenliterals (nach der Verkettung) - C++-Standard: 65536, Visual C++-Compiler: 65535 Einzelbyte-Zeichen, einschließlich der `null` Terminator und 32767 Doppelbyte-Zeichen, einschließlich der `null` Abschlusszeichen.  
  
-   Ebenen der geschachtelten Klasse, Struktur oder union Definitionen in einer einzelnen `struct-declaration-list` -C++-Standard: 256, Visual C++-Compiler: 16.  
  
-   In der Konstruktordefinition eines - C++-standard datenmemberinitialisierer: 6144, Visual C++-Compiler: mindestens 6144.  
  
-   Bereich Qualifikationen von einem Bezeichner - C++-standard: 256, Visual C++-Compiler: 127.  
  
-   Geschachtelte `extern` Spezifikationen - C++-standard: 1024, Visual C++-Compiler: 9 (wird dabei nicht mitgezählt impliziter `extern` Spezifikation im globalen Gültigkeitsbereich oder 10, wenn Sie die implizite zählen `extern` Spezifikation im globalen Gültigkeitsbereich...  
  
-   Vorlagenargumente in einer Vorlagendeklaration - C++-standard: 1024, Visual C++-Compiler: 2046.  
  
## <a name="see-also"></a>Siehe auch  
 [Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md)