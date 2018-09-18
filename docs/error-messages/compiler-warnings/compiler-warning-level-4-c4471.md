---
title: Compilerwarnung (Stufe 4) C4471 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4471
dev_langs:
- C++
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bcbeafb6952bc40f7fb67c6a0baa2e90051d3ca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023357"
---
# <a name="compiler-warning-level-4-c4471"></a>Compilerwarnung (Stufe 4) C4471

"*Enumeration*': eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung müssen einen zugrunde liegenden Typ (Int wird angenommen)

Eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung wurde ohne einen Bezeichner für den zugrunde liegenden Typ gefunden. Standardmäßig geht davon aus Visual C++ `int` der zugrunde liegenden Typ einer Enumeration ist. Dies kann Probleme verursachen, wenn Sie ein anderen Typ in der Enumerationsdefinition z. B. verwendet wird, wenn ein anderer expliziter Typ angegeben ist, oder ein anderen Typ implizit durch einen Initialisierer festgelegt ist. Möglicherweise müssen Sie auch die Portabilitätsprobleme; Nehmen Sie nicht anderen Compilern an `int` ist der zugrunde liegenden Typ einer Enumeration.

Diese Warnung ist standardmäßig deaktiviert; Verwenden Sie "/ Wall" oder/w*N*4471 zum in der Befehlszeile aktivieren, oder verwenden Sie #pragma [Warnung](../../preprocessor/warning.md) in der Quelldatei.

Diese Warnung ist in einigen Fällen sichergestellt. Wenn Sie eine Vorwärtsdeklaration für eine Enumeration nach der Definition angezeigt wird, kann diese Warnung ausgelöst werden. Beispielsweise ist dieser Code gültig ist, obwohl sie C4471 führen kann:

```cpp
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```

## <a name="example"></a>Beispiel

Im Allgemeinen ist es sicher ist, verwenden die vollständige Definition für eine Enumeration ohne bereichseinschränkung anstelle einer Vorwärtsdeklaration. Sie können die Definition in einer Headerdatei einfügen und fügen Sie es in den Quelldateien, die darauf verweisen. Dies funktioniert in Code geschrieben wurde, für die C ++ 98 und höher. Es wird empfohlen, diese Lösung für Portabilität und einfache Wartung.

```cpp
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```

## <a name="example"></a>Beispiel

In C ++ 11 können Sie einen expliziten Typ und die Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung hinzufügen. Diese Lösung wird empfohlen, nur dann, wenn complex-Header-Aufnahme-Logik verhindert, dass die Verwendung der Definition anstelle einer Vorwärtsdeklaration. Diese Lösung kann zu einem Wartungsproblem führen: Wenn Sie den zugrunde liegenden Typ, der für die Enumerationsdefinition verwendet, müssen Sie auch alle forward Deklarationen entsprechend ändern oder automatische Fehler in Ihrem Code enthalten. Sie können die Vorwärtsdeklaration einfügen, in eine Headerdatei, um dieses Problem zu minimieren.

```cpp
// C4471c.cpp
// Client code for enumeration defined in C4471d.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example;    // C4471, int assumed
// To fix, replace the lines above with the forward declarations:
// enum Example : unsigned;
// ...
```

```cpp
// C4471d.cpp
// Definition for enumeration used in C4471c.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example : unsigned { item = 0x80000000 }; // explicit type
// ...
```

Wenn Sie einen expliziten Typ für eine Enumeration angeben, sollten Sie die Warnung auch aktivieren [C4369](compiler-warning-level-1-C4369.md), das ist standardmäßig aktiviert. Situationen, in denen ein Enumerationselement erforderlich, einen anderen Typ als dem explizit angegebenen Typ sind, identifiziert.

## <a name="example"></a>Beispiel

Sie können Ihren Code, um einer bereichsbezogenen Enumeration ist ein Feature zu verwenden, die neu in C ++ 11 ist ändern. Sowohl die Definition als auch alle Clientcode, der den Enumerationstyp verwendet müssen geändert werden, um eine Bereichsbezogene Enumeration verwenden. Es wird empfohlen, dass Sie eine Bereichsbezogene Enumeration verwenden, wenn Sie Probleme mit Namespacekonflikte, haben wie die Namen der definierten Enumerationselemente auf den Bereich der Enumeration beschränkt sind. Ein weiteres Feature von einer bereichsbezogenen Enumeration ist, dass der Member in einen anderen Typ für einen Ganzzahl- oder -Enumeration, die möglicherweise eine Quelle für schwer erkennbare Fehler entstehen, implizit konvertiert werden können.

```cpp
// C4471e.cpp
// Client code for scoped enumeration defined in C4471f.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum Example;    // C4471
// To fix, replace the line above with the forward declaration:
// enum class Example;
// ...
```

```cpp
// C4471f.cpp
// Definition for scoped enumeration used in C4471e.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum class Example { item = 0 };
// ...
```

