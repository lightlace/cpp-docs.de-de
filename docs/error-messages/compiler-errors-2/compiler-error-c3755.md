---
title: Compilerfehler C3755 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 647f62fa75226fd2c80d1bf6285d76e1c2f8c4be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026725"
---
# <a name="compiler-error-c3755"></a>Compilerfehler C3755

'Delegat': ein Delegat ist möglicherweise nicht definiert

Ein [Delegate (Komponentenerweiterungen)](../../windows/delegate-cpp-component-extensions.md) deklariert, aber nicht definiert werden können.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3755 generiert.

```
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

## <a name="example"></a>Beispiel

C3755 kann auch auftreten, wenn Sie versuchen, eine Delegatvorlage zu erstellen. Im folgende Beispiel wird die C3755 generiert.

```
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```