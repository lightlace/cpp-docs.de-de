---
title: "&lt; Codecvt &gt;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "codecvt"
  - "std::<codecvt>"
  - "std.<codecvt>"
  - "<codecvt>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt-Header"
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# &lt; Codecvt &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert mehrere Vorlagenklassen, die Objekte, die basierend auf der Vorlagenklasse beschreiben [Codecvt](../standard-library/codecvt-class.md). Diese Objekte können dienen als [gebietsschemafacets](../standard-library/locale-class.md#facet_class) Konvertierungen zwischen einer Sequenz von Werten des Typs steuern `Elem` und eine Sequenz von Werten des Typs `char`.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <codecvt>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die gebietsschemafacets in diesem Header deklariert Konvertieren zwischen mehreren zeichencodierungen. Für Breitzeichen (innerhalb des Programms in fester Größe ganzen Zahlen gespeichert):  
  
-   UCS-4 ist Unicode (ISO 10646) innerhalb des Programms codiert  
  
-   UCS-4 ist Unicode (ISO 10646) innerhalb der Anwendung als 32-Bit-Ganzzahl codiert.  
  
-   UCS-2 wird Unicode codiert innerhalb des Programms  
  
-   UCS-2 ist Unicode im Programm als 16-Bit-Ganzzahl codiert.  
  
-   UTF-16 wird Unicode codiert wurde, in die Anwendung als eine  
  
-   UTF-16 wird Unicode im Programm als ein oder zwei 16-Bit-Ganzzahlen codiert. (Beachten Sie, dass dies nicht alle Anforderungen von einer gültigen Breitzeichen-Codierung für Standard-C oder C++-Standard entspricht. Dennoch ist es daher verbreitet.)  
  
 Für Bytestreams (in einer Datei gespeichert, als ein Byte-Sequenz übertragen oder gespeichert, die innerhalb des Programms in einem Array von `char`):  
  
-   UTF-8 ist Unicode codiert  
  
-   UTF-8 ist Unicode als mindestens 8-Bit-Bytes mit deterministisch Byte Order in einen Bytestream codiert.  
  
-   UTF-16LE wird Unicode codiert  
  
-   UTF-16LE ist in einem Bytestream als UTF-16 codierte Unicode jeder 16-Bit-Ganzzahl, die zunächst als zwei 8-Bit-Bytes weniger signifikante Byte dargestellt.  
  
-   UTF-16BE wird Unicode codiert  
  
-   UTF-16BE ist in einem Bytestream als UTF-16 codierte Unicode jeder 16-Bit-Ganzzahl, die zunächst als zwei 8-Bit-Bytes, größere Byte dargestellt.  
  
### <a name="enumerations"></a>Enumerationen  
  
|||  
|-|-|  
|[codecvt_mode](../Topic/%3Ccodecvt%3E%20enums.md#codecvt_mode_enumeration)|Gibt die Konfigurationsinformationen für gebietsschemafacets an.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[codecvt_utf8](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf8)|Stellt die gebietsschemafacet zwischen Breitzeichen als UCS-2 oder UCS-4 codiert und eines Bytestreams, der als UTF-8 codiert konvertiert.|  
|[codecvt_utf8_utf16](%3Ccodecvt%3E%20functions.md#codecvt_utf8_utf16)|Stellt gebietsschemafacet zwischen Zeichen als UTF-16 codiert und eines Bytestreams, der als UTF-8 codiert konvertiert.|  
|[codecvt_utf16](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf16)|Stellt die gebietsschemafacet zwischen Breitzeichen als UCS-2 oder UCS-4 codiert und einem Bytestream codiert als UTF-16LE oder UTF-16BE konvertiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Codecvt>  
  
 **Namespace:** Stdt  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)




