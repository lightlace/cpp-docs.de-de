---
title: Ausgabedateistream-Memberfunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
ms.openlocfilehash: eba627c69437754a9c0a819167443aa00c025fef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370839"
---
# <a name="output-file-stream-member-functions"></a>Ausgabedateistream-Memberfunktionen

Ausgabedateistream-Memberfunktionen verfügen über drei Arten: die, die Manipulatoren entsprechen, die, die unformatierte Schreibvorgänge ausführen, und die, die andernfalls den Streamstatus ändern und keinen entsprechenden Manipulator oder Einfügungsoperator haben. Für die sequenzielle, formatierte Ausgabe können Sie nur Einfügungsoperatoren und Manipulatoren verwenden. Bei einer binäre Datenträgerausgabe verwenden Sie andere Memberfunktionen, mit oder ohne Einfügungsoperatoren.

## <a name="the-open-function-for-output-streams"></a>Die open-Funktion für Ausgabestreams

Verwenden Sie einen ausgabedateistream ([Ofstream](../standard-library/basic-ofstream-class.md)), müssen Sie diesen Stream einer bestimmten Datenträgerdatei im Konstruktor zuordnen oder die `open` Funktion. Bei Verwendung der `open` -Funktion, Sie können das gleiche Streamobjekt mit einer Reihe von Dateien wiederverwenden. In beiden Fällen sind die Argumente, die die Datei beschreiben identisch.

Beim Öffnen der Datei mit einem Ausgabestream verknüpft ist, geben Sie in der Regel eine `open_mode` Flag. Sie können diese Flags kombinieren, die in der `ios`-Klasse mit dem bitweisen OR-Operator ( &#124; ) als Enumeratoren definiert werden. Finden Sie unter [ios_base:: openmode](../standard-library/ios-base-class.md#openmode) eine Liste der Enumeratoren.

Drei allgemeine Situationen für die Ausgabestreams umfassen Modusoptionen:

- Erstellen einer Datei. Wenn die Datei bereits vorhanden ist, wird die alte Version gelöscht.

   ```cpp
   ostream ofile("FILENAME");
   // Default is ios::out

   ofstream ofile("FILENAME", ios::out);
   // Equivalent to above
   ```

- Anfügen von Datensätzen an eine vorhandene Datei oder Erstellen derselben, wenn sie nicht vorhanden ist.

   ```cpp
   ofstream ofile("FILENAME", ios::app);
   ```

- Einzelnes Öffnen von zwei Dateien auf demselben Stream.

   ```cpp
   ofstream ofile();
   ofile.open("FILE1", ios::in);
   // Do some output
   ofile.close();    // FILE1 closed
   ofile.open("FILE2", ios::in);
   // Do some more output
   ofile.close();    // FILE2 closed
   // When ofile goes out of scope it is destroyed.
   ```

## <a name="the-put"></a>Der put

Die **put**-Funktion schreibt ein Zeichen in den Ausgabestream. Die beiden folgenden Anweisungen sind standardmäßig identisch, aber die zweite ist von den Streamformatargumenten betroffen:

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>Der Schreibvorgang

Die `write` -Funktion schreibt einen Speicherblock in einen Ausgabestream für die Datei. Das Längenargument bestimmt die Anzahl geschriebener Bytes. Dieses Beispiel erstellt einen Ausgabestream für die Datei und schreibt den binären Wert der `Date`-Struktur hinein:

```cpp
// write_function.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;

struct Date
{
   int mo, da, yr;
};

int main( )
{
   Date dt = { 6, 10, 92 };
   ofstream tfile( "date.dat" , ios::binary );
   tfile.write( (char *) &dt, sizeof dt );
}
```

Die `write` -Funktion wird nicht beendet, wenn ein Null-Zeichen erreicht wird, damit die vollständige Klassenstruktur geschrieben wird. Die Funktion akzeptiert zwei Argumente: ein **Char** Zeiger und die Anzahl der zu schreibenden Zeichen. Beachten Sie die erforderliche Umwandlung in **Char** <strong>\*</strong> vor der Adressierung des Strukturobjekts.

## <a name="the-seekp-and-tellp-functions"></a>Die Funktionen seekp und tellp

Ein Ausgabestream für die Datei hält einen internen Zeiger, der auf die Position zeigt, in der die Daten als nächstes geschrieben werden sollen. Die `seekp`-Memberfunktion legt diesen Zeiger fest und bietet somit Random_Access-Datenträgerdateiausgaben. Die `tellp`-Memberfunktion gibt die gespeicherte Dateiposition zurück. Beispiele für die Verwendung von Entsprechungen des Eingabestreams für `seekp` und `tellp`, finden Sie unter [Die Funktionen seekg und tellg](../standard-library/input-stream-member-functions.md).

## <a name="the-close-function-for-output-streams"></a>Die close-Funktion für Ausgabestreams

Die `close` Memberfunktion schließt die Datenträgerdatei, die einem Ausgabestream zugeordnet. Die Datei muss geschlossen werden, um alle Datenträgerausgaben abzuschließen. Bei Bedarf die `ofstream` Destruktor schließt die Datei für Sie, aber Sie können die `close` ausgeführt werden, wenn Sie eine andere Datei für das gleiche Streamobjekt öffnen müssen.

Destruktor der Ausgabestream schließt automatisch eine streamdatei nur, wenn den Konstruktor oder die `open` Memberfunktion die Datei geöffnet. Wenn Sie einen Dateideskriptor für eine bereits geöffneten Datei oder dem Konstruktor übergeben die `attach` Member-Funktion müssen Sie die Datei explizit schließen.

## <a name="vclrferrorprocessingfunctionsanchor10"></a> Fehlerverarbeitende Funktionen

Verwenden Sie diese Memberfunktionen, um beim Schreiben in einen Stream auf Fehler zu testen:

|Funktion|Rückgabewert|
|--------------|------------------|
|[bad](basic-ios-class.md#bad)|Gibt **TRUE** zurück, wenn ein nicht behebbarer Fehler vorhanden ist.|
|[fail](basic-ios-class.md#fail)|Gibt **TRUE** zurück, wenn ein nicht behebbarer Fehler oder eine „erwartete“ Bedingung, wie z.B. ein Konvertierungsfehler vorhanden ist oder wenn die Datei nicht gefunden wird. Verarbeitung kann oft nach einem Aufruf von fortgesetzt `clear` mit einem NULL-Argument.|
|[good](basic-ios-class.md#good)|Gibt **TRUE** zurück, wenn kein Fehler (nicht behebbar oder anderweitig) vorhanden und das End-of-File-Flag nicht festgelegt ist.|
|[eof](basic-ios-class.md#eof)|Gibt **TRUE** auf das End-of-File-Bedingung zurück.|
|[clear](basic-ios-class.md#clear)|Legt den internen Fehlerzustand fest. Wenn mit den Standardargumenten aufgerufen, löscht er alle Fehlerbits.|
|[rdstate](basic-ios-class.md#rdstate|Gibt den aktuellen Fehlerstatus zurück.|

Der **!** Operator wird überladen, um die gleiche Funktion wie führen Sie die `fail` Funktion. Daher ist der Ausdruck:

```cpp
if(!cout)...
```

identisch mit folgendem Ausdruck:

```cpp
if(cout.fail())...
```

Der **void\*()**-Operator wird überladen, um das Gegenteil des **!** Operator zu sein; daher kommt der Ausdruck:

```cpp
if(cout)...
```

gleich:

```cpp
if(!cout.fail())...
```

Die **"void"\*()** Operator entspricht nicht `good` , da er nicht am Ende der Datei getestet wird.

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)<br/>
