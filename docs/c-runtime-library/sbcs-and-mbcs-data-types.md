---
title: "SBCS- und MBCS-Datentypen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MBCS"
  - "SBCS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SBCS- und MBCS-Datentypen"
  - "Datentypen [C], MBCS und SBCS"
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# SBCS- und MBCS-Datentypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede Laufzeitbibliotheksroutine Microsoft `MBCS`, die nur ein Mehrbytezeichen behandelt oder ein Byte eines Mehrbytezeichens erwartet ein Argument `unsigned``int` \(wobei 0x00 \<\= Zeichenwert \<\= 0xFFFF und 0x00\- \<\= Bytewert \<\= 0xFF\).  Eine `MBCS` \- Routine, die Mehrbytebytes oder \-Zeichen in einem Zeichenfolgenkontext behandelt, erwartet einer Mehrbyte\-Zeichenfolge, als Zeiger `unsigned``char` dargestellt.  
  
> [!CAUTION]
>  Jedes Byte eines Mehrbytezeichens kann in äußerst \- `char` dargestellt werden.  Eine `SBCS` oder ein `MBCS` Einzelbytezeichen des Typs `char` mit einem Wert, der größer als 0x7F negativ.,  Wenn ein solcher Zeichen direkt in `int` oder `long` konvertiert wird, wird das Ergebnis vom Compiler signaturerweitert und daher kann zu unerwarteten Ergebnissen führen.  
  
 Daher empfiehlt es sich, ein Byte eines Mehrbytezeichens als äußerst \- `unsigned char` darzustellen.  Oder, ein negatives Ergebnis vermeiden, ein Einzelbytezeichen des Typs `char` einfach an `unsigned char` konvertieren, bevor er von `int` oder `long` konvertiert wird.  
  
 Da einige `SBCS` ZeichenfolgeBehandlungsfunktionen `char*`\-Parameter \(mit Vorzeichen\), tritt `_MBCS` eine Compiler\-Warnung ausgegeben, definiert wird.  Es gibt drei Möglichkeiten, diese Warnung zu vermeiden, aufgeführt in der Reihenfolge der Effizienz:  
  
1.  Verwenden Sie die typsicheren "" Inlinefunktionen in TCHAR.H.  Dies ist das Standardverhalten.  
  
2.  Verwenden Sie "verweisen" macros in TCHAR.H, indem Sie in der Befehlszeile `_MB_MAP_DIRECT` definieren.  In diesem Fall müssen Sie die Typübereinstimmung manuell sicherstellen.  Dies ist die schnellste Methode, jedoch nicht typsicher ist.  
  
3.  Verwenden Sie die typsicheren statisch verknüpften "" Bibliotheksfunktionen in TCHAR.H.  Definieren Sie hierzu in der Befehlszeile die Konstante `_NO_INLINING`.  Dies ist die langsamste Methode; sie bietet jedoch auch die größte Typsicherheit.  
  
## Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)