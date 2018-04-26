---
title: Konstruieren von Eingabestreamobjekten| Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a63ba3d8e54e416313ec24d7455ca4cf70979b9f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="constructing-input-stream-objects"></a>Konstruieren von Eingabestreamobjekten

Wenn Sie lediglich das `cin`-Objekt verwenden, müssen Sie keinen Eingabestream erstellen. Die Erstellung eines Eingabestreams ist jedoch erforderlich, wenn Sie Folgendes verwenden:

- [Konstruktoren für Dateieingabestream](#vclrfinputfilestreamconstructorsanchor8)

- [Konstruktoren für Zeichenfolge-Eingabestream](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a>Konstruktoren für Dateieingabestream

Es gibt zwei Möglichkeiten, einen Dateieingabestream zu erstellen:

- Verwenden Sie den `void`-Argumentkonstruktor, und rufen Sie anschließend die `open`-Memberfunktion auf:

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
