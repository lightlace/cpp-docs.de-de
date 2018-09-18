---
title: Überladungsauflösung von Funktionsvorlagenaufrufen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates overload resolution
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0eae1d77b3d0c9fa34cb2bbd5f39548aea83f6a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067154"
---
# <a name="overload-resolution-of-function-template-calls"></a>Überladungsauflösung von Funktionsvorlagenaufrufen

Eine Funktionsvorlage kann nicht auf Vorlagen basierende Funktionen des gleichen Namens überladen. In diesem Szenario werden Funktionsaufrufe zuerst mithilfe der Vorlagenargumentableitung aufgelöst, um die Funktionsvorlage mit einer eindeutigen Spezialisierung zu instanziieren. Wenn die Vorlagenargumentableitung fehlschlägt, werden die anderen Funktionsüberladungen zur Auflösung des Aufrufs in Erwägung gezogen. Zu diesen anderen Überladungen, auch Kandidatensatz genannt, gehören nicht auf Vorlagen basierende Funktionen sowie andere instanziierte Funktionsvorlagen. Wenn die Vorlagenargumentableitung erfolgreich ist, wird die generierte Funktion mit anderen Funktionen verglichen, um die beste Übereinstimmung nach den Regeln für die Überladungsauflösung zu bestimmen. Weitere Informationen finden Sie unter [Funktionsüberladung](function-overloading.md).

## <a name="example"></a>Beispiel

Wenn eine nicht auf Vorlagen basierende Funktion ein gleich gute Übereinstimmung wie eine Vorlagenfunktion darstellt, wird die nicht auf Vorlagen basierende Funktion ausgewählt (es sei denn, die Vorlagenargumente wurden explizit angegeben), wie im Aufruf `f(1, 1)` im folgenden Beispiel gezeigt.

```cpp
// template_name_resolution9.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void f(int, int) { cout << "f(int, int)" << endl; }
void f(char, char) { cout << "f(char, char)" << endl; }

template <class T1, class T2>
void f(T1, T2)
{
   cout << "void f(T1, T2)" << endl;
};

int main()
{
   f(1, 1);   // Equally good match; choose the nontemplate function.
   f('a', 1); // Chooses the template function.
   f<int, int>(2, 2);  // Template arguments explicitly specified.
}
```

```Output
f(int, int)
void f(T1, T2)
void f(T1, T2)
```

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht, dass die genau übereinstimmende Vorlagenfunktion bevorzugt wird, wenn die nicht auf Vorlagen basierende Funktionen eine Konvertierung erfordert.

```cpp
// template_name_resolution10.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void f(int, int) { cout << "f(int, int)" << endl; }

template <class T1, class T2>
void f(T1, T2)
{
   cout << "void f(T1, T2)" << endl;
};

int main()
{
   long l = 0;
   int i = 0;
   // Call the template function f(long, int) because f(int, int)
   // would require a conversion from long to int.
   f(l, i);
}
```

```Output
void f(T1, T2)
```

## <a name="see-also"></a>Siehe auch

[Namensauflösung](../cpp/templates-and-name-resolution.md)<br/>
[typename](../cpp/typename.md)