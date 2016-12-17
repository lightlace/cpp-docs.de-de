---
title: "Zeichenzuweisungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichen [C++], Zuweisungen"
  - "MBCS [C++], Zeichenzuweisungen"
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "ghogen"
manager: "ghogen"
---
# Zeichenzuweisungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sehen Sie sich das folgende Beispiel an, in dem die `while`\-Schleife eine Zeichenfolge scannt und alle Zeichen mit Ausnahme des 'X' in eine andere Zeichenfolge kopiert:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 Dieser Code kopiert das Byte in `sz2` an den Ort, auf den durch `sz1` verwiesen wird. Danach wird `sz1` für den Empfang des nächsten Byte inkrementiert.  Wenn es sich beim nächsten Zeichen in `sz2` jedoch um ein Doppelbytezeichen handelt, wird von der Zuordnung zu `sz1` lediglich das erste Byte kopiert.  Der folgende Code verwendet eine portable Funktion, um das Zeichen sicher zu kopieren und `sz1` und `sz2` richtig zu inkrementieren:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## Siehe auch  
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)   
 [Zeichenvergleich](../text/character-comparison.md)