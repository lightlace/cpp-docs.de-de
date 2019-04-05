---
title: once
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
ms.openlocfilehash: 6061fe77960aa64e2dcb39db05897ef0e7fb5f2e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039876"
---
# <a name="once"></a>once
Gibt an, dass die Datei beim Kompilieren einer Quellcodedatei nur einmal vom Compiler eingefügt (geöffnet) wird.

## <a name="syntax"></a>Syntax

```
#pragma once
```

## <a name="remarks"></a>Hinweise

Die Verwendung von `#pragma once` kann die Builderstellungsdauer verringern, da der Compiler nicht öffnen und Lesen Sie die Datei nach dem ersten `#include` der Datei in der Übersetzungseinheit. Dies wird als bezeichnet *Multiple-include-Optimierung*. Es wurde eine ähnliche Wirkung wie das `#include guard` Idiom, das präprozessormakrodefinitionen verwendet, um mehrere Einschlüsse der Inhalte der Datei zu verhindern. Dies wird auch verhindert, dass Verstöße gegen die *eine Richtliniendefinition*– die Anforderung, dass alle Vorlagen, Typen, Funktionen und Objekte in Ihrem Code nicht mehr als eine Definition enthalten.

Zum Beispiel:

```
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

Wir empfehlen die `#pragma once`-Richtlinie für neuen Code, da sie den globalen Namespace nicht mit einem Präprozessorsymbol verunreinigt. Sie erfordert weniger Eingaben, ist weniger verwirrend und kann keine Symbolkonflikte verursachen – Fehler, die verursacht werden, wenn unterschiedliche Headerdateien das gleiche Präprozessorsymbol als Schutzwert verwenden. Sie ist nicht Teil des C++-Standards, wird jedoch portabel durch mehrere allgemeine Compiler implementiert.

Die gleichzeitige Verwendung von #include-Schutz-Idiom und `#pragma once` in derselben Datei bietet keinen Vorteil. Der Compiler erkennt das #include-Schutz-Idiom und implementiert die multiple-include-Optimierung genauso wie die `#pragma once`-Richtlinie, wenn kein Nicht-Kommentarcode oder keine Präprozessordirektive vor oder nach der Standardform des Idioms steht:

```
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

Es wird empfohlen die `#include guard` Idiom, wenn der Code für Compiler portabel sein muss, die keine implementieren die `#pragma once` Richtlinie, um die Konsistenz mit vorhandenem Code aufrechtzuerhalten oder wenn die Multiple-include-Optimierung nicht möglich ist. Dies kann bei komplexen Projekten passieren, wenn Dateisystemaliasing oder Alias-Includepfade verhindern, dass der Compiler identische Includedateien über den kanonischen Pfad identifiziert.

Achten Sie darauf, dass Sie nicht mit `#pragma once` oder `#include guard` Idiom in Headerdateien, die entwickelt wurden, enthalten mehrere Male, indem Präprozessorsymbole zum Steuern ihrer Effekte. Ein Beispiel dieser Entwurf, finden Sie unter den \<assert.h > Header-Datei. Achten Sie auch darauf zum Verwalten von Standardincludepfade, um zu vermeiden, erstellen mehrere Pfade für eingeschlossene Dateien, die zunichte machen, können die Multiple-include-Optimierung für `#include guard`s und `#pragma once`.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)