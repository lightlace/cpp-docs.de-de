---
title: Compilerfehler C2504 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fb11774f65454799761913babb428dc6a471743
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054128"
---
# <a name="compiler-error-c2504"></a>Compilerfehler C2504

'Klasse': Basisklasse undefiniert

Die Basisklasse der Klasse deklariert, aber nicht definiert.  Mögliche Ursachen:

1. Include-Datei fehlt.

1. Externe Basisklasse ist nicht mit deklariert ["extern"](../../cpp/using-extern-to-specify-linkage.md).

Im folgende Beispiel wird die C2504 generiert:

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

OKAY

```
class C{};
class D : public C {};
```