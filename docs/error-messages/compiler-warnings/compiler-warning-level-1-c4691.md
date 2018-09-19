---
title: Compilerwarnung (Stufe 1) C4691 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4691
dev_langs:
- C++
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca063d61b799a10bd1d629fdba1293e0a66b0752
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095117"
---
# <a name="compiler-warning-level-1-c4691"></a>Compilerwarnung (Stufe 1) C4691

'Typ': Typ verwiesen wurde erwartet, in der nicht referenzierte Assembly "File", Typ, der in der aktuellen Übersetzungseinheit, die stattdessen verwendet

Die Metadatendatei, die mit der ursprünglichen Typdefinition ist nicht auf die verwiesen wird, und der Compiler verwendet eine lokale Definition.

Im Fall, in dem Sie neu erstellen *Datei*, C4691 ignoriert oder deaktiviert Sie sich mit dem Pragma [Warnung](../../preprocessor/warning.md).  D. h. wenn die Datei, die Sie erstellen, in denen der Compiler erwartet in der Definition des Typs, identisch mit der Datei ist, können Sie C4691 ignorieren.

Allerdings kann unerwartetes Verhalten auftreten, wenn der Compiler eine Definition verwendet, die nicht aus der gleichen Assembly, die in den Metadaten verwiesen wird; CLR-Typen sind nicht nur durch den Namen des Typs, sondern auch von der Assembly typisiert.  D. h. unterscheidet sich ein Typ "Z" aus Assembly z.dll ist ein Z-Typ aus der Assembly y.dll.

## <a name="example"></a>Beispiel

Dieses Beispiel enthält die ursprünglichen Typdefinition.

```
// C4691_a.cpp
// compile with: /clr /LD /W1
public ref class Original_Type {};
```

## <a name="example"></a>Beispiel

In diesem Beispiel auf C4691_a.dll verwiesen und ein Feld vom Typ Original_Type.

```
// C4691_b.cpp
// compile with: /clr /LD
#using "C4691_a.dll"
public ref class Client {
public:
   Original_Type^ ot;
};
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4691 generiert.  Beachten Sie in diesem Beispiel enthält eine Definition für Original_Type und verweist auf keine C4691a.dll verwiesen wird.

Verweisen auf die Metadaten-Datei, die die ursprünglichen Typdefinition enthält, und entfernen Sie die lokale Deklaration und Definition, um zu beheben.

```
// C4691_c.cpp
// compile with: /clr /LD /W1
// C4691 expected

// Uncomment the following line to resolve.
// #using "C4691_a.dll"
#using "C4691_b.dll"

// Delete the following line to resolve.
ref class Original_Type;

public ref class MyClass : Client {};
```