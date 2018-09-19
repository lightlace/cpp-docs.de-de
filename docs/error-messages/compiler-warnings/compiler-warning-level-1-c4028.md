---
title: Compilerwarnung (Stufe 1) C4028 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4028
dev_langs:
- C++
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6c71f04b8f0829bbc321d38a18e4307df51ff0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054739"
---
# <a name="compiler-warning-level-1-c4028"></a>Compilerwarnung (Stufe 1) C4028

formale Parameter 'Nummer' unterscheidet sich von der Deklaration

Der Typ des formalen Parameters stimmt nicht mit dem entsprechenden Parameter in der Deklaration überein. Der Typ in der ursprünglichen Deklaration wird verwendet.

Diese Warnung gilt nur für C#-Quellcode.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4028 generiert.

```
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```