---
title: "Deklaration eines verwalteten Klassentyps"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__gc-Typen"
  - "__value-Schlüsselwort"
  - "class-Schlüsselwort [C++], CLR"
  - "Klassen [C++], Verwaltet"
  - "Schnittstellenklassenschlüsselwort"
  - "Verwaltete Klassen"
  - "ref-Schlüsselwort [C++]"
  - "value-Schlüsselwort [C++]"
  - "Werttypen, Deklarieren"
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Deklaration eines verwalteten Klassentyps
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Art und Weise, einen Verweisklassentyp zu deklarieren, hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 In Managed Extensions wird einem Verweisklassentyp das `__gc`\-Schlüsselwort vorangestellt.  In der neuen Syntax wird das `__gc`\-Schlüsselwort durch eines von zwei durch Leerzeichen getrennten Schlüsselwörtern ersetzt: `ref class` oder `ref struct`.  Die Wahl von `struct` oder `class` gibt die öffentliche \(für `struct`\) oder private \(für `class`\) Standardzugriffsebene der Member an, die innerhalb eines nicht bezeichneten Anfangsabschnitts im Text des Typen deklariert werden.  
  
 Ebenso wird in Managed Extensions einem Wertklassentyp das `__value`\-Schlüsselwort vorangestellt.  In der neuen Syntax wird das `__value`\-Schlüsselwort durch eines von zwei durch Leerzeichen getrennten Schlüsselwörtern ersetzt: `value class` oder `value struct`.  
  
 Ein Schnittstellentyp wurde in Managed Extensions mit dem Schlüsselwort `__interface` gekennzeichnet.  In der neuen Syntax wird dieses Schlüsselwort durch `interface class` ersetzt.  
  
 Betrachten Sie zum Beispiel die folgenden Klassendeklarationen in Managed Extensions:  
  
```  
public __gc class Block {};     // reference class  
public __value class Vector {}; // value class  
public __interface IFooBar {};  // interface class  
```  
  
 In der neuen Syntax sehen die entsprechenden Deklarationen wie folgt aus:  
  
```  
public ref class Block {};         // reference class  
public value class Vector {};      // value class  
public interface class IFooBar {}; // interface class  
```  
  
## Festlegen einer abstrakten Klasse  
 In Managed Extensions setzen Sie das Schlüsselwort `__abstract` vor das `class`\-Schlüsselwort \(entweder vor oder nach `__gc`\), um anzugeben, dass die Klasse unvollständig ist und Objekte der Klasse nicht innerhalb des Programms erstellt werden können:  
  
```  
public __gc __abstract class Shape {};  
public __gc __abstract class Shape2D: public Shape {};  
```  
  
 In der neuen Syntax setzen Sie das `abstract`\-Kontextschlüsselwort hinter den Klassennamen und entweder vor den Klassenkörper, die Ableitungsliste der Basisklasse oder ein Semikolon.  
  
```  
public ref class Shape abstract {};  
public ref class Shape2D abstract : public Shape{};  
```  
  
 Die semantische Bedeutung bleibt natürlich unverändert.  
  
## Festlegen einer versiegelten Klasse  
 In Managed Extensions setzen Sie das Schlüsselwort `__sealed` vor das `class`\-Schlüsselwort \(entweder vor oder nach `__gc`\), um anzugeben, dass keine Vererbung von Objekten der Klasse möglich ist:  
  
```  
public __gc __sealed class String {};  
```  
  
 In der neuen Syntax setzen Sie das `sealed`\-Kontextschlüsselwort hinter den Klassennamen und entweder vor den Klassenkörper, die Ableitungsliste der Basisklasse oder ein Semikolon.  
  
 Sie können eine Klasse sowohl ableiten als auch versiegeln.  Zum Beispiel wird die `String`\-Klasse implizit von `Object` abgeleitet.  Der Vorteil des Versiegelns einer Klasse besteht darin, dass dadurch die statische Auflösung \(und zwar während der Kompilierung\) aller virtuellen Funktionsaufrufe über das versiegelte Referenzklassenobjekt unterstützt wird.  Denn der `sealed`\-Bezeichner garantiert, dass das `String`\-Trackinghandle nicht auf eine nachfolgend abgeleitete Klasse verweisen kann, die möglicherweise eine überschreibende Instanz der aufgerufenen virtuellen Methode bereitstellt.  Hier sehen Sie ein Beispiel für eine versiegelte Klasse in der neuen Syntax:  
  
```  
public ref class String sealed {};  
```  
  
 Eine Klasse kann gleichzeitig als abstrakt und als versiegelt festgelegt werden – dies ist eine besondere Bedingung, die angibt, dass es sich um eine statische Klasse handelt.  In der CLR\-Dokumentation wird dies wie folgt beschrieben:  
  
 "Ein Typ, der sowohl `abstract` als auch `sealed` ist, darf nur über statische Member verfügen und dient als ein Element, das in einigen Programmiersprachen Namespace genannt wird."  
  
 Das folgende Beispiel zeigt die Deklaration einer abstrakten versiegelten Klasse mithilfe der Managed Extensions\-Syntax:  
  
```  
public __gc __sealed __abstract class State {  
public:  
   static State() {}  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
 und so sieht diese Deklaration übersetzt in die neue Syntax aus:  
  
```  
public ref class State abstract sealed {  
public:  
   static State();  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
## CLR\-Vererbung: Festlegen der Basisklasse  
 Im CLR\-Objektmodell wird nur die öffentliche einfache Vererbung unterstützt.  Allerdings wurde in Managed Extensions die ISO\-C\+\+\-Standardinterpretation einer Basisklasse beibehalten ohne Zugriffsschlüsselwort zum Festlegen einer privaten Ableitung.  Dies hatte zur Folge, dass jede CLR\-Vererbungsdeklaration beim Überschreiben der Standardinterpretation das `public`\-Schlüsselwort bereitstellen musste.  
  
```  
// Managed Extensions: error: defaults to private derivation  
__gc class Derived : Base {};  
```  
  
 In der neuen Syntaxdefinition weist das Fehlen eines Zugriffsschlüsselworts auf eine öffentliche Ableitung in einer CLR\-Vererbungsdefinition hin.  Daher ist das `public`\-Zugriffsschlüsselwort nicht mehr erforderlich, sondern optional.  Diese Änderung in der Syntax wird der Vollständigkeit halber hier aufgeführt, obgleich der Managed Extensions for C\+\+\-Code nicht geändert werden muss.  
  
```  
// New syntax: ok: defaults to public derivation  
ref class Derived : Base{};  
```  
  
## Siehe auch  
 [Verwaltete Typen \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [abstract](../windows/abstract-cpp-component-extensions.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)