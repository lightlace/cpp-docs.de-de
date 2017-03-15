---
title: "Puffer&#252;berlauf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Pufferüberläufe [C++]"
  - "Puffer [C++], Zeichengrößen"
  - "MBCS [C++], Pufferüberlauf"
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Puffer&#252;berlauf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterschiedliche Zeichengrößen führen unter Umständen zu Problemen, wenn Zeichen in einem Puffer gespeichert werden.  Betrachten Sie den folgenden Code, von dem Zeichen aus der Zeichenfolge `sz` in den Puffer `rgch` kopiert werden:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 Folgende Frage stellt sich: War das zuletzt kopierte Byte ein führendes Byte?  Der folgende Code löst das Problem nicht, da durch seine Ausführung ein Pufferüberlauf verursacht werden kann:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Durch den `_mbccpy`\-Aufruf wird versucht, das Zeichen vollständig zu kopieren, unabhängig davon, ob es sich um ein oder zwei Bytes handelt.  Dabei wird jedoch nicht berücksichtigt, dass das letzte Zeichen möglicherweise nicht im Puffer abgelegt werden kann, wenn das Zeichen eine Länge von zwei Bytes hat.  Die richtige Lösung lautet wie folgt:  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Im Rahmen des Schleifentests wird von diesem Code zunächst ein Test bezüglich eines möglichen Pufferüberlaufs durchgeführt. Hierbei wird mit `_mbclen` die Größe des Zeichens überprüft, auf das derzeit durch `sz` verwiesen wird.  Wenn Sie die `_mbsnbcpy`\-Funktion aufrufen, können Sie den Code in der `while`\-Schleife durch eine einzelne Codezeile ersetzen.  Beispiel:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## Siehe auch  
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)