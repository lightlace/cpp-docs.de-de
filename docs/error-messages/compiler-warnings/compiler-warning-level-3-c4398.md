---
title: Compilerwarnung (Stufe 3) C4398 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c38ade6b75242fdd5144481e3415e914cb6773c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704613"
---
# <a name="compiler-warning-level-3-c4398"></a>Compilerwarnung (Stufe 3) C4398

> "*Variable*": prozessspezifisch globales Objekt möglicherweise nicht ordnungsgemäß mit mehreren Anwendungsdomänen; erwägen __declspec(appdomain)

## <a name="remarks"></a>Hinweise

Eine virtuelle Funktion mit [__clrcall](../../cpp/clrcall.md) -Aufrufkonvention in einem systemeigenen Typ bewirkt die Erstellung einer pro Anwendung Domäne Vtable. Eine solche Variable möglicherweise nicht ordnungsgemäß korrigiert werden, wenn in mehreren Anwendungsdomänen verwendet.

Sie können diese Warnung beheben, indem Sie explizite Markierung der Variablen `__declspec(appdomain)`. In Versionen von Visual Studio vor Visual Studio 2017, können Sie diese Warnung beheben, durch die Kompilierung mit **/CLR: pure**, wodurch globale Variablen pro-Appdomain standardmäßig. Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md) und [Anwendungsdomänen und Visual C++](../../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4398 generiert.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```