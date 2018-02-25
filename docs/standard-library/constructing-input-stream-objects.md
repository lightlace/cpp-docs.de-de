---
title: Konstruieren von Eingabestreamobjekten| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a189fa948bc8c6be7acdac0dcc50e9585e82a082
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="constructing-input-stream-objects"></a>Konstruieren von Eingabestreamobjekten
Wenn Sie lediglich das `cin`-Objekt verwenden, müssen Sie keinen Eingabestream erstellen. Die Erstellung eines Eingabestreams ist jedoch erforderlich, wenn Sie Folgendes verwenden:  
  
- [Konstruktoren für Dateieingabestream](#vclrfinputfilestreamconstructorsanchor8)  
  
- [Konstruktoren für Zeichenfolge-Eingabestream](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a>Konstruktoren für Dateieingabestream  
 Es gibt zwei Möglichkeiten, einen Dateieingabestream zu erstellen:  
  
-   Verwenden Sie den `void`-Argumentkonstruktor, und rufen Sie anschließend die `open`-Memberfunktion auf:  
  
 ```  
    ifstream myFile; // On the stack  
    myFile.open("filename");

 
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Geben Sie einen Dateinamen und Modus-Flags im Konstruktoraufruf an, was die Datei während des Erstellungsprozesses öffnet:  
  
 ```  
    ifstream myFile("filename");
```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a>Konstruktoren für Zeichenfolge-Eingabestream  
 Konstruktoren für Zeichenfolge-Eingabestream erfordern die Adresse von vorab zugeordnetem, vorinitialisierten Speicher:  
  
```  
string s("123.45");

double amt;  
istringstream myString(s);

//istringstream myString("123.45") also works  
myString>> amt; // amt contains 123.45  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)

