---
title: Benutzerdefinierte Typkonvertierungen (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- explicit_cpp
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++], and constants
- conversion functions
- explicit keyword
- type conversion
- constructors [C++], drawbacks
- conversion constructors
- type conversion [C++], explicit conversion
- coercion
- conversions [C++], explicit
- objects [C++], converting
- conversion functions, rules for declaring
- declaring functions, conversion functions
- functions [C++], conversion
- converting objects
- constructors [C++], conversion
- conversions [C++], by constructors
- data type conversion [C++], explicit
ms.assetid: d40e4310-a190-4e95-a34c-22c5c20aa0b9
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 778c5a659755b5c79f79e9b846441c3e0665995e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="user-defined-type-conversions-c"></a>Benutzerdefinierte Typkonvertierungen (C++)
Ein *Konvertierung* produziert einen neuen Wert eines bestimmten Typs aus einem Wert eines anderen Typs. *Standardkonvertierungen* sind in der C++-Sprache und Unterstützung, die integrierten Typen, und Sie können erstellen, integriert *benutzerdefinierte Konvertierungen* zum Durchführen von Konvertierungen zu, von oder zwischen benutzerdefinierten Typen.  
  
 Die Standardkonvertierungen konvertieren zwischen integrierten Typen, zwischen Zeigern oder Verweisen auf Typen, die durch Vererbung verwandt sind, von und zu void-Zeigern und zum NULL-Zeiger. Weitere Informationen finden Sie unter [Standardkonvertierungen](../cpp/standard-conversions.md). Benutzerdefinierte Konvertierungen konvertieren zwischen benutzerdefinierten Typen oder zwischen benutzerdefinierten Typen und integrierten Typen. Sie können diese als implementieren [konvertierungskonstruktoren](#ConvCTOR) oder als [Konvertierungsfunktionen](#ConvFunc).  
  
 Konvertierungen können entweder explizit sein—wenn ein Programmierer einen Typen z. B. durch eine Umwandlung oder direkte Initialisierung in einen anderen Typen konvertiert—oder implizit—wenn die Sprache oder das Programm einen anderen Typen als den vom Programmierer angegeben verlangt.  
  
 Implizite Konvertierungen werden in den folgenden Fällen ausgeführt:  
  
-   Wenn ein Argument einer Funktion nicht vom gleichen Typ ist wie der entsprechende Parameter.  
  
-   Wenn ein Rückgabewert einer Funktion nicht vom gleichen Typ ist wie der Rückgabetyp der Funktion.  
  
-   Wenn ein Initialisiererausdruck nicht vom gleichen Typ ist wie das initialisierte Objekt.  
  
-   Wenn ein Ausdruck, der eine Bedingungsanweisung, ein Schleifenkonstrukt oder einen Switch kontrolliert, nicht den richtigen Ergebnistyp für diese Kontrolle hat.  
  
-   Wenn ein an einen Operator übergebener Operand nicht vom gleichen Typ ist wie der entsprechende Operand-Parameter. Für integrierte Operatoren müssen beide Operanden vom gleichen Typ sein und werden in einen gemeinsamen Typen konvertiert, der beide Operanden darstellen kann. Weitere Informationen finden Sie unter [Standardkonvertierungen](standard-conversions.md). Für benutzerdefinierte Operatoren müssen alle Operanden vom gleichen Typ sein wie der entsprechende Operand-Parameter.  
  
 Wenn eine Standardkonvertierung eine implizite Konvertierung nicht ausführen kann, kann der Compiler eine benutzerdefinierte Konvertierung verwenden, optional gefolgt von einer zusätzlichen Standardkonvertierung zur Vervollständigung.  
  
 Wenn zwei oder mehrere benutzerdefinierte Konvertierungen mit derselben Konvertierung an einem Konvertierungsort verfügbar sind, wird die Konvertierung auch als "Mehrdeutig" bezeichnet. Solche Mehrdeutigkeiten führen zu einem Fehler, da der Compiler nicht ermitteln kann, welche der verfügbaren Konvertierungen ausgeführt werden soll. Die Definition mehrerer Wege für dieselbe Konvertierung ist jedoch nicht zwangsläufig ein Fehler, da sich die Konvertierungen an unterschiedlichen Stellen im Quellcode befinden können, z. B. in Abhängigkeit von den Headerdateien der jeweiligen Quelldatei. Sofern an jedem Konvertierungsort nur eine Konvertierung verfügbar ist, liegt keine Mehrdeutigkeit vor. Mehrdeutige Konvertierungen können auf verschiedene Arten entstehen. Die gängigsten Arten sind:  
  
-   Mehrfachvererbung. Die Konvertierung ist in mehr als einer Basisklasse definiert. 
  
-   Mehrdeutige Funktionsaufrufe. Die Konvertierung ist gleichzeitig als Konvertierungskonstruktor des Zieltyps und als Konvertierungsfunktion des Quelltyps definiert. Weitere Informationen finden Sie unter [Konvertierungsfunktionen](#ConvFunc).  
  
 Mehrdeutigkeiten können normalerweise aufgelöst werden, in dem der Name des betreffenden Typs vollständiger angegeben wird, oder durch eine explizite Umwandlung zur Klarstellung Ihrer Absicht.  
  
 Sowohl Konvertierungskonstruktoren als auch Konvertierungsfunktionen folgen den Regeln für die Memberzugriffssteuerung. Die Zugänglichkeit der Konvertierungen wird jedoch nur berücksichtigt, wenn eine eindeutige Konvertierung ermittelt werden kann. Eine Konvertierung kann also auch dann mehrdeutig sein, wenn die Zugriffsebene einer konkurrierenden Konvertierung deren Ausführung verhindern würde. Weitere Informationen zu Memberzugriff, finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md).  
  
## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>Das Schlüsselwort explicit und Probleme mit impliziter Konvertierung  
 Wenn Sie eine benutzerdefinierte Konvertierung erstellen, kann der Compiler diese standardmäßig für implizite Konvertierungen verwenden. Manchmal ist dies erwünscht, aber in anderen Fällen können die einfachen Regeln des Compilers für implizite Konvertierungen dazu führen, dass dieser unerwünschten Code akzeptiert.  
  
 Ein bekanntes Beispiel für eine problematische implizite Konvertierung ist die Konvertierung nach `bool`. Es gibt zahlreiche Gründe für die Erstellung eines Klassentyps, der in einem Boolean-Kontext verwendet werden kann—z. B. zur Steuerung einer `if`-Anweisung oder einer Schleife—aber wenn der Compiler eine benutzerdefinierte Konvertierung zu einem integrierten Typ ausführt, kann es passieren, dass im Anschluss eine zusätzliche Standardkonvertierung ausgeführt wird. Mit dieser zusätzlichen Standardkonvertierung wird z. B. die Heraufstufung von `short` zu `int` ermöglicht. Allerdings wird auch die Tür für weniger offensichtliche Konvertierungen geöffnet—z. B. von `bool` zu `int`, wodurch Ihr Klassentyp in integer-Kontexten verwendet werden kann, die nie beabsichtigt waren. Dieses Problem ist bekannt als die *Safe Bool Problem*. Bei dieser Art von Problemen hilft das Schlüsselwort `explicit`.  
  
 Das Schlüsselwort `explicit` teilt dem Compiler mit, dass die angegebene Konvertierung nicht zur Ausführung impliziter Konvertierungen verwendet werden darf. Vor der Einführung des Schlüsselworts `explicit` mussten Sie entweder die unbeabsichtigten möglichen Konsequenzen impliziter Konvertierungen in Kauf nehmen oder weniger praktische, benannte Konvertierungsfunktionen als Umgehung verwenden, um die praktische Syntax impliziter Konvertierungen nutzen zu können. Mit dem Schlüsselwort `explicit` können Sie nun praktische Konvertierungen erstellen, die nur für explizite Umwandlungen oder direkte Initialisierung verwendet werden können und die nicht zu der Art von Problemen führen, die durch das Safe Bool Problem exemplarisch beschrieben wurden.  
  
 Das Schlüsselwort `explicit` kann seit C++98 für Konvertierungskonstruktoren und seit C++11 für Konvertierungsfunktionen verwendet werden. Die folgenden Abschnitte enthalten weitere Informationen zur Verwendung des Schlüsselworts `explicit`.  
  
##  <a name="ConvCTOR"></a>Konvertierungskonstruktoren  
 Konvertierungskonstruktoren definieren Konvertierungen von benutzerdefinierten oder integrierten Typen zu einem benutzerdefinierten Typ. Das folgende Beispiel zeigt einen Konvertierungskonstruktor, der vom integrierten Typ `double` zum benutzerdefinierten Typ `Money` konvertiert.  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    Money(double _amount) : amount{ _amount } {};  
  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << balance.amount << std::endl;  
}  
  
int main(int argc, char* argv[])  
{  
    Money payable{ 79.99 };  
  
    display_balance(payable);  
    display_balance(49.95);  
    display_balance(9.99f);  
  
    return 0;  
}  
```  
  
 Beachten Sie, dass der erste Aufruf der Funktion `display_balance`, die ein Argument vom Typ `Money` entgegennimmt, keine Konvertierung erfordert, da das Argument bereits vom korrekten Typ ist. Allerdings beim zweiten Aufruf von `display_balance`, eine Konvertierung ist erforderlich, da der Typ des Arguments, eine `double` mit einem Wert von `49.95`, nicht was die Funktion erwartet. Die Funktion kann diesen Wert nicht direkt verwenden. Da jedoch eine Konvertierung vom Typ des Arguments—`double`—zum Typ des passenden Parameters—`Money`—existiert, wird ein temporärer Wert vom Typ `Money` aus dem Argument erstellt und für den Funktionsaufruf verwendet. Im dritten Aufruf `display_balance`, beachten Sie, dass das Argument keine `double`, sondern eine `float` mit einem Wert von `9.99`– und noch der Funktionsaufruf kann immer noch abgeschlossen werden, da der Compiler eine standardkonvertierung ausführen kann – in diesem Fall , aus `float` auf `double`– und führen Sie dann die benutzerdefinierte Konvertierung von `double` zu `Money` um die erforderliche Konvertierung abzuschließen.  
  
### <a name="declaring-conversion-constructors"></a>Deklarieren von Konvertierungskonstruktoren  
 Beim Deklarieren von Konvertierungskonstruktoren gelten die folgenden Regeln:  
  
-   Der Zieltyp der Konvertierung ist der benutzerdefinierte Typ, der konstruiert wird.  
  
-   Konvertierungskonstruktoren erwarten normalerweise genau ein Argument, das vom Quelltyp ist. Konvertierungskonstruktoren können jedoch zusätzliche Parameter definieren, wenn jeder dieser zusätzlichen Parameter einen Standardwert hat. Der Quelltyp ist weiterhin der Typ des ersten Parameters.  
  
-   Konvertierungskonstruktoren definieren wie auch alle anderen Konstruktoren keinen Rückgabetyp. Die Angabe eines Rückgabetyps bei der Deklaration führt zu einem Fehler.  
  
-   Konvertierungskonstruktoren können explizit sein.  
  
### <a name="explicit-conversion-constructors"></a>Explizite Konvertierungskonstruktoren  
 Wenn Sie einen Konvertierungskonstruktor als `explicit` deklarieren, kann dieser nur für die direkte Initialisierung von Objekten oder zum Ausführen expliziter Umwandlungen verwendet werden. Damit wird verhindert, dass Funktionen, die ein Argument vom Klassentyp erwarten, ebenfalls implizit Argument vom Quelltyp des Konvertierungskonstruktors akzeptieren. Außerdem wird verhindert, dass der Klassentyp aus einem Wert des Quelltyps durch Kopieren initialisiert wird. Das folgende Beispiel zeigt die Definition eines expliziten Konvertierungskonstruktors und dessen Auswirkungen auf die Wohlgeformtheit des Codes.  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    explicit Money(double _amount) : amount{ _amount } {};  
  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << balance.amount << std::endl;  
}  
  
int main(int argc, char* argv[])  
{  
    Money payable{ 79.99 };        // Legal: direct initialization is explicit.  
  
    display_balance(payable);      // Legal: no conversion required  
    display_balance(49.95);        // Error: no suitable conversion exists to convert from double to Money.  
    display_balance((Money)9.99f); // Legal: explicit cast to Money  
  
    return 0;  
}  
```  
  
 In diesem Beispiel können Sie den expliziten Konvertierungskonstruktor weiterhin für die direkte Initialisierung von `payable` verwenden. Falls Sie jedoch `Money payable = 79.99;` durch Kopieren initialisieren, erhalten Sie einen Fehler. Der erste Aufruf von `display_balance` ist nicht betroffen, da das Argument vom korrekten Typ ist. Der zweite Aufruf von `display_balance` führt zu einem Fehler, da der Konvertierungskonstruktor nicht für implizite Konvertierungen verwendet werden kann. Der dritte Aufruf von `display_balance` ist korrekt dank der expliziten Umwandlung nach `Money`. Der Compiler hat die Umwandlung allerdings dennoch durch eine implizite Umwandlung von `float` zu `double` unterstützt.  
  
 Obwohl die Vorzüge impliziter Konvertierungen verlockend sind, können diese zu schwer auffindbaren Bugs führen. Als Standardregel sollten alle Konvertierungskonstruktoren explizit sein, es sei denn, Sie möchten eine bestimmte Konvertierung implizit erlauben.  
  
##  <a name="ConvFunc"></a>Konvertierungsfunktionen  
 Konvertierungsfunktionen definieren Konvertierungen von einem benutzerdefinierten Typ zu anderen Typen. Diese Funktionen werden manchmal auch als "Umwandlungsoperatoren" bezeichnet, da sie zusammen mit Konvertierungskonstruktoren aufgerufen werden, wenn ein Wert zu einem anderen Typ umgewandelt wird. Das folgende Beispiel zeigt eine Konvertierungsfunktion, die vom benutzerdefinierten Typ `Money` zum integrierten Typ `double` konvertiert:  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    Money(double _amount) : amount{ _amount } {};  
  
    operator double() const { return amount; }  
private:  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << balance << std::endl;  
}  
  
```  
  
 Beachten Sie, dass die Membervariable `amount` privat ist und dass eine öffentliche Konvertierungsfunktion zum Typ `double` eingeführt wird, nur um den Wert von `amount` zurückzugeben. In der Funktion `display_balance` erfolgt eine implizite Konvertierung, wenn der Wert von `balance` durch den Operator zum Einfügen des Datenstroms `<<` in die Standardausgabe geschrieben wird. Für den benutzerdefinierten Typ `Money` ist kein Operator zum Einfügen des Datenstroms definiert. Da jedoch ein solcher Operator für den integrierten Typ `double` existiert, kann der Compiler die Konvertierungsfunktion von `Money` zu `double` verwenden, um den Operator zum Einfügen des Datenstroms zu erfüllen.  
  
 Konvertierungsfunktionen werden an abgeleitete Klassen vererbt. Konvertierungsfunktionen in abgeleiteten Klassen überschreiben geerbte Konvertierungsfunktionen nur dann, wenn diese zum exakt gleichen Typ konvertieren. Eine benutzerdefinierte Konvertierungsfunktion der abgeleiteten Klasse `operator int` überschreibt—bzw. beeinflusst—eine benutzerdefinierte Konvertierungsfunktion der Basisklasse `operator short` nicht, obwohl die Standardkonvertierungen eine Konvertierungsbeziehung zwischen `int` und `short` definieren.  
  
### <a name="declaring-conversion-functions"></a>Deklarieren von Konvertierungsfunktionen  
 Beim Deklarieren von Konvertierungsfunktionen gelten die folgenden Regeln:  
  
-   Der Zieltyp der Konvertierung muss vor der Deklaration der Konvertierungsfunktion deklariert werden. Klassen, Strukturen, Enumerationen und typedefs können nicht innerhalb der Deklaration der Konvertierungsfunktion deklariert werden.  
  
    ```  
    operator struct String { char string_storage; }() // illegal  
    ```  
  
-   Konvertierungsfunktionen akzeptieren keine Argumente. Die Angabe von Parametern bei der Deklaration führt zu einem Fehler.  
  
-   Der Rückgabetyp einer Konvertierungsfunktion wird durch deren Namen festgelegt, der gleichzeitig der Name des Zieltyps der Konvertierung ist. Die Angabe eines Rückgabetyps bei der Deklaration führt zu einem Fehler.  
  
-   Konvertierungsfunktionen können virtual sein.  
  
-   Konvertierungsfunktionen können explizit sein.  
  
### <a name="explicit-conversion-functions"></a>Explizite Konvertierungsfunktionen  
 Wenn eine Konvertierungsfunktion als explizit deklariert wird, kann diese nur für explizite Umwandlungen verwendet werden. Damit wird verhindert, dass Funktionen, die ein Argument vom Zieltyp der Konvertierungsfunktion erwarten, ebenfalls implizit Argument vom Klassentyp akzeptieren. Außerdem wird verhindert, dass Instanzen des Zieltyps aus einem Wert des Klassentyps durch Kopieren initialisiert werden. Das folgende Beispiel zeigt die Definition einer expliziten Konvertierungsfunktion und deren Auswirkungen auf die Wohlgeformtheit des Codes.  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    Money(double _amount) : amount{ _amount } {};  
  
    explicit operator double() const { return amount; }  
private:  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << (double)balance << std::endl;  
}  
  
```  
  
 Die Konvertierungsfunktion `operator double` ist in diesem Fall explizit, und eine explizite Umwandlung zum Typ `double` wurde in der Funktion `display_balance` für die Ausführung der Konvertierung eingefügt. Ohne diese Umwandlung wäre der Compiler nicht in der Lage, den geeigneten Operator zum Einfügen des Datenstroms `<<` für den Typ `Money` zu ermitteln, und ein Fehler wäre die Folge.  
  

