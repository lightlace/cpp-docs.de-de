---
title: "Arrays (C++ Component Extensions)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "cli::array"
  - "details::array"
  - "lang::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array keyword [C++]"
  - "declaring arrays, about declaring arrays"
  - "arrays [C++], multidimensional"
  - "multidimensional arrays"
  - "arrays [C++]"
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
caps.latest.revision: 34
caps.handback.revision: "34"
ms.author: "mblome"
manager: "ghogen"
---
# Arrays (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Platform::Array<T>` geben [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], oder das `array`\-Schlüsselwort in [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)], deklariert ein Array eines angegebenen Typs und des Anfangswerts.  
  
## Alle Plattformen  
 Das Array muss deklariert werden, indem den Modifizierer des Handle\-zuObjekts \(^\) nach der spitze Klammer \(\>\) in der Deklaration verwendet.  
  
 Die Anzahl der Elemente des Arrays ist nicht Teil des Typs.  Eine Arrayvariable kann unterschiedliche Größen Arrays verweisen.  
  
 Im Gegensatz Standard\-C\+\+ ist Tiefstellung kein Synonym für Zeigerarithmetik und nicht auswechselbar.  
  
 Weitere Informationen zu Arrays, finden Sie unter:  
  
-   [Array\-Kovarianz](../misc/array-covariance.md)  
  
-   [Gewusst wie: Verwenden von Arrays in C\+\+\/CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
  
-   [Gewusst wie: Erstellen von mehrdimensionalen Arrays](../misc/how-to-create-multidimension-arrays.md)  
  
-   [Gewusst wie: Erstellen von Arrays aus verwalteten Arrays \(verzweigte Arrays\)](../misc/how-to-create-arrays-of-managed-arrays-jagged-arrays.md)  
  
-   [Gewusst wie: Erstellen von Typedefs in verwalteten Arrays](../misc/how-to-make-typedefs-for-managed-arrays.md)  
  
-   [Gewusst wie: Verwenden von verwalteten Arrays als Vorlagentypparameter](../misc/how-to-use-managed-arrays-as-template-type-parameters.md)  
  
-   [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
-   [Gewusst wie: Sortieren von Arrays](../misc/how-to-sort-arrays.md)  
  
-   [Gewusst wie: Sortieren von Arrays anhand benutzerdefinierter Kriterien](../misc/how-to-sort-arrays-using-custom-criteria.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Arrays sind Member des `Platform`\-Namespace.  Arrays können nur eindimensional sein.  
  
 **Syntax**  
  
 Das erste Beispiel der Syntax wird das `ref new` Aggregatsschlüsselwort, um ein Array zu verknüpfen.  Das zweite Beispiel deklariert ein lokales Array.  
  
```  
  
        [qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = ref new [Platform::]Array< initialization-type > [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = {initialization-list [,...]}  
  
```  
  
 \[*qualifiers* optional\]  
 Eine oder mehrere dieser Speicherklassenspezifizierer: [änderbar](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statisch](../misc/static-cpp.md).  
  
 `array-type`  
 Der Typ der Arrayvariablen.  Gültige Typen [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] sind Klassen und grundlegende Typen, Verweisklassen und Strukturen, Wertklassen und Strukturen und systemeigene Zeiger \(`type``*`\).  
  
 `rank` \[optional\]  
 Die Anzahl der Dimensionen des Arrays.  Muss 1 \(null\) sein.  
  
 `identifier`  
 Der Name der Arrayvariablen.  
  
 `initialization-type`  
 Der Typ der Werte, die das Array initialisieren.  Normalerweise sind `array-type` und `initialization-type` der gleiche Typ.  Allerdings können die Typen unterscheiden, wenn eine Konvertierung von `initialization-type` in `array-type`\- für Beispiel gibt, wenn `initialization-type` von `array-type` abgeleitet ist.  
  
 `initialization-list` \[optional\]  
 Eine durch Trennzeichen getrennte Liste von Werten in geschweiften Klammern, die die Elemente des Arrays initialisieren.  Wenn `rank-size-list``(3)` festgelegt wäre, die ein eindimensionales Array mit 3 Elementen deklarieren, kann `initialization list``{1,2,3}` sein.  
  
 **Hinweise**  
  
 Sie können zur Kompilierzeit erkennen, ob ein Typ mit Verweiszählung verwendet ein Array mit `__is_ref_array(``type``)` ist.  Weitere Informationen finden Sie unter [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
### Beispiele  
 Im folgenden Beispiel wird ein eindimensionales Array, das 100 Elemente verfügt.  
  
```  
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
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntax**  
  
 Das erste Beispiel der Syntax wird das `gcnew`\-Schlüsselwort, um ein Array zu verknüpfen.  Das zweite Beispiel deklariert ein lokales Array.  
  
```  
  
        [qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = gcnew [cli::]array< initialization-type [,rank] >(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = {initialization-list [,...]}  
  
```  
  
 \[*qualifiers* optional\]  
 Eine oder mehrere dieser Speicherklassenspezifizierer: [änderbar](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statisch](../misc/static-cpp.md).  
  
 `array-type`  
 Der Typ der Arrayvariablen.  Gültige Typen sind [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] und Grundlagentypen Verweisklassen, Klassen und Strukturen, Wertklassen und Strukturen, systemeigene Zeiger \(`type``*`\) und systemeigenen HÜLSE \(Plain Old Data\) Typen.  
  
 `rank` \[optional\]  
 Die Anzahl der Dimensionen des Arrays.  Der Standardwert ist 1; das Maximum ist 32.  Jede Dimension des Arrays ist selbst ein Array.  
  
 `identifier`  
 Der Name der Arrayvariablen.  
  
 `initialization-type`  
 Der Typ der Werte, die das Array initialisieren.  Normalerweise sind `array-type` und `initialization-type` der gleiche Typ.  Allerdings können die Typen unterscheiden, wenn eine Konvertierung von `initialization-type` in `array-type`\- für Beispiel gibt, wenn `initialization-type` von `array-type` abgeleitet ist.  
  
 `rank-size-list`  
 Eine durch Trennzeichen getrennte Liste der Größe jeder Dimension im Array.  Wenn der Parameter `initialization-list` angegeben wird, kann der Compiler die Größe der Dimension ableiten und `rank-size-list` kann ausgelassen werden.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von mehrdimensionalen Arrays](../misc/how-to-create-multidimension-arrays.md).  
  
 `initialization-list` \[optional\]  
 Eine durch Trennzeichen getrennte Liste von Werten in geschweiften Klammern, die die Elemente des Arrays initialisieren.  Oder eine durch Trennzeichen getrennte Liste mit verschachtelten *initialization\-list*\-Elemente, die die Elemente in einem mehrdimensionalen Feld initialisieren.  
  
 Wenn `rank-size-list``(3)` festgelegt wäre, die ein eindimensionales Array mit 3 Elementen deklarieren, kann `initialization list``{1,2,3}` sein.  Wenn `rank-size-list``(3,2,4)` festgelegt wäre, die ein dreidimensionales Array mit 3 Elementen in der ersten Dimension deklariert, können 2 Elemente in zweites und 4 Elemente im dritten, `initialization-list``{{1,2,3},{0,0},{-5,10,-21,99}}` sein.\)  
  
 **Hinweise**  
  
 `array` ist im Namespace [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Wie Standard\-C\+\+ sind die Indizes eines Arrays nullbasiert, und ein Array ist indiziert, indem es verwendet eckige Klammern \(\[\]\).  Im Gegensatz Standard\-C\+\+ werden die Indizes eines mehrdimensionalen Feldes in einer Liste von Indizes für jede Dimension anstelle eines Satzes Operatoren angegeben der eckigen Klammer \(\[\]\) für jede Dimension.  Beispielsweise *identifier*\[*index1*, *index2*\] und nicht *identifier*\[*index1*\] \[ *index2*\].  
  
 Alle verwalteten Arrays erben von `System::Array`.  Jede Methode oder Eigenschaft von `System::Array` können direkt der Arrayvariablen angewendet werden.  
  
 Wenn Sie einem Array zuordnen, dessen Elementtyp Zeiger\-zu einer verwalteten Klasse ist, sind die Elemente 0 initialisiert.  
  
 Wenn Sie einem Array zuordnen, dessen Elementtyp ein Werttyp ist `V`, ist der Standardkonstruktor für `V` auf jedes Arrayelement angewendet.  Weitere Informationen finden Sie unter [.NET Framework\-Entsprechungen der systemeigenen Typen in C\+\+](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Zur Kompilierzeit können Sie erkennen, ob ein Typ ein Common Language Runtime \(CLR\)\- Array mit `__is_ref_array(``type``)` ist.  Weitere Informationen finden Sie unter [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 Im folgenden Beispiel wird ein eindimensionales Array, das Elemente, 100 hat und ein dreidimensionales Array, das Elemente 3 in der ersten Dimension verfügt, 5 Elemente in zweites und 6 Elemente im dritten.  
  
```  
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
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)