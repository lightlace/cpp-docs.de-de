---
title: Compilerfehler C3381 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3381
dev_langs:
- C++
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd6c1d641f7476d3c372939b948931a306e0f80
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080713"
---
# <a name="compiler-error-c3381"></a>Compilerfehler C3381

'Assembly': Assemblyzugriffsspezifizierer sind nur in Code verfügbar, der mit einer /clr-Option kompiliert wurde

Systemeigene Typen können außerhalb der Assembly sichtbar sein, aber Sie können nur Assemblyzugriff für systemeigene Typen in einem **"/ CLR"** Kompilierung.

Weitere Informationen finden Sie unter [geben Sichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3381 generiert.

```
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```