---
title: once-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
ms.openlocfilehash: 643ad83b672f7b632925383972751a966256eb41
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220538"
---
# <a name="once-pragma"></a>once-Pragma

Gibt an, dass der Compiler die Header Datei nur einmal einschließt, wenn eine Quell Code Datei kompiliert wird.

## <a name="syntax"></a>Syntax

> **einmal #Pragma**

## <a name="remarks"></a>Hinweise

Die Verwendung von `#pragma once` kann Buildzeiten reduzieren, da der Compiler die Datei nach dem ersten `#include` der Datei in der Übersetzungseinheit nicht mehr öffnet und liest. Dies wird als *Multi-include-Optimierung*bezeichnet. Es wirkt sich ähnlich wie das *include Guard* -Idiom aus, das präprozessormakrodefinitionen verwendet, um mehrere includeinhalte der Datei zu vermeiden. Außerdem hilft es bei Verstößen gegen *eine Definitions Regel*, die Anforderung, dass alle Vorlagen, Typen, Funktionen und Objekte nicht mehr als eine Definition im Code aufweisen.

Beispiel:

```cpp
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

Wir empfehlen die `#pragma once`-Richtlinie für neuen Code, da sie den globalen Namespace nicht mit einem Präprozessorsymbol verunreinigt. Er erfordert weniger Typisierung, ist weniger ablenkend und kann keine *Symbol*Konflikte verursachen. Fehler, die verursacht werden, wenn unterschiedliche Header Dateien das gleiche Präprozessorsymbol wie der Wächter Wert verwenden. Sie ist nicht Teil des C++ Standards, aber Sie ist von mehreren gängigen Compilern portabel implementiert.

Es gibt keinen Vorteil, sowohl das include-Schutz-Idiom als `#pragma once` auch in der gleichen Datei zu verwenden. Der Compiler erkennt das include-Schutz-Idiom und implementiert die Multiple-include-Optimierung genauso wie die `#pragma once` -Direktive, wenn kein nicht-Kommentar Code oder keine Präprozessordirektive vor oder nach der Standardform des Ausdrucks steht:

```cpp
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

Wir empfehlen das include-Schutz-Idiom, wenn Code für Compiler portabel sein muss, `#pragma once` die die-Direktive nicht implementieren, um die Konsistenz mit vorhandenem Code aufrechtzuerhalten, oder wenn die Multi-include-Optimierung nicht möglich ist. Dies kann in komplexen Projekten vorkommen, wenn Dateisystem Aliasing oder Alias-Includepfade verhindern, dass der Compiler identische Includedateien nach kanonischen Pfad identifiziert.

Achten Sie darauf, dass `#pragma once` Sie nicht oder das include Guard-Idiom in Header Dateien verwenden, die mehrere Male eingeschlossen werden sollen, die Präprozessorsymbole verwenden, um ihre Auswirkungen zu steuern. Ein Beispiel für diesen Entwurf finden Sie in der \<>-Header Datei Assert. h. Achten Sie auch darauf, die Includepfade zu verwalten, um zu vermeiden, dass mehrere Pfade zu eingebundenen Dateien erstellt werden. Dies kann die Multi `#pragma once`-include-Optimierung für beide include-Wächter und-

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
