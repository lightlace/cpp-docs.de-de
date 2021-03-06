---
title: Konstruieren von Ausgabestreamobjekten
ms.date: 11/04/2016
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
ms.openlocfilehash: d7bec211f30986deccc869a879dd5155ea70996b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457286"
---
# <a name="constructing-output-stream-objects"></a>Konstruieren von Ausgabestreamobjekten

Wenn Sie lediglich die vordefinierten `cout`, `cerr` oder `clog`-Objekte verwenden, müssen Sie keinen Ausgabestream erstellen. Verwenden Sie folgende Konstruktoren:

- [Konstruktoren für Dateiausgabestream](#vclrfoutputfilestreamconstructorsanchor1)

- [Konstruktoren für Zeichenfolge-Ausgabestream](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="vclrfoutputfilestreamconstructorsanchor1"></a>Konstruktoren für Dateiausgabestream

Sie können einen Dateiausgabestream auf eine der beiden folgenden Arten erstellen:

- Verwenden Sie den Standardkonstruktor, und rufen Sie anschließend die `open`-Memberfunktion auf:

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- Geben Sie einen Dateinamen und Modus-Flags im Konstruktoraufruf ein.

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="vclrfoutputstringstreamconstructorsanchor2"></a>Konstruktoren für Zeichenfolge-Ausgabestream

Um einen Zeichenfolge-Ausgabestream zu erstellen, können Sie `ostringstream` auf folgende Art verwenden:

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

Der `ends`-„Manipulator“ fügt der Zeichenfolge die erforderlichen, abschließenden Null-Zeichen hinzu.

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)
