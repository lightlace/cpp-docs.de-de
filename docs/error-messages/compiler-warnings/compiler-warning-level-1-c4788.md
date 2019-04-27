---
title: Compilerwarnung (Stufe 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: c51a4409c2a3028823462539343654b5eac365d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187204"
---
# <a name="compiler-warning-level-1-c4788"></a>Compilerwarnung (Stufe 1) C4788

'Bezeichner': Der Bezeichner wurde auf 'Anzahl' Zeichen gekürzt.

Durch den Compiler wird die für einen Funktionsnamen zugelassene maximale Länge eingeschränkt. Wenn der Compiler Funclets für EH/SEH-Code generiert, werden durch den Namen der Funktion mit etwas Text voranstellen der Funclet-Name bildet, z. B. "__catch," "\__unwind", oder eine andere Zeichenfolge.

Wenn der erstellte funclet-Name zu lang ist, wird dieser vom Compiler gekürzt, und es wird C4788 ausgegeben.

Um diese Warnung zu vermeiden, kürzen Sie den ursprünglichen Funktionsnamen. Wenn es sich bei der Funktion um eine C++-Vorlagenfunktion oder -Methode handelt, verwenden Sie für einen Teil des Namens eine Typdefinition. Zum Beispiel:

```
C1<x, y, z<T>>::C2<a,b,c>::f
```

Dies kann durch Folgendes ersetzt werden:

```
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

Diese Warnung tritt nur in der X64 Compiler.