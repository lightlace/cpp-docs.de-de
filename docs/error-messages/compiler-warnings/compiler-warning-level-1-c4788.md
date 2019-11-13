---
title: Compilerwarnung (Stufe 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: 03ce38aaa910a410025c5cccdf39646d34104779
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052387"
---
# <a name="compiler-warning-level-1-c4788"></a>Compilerwarnung (Stufe 1) C4788

'Bezeichner': Der Bezeichner wurde auf 'Anzahl' Zeichen gekürzt.

Durch den Compiler wird die für einen Funktionsnamen zugelassene maximale Länge eingeschränkt. Wenn der Compiler funclets für EH/SEH-Code generiert, bildet er den funclet-Namen, indem er den Funktionsnamen mit einem Text vorangestellt, z. b. "__catch", "\__unwind" oder einer anderen Zeichenfolge.

Wenn der erstellte funclet-Name zu lang ist, wird dieser vom Compiler gekürzt, und es wird C4788 ausgegeben.

Um diese Warnung zu vermeiden, kürzen Sie den ursprünglichen Funktionsnamen. Wenn es sich bei der Funktion um eine C++-Vorlagenfunktion oder -Methode handelt, verwenden Sie für einen Teil des Namens eine Typdefinition. Beispiel:

```cpp
C1<x, y, z<T>>::C2<a,b,c>::f
```

Dies kann durch Folgendes ersetzt werden:

```cpp
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

Diese Warnung tritt nur im x64-Compiler auf.