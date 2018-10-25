---
title: Arrays (C++ / CLI und C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 29f84515bfa802af8d6463d34de9b6717c8df044
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061325"
---
# <a name="arrays-ccli-and-ccx"></a>Arrays (C++ / CLI und C++ / CX)

Die `Platform::Array<T>` Typ in C++ / CX oder **Array** -Schlüsselwort in C++ / CLI, deklariert ein Array aus dem angegebenen Parametertyp und der ursprüngliche Wert.

## <a name="all-platforms"></a>Alle Plattformen

Das Array muss deklariert werden, mit dem Handle-to-Object (^)-Modifizierer nach die schließende spitze Klammer (>) in der Deklaration.
Die Anzahl der Elemente des Arrays ist nicht Teil des Typs. Eine Arrayvariable kann Arrays von unterschiedlicher Größe verweisen.

Im Gegensatz zu standard C++ Indizierung kein Synonym für Zeigerarithmetik und ist nicht kommutativ.

Weitere Informationen zu Arrays finden Sie unter:

- [Vorgehensweise: Verwenden von Arrays in C++/CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)

- [Variable Argumentlisten (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)

## <a name="windows-runtime"></a>Windows-Runtime

Arrays sind Mitglieder der `Platform` Namespace. Arrays können nur eindimensional sein.

### <a name="syntax"></a>Syntax

Im ersten Beispiel der Syntax wird die **Ref neue** -aggregatschlüsselwort ein Array zuweisen. Im zweite Beispiel wird ein lokales Array deklariert.

```cpp
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier =
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]

[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier =
    {initialization-list [,...]}
```

*Qualifizierer*<br/>
(Optional) Eine oder mehrere der folgenden Speicherklassenspezifizierer: [änderbare](../cpp/mutable-data-members-cpp.md), [flüchtige](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), ["extern"](../cpp/using-extern-to-specify-linkage.md), [statische](../cpp/static-members-cpp.md).

*Array-Typ*<br/>
Der Typ der Arrayvariablen. Gültige Typen sind Windows-Runtime-Klassen und grundlegenden Typen, Verweisklassen und Strukturen, Wertklassen und Strukturen und nativen Zeigern (`type*`).

*rank*<br/>
(Optional) Die Anzahl der Dimensionen des Arrays. 1 muss sein.

*identifier*<br/>
Der Name der Arrayvariablen.

*Initialisierung-Typ*<br/>
Der Typ der Werte, die das Array initialisiert werden. In der Regel *Arraytyp* und *Initialisierung vom Typ* denselben Typ aufweisen. Die Typen kann jedoch anders, wenn es eine Konvertierung von erfolgt *Initialisierung vom Typ* zu *Arraytyp*– z. B. wenn *Initialisierung vom Typ* abgeleitetist*Arraytyp*.

*Initialisierungsliste*<br/>
(Optional) Eine durch Trennzeichen getrennte Liste von Werten in geschweiften Klammern, die die Elemente des Arrays zu initialisieren. Z. B. wenn *Rang-Größe-List* wurden `(3)`, die deklariert wird, eines eindimensionalen Arrays von 3 Elemente *Initialisierungsliste* möglicherweise `{1,2,3}`.

### <a name="remarks"></a>Hinweise

Sie können zur Kompilierzeit erkennen, ob ein Typ ein Array mit verweiszählung mit `__is_ref_array(type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

### <a name="examples"></a>Beispiele

Das folgende Beispiel erstellt ein eindimensionales Array, das 100 Elemente verfügt.

```cpp
// cwr_array.cpp
// compile with: /ZW
using namespace Platform;
ref class MyClass {};
int main() {
   // one-dimensional array
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);
   My1DArray[99] = ref new MyClass();
}
```

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="syntax"></a>Syntax

Im ersten Beispiel der Syntax wird die **Gcnew** Schlüsselwort, um ein Array zuweisen. Im zweite Beispiel wird ein lokales Array deklariert.

```cpp
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier =
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]

[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier =
    {initialization-list [,...]}
```

*Qualifizierer*<br/>
(Optional) Eine oder mehrere der folgenden Speicherklassenspezifizierer: [änderbare](../cpp/mutable-data-members-cpp.md), [flüchtige](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), ["extern"](../cpp/using-extern-to-specify-linkage.md), [statische](../cpp/static-members-cpp.md).

*Array-Typ*<br/>
Der Typ der Arrayvariablen. Gültige Typen sind Windows-Runtime-Klassen und grundlegenden Typen, Verweisklassen und Strukturen, Wertklassen und Strukturen, systemeigene Zeiger (`type*`), und Typen für native POD (plain old Data).

*rank*<br/>
(Optional) Die Anzahl der Dimensionen des Arrays. Der Standardwert ist 1. Der Höchstwert beträgt 32. Jede Dimension des Arrays ist selbst ein Array.

*identifier*<br/>
Der Name der Arrayvariablen.

*Initialisierung-Typ*<br/>
Der Typ der Werte, die das Array initialisiert werden. In der Regel *Arraytyp* und *Initialisierung vom Typ* denselben Typ aufweisen. Die Typen kann jedoch anders, wenn es eine Konvertierung von erfolgt *Initialisierung vom Typ* zu *Arraytyp*– z. B. wenn *Initialisierung vom Typ* abgeleitetist*Arraytyp*.

*Liste der Rank-Größe*<br/>
Eine durch Trennzeichen getrennte Liste der Größe der einzelnen Dimensionen im Array. Auch wenn die *Initialisierungsliste* -Parameter angegeben wird, kann der Compiler die Größe der einzelnen Dimensionen folgern und *Rang-Größe-List* kann ausgelassen werden.

*Initialisierungsliste*<br/>
(Optional) Eine durch Trennzeichen getrennte Liste von Werten in geschweiften Klammern, die die Elemente des Arrays zu initialisieren. Eine durch Trennzeichen getrennte Liste der geschachtelte oder *Initialisierungsliste* Elemente, die die Elemente in ein mehrdimensionales Array zu initialisieren.

Z. B. wenn *Rang-Größe-List* wurden `(3)`, die deklariert wird, eines eindimensionalen Arrays von 3 Elemente *Initialisierungsliste* möglicherweise `{1,2,3}`. Wenn *Rang-Größe-List* wurden `(3,2,4)`, die deklariert wird, eines dreidimensionalen Arrays von 3 Elementen in der ersten Dimension, 2 Elemente in der Sekunde und 4 Elemente in der dritten *Initialisierungsliste* möglicherweise `{{1,2,3},{0,0},{-5,10,-21,99}}`.)

### <a name="remarks"></a>Hinweise

**Array** befindet sich in der [Platform-, Default- und Cli-Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) Namespace.

Wie standard C++ die Indizes eines Arrays sind nullbasiert, und ein Array mit eckigen Klammern ([]) indiziert wird. Im Gegensatz zu standard C++ werden die Indizes der ein mehrdimensionales Array in eine Liste von Indizes für jede Dimension statt eines Satzes von eckigen Klammern ([])-Operatoren für die einzelnen Dimensionen angegeben. Z. B. *Bezeichner*[*index1*, *index2*] anstelle von *Bezeichner*[*index1*] [ *index2*].

Alle verwalteten Arrays erben `System::Array`. Eine beliebige Methode oder Eigenschaft `System::Array` kann direkt auf die Arrayvariable angewendet werden.

Wenn Sie ein Array, dessen Elementtyp zuordnen ist Zeiger-auf eine verwaltete Klasse, die Elemente sind 0 initialisiert.

Wenn Sie ein Array, dessen Elementtyp zuweisen, ist ein Werttyp `V`, der Standardkonstruktor für `V` gilt für jedes Arrayelement. Weitere Informationen finden Sie unter [.NET Framework-Entsprechungen in Native C++-Typen (C++ / CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).

Zum Zeitpunkt der Kompilierung können Sie erkennen, ob ein Typ ein common Language Runtime (CLR)-Array mit `__is_ref_array(type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Beispiel erstellt ein eindimensionales Array, das 100 Elemente verfügt, und ein dreidimensionales Array, das über 3 Elemente in der ersten Dimension, 5 Elemente in der Sekunde und 6 Elemente im dritten verfügt.

```cpp
// clr_array.cpp
// compile with: /clr
ref class MyClass {};
int main() {
   // one-dimensional array
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);
   My1DArray[99] = gcnew MyClass();

   // three-dimensional array
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);
   My3DArray[0,0,0] = gcnew MyClass();
}
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)