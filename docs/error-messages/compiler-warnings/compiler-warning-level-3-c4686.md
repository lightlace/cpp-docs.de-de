---
title: Compilerwarnung (Stufe 3) C4686 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4686
dev_langs:
- C++
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32a44cd929eb7629ef317ce9847950b613bde52c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202079"
---
# <a name="compiler-warning-level-3-c4686"></a>Compilerwarnung (Stufe 3) C4686

> "*einen benutzerdefinierten Typ*": mögliche verhaltensänderung, Änderung in der UDT gibt zurück Aufrufkonvention

## <a name="remarks"></a>Hinweise

Eine Spezialisierung einer Klassenvorlage wurde nicht definiert ist, bevor er in einem Rückgabetyp verwendet wurde. Alle Elemente, die die Klasse instanziiert wird C4686; aufgelöst werden deklarieren eine Instanz oder das Zugreifen auf einen Member (C\<Int >:: nichts) sind auch Optionen.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Verwenden Sie stattdessen Folgendes:

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```