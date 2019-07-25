---
title: Konstruieren von Eingabestreamobjekten
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: c000a9e927169ef710554372217ba15089ee11b8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457293"
---
# <a name="constructing-input-stream-objects"></a>Konstruieren von Eingabestreamobjekten

Wenn Sie lediglich das `cin`-Objekt verwenden, müssen Sie keinen Eingabestream erstellen. Die Erstellung eines Eingabestreams ist jedoch erforderlich, wenn Sie Folgendes verwenden:

- [Konstruktoren für Dateieingabestream](#vclrfinputfilestreamconstructorsanchor8)

- [Konstruktoren für Zeichenfolge-Eingabestream](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a>Konstruktoren für Dateieingabestream

Es gibt zwei Möglichkeiten, einen Dateieingabestream zu erstellen:

- Verwenden Sie den **void** -Argumentkonstruktor, und `open` nennen Sie dann die Member-Funktion:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Geben Sie einen Dateinamen und Modus-Flags im Konstruktoraufruf an, was die Datei während des Erstellungsprozesses öffnet:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a>Konstruktoren für Zeichenfolge-Eingabestream

Konstruktoren für Zeichenfolge-Eingabestream erfordern die Adresse von vorab zugeordnetem, vorinitialisierten Speicher:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)
