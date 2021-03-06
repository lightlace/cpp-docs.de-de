---
title: Ausgabedateistream-Memberfunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
ms.openlocfilehash: 8c23008d0c46a532f11e89442328ed25cc203077
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453057"
---
# <a name="output-file-stream-member-functions"></a>Ausgabedateistream-Memberfunktionen

Ausgabedateistream-Memberfunktionen verfügen über drei Arten: die, die Manipulatoren entsprechen, die, die unformatierte Schreibvorgänge ausführen, und die, die andernfalls den Streamstatus ändern und keinen entsprechenden Manipulator oder Einfügungsoperator haben. Für die sequenzielle, formatierte Ausgabe können Sie nur Einfügungsoperatoren und Manipulatoren verwenden. Bei einer binäre Datenträgerausgabe verwenden Sie andere Memberfunktionen, mit oder ohne Einfügungsoperatoren.

## <a name="the-open-function-for-output-streams"></a>Die open-Funktion für Ausgabestreams

Um einen ausgabedateistream ([ofstream](../standard-library/basic-ofstream-class.md)) zu verwenden, müssen Sie diesen Stream einer bestimmten Datenträger Datei im Konstruktor `open` oder der-Funktion zuordnen. Wenn Sie die `open` -Funktion verwenden, können Sie das gleiche Stream-Objekt mit einer Reihe von Dateien wieder verwenden. In beiden Fällen sind die Argumente, die die Datei beschreiben identisch.

Wenn Sie die Datei öffnen, die einem Ausgabestream zugeordnet ist, `open_mode` geben Sie im Allgemeinen ein Flag an. Sie können diese Flags kombinieren, die in der `ios`-Klasse mit dem bitweisen OR-Operator ( &#124; ) als Enumeratoren definiert werden. Finden Sie unter [ios_base:: openmode](../standard-library/ios-base-class.md#openmode) eine Liste der Enumeratoren.

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

## <a name="the-put"></a>Der Put-

Die **put**-Funktion schreibt ein Zeichen in den Ausgabestream. Die beiden folgenden Anweisungen sind standardmäßig identisch, aber die zweite ist von den Streamformatargumenten betroffen:

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>Der Schreibvorgang

Die `write` -Funktion schreibt einen Speicherblock in einen ausgabedateistream. Das Längenargument bestimmt die Anzahl geschriebener Bytes. Dieses Beispiel erstellt einen Ausgabestream für die Datei und schreibt den binären Wert der `Date`-Struktur hinein:

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

Die `write` Funktion wird nicht angehalten, wenn Sie ein NULL-Zeichen erreicht, sodass die gesamte Klassenstruktur geschrieben wird. Die Funktion nimmt zwei Argumente an: einen **char** -Zeiger und die Anzahl der zu schreibenden Zeichen. Beachten Sie die erforderliche Umwandlung in **char** <strong>\*</strong> vor der Adresse des Struktur Objekts.

## <a name="the-seekp-and-tellp-functions"></a>Die Funktionen seekp und tellp

Ein Ausgabestream für die Datei hält einen internen Zeiger, der auf die Position zeigt, in der die Daten als nächstes geschrieben werden sollen. Die `seekp`-Memberfunktion legt diesen Zeiger fest und bietet somit Random_Access-Datenträgerdateiausgaben. Die `tellp`-Memberfunktion gibt die gespeicherte Dateiposition zurück. Beispiele für die Verwendung von Entsprechungen des Eingabestreams für `seekp` und `tellp`, finden Sie unter [Die Funktionen seekg und tellg](../standard-library/input-stream-member-functions.md).

## <a name="the-close-function-for-output-streams"></a>Die close-Funktion für Ausgabestreams

Die `close` Member-Funktion schließt die einem Ausgabedatei Datenstrom zugeordnete Datenträger Datei. Die Datei muss geschlossen werden, um alle Datenträgerausgaben abzuschließen. Bei Bedarf schließt der `ofstream` debugtor die Datei für Sie, aber Sie können die `close` -Funktion verwenden, wenn Sie eine andere Datei für das gleiche Streamobjekt öffnen müssen.

Der Ausgabestream-debugtor schließt automatisch die Datei eines Streams, wenn der `open` Konstruktor oder die Member-Funktion die Datei geöffnet hat. Wenn Sie dem Konstruktor einen Dateideskriptor für eine bereits geöffnete Datei übergeben oder die `attach` Member-Funktion verwenden, müssen Sie die Datei explizit schließen.

## <a name="vclrferrorprocessingfunctionsanchor10"></a> Fehlerverarbeitende Funktionen

Verwenden Sie diese Memberfunktionen, um beim Schreiben in einen Stream auf Fehler zu testen:

|Funktion|Rückgabewert|
|--------------|------------------|
|[bad](basic-ios-class.md#bad)|Gibt **TRUE** zurück, wenn ein nicht behebbarer Fehler vorhanden ist.|
|[fail](basic-ios-class.md#fail)|Gibt **TRUE** zurück, wenn ein nicht behebbarer Fehler oder eine „erwartete“ Bedingung, wie z.B. ein Konvertierungsfehler vorhanden ist oder wenn die Datei nicht gefunden wird. Die `clear` Verarbeitung kann häufig nach einem-Befehl mit einem NULL-Argument fortgesetzt werden.|
|[good](basic-ios-class.md#good)|Gibt **TRUE** zurück, wenn kein Fehler (nicht behebbar oder anderweitig) vorhanden und das End-of-File-Flag nicht festgelegt ist.|
|[eof](basic-ios-class.md#eof)|Gibt **TRUE** auf das End-of-File-Bedingung zurück.|
|[clear](basic-ios-class.md#clear)|Legt den internen Fehlerzustand fest. Wenn mit den Standardargumenten aufgerufen, löscht er alle Fehlerbits.|
|Rdstate (Basic-IOS-Class. MD # Rdstate|Gibt den aktuellen Fehlerstatus zurück.|

Der **!** der Operator ist überladen, um die gleiche Funktion `fail` wie die Funktion auszuführen. Daher ist der Ausdruck:

```cpp
if(!cout)...
```

identisch mit folgendem Ausdruck:

```cpp
if(cout.fail())...
```

Der **void\*()** -Operator wird überladen, um das Gegenteil des **!** Operator zu sein; daher kommt der Ausdruck:

```cpp
if(cout)...
```

gleich:

```cpp
if(!cout.fail())...
```

Der **void\*()** -Operator ist nicht äquivalent `good` zu, da er das Dateiende nicht testet.

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)
