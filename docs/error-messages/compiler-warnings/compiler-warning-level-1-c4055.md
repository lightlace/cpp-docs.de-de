---
title: Compilerwarnung (Stufe 1) C4052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- C4055
dev_langs:
- C++
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29b1c8bcc836e35f7b8b81954ef247527d8ec35e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="compiler-warning-level-1-c4055"></a>Compilerwarnung (Stufe 1) C4055

> "*Konvertierung*": von Datenzeiger '*Typ1*'zu Funktionszeiger'*Typ2*"

## <a name="remarks"></a>Hinweise

**Veraltet:** diese Warnung wird von Visual Studio 2017 und neueren Versionen nicht generiert.

Ein Datenzeiger wird (möglicherweise falsch) in einen Funktionszeiger umgewandelt. Dies ist unter „/Za“ eine Warnung der Stufe 1 und unter „/Ze“ eine Warnung der Stufe 4.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4055 generiert:

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

Unter „/Ze“ ist dies eine Warnung der Stufe 4.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
