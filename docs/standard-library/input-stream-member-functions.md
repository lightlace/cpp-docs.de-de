---
title: Eingabestream-Memberfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57288e7eb85e3d23fe8790ac3097cab82acdcf8b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954668"
---
# <a name="input-stream-member-functions"></a>Eingabestream-Memberfunktionen

Eingabestream-Memberfunktionen werden für Datenträgereingaben verwendet. Diese Memberfunktionen umfassen:

- [Die open-Funktion für die Eingabestreams](#vclrftheopenfunctionforinputstreamsanchor11)

- [GET-Anforderung](#vclrfthegetfunctionanchor12)

- [Die getline](#vclrfthegetlinefunctionanchor13)

- [Die schreibgeschützte](#vclrfthereadfunctionanchor14)

- [Die seekg- und tellg-Funktionen](#vclrftheseekgandtellgfunctionsanchor7)

- [Die clos-Funktion für Eingabestreams](#vclrftheclosefunctionforinputstreamsanchor15)

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Die open-Funktion für Eingabestreams

Wenn Sie einen Eingabedateistream (ifstream) verwenden, müssen Sie den Stream einer bestimmten Datenträgerdatei zuordnen. Hierzu können Sie im Konstruktor oder Sie können die `open` Funktion. In beiden Fällen sind die Argumente gleich.

Geben Sie Sie in der Regel eine [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) zu kennzeichnen, wenn beim Öffnen der Datei, die mit einem Eingabestream verknüpft ist (der Standardmodus ist `ios::in`). Eine Liste mit den `open_mode` Flags finden Sie unter [öffnen](#vclrftheopenfunctionforinputstreamsanchor11). Die Flags können mit dem bitweisen OR-Operator ( &#124; ) kombiniert werden.

Um eine Datei zu lesen, verwenden Sie zunächst die `fail` Memberfunktion, um zu bestimmen, ob es vorhanden ist:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a> GET-Anforderung

Die unformatierte `get` Memberfunktion funktioniert wie die `>>` -Operator mit zwei Ausnahmen. Zuerst die `get` Funktion enthält Leerzeichen, wohingegen der Extraktor Leerzeichen ausschließt bei der `skipws` Flag festgelegt ist (Standardeinstellung). Zweitens wird die `get` Funktion ist weniger wahrscheinlich dazu führen, dass einen gebundener Ausgabestream (`cout`, z. B.) geleert zu werden.

Eine Variante der `get` Funktion gibt eine Pufferadresse und die maximale Anzahl der zu lesenden Zeichen. Dies hilft dabei, die Anzahl der Zeichen einzuschränken, die zu einer bestimmten Variable gesendet werden, wie dieses Beispiel zeigt:

```cpp
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

```Input
1234
```

### <a name="sample-output"></a>Beispielausgabe

```Output
1234
```

## <a name="vclrfthegetlinefunctionanchor13"></a> Die getline

Die `getline` Memberfunktion ähnelt der `get` Funktion. Beide Funktionen ermöglichen ein drittes Argument, das abschließende Zeichen für die Eingabe angibt. Der Standardwert ist das Zeilenumbruchzeichen. Beide Funktionen reservieren ein Zeichen für das benötigte abschließende Zeichen. Allerdings `get` verlässt das abschließende Zeichen im Datenstrom und `getline` entfernt das abschließende Zeichen.

Im folgenden Beispiel wird ein abschließendes Zeichen für den Eingabestream angegeben:

```cpp
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

```Input
test
```

## <a name="vclrfthereadfunctionanchor14"></a> Die schreibgeschützte

Die `read` Memberfunktion liest Bytes aus einer Datei in einen angegebenen Bereich des Arbeitsspeichers. Das Längenargument bestimmt die Anzahl gelesener Bytes. Wenn Sie dieses Argument nicht einfügen, wird das Lesen beendet, sobald das physische Ende der Datei erreicht ist, oder, bei einer Textmodusdatei, wenn ein eingebettetes `EOF`-Zeichen gelesen wird.

Dieses Beispiel liest einen binären Datensatz aus einer Lohnabrechnungsdatei in eine Struktur:

```cpp
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

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Die seekg- und tellg-Funktionen

Eingabedatei-Streams behalten einen internen Zeiger auf der Position in der Datei, in der Daten als Nächstes gelesen werden. Legen Sie diesen Zeiger mit der `seekg`-Funktion fest, wie hier gezeigt:

```cpp
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

Verwendung von `seekg` damit datensatzorientierte Datenverwaltungssysteme implementiert werden soll, Multiplizieren Sie die Datensatzgröße von fester Länge durch die Datensatznummer zum Abrufen der Byte-Position relativ zum Ende der Datei und verwenden Sie dann die `get` Objekt zum Lesen des Datensatzes.

Die `tellg`-Memberfunktion gibt die aktuelle Dateiposition zum Lesen zurück. Dieser Wert ist vom Typ `streampos`, ein `typedef` in \<iostream > definierter Wert. Das folgende Beispiel liest eine Datei und zeigt Meldungen an, die die Positionen der Leerzeichen zeigen.

```cpp
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

## <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> Die close-Funktion für Eingabestreams

Die `close` Memberfunktion schließt die Datenträgerdatei, die einem eingabedateistream zugeordnet, und das Betriebssystem-Dateihandle frei. Die [Ifstream](../standard-library/basic-ifstream-class.md) Destruktor schließt die Datei für Sie, aber Sie können die `close` ausgeführt werden, wenn Sie eine andere Datei für das gleiche Streamobjekt öffnen müssen.

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
