---
title: Compilerwarnung (Stufe 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: b6fd45dc6c28c0d12eb2b2991f8a087b1841d1a9
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189145"
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