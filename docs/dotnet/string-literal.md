---
title: Zeichenfolgenliteral | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- string literals
- strings [C++], string literals
ms.assetid: 6d1fc3f8-0d58-4d68-9678-16b4f6dc4766
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ac847f67421802fe4d31f2d66b34128e4b24794
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="string-literal"></a>Zeichenfolgenliterale
Die Behandlung von Zeichenfolgenliteralen hat gegenüber Managed Extensions für C++ in Visual C++ geändert.  
  
 In Managed Extensions for C++ Language Design, eine verwaltete Zeichenfolge, die Literale angegeben wurde, indem das Zeichenfolgenliteral mit voran ein `S`. Zum Beispiel:  
  
```  
String *ps1 = "hello";  
String *ps2 = S"goodbye";  
```  
  
 Die Leistung Mehraufwand zwischen zwei Initialisierungen beläuft sich auf nicht triviale, als die folgenden CIL Darstellung wird veranschaulicht, wie durch **"Ildasm"**:  
  
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
  
 Also eine bemerkenswerte speicherersparnis nur merken (oder Learning) eine literale Zeichenfolge als Präfix mit einem `S`. In der neuen Syntax wird die Behandlung von Zeichenfolgenliteralen transparent, erfolgt vom Kontext Verwendung bestimmt. Die `S` muss nicht mehr angegeben werden.  
  
 Was geschieht Fälle, in denen wir explizit müssen, den Compiler eine Interpretation oder einem anderen? In diesen Fällen verwenden wir eine explizite Umwandlung. Zum Beispiel:  
  
```  
f( safe_cast<String^>("ABC") );  
```  
  
 Darüber hinaus führt das Zeichenfolgenliteral jetzt entspricht einem `String` mit einer standardkonvertierung, anstatt eine einfache Konvertierung. Obwohl dies nicht klingen möglicherweise wesentlich ändert die Auflösung der überladene Funktion darunter ein `String` und ein `const char*` als konkurrierende formale Parameter. Die Lösung, die einmal aufgelöst wurde eine `const char*` Instanz ist jetzt als mehrdeutig markiert. Zum Beispiel:  
  
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
  
 Warum gibt es einen Unterschied? Seit mehr als eine Instanz mit dem Namen `f` vorhanden ist innerhalb des Programms, die dies erfordert die Funktion Überladung Auflösungsalgorithmus auf den Aufruf angewendet werden soll. Die formale Auflösung einer überladenen Funktion umfasst drei Schritte.  
  
1.  Die Auflistung der möglichen Funktionen. Die kandidatenfunktionen sind diese Methoden innerhalb des Bereichs, die den Namen der aufgerufenen Funktion lexikalisch entsprechen. Z. B. seit `f()` wird aufgerufen, durch eine Instanz von `R`, werden alle Funktionen mit dem Namen `f` , die nicht Mitglied sind `R` (oder seiner Hierarchie Basisklasse) sind nicht kandidatenfunktionen. In unserem Beispiel gibt es zwei mögliche Funktionen. Dies sind die beiden Memberfunktionen der `R` mit dem Namen `f`. In dieser Phase schlägt ein Aufruf in die Candidate Funktion leer ist.  
  
2.  Der Satz von durchführbare Funktionen aus den möglichen Funktionen. Eine sinnvolle Funktion ist eine, die mit den Argumenten im Aufruf angegebenen angesichts der Anzahl von Argumenten und ihre Typen aufgerufen werden können. In unserem Beispiel sind beide möglichen Funktionen auch durchführbare Funktionen. In dieser Phase schlägt ein Aufruf in die geeignete Funktion leer ist.  
  
3.  Wählen Sie die Funktion, die die beste Übereinstimmung des Aufrufs darstellt. Dazu ordnen die Konvertierungen angewendet, um die Argumente für den Typ der Gültigkeit Funktionsparameter zu transformieren. Dies ist eine verhältnismäßig einfach mit einem einzelnen Parameter-Funktion; Es wird etwas komplexer, wenn mehrere Parameter vorhanden sind. Ein Aufruf fehlschlägt in dieser Phase, wenn keine beste Übereinstimmung vorhanden ist. D. h., wenn die Konvertierungen, die zum Transformieren des Typs des tatsächlichen Arguments in den Typ des formalen Parameters gleich gut geeignet sind. Der Aufruf wird als mehrdeutig gekennzeichnet.  
  
 In Managed Extensions die Auflösung dieses Aufrufs aufgerufen, die `const char*` Instanz als beste Übereinstimmung. In der neuen Syntax wird die Konvertierung entsprechend der erforderlichen `"abc"` auf `const char*` und `String^` gleichwertig jetzt – d. h., gut -, sodass der Aufruf als fehlerhaft -, d. h. gekennzeichnet ist als mehrdeutig.  
  
 Dies führt uns auf zwei Fragen:  
  
-   Was ist, dass der Typ des tatsächlichen Arguments `"abc"`?  
  
-   Was ist der Algorithmus zum bestimmen, wann eine typkonvertierung besser als ein anderes ist?  
  
 Der Typ des Zeichenfolgenliterals `"abc"` ist `const char[4]` -Denken Sie daran, es ist ein impliziter null abschließende Zeichen am Ende jeder Zeichenfolge Zeichenfolgenliteral.  
  
 Der Algorithmus für zu bestimmen, wann eine Konvertierung ist besser als eine andere umfasst, platzieren die möglichen typkonvertierungen in einer Hierarchie. Hier ist meine Verständnis dieser Hierarchie - alle diese Konvertierungen natürlich sind implizit. Verwenden eine explizite Umwandlungsnotation überschreibt die Hierarchie, die ähnlich wie die Klammern überschreibt die üblichen Operatorrangfolge eines Ausdrucks.  
  
1.  Eine genaue Übereinstimmung wird empfohlen. Überraschenderweise für ein Argument, um eine genaue Übereinstimmung sein, muss es nicht genau mit den Parametertyp übereinstimmen; Es muss nur genau genug sein. Dies ist der Schlüssel zum Verständnis, was passiert in diesem Beispiel wird und wie die Sprache geändert hat.  
  
2.  Eine Höherstufung ist besser als eine standardkonvertierung. Z. B. Höherstufen einer `short int` auf ein `int` ist besser als das Konvertieren von einer `int` in eine `double`.  
  
3.  Eine standardkonvertierung ist besser als eine Boxingkonvertierung. Konvertieren Sie z. B. ein `int` in eine `double` ist besser, Boxing ein `int` in ein `Object`.  
  
4.  Eine Boxingkonvertierung ist besser als eine implizite Konvertierung von benutzerdefinierten. Boxing z. B. ein `int` in einer `Object` ist besser als das Anwenden eines Konvertierungsoperators eine `SmallInt` -Wertklasse.  
  
5.  Eine implizite Konvertierung von benutzerdefinierten ist überhaupt keine Konvertierung besser. Eine implizite Konvertierung von benutzerdefinierten ist der letzte vor dem Fehler (mit der Einschränkung, dass die formale Signatur ein Parameterarray oder mit den Auslassungspunkten an dieser Position enthalten kann).  
  
 Was bedeutet es zu sagen, dass eine genaue Übereinstimmung nicht unbedingt genau eine Übereinstimmung ist? Beispielsweise `const char[4]` stimmt nicht genau überein, entweder `const char*` oder `String^`, und noch die Mehrdeutigkeit in unserem Beispiel ist zwischen beiden in Konflikt stehenden genaue Übereinstimmungen!  
  
 Eine genaue Übereinstimmung, wie es der Fall ist, umfasst eine Reihe von triviale Konvertierungen enthält. Es gibt vier triviale Konvertierungen unter ISO C++, die angewendet werden können und dennoch als genaue Übereinstimmung zu qualifizieren. Drei werden als Lvalue-Transformationen bezeichnet. Vierter Typ ist eine Qualifizierung Konvertierung aufgerufen werden. Die drei Lvalue-Transformationen sind als besser genaue Übereinstimmung als eine erfordert eine Qualifikation Konvertierung behandelt.  
  
 Eine Form der Lvalue-Transformation ist die systemeigene Array, Zeiger-Konvertierung. Dies kommt in den Abgleich eine `const char[4]` auf `const char*`. Aus diesem Grund die Übereinstimmung der `f("abc")` zu `f(const char*)` ist eine genaue Übereinstimmung. In der früheren galt unsere Sprache war dies die beste Übereinstimmung in der Tat.  
  
 Für der Compiler an, den Aufruf als mehrdeutig kennzeichnet erfordert daher, dass die Konvertierung von einem `const char[4]` auf eine `String^` werden auch eine genaue Übereinstimmung über eine triviale Konvertierung. Dies ist die Änderung, die in der neuen Sprachversion eingeführt wurde. Und daher wird der Aufruf jetzt gekennzeichnet ist als mehrdeutig.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Sprachänderungen (C + c++ / CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [String](../windows/string-cpp-component-extensions.md)