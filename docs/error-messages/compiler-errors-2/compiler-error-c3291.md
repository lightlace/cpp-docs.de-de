---
title: Compilerfehler C3291 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3291
dev_langs:
- C++
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f92c45a70c86da2cf2272cd6a49aaf230ed8a7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024215"
---
# <a name="compiler-error-c3291"></a>Compilerfehler C3291

"default": Kann nicht der Name einer trivial-Eigenschaft sein.

Eine trivial-Eigenschaft kann nicht als `default`benannt werden. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3291 generiert:

```
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```