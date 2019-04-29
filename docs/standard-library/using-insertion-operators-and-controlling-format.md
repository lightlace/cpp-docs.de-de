---
title: Verwenden von Einfügeoperatoren und Festlegen des Formats
ms.date: 11/04/2016
helpviewer_keywords:
- insertion operators
ms.assetid: cdefe986-6548-4cd1-8a67-b431d7d36a1c
ms.openlocfilehash: 8c04cc6d5deeaf5dfea65a7f8e92a8569084c077
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362269"
---
# <a name="using-insertion-operators-and-controlling-format"></a>Verwenden von Einfügeoperatoren und Festlegen des Formats

In diesem Thema wird veranschaulicht, wie Sie das Format steuern und Einfügeoperatoren für Ihre eigenen Klassen erstellen. Der Einfügeoperator (**<<**), der für alle standardmäßigen C++-Datentypen vorprogrammiert ist, sendet Bytes an ein Ausgabestreamobjekt. Einfügeoperatoren arbeiten mit vordefinierten „Manipulatoren“, d. h. Elementen, die das Standardformat von Ganzzahlargumenten ändern.

Sie können das Format mit den folgenden Optionen steuern:

- [Breite der Ausgabe](#vclrfoutputwidthanchor3)

- [Ausrichtung](#vclrfalignmentanchor4)

- [Genauigkeit](#vclrfprecisionanchor5)

- [Basis](#vclrfradixanchor6)

## <a name="vclrfoutputwidthanchor3"></a> Breite der Ausgabe

Um die Ausgabe auszurichten, geben Sie die Breite der Ausgabe für jedes Element durch Platzieren der `setw` -Manipulator im Stream oder durch Aufrufen der `width` Member-Funktion. In diesem Beispiel werden die Werte in einer Spalte mit einer Breite von mindestens 10 Zeichen rechtsbündig ausgerichtet:

```cpp
// output_width.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   for( int i = 0; i < 4; i++ )
   {
      cout.width(10);
      cout << values[i] << '\n';
   }
}
```

```Output
      1.23
     35.36
     653.7
   4358.24
```

Führende Leerzeichen werden Werten mit einer Breite von weniger als 10 Zeichen hinzugefügt.

Um ein Feld aufzufüllen, verwenden die `fill` Memberfunktion, die den Wert des auffüllzeichens für Felder mit einer angegebenen Breite festlegt. Der Standardwert ist leer. Zum Auffüllen der Zahlenspalte mit einem Sternchen ändern Sie die vorherige **for**-Schleife wie folgt:

```cpp
for (int i = 0; i <4; i++)
{
    cout.width(10);
    cout.fill('*');
    cout << values[i] << endl;
}
```

Der `endl`-Manipulator ersetzt das Zeilenvorschubzeichen (`'\n'`). Die Ausgabe sieht wie folgt aus:

```Output
******1.23
*****35.36
*****653.7
***4358.24
```

Verwenden Sie zum Angeben der Breite für Datenelemente in der gleichen Zeile den `setw`-Manipulator:

```cpp
// setw.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   char *names[] = { "Zoot", "Jimmy", "Al", "Stan" };
   for( int i = 0; i < 4; i++ )
      cout << setw( 7 )  << names[i]
           << setw( 10 ) << values[i] << endl;
}
```

Die `width` Member-Funktion wird in deklariert \<Iostream >. Bei Verwendung von `setw` oder einem anderen Manipulator mit Argumenten, müssen Sie \<iomanip> einschließen. In der Ausgabe werden Zeichenfolgen in einem Feld der Breite 6 und Ganzzahlen in einem Feld der Breite 10 ausgegeben:

```Output
   Zoot      1.23
  Jimmy     35.36
     Al     653.7
   Stan   4358.24
```

Weder `setw` noch `width` werden Werte abgeschnitten. Wenn eine formatierte Ausgabe die Breite überschreitet, wird je nach der Einstellung der Genauigkeit des Streams der gesamte Wert ausgegeben. Beide `setw` und `width` betreffen nur das folgende Feld. Die Feldbreite wird auf das Standardverhalten (die erforderliche Breite) zurückgesetzt, nachdem ein Feld ausgegeben wurde. Jedoch behalten die anderen Streamformatoptionen ihre Gültigkeit, bis sie geändert werden.

## <a name="vclrfalignmentanchor4"></a> Ausrichtung

Ausgabestreams werden standardmäßig als rechtsbündiger Text ausgegeben. Um die Namen im vorherigen Beispiel linksbündig und die Zahlen rechtsbündig auszurichten, ersetzen Sie die **for**-Schleife wie folgt:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6) << names[i]
         << resetiosflags(ios::left)
         << setw(10) << values[i] << endl;
```

Die Ausgabe sieht wie folgt aus:

```Output
Zoot        1.23
Jimmy      35.36
Al         653.7
Stan     4358.24
```

Das Flag für die linksbündige Ausrichtung wird durch Verwendung des [setiosflags](../standard-library/iomanip-functions.md#setiosflags)-Manipulators mit dem Enumerator `left` festgelegt. Dieser Enumerator wird in der [ios](../standard-library/basic-ios-class.md)-Klasse definiert, sodass dessen Verweis das **ios::**-Präfix enthalten muss. Der [resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)-Manipulator deaktiviert das Flag für die linksbündige Ausrichtung. Im Gegensatz zu `width` und `setw`, die Auswirkungen der `setiosflags` und `resetiosflags` kann nicht rückgängig gemacht.

## <a name="vclrfprecisionanchor5"></a> Genauigkeit

Der Standardwert für die Gleitkommagenauigkeit ist sechs. Beispielsweise wird die Zahl 3466.9768 als 3466.98 gedruckt. Die Ausgabeart dieses Werts können Sie mit dem [setprecision](../standard-library/iomanip-functions.md#setprecision)-Manipulator ändern. Der Manipulator hat zwei Flags: [fixed](../standard-library/ios-functions.md#fixed) und [scientific](../standard-library/ios-functions.md#scientific). Wenn [fixed](../standard-library/ios-functions.md#fixed) festgelegt ist, wird die Zahl als 3466,976800 ausgegeben. Wenn `scientific` festgelegt ist, wird sie als 3.4669773 + 003 ausgegeben.

Um die unter [Ausrichtung](#vclrfalignmentanchor4) angezeigten Gleitkommazahlen mit einer signifikanten Stelle anzuzeigen, ersetzen Sie die **for**-Schleife wie folgt:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6)
         << names[i]
         << resetiosflags(ios::left)
         << setw(10)
         << setprecision(1)
         << values[i]
         << endl;
```

Das Programm gibt diese Liste aus:

```Output
Zoot          1
Jimmy     4e+01
Al        7e+02
Stan      4e+03
```

Um die wissenschaftliche Schreibweise zu vermeiden, fügen Sie diese Anweisung vor der **for**-Schleife ein:

```cpp
cout << setiosflags(ios::fixed);
```

Bei fester Schreibweise gibt das Programm mit einer Ziffer nach dem Dezimaltrennzeichen aus.

```Output
Zoot         1.2
Jimmy       35.4
Al         653.7
Stan      4358.2
```

Wenn Sie ändern die `ios::fixed` flag `ios::scientific`, gibt das Programm Folgendes:

```cpp
Zoot    1.2e+00
Jimmy   3.5e+01
Al      6.5e+02
Stan    4.4e+03
```

Auch hier gibt das Programm mit einer Ziffer nach dem Dezimaltrennzeichen aus. Wenn entweder `ios::fixed` oder `ios::scientific` festgelegt ist, der Genauigkeit bestimmt die Anzahl der Ziffern nach dem Dezimaltrennzeichen an. Wenn keines der beiden Flags festgelegt ist, bestimmt der Wert für die Genauigkeit die Gesamtzahl der signifikanten Stellen. Der `resetiosflags`-Manipulator deaktiviert diese Flags.

## <a name="vclrfradixanchor6"></a> Basis

Die `dec`, `oct`, und `hex` Manipulatoren legen die Standardbasis für ein- und Ausgabe. Wenn Sie einfügen, z. B. die `hex` -Manipulator in den Ausgabestream, der das Objekt ordnungsgemäß übersetzt die interne datendarstellung von Ganzzahlen in ein hexadezimales Ausgabeformat. Die Zahlen werden mit den Ziffern a bis f in Kleinbuchstaben angezeigt, wenn das Flag [uppercase](../standard-library/ios-functions.md#uppercase) (für Großbuchstaben) deaktiviert ist (Standard). Andernfalls werden sie in Großbuchstaben angezeigt. Die Standardbasis lautet `dec` (dezimal).

## <a name="quoted-strings-c14"></a>Zeichenfolge in Anführungszeichen (C++14)

Wenn Sie eine Zeichenfolge in einen Stream einfügen, können Sie dieselbe Zeichenfolge problemlos wieder abrufen, indem Sie die stringstream::str()-Memberfunktion aufrufen. Wenn Sie allerdings den Extraktionsoperator verwenden möchten, um den Stream zu einem späteren Zeitpunkt in eine neue Zeichenfolge einzufügen, erhalten Sie möglicherweise ein unerwartetes Ergebnis, da der >>-Operator standardmäßig stoppt, wenn er auf das erste Leerzeichen trifft.

```cpp
std::stringstream ss;
std::string inserted = "This is a sentence.";
std::string extracted;

ss << inserted;
ss >> extracted;

std::cout << inserted;     //  This is a sentence.
std::cout << extracted;    //  This
```

Dieses Verhalten können Sie manuell umgehen, um die Zeichenfolgen-Roundtrips bequemer, C ++ 14 Stellen fügt jedoch das `std::quoted` streammanipulator in \<Iomanip >. Beim Einfügen umgibt `quoted()` die Zeichenfolge mit einem Trennzeichen (standardmäßig doppelte Anführungszeichen „"“), und bei der Extraktion wird der Stream so manipuliert, dass alle Zeichen extrahiert werden, bis das finale Trennzeichen gefunden wird. Eingebettete Anführungszeichen werden mit Escapezeichen versehen (standardmäßig „\\\\“).

Die Trennzeichen sind nur im Streamobjekt vorhanden; Sie sind nicht in der extrahierten Zeichenfolge vorhanden, aber sie sind in der Zeichenfolge, die vom [basic_stringstream:: str](../standard-library/basic-stringstream-class.md#str).

Das Leerzeichenverhalten der Einfüge- und Extraktionsvorgänge ist unabhängig von der Art der Darstellung einer Zeichenfolge im Code, sodass der in Anführungszeichen gesetzte Operator unabhängig davon nützlich ist, ob die Eingabezeichenfolge ein unformatiertes Zeichenfolgenliteral oder eine reguläre Zeichenfolge ist. Die Eingabezeichenfolge kann unabhängig vom Format eingebettete Anführungszeichen, Zeilenumbrüche, Tabulatoren usw. aufweisen, und diese werden vom quoted()-Manipulator beibehalten.

Weitere Informationen und Beispiele für vollständigen Code finden Sie unter [in Anführungszeichen](../standard-library/iomanip-functions.md#quoted).

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)<br/>
