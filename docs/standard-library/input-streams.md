---
title: Eingabestreams
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
ms.openlocfilehash: 0f56f5ffc8e61c0881eddbbd65e1c431b9219674
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404922"
---
# <a name="input-streams"></a>Eingabestreams

Ein Eingabestreamobjekt ist eine Quelle von Bytes. Die drei wichtigsten Eingabestreamklassen sind [istream](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md), und [istringstream](../standard-library/basic-istringstream-class.md).

Die `istream`-Klasse wird am besten für die sequenzielle Textmodus-Eingabe verwendet. Sie können Objekte der Klasse `istream` für einen gepufferten oder ungepufferten Vorgang konfigurieren. Alle Funktionalitäten der Basisklasse `ios` sind in `istream` enthalten. Sie werden nur selten Objekte aus der Klasse `istream` erstellen. Stattdessen werden Sie in der Regel das vordefinierte `cin`-Objekt verwenden, welches eigentlich ein Objekt der Klasse [ostream](../standard-library/basic-ostream-class.md) ist. In einigen Fällen weisen Sie nach dem Programmstart `cin` auf andere Streamobjekte zu.

Die `ifstream`-Klasse unterstützt die Datenträgereingabe. Wenn Sie einen Datenträger nur für Eingaben benötigen, erstellen Sie ein Objekt der Klasse `ifstream`. Sie können die Binär-oder Textmodusdaten angeben. Wenn Sie im Konstruktor einen Dateinamen angeben, wird die Datei automatisch geöffnet, wenn das Objekt erstellt wird. Andernfalls können Sie die `open`-Funktion nach dem Aufrufen des Standardkonstruktors verwenden. Viele Formatierungsoptionen und Memberfunktionen gelten für `ifstream`-Objekte. Alle Funktionalitäten der Basisklasse `ios` und `istream` sind in `ifstream` enthalten.

Wie die Bibliotheksfunktion `sscanf_s` unterstützt die `istringstream`-Klasse die Eingabe von Zeichenfolgen im Arbeitsspeicher. Um Daten von einem Zeichenarray zu extrahieren, das einen NULL-Terminator hat, ordnen Sie die Zeichenfolge zu und initialisieren Sie sie. Anschließend erstellen Sie ein Objekt der Klasse `istringstream`.

## <a name="in-this-section"></a>In diesem Abschnitt

[Konstruieren von Eingabestreamobjekten](../standard-library/constructing-input-stream-objects.md)

[Verwenden von Extraktionsoperatoren](../standard-library/using-extraction-operators.md)

[Überprüfen von Extraktionen](../standard-library/testing-for-extraction-errors.md)

[Eingabestream-Manipulatoren](../standard-library/input-stream-manipulators.md)

[Eingabestream-Memberfunktionen](../standard-library/input-stream-member-functions.md)

[Überladen des Operators >> für eigene Klassen](../standard-library/overloading-the-input-operator-for-your-own-classes.md)

## <a name="see-also"></a>Siehe auch

[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
