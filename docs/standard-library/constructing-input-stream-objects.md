---
title: Konstruieren von Eingabestreamobjekten| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7e8c664bd6632f480ba53b9dedea914bbc8e4dd7
ms.lasthandoff: 02/24/2017

---
# <a name="constructing-input-stream-objects"></a>Konstruieren von Eingabestreamobjekten
Wenn Sie lediglich das `cin`-Objekt verwenden, müssen Sie keinen Eingabestream erstellen. Die Erstellung eines Eingabestreams ist jedoch erforderlich, wenn Sie Folgendes verwenden:  
  
- [Konstruktoren für Dateieingabestream](#vclrfinputfilestreamconstructorsanchor8)  
  
- [Konstruktoren für Zeichenfolge-Eingabestream](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="a-namevclrfinputfilestreamconstructorsanchor8a-input-file-stream-constructors"></a><a name="vclrfinputfilestreamconstructorsanchor8"></a>Konstruktoren für Dateieingabestream  
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
  
##  <a name="a-namevclrfinputstringstreamconstructorsanchor9a-input-string-stream-constructors"></a><a name="vclrfinputstringstreamconstructorsanchor9"></a>Konstruktoren für Zeichenfolge-Eingabestream  
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


