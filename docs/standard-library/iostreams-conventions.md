---
title: iostreams-Konventionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7d9004c82d740b6abca87e3cce9d0e73e0b6fc62
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="iostreams-conventions"></a>iostreams-Konventionen
Der iostreams-Headers unterstützen Konvertierungen zwischen Text und kodierten Formen, und zwischen Eingabe und Ausgabe in externe Dateien:  
  
|||  
|-|-|  
|[\<fstream>](../standard-library/fstream.md)|[\<iomanip>](../standard-library/iomanip.md)|  
|[\<ios>](../standard-library/ios.md)|[\<iosfwd>](../standard-library/iosfwd.md)|  
|[\<iostream>](../standard-library/iostream.md)|[\<istream>](../standard-library/istream.md)|  
|[\<ostream>](../standard-library/ostream.md)|[\<sstream>](../standard-library/sstream.md)|  
|[\<streambuf>](../standard-library/streambuf.md)|[\<strstream>](../standard-library/strstream.md)|  
  
 Für den einfachsten Gebrauch von „iostreams“ müssen Sie nur den Header [\<iostreams>](../standard-library/iostream.md) verwenden. Dann können Sie Werte aus [cin](../standard-library/iostream.md#cin) oder [wcin](../standard-library/iostream.md#wcin) extrahieren, um die Standardeingabe zu lesen. Die Regeln, die Sie dafür befolgen müssen, finden Sie in der Beschreibung der [basic_istream-Klasse](../standard-library/basic-istream-class.md). Außerdem können Sie Werte in [cout](../standard-library/iostream.md#cout) oder [wcout](../standard-library/iostream.md#wcout) einfügen, um die Standardausgabe zu schreiben. Die Regeln, die Sie dafür befolgen müssen, finden Sie in der Beschreibung der [basic_ostream-Klasse](../standard-library/basic-ostream-class.md). Sie können die Formatsteuerung, die Extraktoren und Insertoren gemein ist, mit der [basic-ios-Klasse](../standard-library/basic-ios-class.md) verwalten. Mehrere Manipulatoren sind an der Manipulation von Formatinformationen in Form von Extraktion und Insertion von Objekten beteiligt.  
  
 Sie können die gleiche iostreams-Vorgänge auch mithilfe der unter [\<fstream<](../standard-library/fstream.md) angegebenen Klassen auf Dateien anwenden, die Sie über den Dateinamen geöffnet haben. Um zwischen iostreams und Objekten der [basic_string-Klasse](../standard-library/basic-string-class.md) zu konvertieren, verwenden Sie die unter [\<sstream>](../standard-library/sstream.md) angegebenen Klassen. Um das gleiche mit C-Zeichenfolgen zu machen, verwenden Sie die unter [\<strstream>](../standard-library/strstream.md) angegebenen Klassen.  
  
 Die restlichen Headers bieten Supportdienste, die nur für sehr fortgeschrittene Benutzer der iostreams-Klassen von direktem Interesse sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

