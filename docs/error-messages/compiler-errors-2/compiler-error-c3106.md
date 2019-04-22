---
title: Compilerfehler C3106
ms.date: 11/04/2016
f1_keywords:
- C3106
helpviewer_keywords:
- C3106
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
ms.openlocfilehash: c5ed544549aecd9811279e065d7c252fe085e545
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775988"
---
# <a name="compiler-error-c3106"></a>Compilerfehler C3106

'Attribut': unbenannte Argumente müssen vor benannte Argumenten stehen.

Unbenannte Argumente müssen zu einem Attribut vor benannten Argumenten übergeben werden.

Weitere Informationen finden Sie unter [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3106 generiert.

```
// C3106.cpp
// compile with: /c
[module(name="MyLib", dll)];   // C3106
[module(dll, name="MyLib")];   // OK
```