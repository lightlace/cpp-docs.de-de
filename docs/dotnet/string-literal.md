---
title: "Zeichenfolgenliterale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichenfolgenliterale"
  - "Zeichenfolgen [C++], Zeichenfolgenliterale"
ms.assetid: 6d1fc3f8-0d58-4d68-9678-16b4f6dc4766
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Zeichenfolgenliterale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Behandlung von Zeichenfolgenliteralen hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Im Sprachdesign von Managed Extensions for C\+\+ wurde ein verwaltetes Zeichenfolgenliteral durch ein einleitendes `S` gekennzeichnet.  Beispiel:  
  
```  
String *ps1 = "hello";  
String *ps2 = S"goodbye";  
```  
  
 Der unterschiedliche Leistungsaufwand der beiden Initialisierungsvarianten erweist sich als nicht unwesentlich, wie die folgende mit **ildasm** angezeigte CIL\-Darstellung zeigt:  
  
```  
// String *ps1 = "hello";  
ldsflda    valuetype $ArrayType$0xd61117dd  
     modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier)   
     '?A0xbdde7aca.unnamed-global-0'  
  
newobj instance void [mscorlib]System.String::.ctor(int8*)  
stloc.0  
  
// String *ps2 = S"goodbye";  
ldstr      "goodbye"  
stloc.0  
```  
  
 Dafür, dass man lediglich lernen bzw. sich daran erinnern muss, eine literale Zeichenfolge mit einem führenden `S` zu versehen, lässt sich eine bemerkenswerte Leistungseinsparung erzielen.  In der neuen Syntax ist die Behandlung von Zeichenfolgenliteralen transparent und vom Verwendungskontext abhängig.  Das `S` muss nicht mehr angegeben werden.  
  
 Was geschieht in Fällen, in denen wir den Compiler explizit auf die eine oder andere Interpretation festlegen müssen?  In diesen Fällen verwenden wir eine explizite Umwandlung.  Beispiel:  
  
```  
f( safe_cast<String^>("ABC") );  
```  
  
 Darüber hinaus entspricht das Zeichenfolgenliteral jetzt eher einem `String` mit einfacher Konvertierung statt einer Standardkonvertierung.  Dieser Unterschied mag unwesentlich klingen, jedoch ändert sich dadurch die Auflösung einer Reihe von überladenen Funktionen, die ein `String` und ein `const char*` als konkurrierende formale Parameter enthalten.  Die Auflösung, die vorher zu einer `const char*`\-Instanz auflöste, wird jetzt als mehrdeutig gekennzeichnet.  Beispiel:  
  
```  
ref struct R {  
   void f(const char*);  
   void f(String^);  
};  
  
int main () {  
   R r;  
   // old syntax: f( const char* );  
   // new syntax: error: ambiguous  
   r.f("ABC");   
}  
```  
  
 Wie kommt es zu diesem Unterschied?  Da es innerhalb des Programms mehr als eine Instanz mit dem Namen `f` gibt, ist es erforderlich, den Auflösungsalgorithmus für die Funktionsüberladung auf den Aufruf anzuwenden.  Die formale Auflösung einer überladenen Funktion umfasst drei Schritte.  
  
1.  Die Auflistung der möglichen Funktionen.  Mögliche Funktionen sind solche Methoden innerhalb des Gültigkeitsbereichs, die lexikalisch dem Namen der aufgerufenen Funktion entsprechen.  Wenn beispielsweise `f()` durch eine Instanz von `R` aufgerufen wird, sind alle Funktionen mit dem Namen `f`, die nicht Member von `R` \(oder der zugehörigen Basisklassenhierarchie\) sind, keine möglichen Funktionen.  In unserem Beispiel gibt es zwei mögliche Funktionen.  Und zwar die beiden Memberfunktionen von `R` mit dem Namen `f`.  In dieser Phase schlägt ein Aufruf fehl, wenn die Gruppe möglicher Funktionen leer ist.  
  
2.  Die Gruppe durchführbarer Funktionen unter den möglichen Funktionen.  Eine Funktion gilt als durchführbar, wenn Anzahl und Typ ihrer Argumente denen des Aufrufs entsprechen und sie daher mit den angegebenen Argumenten aufgerufen werden kann.  In unserem Beispiel sind beide möglichen Funktionen auch durchführbare Funktionen.  In dieser Phase schlägt ein Aufruf fehl, wenn die Gruppe durchführbarer Funktionen leer ist.  
  
3.  Wählen Sie die Funktion aus, die dem Aufruf am besten entspricht.  Werten Sie hierzu die Konvertierungen, die erforderlich sind, um die Argumente den Parametertypen der durchführbaren Funktion anzupassen.  Dies ist bei Funktionen mit einem einzelnen Parameter relativ einfach; wenn mehrere Parameter zu übergeben sind, wird es etwas komplizierter.  In dieser Phase schlägt ein Aufruf fehl, wenn es keine bestmögliche Übereinstimmung gibt.  D. h., wenn die Konvertierungen, die erforderlich sind, um den jeweiligen Argumenttyp in den Typ des formalen Parameters umzuwandeln, gleichwertig sind.  Der Aufruf wird als mehrdeutig gekennzeichnet.  
  
 In Managed Extensions rief die Auflösung dieses Aufrufs die `const char*`\-Instanz als bestmögliche Übereinstimmung auf.  In der neuen Syntax sind die notwendigen Konvertierungen zur Anpassung von `"abc"` an `const char*` und `String^` gleichwertig, also gleich gut. Der Aufruf wird daher als mehrdeutig gekennzeichnet.  
  
 Dies führt zu zwei Fragen:  
  
-   Welchen Typ hat das Argument `"abc"`?  
  
-   Nach welchem Algorithmus wird bestimmt, ob die eine Typkonvertierung besser ist als die andere?  
  
 Der Typ des Zeichenfolgenliterals `"abc"` ist `const char[4]`. Erinnern Sie sich, dass jedes Zeichenfolgenliteral implizit durch ein NULL\-Zeichen abgeschlossen wird.  
  
 Zum Bestimmungsalgorithmus, ob eine Typkonvertierung besser ist als die andere, gehört auch das Einordnen der möglichen Typkonvertierungen in eine Hierarchie.  Nach meinem Verständnis dieser Hierarchie sind natürlich alle Konvertierungen implizit.  Die Verwendung einer expliziten Umwandlungsnotation überwindet die Hierarchie, ähnlich wie Klammern die übliche Operatorenrangfolge eines Ausdrucks.  
  
1.  Am besten ist eine genaue Übereinstimmung.  Überaschenderweise ist es für eine genaue Übereinstimmung eines Arguments nicht notwendig, dass es dem Parametertyp exakt entspricht; die Übereinstimmung muss nur genau genug sein.  Hierin liegt der Schlüssel zum Verständnis dieses Beispiels und dieser Sprachänderung.  
  
2.  Eine Erweiterung ist besser als eine Standardkonvertierung.  Zum Beispiel ist es besser, einen `short int` zu einem `int` zu erweitern, als einen `int` in einen `double` zu konvertieren.  
  
3.  Eine Standardkonvertierung ist einer Boxingkonvertierung vorzuziehen.  Zum Beispiel ist es besser, einen `int` in einen `double` zu konvertieren, als einen `int` mittels Boxing in ein `Object` zu konvertieren.  
  
4.  Eine Boxingkonvertierung ist besser als eine implizite benutzerdefinierte Konvertierung.  Das Boxing eines `int` in ein `Object` ist beispielsweise besser als die Anwendung eines Konvertierungsoperators einer `SmallInt`\-Wertklasse.  
  
5.  Eine implizite benutzerdefinierte Konvertierung ist besser als überhaupt keine Konvertierung.  Eine implizite benutzerdefinierte Konvertierung ist der letzte Ausweg \(Ausnahme: Die formale Signatur enthält an dieser Position ein Parameterarray oder eine Ellipse\).  
  
 Was bedeutet also die Aussage, dass eine genaue Übereinstimmung nicht notwendigerweise genau übereinstimmen muss?  `const char[4]` findet beispielsweise weder eine exakte Übereinstimmung in `const char*` noch in `String^`; und dennoch basiert die Mehrdeutigkeit in unserem Beispiel auf dem Konflikt zweier Treffer mit genauer Übereinstimmung\!  
  
 Das liegt daran, dass eine genaue Übereinstimmung eine Reihe trivialer Konvertierungen enthalten kann.  Es gibt vier triviale Konvertierungen in ISO\-C\+\+, die angewendet werden können und nicht gegen eine genaue Übereinstimmung sprechen.  Drei davon werden als lvalue\-Transformationen bezeichnet.  Der vierte Typ wird als Qualifikationskonvertierung bezeichnet.  Die drei lvalue\-Transformationen werden als bessere genaue Übereinstimmung behandelt als eine Qualifikationskonvertierung.  
  
 Eine Form der lvalue\-Transformation ist die Konvertierung eines systemeigenen Arrays in einen Zeiger.  Diese kommt bei der Anpassung von `const char[4]` an `const char*` zum Einsatz.  Deshalb gilt die Übereinstimmung von `f("abc")` mit `f(const char*)` als genaue Übereinstimmung.  In den früheren Versionen unserer Sprache galt dies tatsächlich als beste Übereinstimmung.  
  
 Damit der Compiler den Aufruf als mehrdeutig kennzeichnet, ist es deshalb erforderlich, dass die Konvertierung von `const char[4]` in `String^` aufgrund einer trivialen Konvertierung ebenfalls genau übereinstimmt.  Dies ist die Änderung in der neuen Sprachversion.  Und daher wird der Aufruf jetzt als mehrdeutig gekennzeichnet.  
  
## Siehe auch  
 [Allgemeine Sprachänderung](../dotnet/general-language-changes-cpp-cli.md)   
 [String](../windows/string-cpp-component-extensions.md)