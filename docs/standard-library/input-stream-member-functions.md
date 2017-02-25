---
title: "Eingabestream-Memberfunktionen | Microsoft Docs"
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
  - "Eingabestreamobjekte"
  - "Eingabestreams, Memberfunktionen"
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Eingabestream-Memberfunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eingabestreammemberfunktionen werden für Datenträgereingabe verwendet.  Das Memberfunktionseinschließung:  
  
-   [Die geöffnete Funktion für Eingabestreams](#vclrftheopenfunctionforinputstreamsanchor11)  
  
-   [Die Version Funktion](#vclrfthegetfunctionanchor12)  
  
-   [Die getline Funktion](#vclrfthegetlinefunctionanchor13)  
  
-   [Die Lesenfunktion](#vclrfthereadfunctionanchor14)  
  
-   [Die seekg und tellg Funktionen](#vclrftheseekgandtellgfunctionsanchor7)  
  
-   [Die Funktion für Eingabestreams neben](#vclrftheclosefunctionforinputstreamsanchor15)  
  
##  <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Die geöffnete Funktion für Eingabestreams  
 Wenn Sie einen Eingabedateistream \(ifstream\) verwenden, müssen Sie den Stream mit einer bestimmten Datenträgerdatei zuordnen.  Sie können dies im Konstruktor ausführen, oder Sie können die Funktion **open** verwenden.  In beiden Fällen sind die Argumente identisch.  
  
 Sie geben normalerweise einem [ios\_base::openmode](../Topic/ios_base::openmode.md)\-Flag an, wenn Sie die Datei öffnen, die mit einem Eingabestream zugeordnet ist \(Standardmodus\) ist **ios::in**.  Eine Liste der **open\_mode**\-Flags, finden Sie unter [Die geöffnete Funktion](#vclrftheopenfunctionforinputstreamsanchor11).  Die Flags können mit dem bitweisen kombiniert werden OR \( &#124; Operator.\)  
  
 Um eine Datei lesen, zuerst die **Fehler**\-Memberfunktion, zu bestimmen, ob sie vorhanden ist:  
  
```  
istream ifile( "FILENAME" );  
if ( ifile.fail() )  
// The file does not exist ...  
```  
  
##  <a name="vclrfthegetfunctionanchor12"></a> Die Version Funktion  
 Der unformatierte **abrufen**\-Memberfunktion funktioniert wie der Operator **\>\>** mit zwei Ausnahmen.  enthält zunächst die **abrufen**\-Funktion Leerzeichen, während das Extraktionsprogramm Leerzeichen ausschließt, wenn das [skipws](../Topic/skipws.md)\-Flag festgelegt ist \(Standard\).  Zweitens ist die **abrufen**\-Funktion weniger wahrscheinlich, einen gebundenen Ausgabestream \(`cout`\), zu bewirken geleert werden.  
  
 Eine Variante der **abrufen**\-Funktion gibt eine Pufferadresse und die maximale Anzahl der zu lesenden Zeichen an.  Dies ist zum Einschränken der Anzahl von Zeichen an, die auf eine bestimmte Variable gesendet werden, da dieses Beispiel zeigt:  
  
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
  
### Eingabe  
  
```  
1234  
```  
  
### Beispielausgabe  
  
```  
1234  
```  
  
##  <a name="vclrfthegetlinefunctionanchor13"></a> Die getline Funktion  
 Die **getline**\-Memberfunktion ist der **abrufen**\-Funktion ähnelt.  Beide Funktionen ermöglichen ein drittes Argument, das das Endzeichen für Eingaben angibt.  Der Standardwert ist das Zeilenumbruchzeichen.  Beide Funktionen reserviert einem Zeichen für das erforderliche und Endzeichen.  Allerdings schlägt **abrufen** das Endzeichen im Stream und **getline** entfernt das Endzeichen.  
  
 Im folgenden Beispiel gibt ein und Endzeichen des Eingabestreams an:  
  
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
  
### Eingabe  
  
```  
test  
```  
  
##  <a name="vclrfthereadfunctionanchor14"></a> Die Lesenfunktion  
 Die **Lesen**\-Memberfunktion liest Bytes aus einer Datei zu einem angegebenen Speicherbereich.  Das Längenargument bestimmt die Anzahl der gelesenen Bytes.  Wenn Sie dieses Argument einschließen, wird das Lesen auf, wenn das physische Dateiende, oder im Fall einer Textmodusdatei erreicht wird, wenn ein eingebettetes `EOF` Zeichen gelesen wird.  
  
 In diesem Beispiel liest einen binären Datensatz aus einer Gehaltsabrechnungsdatei in eine Struktur:  
  
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
  
 Das Programm wird davon ausgegangen, dass die Datensätze genau formatiert sind, wie durch die Struktur ohne das Beenden von Wagenrückkehr\- oder Zeilenvorschubzeichen angegeben.  
  
##  <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Die seekg und tellg Funktionen  
 Eingabedateistreams enthalten einen internen Zeiger zur Position in der Datei, in der Daten als Nächstes gelesen werden sollen.  Sie dieses `seekg` Zeiger mit der Funktion, wie hier gezeigt:  
  
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
  
 Um `seekg` zu verwenden Datensatz\-ausgerichtete um Datenverwaltungssysteme zu implementieren, multiplizieren Sie die Rekordgröße fester Länge durch die Datensatznummer um die Byteposition relativ zum Ende der Datei zu erhalten, und verwenden Sie dann das Objekt **abrufen** um den Datensatz zu lesen.  
  
 Die Memberfunktion `tellg` gibt die Position der aktuellen Datei zum Lesen zurück.  Dieser Wert ist vom Typ `streampos`, `typedef`, das im iostream\-Bibliothek \<definiert wird\>.  Im folgenden Beispiel wird eine Datei und zeigt die Nachrichten an, welche die Positionen von Leerzeichen anzeigen.  
  
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
  
##  <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> Die Funktion für Eingabestreams neben  
 Die **schließen**\-Memberfunktion enthält die Datenträgerdatei, die einem Eingabedateistream zugeordnet wird und dem Betriebssystemdateihandle frei.  Der [ifstream](../standard-library/basic-ifstream-class.md) Destruktor enthält die Datei für Sie, jedoch können Sie die Funktion **schließen** verwenden, wenn Sie eine andere Datei für dasselbe Streamobjekt öffnen müssen.  
  
## Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)