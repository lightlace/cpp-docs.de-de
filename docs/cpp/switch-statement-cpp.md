---
title: Switch-Anweisung (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
dev_langs:
- C++
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: 7
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
ms.openlocfilehash: 5e05299d88cadfafb9ccb7523aac33096b90d46b
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="switch-statement-c"></a>switch-Anweisung (C++)
Ermöglicht die Auswahl von mehreren Codeabschnitten, abhängig vom Wert eines ganzzahligen Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```  
   switch ( init; expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die *Ausdruck* muss ein ganzzahliger Typ oder von einem Klassentyp sein, die für die eine eindeutige Konvertierung in ganzzahligen Typ vorhanden ist. Ganzzahlige Erweiterung wird ausgeführt, wie in beschrieben [Standardkonvertierungen](standard-conversions.md).  
  
 Die `switch` -Anweisungstext besteht aus einer Reihe von **Fall** Bezeichnungen sowie ein optionales **Standard** Bezeichnung. Keine zwei Konstante Ausdrücke in **Fall** Anweisungen können auf den gleichen Wert ausgewertet. Die **Standard** Bezeichnung kann nur einmal vorkommen. Die bezeichneten Anweisungen sind für die Syntax nicht erforderlich, aber die Anweisung `switch` ist ohne sie bedeutungslos.   Die default-Anweisung muss nicht am Ende stehen. Sie kann überall im Text der switch-Anweisung vorkommen. Eine case- oder default-Bezeichnung kann nur innerhalb einer switch-Anweisung angezeigt werden.  
  
 Die *Konstantenausdruck* in jedem **Fall** Bezeichnung wird in den Typ des konvertiert *Ausdruck* und im Vergleich zu *Ausdruck* für auf Gleichheit. Die Steuerung an die Anweisung, deren **Fall** *Konstantenausdruck* entspricht dem Wert *Ausdruck*. Der resultierende Verhalten wird in der folgenden Tabelle gezeigt.  
  
### <a name="switch-statement-behavior"></a>Verhalten der switch-Anweisung  
  
|Bedingung|Aktion|  
|---------------|------------|  
|Der konvertierte Wert stimmt mit dem des hochgestuften steuernden Ausdrucks überein.|Die Steuerung wird an die Anweisung übertragen, die auf die Bezeichnug folgt.|  
|Keine der Konstanten entspricht den Konstanten in der **Fall** Bezeichnungen; eine **Standard** Bezeichnung vorhanden ist.|Die Steuerung an die **Standard** Bezeichnung.|  
|Keine der Konstanten entspricht den Konstanten in der **Fall** Bezeichnungen. **Standard** -Bezeichnung ist nicht vorhanden.|Nachdem die `switch`-Anweisung ausgeführt wurde, wird die Steuerung an die Anweisung übergeben.|  
  
 Wenn ein entsprechender Ausdruck gefunden wird, ist Steuerelement nicht von nachfolgenden behindert **Fall** oder **Standard** Bezeichnungen. Die [Break](../cpp/break-statement-cpp.md) Anweisung wird verwendet, um die Ausführung beendet und die Übertragung der Steuerung der Anweisung nach der `switch` Anweisung. Ohne eine **Break** -Anweisung wird jede Anweisung von der entsprechenden **Fall** -Bezeichnung bis zum Ende des der `switch`, einschließlich der **Standard**, ausgeführt wird. Zum Beispiel:  
  
```  
// switch_statement1.cpp  
#include <stdio.h>  
  
int main() {  
   char *buffer = "Any character stream";  
   int capa, lettera, nota;  
   char c;  
   capa = lettera = nota = 0;  
  
   while ( c = *buffer++ )   // Walks buffer until NULL  
   {  
      switch ( c )  
      {  
         case 'A':  
            capa++;  
            break;  
         case 'a':  
            lettera++;  
            break;  
         default:  
            nota++;  
      }  
   }  
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",  
      capa, lettera, (capa + lettera + nota) );  
}  
```  
  
 Im obigen Beispiel wird `capa` inkrementiert, wenn `c` ein groß geschriebenes `A` ist. Die `break`-Anweisung nach `capa++` beendet die Ausführung des `switch`-Anweisungstexts und übergibt an die `while`-Schleife. Ohne die `break` -Anweisung Ausführung würde "globalere" die nächste bezeichnete Anweisung, damit `lettera` und `nota` ebenfalls erhöht. Einen ähnlichen Zweck erfüllt die `break`-Anweisung für `case 'a'`. Wenn `c` ein klein geschriebenes `a` ist, wird `lettera` erhöht, und die `break`-Anweisung beendet den `switch`-Anweisungstext. Wenn `c` nicht `a` oder `A` ist, wird die `default`-Anweisung ausgeführt.  

 **Visual Studio 2017 und höher:** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)) die `[[fallthrough]]` -Attribut im C ++ 17-standard angegeben ist. Kann verwendet werden, eine `switch` Anweisung als Hinweis für den Compiler (oder für Personen, die beim Lesen des Codes) richtet sich dieses Verhalten fallen durch. Visual C++-Compiler warnt derzeit nicht auf Fallthrough Verhalten, damit dieses Attribut keine Compilerverhalten Auswirkungen hat. Beachten Sie, dass das Attribut auf eine leere Anweisung innerhalb der Anweisung mit Bezeichnung angewendet wird. mit anderen Worten ist das Semikolon erforderlich.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

 **Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): eine Switch-Anweisung kann einführen und initialisieren Sie eine Variable, deren Bereich auf den Block der Switch-Anweisung beschränkt ist:

```cpp
 switch (Gadget gadget(args); auto s = gadget.get_status())
        {
        case status::good:
            gadget.zip();
            break;
        case status::bad:
            throw BadGadget();
        };
```

 Ein innerer Block einer `switch`-Anweisung kann Definitionen mit Initialisierungen enthalten, solange sie erreichbar sind, d. h. nicht von allen möglichen Ausführungspfaden umgangen. Namen, die mit diesen Deklarationen eingeführt werden, weisen einen lokalen Gültigkeitsbereich auf. Zum Beispiel:  
  
```cpp  
// switch_statement2.cpp  
// C2360 expected  
#include <iostream>  
using namespace std;  
int main(int argc, char *argv[])  
{  
   switch( tolower( *argv[1] ) )  
   {  
       // Error. Unreachable declaration.  
       char szChEntered[] = "Character entered was: ";  
  
   case 'a' :  
       {  
       // Declaration of szChEntered OK. Local scope.  
       char szChEntered[] = "Character entered was: ";  
       cout << szChEntered << "a\n";  
       }  
       break;  
  
   case 'b' :  
       // Value of szChEntered undefined.  
       cout << szChEntered << "b\n";  
       break;  
  
   default:  
       // Value of szChEntered undefined.  
       cout << szChEntered << "neither a nor b\n";  
       break;  
   }  
}  
```  
  
 Eine `switch` Anweisung kann geschachtelt sein. In solchen Fällen **Fall** oder **Standard** zuordnen Bezeichnungen mit der nächsten `switch` -Anweisung, die sie umschließt.  

 
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 In Microsoft C wird die Anzahl von case-Werten in einer `switch`-Anweisung nicht beschränkt. Die Anzahl wird nur durch den verfügbaren Speicher beschränkt. ANSI C erfordert, dass mindestens 257 case-Abschnitte in einer `switch`-Anweisung zulässig sind.  
  
 Bei Microsoft C sind die Microsoft-Erweiterungen standardmäßig aktiviert. Verwenden der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) Compileroption, um diese Erweiterungen zu deaktivieren.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)   
 
