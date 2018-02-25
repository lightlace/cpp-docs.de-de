---
title: Konstruieren von Ausgabestreamobjekten| Microsoft-Dokumentation
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
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf40e6683462803fcf81a9be915a4672baefd3e9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="constructing-output-stream-objects"></a>Konstruieren von Ausgabestreamobjekten
Wenn Sie lediglich die vordefinierten `cout`, `cerr` oder `clog`-Objekte verwenden, müssen Sie keinen Ausgabestream erstellen. Verwenden Sie folgende Konstruktoren:  
  
- [Konstruktoren für Dateiausgabestream](#vclrfoutputfilestreamconstructorsanchor1)  
  
- [Konstruktoren für Zeichenfolge-Ausgabestream](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a>Konstruktoren für Dateiausgabestream  
 Sie können einen Dateiausgabestream auf eine der beiden folgenden Arten erstellen:  
  
-   Verwenden Sie den Standardkonstruktor, und rufen Sie anschließend die `open`-Memberfunktion auf:  
  
 ```  
    ofstream myFile; // Static or on the stack  
    myFile.open("filename");

 
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Geben Sie einen Dateinamen und Modus-Flags im Konstruktoraufruf ein.  
  
 ```  
    ofstream myFile("filename", ios_base::out);
```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a>Konstruktoren für Zeichenfolge-Ausgabestream  
 Um einen Zeichenfolge-Ausgabestream zu erstellen, können Sie `ostringstream` auf folgende Art verwenden:  
  
```  
    using namespace std;  
string sp;  
ostringstream myString;  
myString <<"this is a test" <<ends;  
sp = myString.str();
// Obtain string  
cout <<sp <endl;   
```  
  
 Der `ends`-„Manipulator“ fügt der Zeichenfolge die erforderlichen, abschließenden Null-Zeichen hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)

