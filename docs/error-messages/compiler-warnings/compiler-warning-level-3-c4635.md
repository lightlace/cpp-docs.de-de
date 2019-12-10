---
title: Compilerwarnung (Stufe 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: fd3bf6c1b14c6dae8e2fa95a54e2d4fbc4f295c5
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991854"
---
# <a name="compiler-warning-level-3-c4635"></a>Compilerwarnung (Stufe 3) C4635

XML-Dokumentkommentarziel: Ungültige XML: Grund

Der Compiler hat ein Problem mit XML-Tags gefunden.  Beheben Sie das Problem, und führen Sie die Kompilierung erneut durch.

Im folgenden Beispiel wird C4635 generiert:

```cpp
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

Das Problem bei diesem Beispiel besteht darin, dass das Endtag für die \<Zusammenfassungs > unzureichend ist, und der Compiler erkennt es nicht als \<Zusammenfassungs > Endtag.  Der \<Member >-Tag wird vom Compiler in jeder/doc-Kompilierung in die XDC-Datei eingebettet.  Das Problem hier ist, dass das Endtag \</Member >, nicht mit dem vorherigen Starttag identisch ist, das der Compiler verarbeitet hat (\<Zusammenfassungs >.
