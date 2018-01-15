---
title: '&lt;strstream&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <strstream>
dev_langs: C++
helpviewer_keywords: strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91e127c30b8e360295d7451aa4b35ca8bd420e52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;
Definiert mehrere Klassen, die iostreams-Vorgänge für Sequenzen unterstützt, die in einem reservierten Array des `char`-Objekts gespeichert werden. Solche Sequenzen sind leicht in und aus C-Zeichenfolgen zu konvertieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <strstream>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Objekte vom Typ `strstream` arbeiten mit `char` *, die C-Zeichenfolgen darstellen. Verwenden Sie [\<sstream>](../standard-library/sstream.md) zum Arbeiten mit Objekten des Typs [basic_string](../standard-library/basic-string-class.md).  
  
> [!NOTE]
>  Die Klassen in `<strstream>` sind veraltet. Verwenden Sie stattdessen die Klassen in `<sstream>`.  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[strstreambuf-Klasse](../standard-library/strstreambuf-class.md)|Die Klasse beschreibt einen Streampuffer, der die Übertragung von Elementen in eine bzw. aus einer Sequenz von Elementen steuert, die in einem `char`-Arrayobjekt gespeichert sind.|  
|[istrstream-Klasse](../standard-library/istrstream-class.md)|Die Klasse beschreibt ein Objekt, das die Extraktion von Elementen und codierten Objekten aus einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|  
|[ostrstream-Klasse](../standard-library/ostrstream-class.md)|Die Klasse beschreibt ein Objekt, das die Einfügung von Elementen und codierten Objekten in einen Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|  
|[strstream-Klasse](../standard-library/strstream-class.md)|Die Klasse beschreibt ein Objekt, das die Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|  
  
## <a name="see-also"></a>Siehe auch  
 [\<strstream>](../standard-library/strstream.md)   
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)



