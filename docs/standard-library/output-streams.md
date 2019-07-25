---
title: Ausgabestreams
ms.date: 11/04/2016
helpviewer_keywords:
- output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
ms.openlocfilehash: e650f9fd0bbc7ad483363706e632686e8ec3749e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450176"
---
# <a name="output-streams"></a>Ausgabestreams

Ein Ausgabestreamobjekt ist ein Ziel für Bytes. Die drei wichtigsten Ausgabestreamklassen sind `ostream`, `ofstream` und `ostringstream`.

Die `ostream`-Klasse, durch die abgeleitete Klasse `basic_ostream`, unterstützt die vordefinierten Streamobjekte:

- `cout`-Standardausgabe

- `cerr`-Standardfehler mit eingeschränkter Pufferung

- `clog` ähnlich wie `cerr`, jedoch mit vollständiger Pufferung

Objekte werden nur selten von `ostream` erstellt; im Allgemeinen werden vordefinierte Objekte verwendet. In einigen Fällen weisen Sie vordefinierte Objekte nach dem Programmstart neu zu. Die `ostream`-Klasse, die für gepufferte oder nicht gepufferte Vorgänge konfiguriert werden kann, eignet sich am besten für sequenzielle Textmodusausgabe. Alle Funktionalitäten der Basisklasse `ios` sind in `ostream` enthalten. Wenn Sie ein Objekt der Klasse `ostream` erstellen, müssen Die dem Konstruktor ein `streambuf`-Objekt angeben.

Die `ofstream`-Klasse unterstützt die Datenträgerdateiausgabe. Wenn Sie einen Datenträger nur für Ausgaben benötigen, erstellen Sie ein Objekt der Klasse `ofstream`. Sie können angeben, ob `ofstream`-Objekte Binär-oder Textmodusdaten beim Erstellen des `ofstream`-Objekts oder beim Aufruf der `open`-Memberfunktion des Objekts akzeptieren. Viele Formatierungsoptionen und Memberfunktionen gelten für `ofstream`-Objekte und alle Funktionen der Basisklassen `ios` und `ostream` sind enthalten.

Wenn Sie im Konstruktor einen Dateinamen angeben, wird die Datei automatisch geöffnet, wenn das Objekt erstellt wird. Andernfalls können Sie die `open`-Memberfunktion nach dem Aufrufen des Standardkonstruktors verwenden.

Wie die Laufzeitfunktion `sprintf_s` unterstützt die `ostringstream`-Klasse die Ausgabe von Zeichenfolgen im Arbeitsspeicher. Um eine Zeichenfolge mithilfe der E/A-Streamformatierung im Arbeitsspeicher zu erstellen, erstellen Sie ein Objekt der Klasse `ostringstream`.

## <a name="in-this-section"></a>In diesem Abschnitt

[Konstruieren von Ausgabestreamobjekten](../standard-library/constructing-output-stream-objects.md)

[Verwenden von Einfügeoperatoren und Festlegen des Formats](../standard-library/using-insertion-operators-and-controlling-format.md)

[Ausgabedateistream-Memberfunktionen](../standard-library/output-file-stream-member-functions.md)

[Pufferungseffekte](../standard-library/effects-of-buffering.md)

[Binäre Ausgabedateien](../standard-library/binary-output-files.md)

[Überladen des Operators << für eigene Klassen](../standard-library/overloading-the-output-operator-for-your-own-classes.md)

[Schreiben eigener Manipulatoren ohne Argumente](../standard-library/writing-your-own-manipulators-without-arguments.md)

## <a name="see-also"></a>Siehe auch

[ofstream](../standard-library/basic-ofstream-class.md)\
[ostringstream](../standard-library/basic-ostringstream-class.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)
