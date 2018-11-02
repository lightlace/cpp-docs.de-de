---
title: Funktionsvorlagen
ms.date: 11/04/2016
helpviewer_keywords:
- function templates
- templates, function
- function templates, about function templates
ms.assetid: 59b56a4b-0689-4161-9c07-25021562e2a7
ms.openlocfilehash: 77f3d1ee704c8094fd3bd94597311976e54ba6a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493521"
---
# <a name="function-templates"></a>Funktionsvorlagen

Klassenvorlagen definieren eine Gruppe von verwandten Klassen, die auf den Typargumenten basieren, die der Klasse nach der Instanziierung übergeben werden. Funktionsvorlagen sind den Klassenvorlagen ähnlich, definieren jedoch eine Funktionsreihe. Mit Funktionsvorlagen können Sie eine Gruppe von Funktionen angeben, die auf demselben Code basieren, jedoch auf unterschiedliche Typen oder Klassen reagieren. Die folgende Funktionsvorlage tauscht zwei Elemente aus:

```cpp
// function_templates1.cpp
template< class T > void MySwap( T& a, T& b ) {
   T c(a);
   a = b;
   b = c;
}
int main() {
}
```

Dieser Code definiert eine Gruppe von Funktionen, die die Werte der Argumente auslagern. Aus dieser Vorlage können Sie Funktionen, die Auslagern generieren **Int** und **lange** -Typen sowie benutzerdefinierte Typen. `MySwap` tauscht sogar Klassen aus, wenn der Kopierkonstruktor und der Zuweisungsoperator der Klasse ordnungsgemäß definiert sind.

Darüber hinaus die Funktionsvorlage verhindert, dass Objekte unterschiedlicher Typen austauschen, da der Compiler, welche weiß die *eine* und *b* Parameter zum Zeitpunkt der Kompilierung.

Obwohl diese Aufgabe durch eine nicht auf Vorlagen basierende Funktion mithilfe von void-Zeigern ausgeführt werden kann, ist die Vorlagenversion typsicher. Betrachten Sie folgenden Aufruf:

```cpp
int j = 10;
int k = 18;
CString Hello = "Hello, Windows!";
MySwap( j, k );          //OK
MySwap( j, Hello );      //error
```

Der zweite Aufruf `MySwap` löst einen Kompilierzeitfehler aus, da der Compiler keine `MySwap`-Funktion mit Parametern verschiedener Typen generieren kann. Wenn void-Zeiger verwendet würden, würden beide Funktionsaufrufe ordnungsgemäß kompiliert, die Funktion würde zur Laufzeit jedoch nicht ordnungsgemäß funktionieren.

Die explizite Angabe der Vorlagenargumente für eine Funktionsvorlage ist zulässig. Zum Beispiel:

```cpp
// function_templates2.cpp
template<class T> void f(T) {}
int main(int j) {
   f<char>(j);   // Generate the specialization f(char).
   // If not explicitly specified, f(int) would be deduced.
}
```

Wenn das Vorlagenargument explizit angegeben wird, werden normale implizite Konvertierungen durchgeführt, um das Funktionsargument in den Typ der entsprechenden Funktionsvorlagenparametern zu konvertieren. Im obigen Beispiel konvertiert der Compiler `char j` eingeben **Int**.

## <a name="see-also"></a>Siehe auch

[Vorlagen](../cpp/templates-cpp.md)<br/>
[Funktionsvorlageninstanziierung](../cpp/function-template-instantiation.md)<br/>
[Explizite Instantiierung](../cpp/explicit-instantiation.md)<br/>
[Explizite Spezialisierung von Funktionsvorlagen](../cpp/explicit-specialization-of-function-templates.md)