---
title: Konstruieren von Eingabestreamobjekten| Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c640f1b338fa4b0aa6dbcc408e0729fbf8ff90a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963549"
---
# <a name="constructing-input-stream-objects"></a>Konstruieren von Eingabestreamobjekten

Wenn Sie lediglich das `cin`-Objekt verwenden, müssen Sie keinen Eingabestream erstellen. Die Erstellung eines Eingabestreams ist jedoch erforderlich, wenn Sie Folgendes verwenden:

- [Konstruktoren für Dateieingabestream](#vclrfinputfilestreamconstructorsanchor8)

- [Konstruktoren für Zeichenfolge-Eingabestream](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a>Konstruktoren für Dateieingabestream

Es gibt zwei Möglichkeiten, einen Dateieingabestream zu erstellen:

- Verwenden der **"void"** Argumentkonstruktor, rufen Sie dann die `open` Memberfunktion:

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

[Eingabestreams](../standard-library/input-streams.md)<br/>
