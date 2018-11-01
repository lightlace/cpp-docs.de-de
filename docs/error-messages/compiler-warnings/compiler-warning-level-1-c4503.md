---
title: Compilerwarnung (Stufe 1) C4503
ms.date: 05/14/2018
f1_keywords:
- C4503
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
ms.openlocfilehash: 94c88511d87c3adf3cf5687a94948c83ebc5b3d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459786"
---
# <a name="compiler-warning-level-1-c4503"></a>Compilerwarnung (Stufe 1) C4503

> "*Bezeichner*': Länge des ergänzten Namens wurde überschritten, Name wurde gekürzt.

## <a name="remarks"></a>Hinweise

Diese compilerwarnung ist veraltet und wird nicht in Visual Studio 2017 und höher Compiler generiert.

Der ergänzte Name war länger als das Compilerlimit (4096) und wurde abgeschnitten. Um diese Warnung und das Abschneiden zu vermeiden, verringern Sie die Anzahl der Argumente oder die Länge der Namen von Bezeichnern verwendet. Von ergänzten Namen, die länger als das Compilerlimit einen Hash angewendet werden, und sind nicht Gefahr, dass er ein Konflikt von geschachteltem Klassennamen.

Wenn Sie eine ältere Version von Visual Studio verwenden zu können, diese Warnung ausgegeben werden kann, wenn Ihr Code Vorlagen enthält wiederholt, der auf Vorlagen spezialisiert. Z. B. eine Zuordnung von Zuordnungen (in der C++-Standardbibliothek). In diesem Fall möglich Ihre Typdefinitionen einen Typ (ein **Struktur**, z. B.), die die Zuordnung enthält.

Möglicherweise möchten Sie jedoch nicht den Code umstrukturieren.  Es ist möglich, eine Anwendung, die von C4503 generiert, aber wenn Sie auf ein Symbol abgeschnittene Link-Time-Fehler erhalten, kann schwieriger, den Typ des Symbols in den Fehler zu ermitteln sein. Debuggen von Mai auch sein schwieriger; der Debugger möglicherweise schwierigkeiten der Symbolname zuordnen, auf den Namen fest. Die Richtigkeit des Programms, ist jedoch nicht betroffen, durch den gekürzten Namen.

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C4503 in Compilern vor Visual Studio 2017:

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

Dieses Beispiel zeigt eine Möglichkeit zum Schreiben von Code zum Beheben von C4503:

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