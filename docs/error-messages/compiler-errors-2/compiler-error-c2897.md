---
title: Compilerfehler C2897 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2897
dev_langs:
- C++
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d05663b913a3e310c091b62a81483f28bbf2c09
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049826"
---
# <a name="compiler-error-c2897"></a>Compilerfehler C2897

ein Destruktor/Finalizer kann nicht keine Funktionsvorlage sein.

Destruktoren oder Finalizer können nicht überladen werden können, ist die Deklaration eines Destruktors als eine Vorlage (die einen Satz von Destruktoren definiert würde) nicht zulässig.

Im folgende Beispiel wird die C2897 generiert:

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2897 generiert.

```
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2897 generiert.

```
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```