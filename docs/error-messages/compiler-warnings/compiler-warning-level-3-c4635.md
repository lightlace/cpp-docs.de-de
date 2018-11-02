---
title: Compilerwarnung (Stufe 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: 21873a883b19924ce3ef41511d65f8ae640875f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479234"
---
# <a name="compiler-warning-level-3-c4635"></a>Compilerwarnung (Stufe 3) C4635

XML-Dokumentkommentarziel: Ungültige XML: Grund

Der Compiler hat ein Problem mit XML-Tags gefunden.  Beheben Sie das Problem, und führen Sie die Kompilierung erneut durch.

Im folgenden Beispiel wird C4635 generiert:

```
// C4635.cpp
// compile with: /doc /clr /W3 /c
/// <summary>
/// The contents of the folder have changed.
/// <summary/>   // C4635

// try the following line instead
// /// </summary>
public ref class Test {};
```

Beachten Sie, dass die Ausgabe für dieses Beispiel wie folgt lautet: **Das Endtag 'member' stimmt nicht mit dem Starttag 'summary' überein.**

Das Problem mit diesem Beispiel ist, dass das Endtag für \<summary > nicht ordnungsgemäß formuliert ist, und der Compiler ihn als nicht erkennt die \<summary >-Endtag.  Die \<Member >-Tag wird vom Compiler in jeder Kompilierung/doc in der XDC-Datei eingebettet.  Das Problem ist hier ist also das Endtag \</member >, entspricht nicht das vorherigen Starttag, die der Compiler verarbeitet (\<summary >.