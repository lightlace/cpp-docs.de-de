---
title: "Linkertoolfehler LNK2004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2004"
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK2004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

gp relativer Fixup\-Überlauf zu 'Ziel'; der short\-Abschnitt 'Abschnitt' ist zu groß oder liegt außerhalb des gültigen Bereichs.  
  
 Der Abschnitt war zu groß.  
  
 Um diesen Fehler zu beheben, verringern Sie die Größe des short\-Abschnitts, indem Sie in den long\-Abschnitten mit \#pragma section\(".sectionname", read, write, long\) Daten explizit einfügen und `__declspec(allocate(".sectionname"))` für Datendefinitionen und \-deklarationen verwenden.  Beispiel:  
  
```  
#pragma section(".data$mylong", read, write, long)  
__declspec(allocate(".data$mylong"))  
char    rg0[1] = { 1 };  
char    rg1[2] = { 1 };  
char    rg2[4] = { 1 };  
char    rg3[8] = { 1 };  
char    rg4[16] = { 1 };  
char    rg5[32] = { 1 };  
```  
  
 Sie können auch logisch gruppierte Daten in ihre eigene Struktur verschieben, die eine Auflistung von Daten mit einer Größe von mehr als 8 Bytes darstellt und vom Compiler einem Abschnitt mit long\-Daten zugewiesen wird.  Beispiel:  
  
```  
// from this...  
int     w1  = 23;  
int     w2 = 46;  
int     w3 = 23*3;  
int     w4 = 23*4;  
  
// to this...  
struct X {  
    int     w1;  
    int     w2;  
    int     w3;  
    int     w4;  
} x  = { 23, 23*2, 23*3, 23*4 };  
  
```  
  
 Auf diesen Fehler folgt der schwerwiegende Fehler `LNK1165`.