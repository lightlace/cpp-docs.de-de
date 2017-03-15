---
title: "property  (C++ Component Extensions)"
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
  - "property_cpp"
  - "property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "property keyword [C++]"
ms.assetid: cc79d2b2-f013-4d81-8252-eece97a18704
caps.latest.revision: 31
caps.handback.revision: "29"
ms.author: "mblome"
manager: "ghogen"
---
# property  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert eine *Eigenschaft*, die eine Memberfunktion ist, die sich wie ein Datenmember oder ein Arrayelement verhält und wie diese aufgerufen wird.  
  
## Alle Laufzeiten  
 Sie können einen der folgenden Typen von Eigenschaften deklarieren.  
  
 *Einfache Eigenschaft*  
 Erstellt standardmäßig einen *set\-Accessor*, der den Eigenschaftswert zuweist, einen *get\-Accessor*, der den Eigenschaftswert abruft, und ein vom Compiler generiertes, privates Datenmember, das den Eigenschaftswert enthält.  
  
 *Property\-Block*  
 Verwenden Sie diesen Typ zum Erstellen von benutzerdefinierten get\- und\/oder set\-Accessoren.  Für die Eigenschaft gilt Lese\-\/Schreibzugriff, wenn get\- und set\-Accessoren definiert sind, sie ist schreibgeschützt, wenn nur der get\-Accessor definiert ist, und lesegeschützt, wenn nur der set\-Accessor definiert ist.  
  
 Sie müssen ein Datenmember explizit so deklarieren, dass es den Eigenschaftswert enthält.  
  
 *Indizierte Eigenschaft*  
 Ein Property\-Block, mit dem Sie einen Eigenschaftswert abrufen und festlegen können, der durch einen oder mehrere Indizes angegeben wird.  
  
 Sie können eine indizierte Eigenschaft erstellen, die entweder einen benutzerdefinierten Eigenschaftsnamen oder einen *Standard*\-Eigenschaftsnamen aufweist.  Der Name der Standardindexeigenschaft ist der Name der Klasse, in der die Eigenschaft definiert ist.  Um eine Standardeigenschaft zu deklarieren, geben Sie das `default`\-Schlüsselwort anstelle eines Eigenschaftsnamens an.  
  
 Sie müssen ein Datenmember explizit so deklarieren, dass es den Eigenschaftswert enthält.  Bei einer indizierten Eigenschaft ist das Datenmember in der Regel ein Array oder eine Sammlung.  
  
### Syntax  
  
```cpp  
  
property type property_name;  
  
property type property_name {  
   access-modifier type get() inheritance-modifier {property_body};  
   access-modifier void set(type value) inheritance-modifier {property_body};  
} property type property_name[index_list] {  
   access-modifier type get(index_list) inheritance-modifier {property_body};  
   access-modifier void set(index_list, value) inheritance-modifier {property_body};  
} property type default[index_list] {  
   access-modifier type get(index_list) inheritance-modifier {property_body};  
   access-modifier void set(index_list, value) inheritance-modifier {property_body};  
}  
  
```  
  
### Parameter  
 `type`  
 Der Datentyp des Eigenschaftwerts und somit die Eigenschaft selbst.  
  
 `property_name`  
 Der Name der Eigenschaft.  
  
 `access-modifier`  
 Ein Zugangsqualifizierer.  Gültige Qualifizierer sind `static` und `virtual`.  
  
 Die get\- und set\-Accessoren müssen nicht den gleichen `virtual`\-Qualifizierer aufweisen, sie müssen aber beim `static`\-Qualifizierer übereinstimmen.  
  
 `inheritance-modifier`  
 Ein Vererbungqualifizierer.  Gültige Qualifizierer sind `abstract` und `sealed`.  
  
 `index_list`  
 Eine durch Kommata getrennte Liste von einem oder mehreren Indizes.  Jeder Index besteht aus einem Indextyp und einem optionalen Bezeichner, der im Methodentext der Eigenschaft verwendet werden kann.  
  
 `value`  
 Der der Eigenschaft in einem set\-Vorgang zuzuweisende Wert, oder der in einem get\-Vorgang abzurufende Wert.  
  
 `property_body`  
 Der Methodentext der Eigenschaft des set\- oder get\-Accessors.  Der `property_body` kann über die `index_list` auf den zugrundeliegende Eigenschaftendatenmember zugreifen, oder als Parameter bei der benutzerdefinierten Verarbeitung.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Weitere Informationen finden Sie unter [Eigenschaften \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755807.aspx).  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntax**  
  
```  
  
modifier property type property_name;  
  
modifier property type property_name {  
   modifier void set(type);  
   modifier type get();  
}  
modifier property type property_name[index-list, value] {  
   modifier void set(index-list, value);  
   modifier type get(index-list);  
  
modifier property type default[index];  
}  
```  
  
 **Parameter**  
  
 *modifier*  
 Ein Modifizierer, der entweder für eine Eigenschaftendeklaration oder eine get\-\/set\-Accessormethode verwendet werden kann.  Mögliche Werte sind `static` und `virtual`.  
  
 *Typ*  
 Der Typ des Werts, der durch die Eigenschaft dargestellt wird.  
  
 *property\_name*  
 Parameter für die Raise\-Methode; muss der Signatur des Delegaten entsprechen.  
  
 *index\_list*  
 Eine durch Kommata getrennte Liste von einem oder mehreren Indizes, die in eckigen Klammern \(der Indexoperator, \(\[\]\)\) angegeben werden.  Geben Sie für jeden Index einen Typ und optional einen Bezeichner an, der im Methodentext der Eigenschaft verwendet werden kann.  
  
 **Hinweise**  
  
 Das erste Syntaxbeispiel zeigt eine *einfache Eigenschaft*, die implizit eine `set`\- und eine `get`\-Methode deklariert.  Der Compiler erstellt automatisch ein privates Feld für die Speicherung des Werts der Eigenschaft.  
  
 Das zweite Syntaxbeispiel zeigt einen *Property\-Block*, der explizit eine `set`\- und eine `get`\-Methode deklariert.  
  
 Das dritte Syntaxbeispiel zeigt eine benutzerdefinierte *Indexeigenschaft*.  Eine Indexeigenschaft nimmt zusätzlich zu dem festzulegenden oder abzurufenden Wert Parameter.  Sie müssen einen Namen für die Eigenschaft angeben.  Im Gegensatz zu einer einfachen Eigenschaft müssen die `set`\- und\/oder `get`\-Methoden einer Indexeigenschaft explizit definiert werden, und Sie müssen einen Namen für die Eigenschaft angeben.  
  
 Das vierte Syntax Beispiel zeigt eine *Standardeigenschaft*, die arrayähnlichen Zugriff auf eine Instanz des Typs bereitstellt.  Das Schlüsselwort `default` dient nur zum Angeben einer Standardeigenschaft.  Der Name der Standardeigenschaft ist der Name des Typs, in dem die Eigenschaft definiert ist.  
  
 Das `property`\-Schlüsselwort kann in einer Klasse, in einer Schnittstelle oder in einem Werttyp angezeigt werden.  Eine Eigenschaft kann über eine get\-Funktion \(schreibgeschützt\), eine set\-Funktion \(lesegeschützt\) oder beide \(Lese\-\/Schreibzugriff\) verfügen.  
  
 Ein Eigenschaftenname kann nicht mit dem Namen der verwalteten Klasse übereinstimmen, in der er enthalten ist.  Der Rückgabetyp der Getter\-Funktion muss dem Typ des letzten Parameters einer entsprechenden Setter\-Funktion entsprechen.  
  
 Für Clientcode sieht eine Eigenschaft wie ein gewöhnliches Datenmember aus, und es kann anhand der gleichen Syntax wie bei einem Datenmember in sie geschrieben oder aus ihr gelesen werden.  
  
 Die Get\- und Set\-Methoden müssen nicht den gleichen `virtual`\-Modifizierer aufweisen.  
  
 Der Zugriff auf die Get\- und Set\-Methode kann sich unterscheiden.  
  
 Die Definition einer Eigenschaftenmethode kann außerhalb des Klassentexts angezeigt werden, genau wie eine normale Methode.  
  
 Die Get\- und Set\-Methode für eine Eigenschaft müssen den gleichen **statischen** Modifizierer aufweisen.  
  
 Eine Eigenschaft ist skalar, wenn ihre Get\- und Set\-Methoden der folgenden Beschreibung entsprechen:  
  
-   Die Get\-Methode besitzt keine Parameter und hat den Rückgabetyp `T`.  
  
-   Die Set\-Methode besitzt einen Parameter des Typs `T` und den Rückgabetyp **void**.  
  
 Es darf nur eine skalare Eigenschaft in einem Bereich mit dem gleichen Bezeichner deklariert werden.  Skalare Eigenschaften können nicht überladen werden.  
  
 Wenn ein Eigenschaftendatenmember deklariert wird, fügt der Compiler ein Datenmember – auch als „Sicherungsspeicher“ bezeichnet – in der Klasse ein.  Allerdings weist der Name des Datenmembers solch eine Form auf, dass Sie nicht auf das Element in der Datenquelle verweisen können, als handele es sich um ein tatsächliches Datenmember der enthaltenen Klasse.  Zeigen Sie mithilfe von ildasm.exe die Metadaten für den Typ und den vom Compiler generierten Namen für den Sicherungsspeicher der Eigenschaft an.  
  
 Für die Accessormethoden sind unterschiedliche Zugriffsmöglichkeiten in einem Property\-Block zulässig.  D. h., dass die Set\-Methode öffentlich und die Get\-Methode privat sein kann.  Es ist jedoch ein Fehler, wenn die Accessormethode weniger restriktiven Zugriff hat als in der Deklaration der Eigenschaft selbst vermerkt ist.  
  
 `property` ist ein kontextbezogenes Schlüsselwort.  Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Weitere Informationen zu Eigenschaften finden Sie unter  
  
-   [Indizierte Eigenschaften](../misc/how-to-use-indexed-properties.md)  
  
-   [Statische Eigenschaften](../misc/how-to-declare-and-use-static-properties.md)  
  
-   [Virtuelle Eigenschaften](../misc/how-to-declare-and-use-virtual-properties.md)  
  
-   [Mehrdimensionale Eigenschaften](../misc/how-to-use-multidimensional-properties.md)  
  
-   [Überladen von Methoden des Eigenschaftenaccessors](../misc/how-to-overload-property-accessor-methods.md)  
  
-   [Gewusst wie: Deklarieren von Abstrakten und Sealed\-Eigenschaften](../misc/how-to-declare-abstract-and-sealed-properties.md)  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 Das folgende Beispiel zeigt die Deklaration und Verwendung eines Eigenschaftendatenmembers und eines Property\-Blocks.  Es zeigt auch, dass ein Eigenschaftenaccessor außerhalb der Klasse definiert werden kann.  
  
```  
// mcppv2_property.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   int MyInt;  
public:  
  
   // property data member  
   property String ^ Simple_Property;  
  
   // property block  
   property int Property_Block {  
  
      int get();  
  
      void set(int value) {  
         MyInt = value;  
      }  
   }  
};  
  
int C::Property_Block::get() {  
   return MyInt;  
}  
  
int main() {  
   C ^ MyC = gcnew C();  
   MyC->Simple_Property = "test";  
   Console::WriteLine(MyC->Simple_Property);  
  
   MyC->Property_Block = 21;  
   Console::WriteLine(MyC->Property_Block);  
}  
```  
  
 **Ausgabe**  
  
  **Test**  
 **21**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)