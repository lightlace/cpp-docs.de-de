---
title: Vererbung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e49e115f6ef4269ddfc7169add6a88e3bb0c54f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064554"
---
# <a name="inheritance--c"></a>Vererbung  (C++)

In diesem Abschnitt wird beschrieben, wie abgeleitete Klassen verwendet werden, um erweiterbare Programme zu erzeugen.

## <a name="overview"></a>Übersicht

Neue Klassen aus vorhandenen Klassen, die mit einem Mechanismus namens "Vererbung" abgeleitet werden (Sie finden die Informationen ab, in [einfache Vererbung](../cpp/single-inheritance.md)). Klassen, die zur Ableitung verwendet werden, werden als "Basisklassen" einer bestimmten abgeleiteten Klasse bezeichnet. Eine abgeleitete Klasse wird mit der folgenden Syntax deklariert:

```cpp
class Derived : [virtual] [access-specifier] Base
{
   // member list
};
class Derived : [virtual] [access-specifier] Base1,
   [virtual] [access-specifier] Base2, . . .
{
   // member list
};
```

Nach dem Tag für die Klasse wird ein Doppelpunkt gefolgt von einer Liste mit grundlegenden Spezifikationen angezeigt.  Die sogenannten Basisklassen müssen zuvor deklariert werden.  Die grundlegenden Spezifikationen können einen Zugriffsspezifizierer enthalten, der eines der Schlüsselwörter **öffentliche**, **geschützt** oder **private**.  Diese Zugriffsspezifizierer werden vor dem Basisklassennamen angezeigt und gelten nur für diese Basisklasse.  Diese Spezifizierer steuern die Berechtigung der abgeleiteten Klasse, die für Member der Basisklasse zu verwenden sind.  Finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md) Informationen für den Zugriff auf Basisklassenmember.  Wenn die Zugriffsspezifizierer weggelassen wird, wird der Zugriff dieser Basis betrachtet **private**.  Die grundlegenden Spezifikationen können das Schlüsselwort enthalten **virtuellen** um virtuelle Vererbung anzugeben.  Dieses Schlüsselwort kann vor oder nach dem Zugriffsspezifizierer angezeigt werden, falls vorhanden.  Wenn virtuelle Vererbung verwendet wird, wird die Basisklasse als virtuelle Basisklasse bezeichnet.

Es können mehrere durch Kommas getrennte Basisklasse angegeben werden.  Wenn eine einzelne Basisklasse angegeben ist, wird das Vererbungsmodell [einzelne Vererbung](../cpp/single-inheritance.md). Wenn mehr als einer Basisklasse angegeben wird, heißt das Vererbungsmodell [mehrfachvererbung](../cpp/multiple-base-classes.md).

Es sind folgende Themen enthalten:

- [Einfache Vererbung](../cpp/single-inheritance.md)

- [Mehrere Basisklassen](../cpp/multiple-base-classes.md)

- [Virtuelle Funktionen](../cpp/virtual-functions.md)

- [Explizite überschreibungen](../cpp/explicit-overrides-cpp.md)

- [Abstrakte Klassen](../cpp/abstract-classes-cpp.md)

- [Zusammenfassung der Bereichsregeln](../cpp/summary-of-scope-rules.md)

Die [__super](../cpp/super.md) und [__interface](../cpp/interface.md) Schlüsselwörter werden in diesem Abschnitt dokumentiert.

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)