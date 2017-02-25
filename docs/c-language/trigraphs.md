---
title: "Trigraphen | Microsoft Docs"
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
  - "? Symbol, Trigraph"
  - "??-Trigraph"
  - "??'-Trigraph"
  - "??--Trigraph"
  - "??!-Trigraph"
  - "??)-Trigraph"
  - "??/-Trigraph"
  - "??<-Trigraph"
  - "??=-Trigraph"
  - "??>-Trigraph"
  - "Fragezeichen, In Trigraphen"
  - "Trigraphen"
ms.assetid: 617f76ec-b8e8-4cfe-916c-4bc32cbd9aeb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Trigraphen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Quellzeichensatz von C\-Quellprogrammen ist im 7\-Bit\-ASCII\-Zeichensatz enthalten, ist aber eine Obermenge des Invariantencodesatzes nach ISO 646\-1983.  Trigraphsequenzen ermöglichen es, C\-Programme ausschließlich mit dem Invariantencodesatz nach ISO\(International Standards Organization\) zu schreiben.  Trigraphen sind Sequenzen von drei Zeichen, die mit zwei aufeinander folgenden Fragezeichen beginnen, und werden vom Compiler durch die entsprechenden Interpunktionszeichen ersetzt.  Sie können Trigraphen in C\-Quelldateien verwenden, die einen Zeichensatz besitzen, der für einige Interpunktionszeichen keine passenden grafischen Darstellungen enthält.  
  
 Die folgende Tabelle zeigt die neun Trigraphsequenzen.  Alle in einer Quelldatei vorkommenden Interpunktionszeichen in der ersten Spalte werden durch das entsprechende Zeichen in der zweiten Spalte ersetzt.  
  
### Trigraphsequenzen  
  
|Trigraph|Interpunktionszeichen|  
|--------------|---------------------------|  
|??\=|\#|  
|??\(|\[|  
|??\/|\\|  
|??\)|\]|  
|??'|^|  
|??\<|{|  
|??\!|&#124;|  
|??\>|}|  
|??\-|~|  
  
 Ein Trigraph wird immer als einzelnes Quellzeichen behandelt.  Die Übersetzung von Trigraphen findet in der ersten [Übersetzungsphase](../preprocessor/phases-of-translation.md) statt, bevor die Erkennung von Escapezeichen in Zeichenfolgenliteralen und Zeichenkonstanten stattfindet.  Nur die neun Trigraphen, die in der obigen Tabelle angegeben sind, werden erkannt.  Alle anderen Zeichensequenzen werden unübersetzt gelassen.  
  
 Die Escapesequenz für Zeichen, **\\?**, verhindert die Fehlinterpretation von Zeichenfolgen, die einem Trigraphen ähneln. Informationen zu Escapesequenzen finden Sie unter [Escapesequenzen](../c-language/escape-sequences.md). Nehmen wir einmal an, Sie versuchen, die Zeichenfolge `What??!` mit dieser `printf`\-Anweisung zu drucken:  
  
```  
printf( "What??!\n" );  
```  
  
 Die gedruckte Zeichenfolge lautet `What|`, da `??!` eine Trigraphsequenz ist, die mit dem Zeichen          `|` ersetzt wurde.  Schreiben Sie die Anweisung wie folgt, um die Zeichenfolge ordnungsgemäß auszugeben:  
  
```  
printf( "What?\?!\n" );  
```  
  
 In dieser `printf`\-Anweisung verhindert der umgekehrte Schrägstrich als Escapezeichen vor dem zweiten Fragezeichen die Fehlinterpretation von `??!` als Trigraph.  
  
## Siehe auch  
 [C\-Bezeichner](../c-language/c-identifiers.md)