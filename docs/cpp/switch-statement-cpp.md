---
title: "switch-Anweisung (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "default"
  - "default_cpp"
  - "switch"
  - "switch_cpp"
  - "case"
  - "case_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case-Schlüsselwort [C++], In switch-Anweisungen"
  - "default-Schlüsselwort [C++]"
  - "switch-Schlüsselwort [C++]"
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# switch-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die Auswahl von mehreren Codeabschnitten, abhängig vom Wert eines ganzzahligen Ausdrucks.  
  
## Syntax  
  
```  
  
      switch ( expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## Hinweise  
 Der *Ausdruck* muss einen integralen Typ aufweisen oder einen Klassentyp, für den eine eindeutige Konvertierung in einen integralen Typ möglich ist.  Ganzzahlige Erweiterung wird wie in [Ganzzahlige Erweiterungen](../misc/integral-promotions.md) beschrieben ausgeführt.  
  
 Der `switch`\-Anweisungstext besteht aus einer Reihe von der **case**\-Bezeichnungen und einer optionalen **default**\-Bezeichnung.  Es können nicht zwei konstante Ausdrücke in **case**\-Anweisungen zum gleichen Wert ausgewertet werden.  Die Bezeichnung **default** kann nur einmal vorkommen.  Die bezeichneten Anweisungen sind für die Syntax nicht erforderlich, aber die Anweisung `switch` ist ohne sie bedeutungslos.   Die default\-Anweisung muss nicht am Ende stehen. Sie kann überall im Text der switch\-Anweisung vorkommen.  Eine case\- oder default\-Bezeichnung kann nur innerhalb einer switch\-Anweisung angezeigt werden.  
  
 Der *Konstantenausdruck* in jeder **case**\-Bezeichnung wird in den Typ des *Ausdrucks* konvertiert und mit *Ausdruck* hinsichtlich ihrer Gleichheit überprüft.  Das Steuerelement wird an die Anweisung übergeben, deren **case***Konstantenausdruck* dem Wert des *Ausdrucks* entspricht.  Der resultierende Verhalten wird in der folgenden Tabelle gezeigt.  
  
### Verhalten der switch\-Anweisung  
  
|Bedingung|Aktion|  
|---------------|------------|  
|Der konvertierte Wert stimmt mit dem des hochgestuften steuernden Ausdrucks überein.|Die Steuerung wird an die Anweisung übertragen, die auf die Bezeichnug folgt.|  
|Keine der Konstanten entspricht den Konstanten in den **case**\-Bezeichnungen. Eine **default**\-Bezeichnung ist vorhanden.|Die Steuerung wird an die **default**\-Bezeichnung übertragen.|  
|Keine der Konstanten entspricht den Konstanten in den **case**\-Bezeichnungen. Eine **default**\-Bezeichnung ist nicht vorhanden.|Nachdem die `switch`\-Anweisung ausgeführt wurde, wird die Steuerung an die Anweisung übergeben.|  
  
 Wenn ein entsprechender Ausdruck gefunden wird, wird die Steuerung nicht von nachfolgenden **case**\- oder **default**\-Bezeichnungen beeinflusst.  Die [break](../cpp/break-statement-cpp.md)\-Anweisung wird verwendet, um die Ausführung der Anweisung und die Übertragung der Steuerung nach der `switch`\-Anweisung zu beenden.  Ohne eine **break**\-Anweisung wird jede Anweisung von der gefundenen **case**\-Bezeichnung bis zum Ende von `switch` \(einschließlich **default**\) ausgeführt.  Beispiel:  
  
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
  
 Im obigen Beispiel wird `capa` inkrementiert, wenn `c` ein groß geschriebenes `A` ist.  Die `break`\-Anweisung nach `capa++` beendet die Ausführung des `switch`\-Anweisungstexts und übergibt an die `while`\-Schleife.  Ohne die `break`\-Anweisung würden `lettera` und `nota` ebenfalls erhöht.  Einen ähnlichen Zweck erfüllt die `break`\-Anweisung für `case 'a'`.  Wenn `c` ein klein geschriebenes `a` ist, wird `lettera` erhöht, und die `break`\-Anweisung beendet den `switch`\-Anweisungstext.  Wenn `c` nicht `a` oder `A` ist, wird die `default`\-Anweisung ausgeführt.  
  
 Ein innerer Block einer `switch`\-Anweisung kann Definitionen mit Initialisierungen enthalten, solange sie erreichbar sind, d. h. nicht von allen möglichen Ausführungspfaden umgangen.  Namen, die mit diesen Deklarationen eingeführt werden, weisen einen lokalen Gültigkeitsbereich auf.  Beispiel:  
  
```  
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
  
 Eine `switch` Anweisung kann geschachtelt sein.  In solchen Fällen werden die Bezeichnungen **case** oder **default** der nächsten `switch`\-Anweisung zugeordnet, die sie umschließt.  
  
## Microsoft\-spezifisch  
 In Microsoft C wird die Anzahl von case\-Werten in einer `switch`\-Anweisung nicht beschränkt.  Die Anzahl wird nur durch den verfügbaren Speicher beschränkt.  ANSI C erfordert, dass mindestens 257 case\-Abschnitte in einer `switch`\-Anweisung zulässig sind.  
  
 Bei Microsoft C sind die Microsoft\-Erweiterungen standardmäßig aktiviert.  Verwenden Sie die [\/Za](../build/reference/za-ze-disable-language-extensions.md)\-Compileroption, um diese Erweiterungen zu deaktivieren.  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) Using Labels in the case Statement](assetId:///a6ff057d-1aee-42ed-a28d-ee6a565b3197)