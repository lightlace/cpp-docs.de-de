---
title: Compilerwarnung (Stufe 1) C4788 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c8a6ad1aa3ae17944b8c2a292d484d55c24d9cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051724"
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