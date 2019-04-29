---
title: Compilerfehler C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: ae416d68831d1964c89d938dfcddd364e521195c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328863"
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