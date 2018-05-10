---
title: Arrays (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a17649402fa6ebe9c98d768badcf36e5700f5b75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="arrays-c-component-extensions"></a>Arrays (Komponentenerweiterungen für C++)
Die `Platform::Array<T>` Typ in C + c++ / CX, oder die `array` Schlüsselwort in C + c++ / CLI, deklariert ein Array eines angegebenen Typs und der Anfangswert.  
  
## <a name="all-platforms"></a>Alle Plattformen  
 Das Array muss deklariert werden, mit dem Handle-to-Object (^)-Modifizierer hinter die schließende spitze Klammer (>) in der Deklaration.  
 Die Anzahl der Elemente des Arrays ist nicht Teil des Typs. Eine Arrayvariable kann auf unterschiedliche Größen haben Arrays verweisen.  
  
 Im Gegensatz zu Standard-c++ Indizierung kein Synonym für Zeigerarithmetik und ist nicht kommutativ.  
  
 Weitere Informationen zu Arrays finden Sie unter:  
  
-   [Vorgehensweise: Verwenden von Arrays in C++/CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [Variable Argumentlisten (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Arrays sind Mitglied der `Platform` Namespace. Arrays können nur eindimensional sein.  
  
### <a name="syntax"></a>Syntax  
  
 Im ersten Beispiel der Syntax wird der `ref new` -aggregatschlüsselwort ein Array zu reservieren. Im zweite Beispiel wird ein lokales Array deklariert.  
  
```  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *Qualifizierer* [optional]  
 Mindestens eines dieser Speicherklassenspezifizierer: [änderbare](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), ["extern"](../cpp/using-extern-to-specify-linkage.md), [statische](../cpp/static-members-cpp.md).  
  
 `array-type`  
 Der Typ der Arrayvariablen. Gültige Typen sind Windows-Runtime-Klassen und grundlegenden Typen, Verweisklassen und Strukturen, Wertklassen und Strukturen und systemeigenen Zeigern (`type*`).  
  
 `rank` [optional]  
 Die Anzahl der Dimensionen des Arrays. 1 muss sein.  
  
 `identifier`  
 Der Name der Arrayvariablen.  
  
 `initialization-type`  
 Der Typ der Werte, die das Array initialisiert werden. In der Regel `array-type` und `initialization-type` denselben Typ aufweisen. Die Typen kann jedoch anders, wenn es eine Konvertierung von erfolgt `initialization-type` auf `array-type`– z. B. wenn `initialization-type` stammt aus `array-type`.  
  
 `initialization-list` [optional]  
 Eine durch Trennzeichen getrennte Liste von Werten in der geschweiften Klammern, die die Elemente des Arrays zu initialisieren. Z. B. wenn `rank-size-list` wurden `(3)`, dem deklariert eines eindimensionalen Arrays von 3 Elemente `initialization list` möglicherweise `{1,2,3}`.  
  
### <a name="remarks"></a>Hinweise  
  
 Sie können zur Kompilierzeit erkennen, ob ein Typ ein Array mit verweiszählung mit ist `__is_ref_array(type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
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
  
 Im ersten Beispiel der Syntax wird der `gcnew` Schlüsselwort, um ein Array zu reservieren. Im zweite Beispiel wird ein lokales Array deklariert.  
  
```  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *Qualifizierer* [optional]  
 Mindestens eines dieser Speicherklassenspezifizierer: [änderbare](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), ["extern"](../cpp/using-extern-to-specify-linkage.md), [statische](../cpp/static-members-cpp.md).  
  
 `array-type`  
 Der Typ der Arrayvariablen. Gültige Typen sind Windows-Runtime-Klassen und grundlegenden Typen, Verweisklassen und Strukturen, Klassen und Strukturen, systemeigene Zeiger (`type*`), und systemeigene POD (plain alte Daten)-Typen.  
  
 `rank` [optional]  
 Die Anzahl der Dimensionen des Arrays. Der Standardwert ist 1. Der Höchstwert beträgt 32. Jede Dimension des Arrays ist selbst ein Array.  
  
 `identifier`  
 Der Name der Arrayvariablen.  
  
 `initialization-type`  
 Der Typ der Werte, die das Array initialisiert werden. In der Regel `array-type` und `initialization-type` denselben Typ aufweisen. Die Typen kann jedoch anders, wenn es eine Konvertierung von erfolgt `initialization-type` auf `array-type`– z. B. wenn `initialization-type` stammt aus `array-type`.  
  
 `rank-size-list`  
 Eine durch Trennzeichen getrennte Liste der Größe der einzelnen Dimensionen im Array. Auch wenn die `initialization-list` Parameter angegeben wird, kann der Compiler die Größe der einzelnen Dimensionen folgern und `rank-size-list` kann ausgelassen werden. 
  
 `initialization-list` [optional]  
 Eine durch Trennzeichen getrennte Liste von Werten in der geschweiften Klammern, die die Elemente des Arrays zu initialisieren. Eine durch Trennzeichen getrennte Liste der geschachtelte oder *Initialisierungsliste* Elemente, die die Elemente in ein mehrdimensionales Array zu initialisieren.  
  
 Z. B. wenn `rank-size-list` wurden `(3)`, dem deklariert eines eindimensionalen Arrays von 3 Elemente `initialization list` möglicherweise `{1,2,3}`. IF `rank-size-list` wurden `(3,2,4)`, die deklariert wird, eines dreidimensionalen Arrays vom 3 Elemente in der ersten Dimension, 2 in der zweiten und 4 Elemente in der dritten `initialization-list` möglicherweise `{{1,2,3},{0,0},{-5,10,-21,99}}`.)  
  
### <a name="remarks"></a>Hinweise  
  
 `array` befindet sich in der [Plattform, Default- und Cli-Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) Namespace.  
  
 Wie Standard-c++ die Indizes eines Arrays sind nullbasiert, und ein Array mit eckigen Klammern ([]) indiziert wird. Im Gegensatz zum standardmäßigen C++ werden die Indizes der ein mehrdimensionales Array in einer Liste von Indizes für jede Dimension statt mit einem Satz von eckigen Klammern ([])-Operatoren für jede Dimension angegeben. Beispielsweise *Bezeichner*[*index1*, *index2*] anstelle von *Bezeichner*[*index1*] [ *index2*].  
  
 Alle verwalteten Arrays Vererben `System::Array`. Eine beliebige Methode oder Eigenschaft `System::Array` können direkt auf die Arrayvariable angewendet werden.  
  
 Wenn Sie ein Array, dessen Elementtyp zuweisen ist Zeiger-auf eine verwaltete Klasse, die Elemente sind 0 initialisiert.  
  
 Wenn Sie ein Array, dessen Elementtyp zuweisen ist ein Werttyp `V`, der Standardkonstruktor für `V` auf jedes Element angewendet wird. Weitere Informationen finden Sie unter [.NET Framework-Entsprechungen in systemeigenen C++-Typen (C + c++ / CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Zum Zeitpunkt der Kompilierung können Sie erkennen, ob ein Typ ein common Language Runtime (CLR)-Array mit ist `__is_ref_array(type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 Das folgende Beispiel erstellt ein eindimensionales Array, das 100 Elemente verfügt, und ein dreidimensionales Array, das 3 Elemente in der ersten Dimension, 5 Elementen in der zweiten und 6 Elemente im dritten verfügt.  
  
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
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)