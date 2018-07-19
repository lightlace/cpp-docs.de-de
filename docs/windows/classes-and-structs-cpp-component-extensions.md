---
title: Klassen und Strukturen (Komponentenerweiterungen für C++) | Microsoft Docs
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
ms.openlocfilehash: 9863786e5e017b69217f984e3aa6d1db597e74d3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864914"
---
# <a name="classes-and-structs--c-component-extensions"></a>Klassen und Strukturen (Komponentenerweiterungen für C++)
Deklariert eine Klasse oder Struktur, deren *Objektlebensdauer* automatisch verwaltet wird. Wenn auf das Objekt nicht mehr zugegriffen werden kann oder den Gültigkeitsbereich verlässt, verwirft Visual C++ automatisch den Speicher, der dem Objekt zugeordnet ist.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 **Syntax**  
  
```  
  
      class_access  
      ref class  
      name  
      modifier :  inherit_accessbase_type {};  
class_accessref structnamemodifier :  inherit_accessbase_type {};  
class_accessvalue classnamemodifier :  inherit_accessbase_type {};  
class_accessvalue structnamemodifier :  inherit_accessbase_type {};  
  
```  
  
 **Parameter**  
  
 *Class_access* (optional)  
 Der Zugriff auf die Klasse oder Struktur, außerhalb der Assembly. Mögliche Werte sind **öffentlichen** und `private` (`private` ist die Standardeinstellung). Geschachtelte Klassen oder Strukturen können keine *Class_access* Spezifizierer.  
  
 *name*  
 Der Name der Klasse oder Struktur.  
  
 *Modifizierer* (optional)  
 [abstrakte](../windows/abstract-cpp-component-extensions.md) und [versiegelten](../windows/sealed-cpp-component-extensions.md) sind gültige Modifizierer.  
  
 *Inherit_access* (optional)  
 Die Zugriff zu `base_type`. Der einzige zulässige Zugriff ist `public` (`public` ist die Standardeinstellung).  
  
 *Base_type* (optional)  
 Ein Basistyp. Jedoch kann ein Werttyp nicht als Basistyp dienen.  
  
 Weitere Informationen finden Sie unter der sprachspezifische Beschreibungen für diesen Parameter in der Windows-Runtime und die Common Language Runtimesections.  
  
 **Hinweise**  
  
 Der Standard-Memberzugriff eines Objekts deklariert mit **Verweisklasse** oder **-Wertklasse** ist `private`. Und die Standard-Memberzugriff eines Objekts deklariert mit **Verweisstruktur** oder **wertstruktur** ist `public`.  
  
 Wenn ein Verweistyp von einem anderen Verweistyp erbt, virtuelle Funktionen in der Basisklasse explizit überschrieben werden müssen (mit [überschreiben](../windows/override-cpp-component-extensions.md)) oder ausgeblendet (mit [new (neuer Slot in Vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)). Die abgeleiteten Klassenfunktionen müssen auch explizit markiert sein `virtual`.  
  
 Zum Zeitpunkt der Kompilierung zu erkennen, ob ein Typ ist ein `ref class` oder `ref struct`, oder ein `value class` oder `value struct`, verwenden Sie `__is_ref_class (type)`, `__is_value_class (type)`, oder `__is_simple_value_class (type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Weitere Informationen über Klassen und Strukturen finden Sie unter  
  
-   [Instanziieren von Klassen und Strukturen](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
 
  
-   [C++-Stack-Semantik für Referenztypen](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md)  
  
-   [Destruktoren und Finalizer wie: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)  
  
-   [Benutzerdefinierte Operatoren (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [Benutzerdefinierte Konvertierungen (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [Vorgehensweise: Kapseln einer nativen Klasse zur Verwendung in C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [Generische Klassen (C++/CLI)](../windows/generic-classes-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 **Hinweise**  
  
 Finden Sie unter [Verweisklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) und [Wertklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx).  
  
 **Parameter**  
  
 *Base_type* (optional)  
 Ein Basistyp. `ref class` oder `ref struct` kann von NULL oder mehr Schnittstellen und NULL oder eins `ref` Typen erben. `value class` oder `value struct` kann von null oder mehreren Schnittstellen erben.  
  
 Wenn Sie ein Objekt mithilfe der `ref class` oder `ref struct` Schlüsselwörter deklarieren, erfolgt der Zugriff auf das Objekt durch einen Handle für ein Objekt, d. h. einen Verweiszähler-Zeiger auf das Objekt. Wenn die deklarierte Variable den Gültigkeitsbereich verlässt, wird der Compiler automatisch das zugrunde liegende Objekt löschen. Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird ein Handle für das Objekt tatsächlich übergeben oder gespeichert.  
  
 Wenn Sie ein Objekt mithilfe der `value class` oder `value struct` Schlüsselwörter deklarieren, wird die Objektlebensdauer das deklarierte Objekt nicht überwacht. Das Objekt ist wie jede andere Standard-C++-Klasse oder -Struktur.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Hinweise**  
  
 Die folgende Tabelle enthält die Unterschiede vom Syntax in der **alle Laufzeiten** Abschnitt, der spezifisch für C++ sind c++ / CLI.  
  
 **Parameter**  
  
 *Base_type* (optional)  
 Ein Basistyp. `ref class` oder `ref struct` kann von NULL oder mehr verwalteten Schnittstellen und NULL oder einem Referenztypen erben. `value class` oder `value struct` kann von null oder mehr verwalteten Schnittstellen erben.  
  
 Die `ref class` und `ref struct` Schlüsselwörter teilen dem Compiler mit, dass die Klasse oder Struktur dem Heap zugeteilt wird. Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird eine Referenz für das Objekt tatsächlich übergeben oder gespeichert.  
  
 Die `value class` und `value struct` Schlüsselwörter teilen dem Compiler, dass der Wert der zugeordneten Klasse oder Struktur an Funktionen übergeben oder in Elemente gespeichert ist.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)