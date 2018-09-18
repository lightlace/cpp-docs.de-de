---
title: Compilerfehler C2917 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2917
dev_langs:
- C++
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2747b001cc81da4edde21f201cd34392c2dcba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020887"
---
# <a name="compiler-error-c2917"></a>Compilerfehler C2917

'Name': Ungültiger Vorlagenparameter.

Eine Vorlagenparameterliste enthält einen Bezeichner, der kein Vorlagenparameter war.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2917 generiert:

```
// C2917.cpp
// compile with: /c
template<class T> class Vector {
   void sort();
};

template<class T*> void Vector<T>::sort() {}   // C2917
// try the following line instead
// template<class T> void Vector<T>::sort() {}
```