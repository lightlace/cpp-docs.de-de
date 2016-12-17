---
title: "Classes and Structs  (C++ Component Extensions)"
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
  - "public"
  - "ref struct"
  - "value_CPP"
  - "ref class"
  - "value struct"
  - "ref struct_cpp"
  - "ref class_cpp"
  - "value class_cpp"
  - "value struct_cpp"
  - "value class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref class keyword [C++]"
  - "value class keyword [C++]"
  - "value struct keyword [C++]"
  - "ref struct keyword [C++]"
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
caps.latest.revision: 32
caps.handback.revision: "32"
ms.author: "mblome"
manager: "ghogen"
---
# Classes and Structs  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert eine Klasse oder Struktur, deren *Objektlebensdauer* automatisch verwaltet wird.  Wenn auf das Objekt nicht mehr zugegriffen werden kann oder den Gültigkeitsbereich verlässt, verwirft Visual C\+\+ automatisch den Speicher, der dem Objekt zugeordnet ist.  
  
## Alle Laufzeiten  
 **Syntax**  
  
```  
  
          class_access ref class    name modifier :  inherit_access base_type {};  
class_access ref struct   name modifier :  inherit_access base_type {};  
class_access value class  name modifier :  inherit_access base_type {};  
class_access value struct name modifier :  inherit_access base_type {};  
  
```  
  
 **Parameter**  
  
 *Class\_access* \(optional\)  
 Der Zugriff auf die Klasse oder Struktur, außerhalb der Assembly.  Mögliche Werte sind **öffentlich** und `private` \(`private` ist der Standardwert\).  Geschachtelte Klassen oder Strukturen können keine *Class\_access* Bezeichner haben.  
  
 *Name*  
 Der Name der Klasse oder Struktur.  
  
 *Modifizierer* \(optional\)  
 [abstrakte](../windows/abstract-cpp-component-extensions.md) und [versiegelte](../windows/sealed-cpp-component-extensions.md) sind gültige Modifizierer.  
  
 *Inherit\_access* \(optional\)  
 Die Zugriff zu `base_type`.  Der einzige zulässige Zugriff ist `public` \(`public` ist die Standardeinstellung\).  
  
 *base\_type* \(optional\)  
 Ein Basistyp.  Jedoch kann ein Werttyp nicht als Basistyp dienen.  
  
 Weitere Informationen finden Sie unter der sprachspezifische Beschreibungen für diesen Parameter in den Abschnitten [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] und [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)].  
  
 **Hinweise**  
  
 Der Standard\-Memberzugriff eines Objekts deklariert mit **Verweisklasse** oder **Wertklasse** ist `private`.  Und der Standard\-Memberzugriff eines Objekts deklariert mit **Verweisklasse** oder **Wertklasse** ist `public`.  
  
 Wenn ein Verweistyp von einem anderen  Verweistyp erbt, dann müssen virtuelle Funktionen in der Basisklasse explizit überschrieben werden \(mit [override](../windows/override-cpp-component-extensions.md)\) oder ausgeblendet \(mit [new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)\).  Die abgeleiteten Klassenfunktionen müssen auch explizit markiert sein `virtual`.  
  
 Um zur Kompilierzeit zu erkennen, ob ein Typ `ref class` oder `ref struct` ist, oder `value class` oder `value struct`, verwenden Sie `__is_ref_class (``type``)`, `__is_value_class (``type``)`, oder `__is_simple_value_class (``type``)`.  Weitere Informationen finden Sie unter [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Weitere Informationen über Klassen und Strukturen finden Sie unter  
  
-   [Instanziieren von Klassen und Strukturen](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
-   [Semantik des this\-Zeigers in Wert\- und Referenztypen](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md)  
  
-   [C\+\+\-Stack\-Semantik für Referenztypen](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md)  
  
-   [öffentliche und private native Klassen](../misc/how-to-declare-public-and-private-on-native-classes.md)  
  
-   [Implizit abstrakte Klassen](../misc/implicitly-abstract-classes.md)  
  
-   [Definieren eines statischen Konstruktors in einer Klasse oder Struktur](../misc/how-to-define-static-constructors-in-a-class-or-struct.md)  
  
-   [Kopierkonstruktor konnte nicht generiert werden](../misc/copy-constructor-may-not-be-generated.md)  
  
-   [Funktionen zum Verdecken nach Signatur in Referenztypen](../misc/hide-by-signature-functions-in-reference-types.md)  
  
-   [Destruktoren und Finalizer in Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md)  
  
-   [Typ\- und Membersichtbarkeit](../misc/type-and-member-visibility.md)  
  
-   [Benutzerdefinierte Operatoren](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [Benutzerdefinierte Konvertierungen](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [Gewusst wie: Kapseln einer systemeigenen Klasse zur Verwendung in C\#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [Generic Classes \(C\+\+\/CLI\)](../windows/generic-classes-cpp-cli.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 Finden Sie unter [Verweisklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) und [Klassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx).  
  
 **Parameter**  
  
 *base\_type* \(optional\)  
 Ein Basistyp.  `ref class` oder `ref struct` kann von NULL oder mehr Schnittstellen und NULL oder eins `ref` Typen erben.  `value class` oder `value struct` kann von null oder mehreren Schnittstellen erben.  
  
 Wenn Sie ein Objekt mithilfe der `ref class` oder `ref struct` Schlüsselwörter deklarieren, erfolgt der Zugriff auf das Objekt durch einen Handle für ein Objekt, d. h. einen Verweiszähler\-Zeiger auf das Objekt.  Wenn die deklarierte Variable den Gültigkeitsbereich verlässt, wird der Compiler automatisch das zugrunde liegende Objekt löschen.  Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird ein Handle für das Objekt tatsächlich übergeben oder gespeichert.  
  
 Wenn Sie ein Objekt mithilfe der `value class` oder `value struct` Schlüsselwörter deklarieren, wird die Objektlebensdauer das deklarierte Objekt nicht überwacht.  Das Objekt ist wie jede andere Standard\-C\+\+\-Klasse oder \-Struktur.  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 Die folgende Tabelle zeigt die Unterschiede die vom Syntax im Abschnitt **Alle Laufzeiten** spezifisch für C\+\+ \/ CLI sind.  
  
 **Parameter**  
  
 *base\_type* \(optional\)  
 Ein Basistyp.  `ref class` oder `ref struct` kann von NULL oder mehr verwalteten Schnittstellen und NULL oder einem Referenztypen erben.  `value class` oder `value struct` kann von null oder mehr verwalteten Schnittstellen erben.  
  
 Die `ref class` und `ref struct` Schlüsselwörter teilen dem Compiler mit, dass die Klasse oder Struktur dem Heap zugeteilt wird.  Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird eine Referenz für das Objekt tatsächlich übergeben oder gespeichert.  
  
 Die `value class` und `value struct` Schlüsselwörter teilen dem Compiler, dass der Wert der zugeordneten Klasse oder Struktur an Funktionen übergeben oder in Elemente gespeichert.  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)