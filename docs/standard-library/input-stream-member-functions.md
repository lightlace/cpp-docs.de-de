---
title: Eingabestream-Memberfunktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f9fb195bfb5e6e35d035ba5a3660bb91644a04ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="input-stream-member-functions"></a>Eingabestream-Memberfunktionen
Eingabestream-Memberfunktionen werden für Datenträgereingaben verwendet. Diese Memberfunktionen umfassen:  
  
- [Die open-Funktion für die Eingabestreams](#vclrftheopenfunctionforinputstreamsanchor11)  
  
- [Die get](#vclrfthegetfunctionanchor12)  
  
- [Die getline](#vclrfthegetlinefunctionanchor13)  
  
- [Die schreibgeschützte](#vclrfthereadfunctionanchor14)  
  
- [Die seekg- und tellg-Funktionen](#vclrftheseekgandtellgfunctionsanchor7)  
  
- [Die clos-Funktion für Eingabestreams](#vclrftheclosefunctionforinputstreamsanchor15)  
  
##  <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Die open-Funktion für Eingabestreams  
 Wenn Sie einen Eingabedateistream (ifstream) verwenden, müssen Sie den Stream einer bestimmten Datenträgerdatei zuordnen. Sie können das im Konstruktor machen, oder die **open**-Funktion verwenden. In beiden Fällen sind die Argumente gleich.  
  
 In der Regel geben Sie ein [ios_base:: openmode](../standard-library/ios-base-class.md#openmode)-Flag an, wenn Sie die Datei öffnen, die einem Eingabestream (der Standardmodus ist **ios::in**) zugeordnet ist. Eine Liste der **Open_mode** Flags finden Sie unter [öffnen](#vclrftheopenfunctionforinputstreamsanchor11). Die Flags können mit dem bitweisen OR-Operator ( &#124; ) kombiniert werden.  
  
 Um eine Datei zu lesen, verwenden Sie zuerst die **fail**-Memberfunktion, um zu bestimmen, ob sie vorhanden ist:  
  
```  
istream ifile("FILENAME");

if (ifile.fail())  
// The file does not exist ...  
```  
  
##  <a name="vclrfthegetfunctionanchor12"></a>Die get
 Die unformatierte **get**-Memberfunktion funktioniert wie der **>>**-Operator, mit zwei Ausnahmen. Erstens enthält die **get**-Funktion Leerzeichen, wohingegen der Extraktor Leerzeichen ausschließt, wenn das **skipws**-Flag festgelegt ist (Standardwert). Zweitens wird die **get**-Funktion weniger wahrscheinlich dazu führen, dass ein gebundener Ausgabestream (z.B. `cout`) gelöscht wird.  
  
 Eine Variante der **get**-Funktion gibt eine Pufferadresse und die maximale Anzahl zu lesender Zeichen an. Dies hilft dabei, die Anzahl der Zeichen einzuschränken, die zu einer bestimmten Variable gesendet werden, wie dieses Beispiel zeigt:  
  
```  
// ioo_get_function.cpp  
// compile with: /EHsc  
// Type up to 24 characters and a terminating character.   
// Any remaining characters can be extracted later.  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   char line[25];  
   cout << " Type a line terminated by carriage return\n>";  
   cin.get( line, 25 );  
   cout << line << endl;  
}  
```  
  
### <a name="input"></a>Eingabe  
  
```  
1234  
```  
  
### <a name="sample-output"></a>Beispielausgabe  
  
```  
1234  
```  
  
##  <a name="vclrfthegetlinefunctionanchor13"></a>Die getline
 Die **getline**-Memberfunktion ähnelt der **get**-Funktion. Beide Funktionen ermöglichen ein drittes Argument, das abschließende Zeichen für die Eingabe angibt. Der Standardwert ist das Zeilenumbruchzeichen. Beide Funktionen reservieren ein Zeichen für das benötigte abschließende Zeichen. Allerdings lässt **get** das abschließende Zeichen im Stream und **getline** entfernt das abschließende Zeichen.  
  
 Im folgenden Beispiel wird ein abschließendes Zeichen für den Eingabestream angegeben:  
  
```  
// getline_func.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char line[100];  
   cout << " Type a line terminated by 't'" << endl;  
   cin.getline( line, 100, 't' );  
   cout << line;  
}  
```  
  
### <a name="input"></a>Eingabe  
  
```  
test  
```  
  
##  <a name="vclrfthereadfunctionanchor14"></a>Die schreibgeschützte
 Die **read**-Memberfunktion liest Bytes aus einer Datei in einem angegebenen Speicherbereich. Das Längenargument bestimmt die Anzahl gelesener Bytes. Wenn Sie dieses Argument nicht einfügen, wird das Lesen beendet, sobald das physische Ende der Datei erreicht ist, oder, bei einer Textmodusdatei, wenn ein eingebettetes `EOF`-Zeichen gelesen wird.  
  
 Dieses Beispiel liest einen binären Datensatz aus einer Lohnabrechnungsdatei in eine Struktur:  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   struct  
   {  
      double salary;  
      char name[23];  
   } employee;  
  
   ifstream is( "payroll" );  
   if( is ) {  // ios::operator void*()  
      is.read( (char *) &employee, sizeof( employee ) );  
      cout << employee.name << ' ' << employee.salary << endl;  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 Das Programm setzt voraus, dass die Datensätze formatiert sind, genau wie durch die Struktur ohne abschließendes Wagenrücklauf- oder Zeilenvorschubzeichen angegeben.  
  
##  <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Die seekg- und tellg-Funktionen  
 Eingabedatei-Streams behalten einen internen Zeiger auf der Position in der Datei, in der Daten als Nächstes gelesen werden. Legen Sie diesen Zeiger mit der `seekg`-Funktion fest, wie hier gezeigt:  
  
```  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)  
      while ( tfile.good() ) { // EOF or failure stops the reading  
         tfile.get( ch );  
         if( !ch ) break;      // quit on null  
         cout << ch;  
      }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 Um `seekg` zu verwenden, damit datensatzorientierte Datenverwaltungssysteme implementiert werden, multiplizieren Sie die Datensatzgröße mit fester Länge durch die Datensatznummer zum Abrufen der Byte-Position relativ zum Ende der Datei, und verwenden Sie anschließend das **get**-Objekt zum Lesen des Datensatzes.  
  
 Die `tellg`-Memberfunktion gibt die aktuelle Dateiposition zum Lesen zurück. Dieser Wert ist vom Typ `streampos`, ein `typedef` in \<iostream > definierter Wert. Das folgende Beispiel liest eine Datei und zeigt Meldungen an, die die Positionen der Leerzeichen zeigen.  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
       while ( tfile.good( ) ) {  
          streampos here = tfile.tellg();  
          tfile.get( ch );  
          if ( ch == ' ' )  
             cout << "\nPosition " << here << " is a space";  
       }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
##  <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> Die close-Funktion für Eingabestreams  
 Die **close**-Memberfunktion schließt die Datenträgerdatei, die einem Eingabedateistream zugeordnet ist, und gibt ein Betriebssystem-Dateihandle frei. Der [ifstream](../standard-library/basic-ifstream-class.md)-Destruktor schließt die Datei für Sie, aber Sie können die **close**-Funktion verwenden, wenn Sie eine andere Datei für das gleiche Streamobjekt öffnen müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)

