---
title: Compilerwarnung (Stufe 1) C4503 | Microsoft Docs
ms.custom: ''
ms.date: 05/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f60fdb44c5368ccc5c5f089002614332d95a63fe
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-warning-level-1-c4503"></a>Compilerwarnung (Stufe 1) C4503

> "*Bezeichner*": ergänzter Name zu lang, Name wurde abgeschnitten.

## <a name="remarks"></a>Hinweise

Dieser compilerwarnung ist veraltet und wird nicht in Visual Studio 2017 und höher Compiler generiert.

Der ergänzte Name wurde länger als das Compilerlimit überschritten (4096) und wurde abgeschnitten. Um diese Warnung und das Abschneiden zu vermeiden, reduzieren Sie die Anzahl der Argumente oder die Länge der Namen von Bezeichnern verwendet. Ergänzte Namen, die länger als das Compilerlimit einen Hashwert angewendet werden, und sind nicht Gefahr, dass er ein Konflikt von geschachteltem Klassennamen.

Wenn Sie eine ältere Version von Visual Studio verwenden, diese Warnung ausgegeben werden kann, wenn Ihr Code Vorlagen enthält spezialisiert auf Vorlagen wiederholt. Z. B. eine Zuordnung von Karten (aus der C++-Standardbibliothek). In diesem Fall möglich den Typdefinitionen einen Typ (ein **Struktur**, z. B.), die die Zuordnung enthält.

Sie könnten jedoch nicht den Code umstrukturieren.  Ist es möglich, eine Anwendung ausgeliefert, die C4503 generiert kann, aber wenn Link Zeit Fehlermeldungen auf ein Symbol, das abgeschnitten angezeigt werden, es schwieriger, den Typ des Symbols in den Fehler zu ermitteln. Debuggen auch möglicherweise sein schwieriger; der Debugger möglicherweise difficultly Zuordnen der Symbolname dem Typnamen. Die Richtigkeit des Programms, ist jedoch nicht betroffen, durch den gekürzten Namen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird im Compiler vor Visual Studio 2017 C4503 generiert:

```cpp
// C4503.cpp
// compile with: /W1 /EHsc /c
// C4503 expected
#include <string>
#include <map>

class Field{};

typedef std::map<std::string, Field> Screen;
typedef std::map<std::string, Screen> WebApp;
typedef std::map<std::string, WebApp> WebAppTest;
typedef std::map<std::string, WebAppTest> Hello;
Hello MyWAT;
```

Dieses Beispiel zeigt eine Möglichkeit, Schreiben Sie Code um C4503 zu beheben:

```cpp
// C4503b.cpp
// compile with: /W1 /EHsc /c
#include <string>
#include <map>

class Field{};

struct Screen2 {
   std::map<std::string, Field> Element;
};

struct WebApp2 {
   std::map<std::string, Screen2> Element;
};

struct WebAppTest2 {
   std::map<std::string, WebApp2> Element;
};

struct Hello2 {
   std::map<std::string, WebAppTest2> Element;
};

Hello2 MyWAT2;
```