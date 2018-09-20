---
title: Klassen und Strukturen (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60e388e18e6d3607dac1946c3fd9a511e948afd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448375"
---
# <a name="classes-and-structs--c-component-extensions"></a>Klassen und Strukturen (Komponentenerweiterungen für C++)

Deklariert eine Klasse oder Struktur, deren *Objektlebensdauer* automatisch verwaltet wird. Wenn auf das Objekt nicht mehr zugegriffen werden kann oder den Gültigkeitsbereich verlässt, verwirft Visual C++ automatisch den Speicher, der dem Objekt zugeordnet ist.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="syntax"></a>Syntax

```cpp
      class_access
      ref class
      name
      modifier :  inherit_accessbase_type {};
class_accessref structnamemodifier :  inherit_accessbase_type {};
class_accessvalue classnamemodifier :  inherit_accessbase_type {};
class_accessvalue structnamemodifier :  inherit_accessbase_type {};

```

### <a name="parameters"></a>Parameter

*class_access*<br/>
(Optional) Der Zugriff auf die Klasse oder Struktur, die außerhalb der Assembly. Mögliche Werte sind **öffentliche** und **private** (**private** ist die Standardeinstellung). Geschachtelte Klassen oder Strukturen können keine *Class_access* Spezifizierer.

*name*<br/>
Der Name der Klasse oder Struktur.

*Modifizierer*<br/>
(Optional) [abstrakte](../windows/abstract-cpp-component-extensions.md) und [versiegelten](../windows/sealed-cpp-component-extensions.md) sind gültige Modifizierer.

*inherit_access*<br/>
(Optional) Der Zugriff auf *Base_type*. Der einzige zulässige Zugriff ist **öffentliche** (**öffentliche** ist die Standardeinstellung).

*base_type*<br/>
(Optional) Ein Basistyp. Jedoch kann ein Werttyp nicht als Basistyp dienen.

Weitere Informationen finden Sie unter der sprachspezifische Beschreibungen für diesen Parameter in der Windows-Runtime und die Common Language Runtimesections.

### <a name="remarks"></a>Hinweise

Die Standard-Memberzugriff eines Objekts deklariert mit **Verweisklasse** oder **Wertklasse** ist **private**. Und die Standard-Memberzugriff eines Objekts deklariert mit **Referenzstruktur** oder **wertstruktur** ist **öffentliche**.

Wenn ein Verweistyp von einem anderen Verweistyp erbt, virtuelle Funktionen in der Basisklasse explizit überschrieben werden müssen (mit [überschreiben](../windows/override-cpp-component-extensions.md)) oder ausgeblendet (mit [new (neuer Slot in Vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)). Die abgeleiteten Klassenfunktionen müssen auch explizit markiert sein **virtuellen**.

Zur Kompilierzeit erkennen, ob ein Typ eine **Verweisklasse** oder **Referenzstruktur**, oder ein **Wertklasse** oder **wertstruktur**, verwenden Sie `__is_ref_class (type)`, `__is_value_class (type)`, oder `__is_simple_value_class (type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

Weitere Informationen über Klassen und Strukturen finden Sie unter

- [Instanziieren von Klassen und Strukturen](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)

- [C++-Stack-Semantik für Referenztypen](../dotnet/cpp-stack-semantics-for-reference-types.md)

- [Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md)

- [Destruktoren und Finalizer in der Vorgehensweise: definieren und Verarbeiten von Klassen und Strukturen (C++ / CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)

- [Benutzerdefinierte Operatoren (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)

- [Benutzerdefinierte Konvertierungen (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)

- [Vorgehensweise: Kapseln einer nativen Klasse zur Verwendung in C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

- [Generische Klassen (C++/CLI)](../windows/generic-classes-cpp-cli.md)

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="remarks"></a>Hinweise

Finden Sie unter [Verweisklassen und Strukturen](../cppcx/ref-classes-and-structs-c-cx.md) und [Wertklassen und Strukturen](https://msdn.microsoft.com/library/windows/apps/hh699861.aspx).

### <a name="parameters"></a>Parameter

*base_type*<br/>
(Optional) Ein Basistyp. Ein **Verweisklasse** oder **Referenzstruktur** kann von NULL oder mehr Schnittstellen und 0 (null) oder ein erben **Ref** Typen. Ein **Wertklasse** oder **wertstruktur** kann nur von NULL oder mehr Schnittstellen erben.

Beim Deklarieren eines Objekts mithilfe der **Verweisklasse** oder **Referenzstruktur** Schlüsselwörter, erfolgt das Objekt durch ein Handle für ein Objekt, d. h. einen Verweiszähler-Zeiger auf das Objekt. Wenn die deklarierte Variable den Gültigkeitsbereich verlässt, wird der Compiler automatisch das zugrunde liegende Objekt löschen. Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird ein Handle für das Objekt tatsächlich übergeben oder gespeichert.

Beim Deklarieren eines Objekts mithilfe der **Wertklasse** oder **wertstruktur** Schlüsselwörter, die Objektlebensdauer das deklarierte Objekt wird nicht überwacht. Das Objekt ist wie jede andere Standard-C++-Klasse oder -Struktur.

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>Hinweise

Die folgende Tabelle enthält die Unterschiede zwischen der Syntax dargestellt, der **alle Laufzeiten** Abschnitt, die spezifisch für C++ / CLI.

### <a name="parameters"></a>Parameter

*base_type*<br/>
(Optional) Ein Basistyp. Ein **Verweisklasse** oder **Referenzstruktur** erben kann, von 0 (null) oder mehr verwalteten Schnittstellen und NULL oder einem Referenztypen. Ein **Wertklasse** oder **wertstruktur** kann nur von NULL oder mehr verwalteten Schnittstellen erben.

Die **Verweisklasse** und **Referenzstruktur** Schlüsselwörter teilen dem Compiler, der die Klasse oder Struktur, die auf dem Heap zugeordnet werden. Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird eine Referenz für das Objekt tatsächlich übergeben oder gespeichert.

Die **Wertklasse** und **wertstruktur** Schlüsselwörter teilen dem Compiler, dass der Wert der zugeordneten Klasse oder Struktur an Funktionen übergeben oder in Elemente gespeichert.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)