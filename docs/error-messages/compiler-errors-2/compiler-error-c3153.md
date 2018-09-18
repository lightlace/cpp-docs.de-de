---
title: Compilerfehler C3153 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3153
dev_langs:
- C++
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 621af32475008eda4d7502530087673dcb4a0848
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016039"
---
# <a name="compiler-error-c3153"></a>Compilerfehler C3153

'Schnittstelle': Sie können keine Instanz einer Schnittstelle erstellen

Eine Schnittstelle kann nicht instanziiert werden. Um der Member einer Schnittstelle zu verwenden, leiten Sie eine Klasse von der Schnittstelle, implementieren Sie die Schnittstellenmember zu und verwenden Sie die Elemente.

Im folgende Beispiel wird die C3153 generiert:

```
// C3153.cpp
// compile with: /clr
interface class A {
};

int main() {
   A^ a = gcnew A;   // C3153
}
```
