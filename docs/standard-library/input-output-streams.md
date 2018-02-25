---
title: Eingabe-/Ausgabestreams | Microsoft-Dokumentation
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
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f4035f84c8e3f173bc36c490304c63fd290eed9c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="inputoutput-streams"></a>Eingabe-/Ausgabestreams
`basic_iostream`, welches in der Headerdatei \<istream > definiert ist, ist die Klassenvorlage für Objekte, die zeichenbasierte Ein- und Ausgabe-E/A-Streams behandeln.  
  
 Es gibt zwei Typdefinitionen, die zeichenspezifische Spezialisierungen von `basic_iostream` definieren und helfen können, den Code leichter lesbar zu machen: `iostream` (nicht zu verwechseln mit der Headerdatei \<iostream >) ist ein E/A-Stream, der auf `basic_iostream<char>` basiert; `wiostream` ist ein E/A-Stream, der auf `basic_iostream<wchar_t>` basiert.  
  
 Weitere Informationen finden Sie unter [basic_iostream-Klasse](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md), und [wiostream](../standard-library/basic-iostream-class.md).  
  
 Abgeleitet von `basic_iostream` ist die Klassenvorlage `basic_fstream`, die zum Übertragen von Zeichendaten in und aus Dateien verwendet wird.  
  
 Es gibt auch Typdefinitionen, die zeichenspezifische Spezialisierungen von `basic_fstream` bereitstellen. Sie sind `fstream`, also ein E/A-Dateistream, der basierend auf `char`, und `wfstream`, also ein E/A-Dateistream, der auf `wchar_t` basiert. Weitere Informationen finden Sie unter [basic_fstream-Klasse](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md) und [wfstream](../standard-library/basic-fstream-class.md). Die Verwendung dieser Typdefinitionen benötigt die Aufnahme der Headerdatei \<fstream >.  
  
> [!NOTE]
>  Wenn ein `basic_fstream`-Objekt die Datei-E/A verwendet, obwohl die zugrundeliegenden Puffer separat festgelegte Positionen für Lesen und Schreiben enthalten, sind die aktuellen Eingabe- und Ausgabepositionen miteinander verbunden. Das Lesen einiger Daten verschiebt die Ausgabeposition.  
  
 Die Klassenvorlage `basic_stringstream` und seine allgemeine Spezialisierung `stringstream`, werden häufig zum Arbeiten mit E/A-Streamobjekten zum Einfügen und Extrahieren von Zeichendaten verwendet. Weitere Informationen finden Sie unter [basic_stringstream-Klasse](../standard-library/basic-stringstream-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [stringstream](../standard-library/basic-stringstream-class.md)   
 [basic_stringstream-Klasse](../standard-library/basic-stringstream-class.md)   
 [\<sstream>](../standard-library/sstream.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)



