---
title: "Speicherung von Bitfeldern"
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
  - "C"
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherung von Bitfeldern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.5.2.1** Die Reihenfolge der Zuordnung von Bitfeldern in einem "int"  
  
 Bitfelder werden innerhalb einer Ganzzahl vom niedrigstwertigen hin zum höchstwertigen Bit angeordnet.  Im folgenden Code etwa  
  
```  
struct mybitfields  
{  
   unsigned a : 4;  
   unsigned b : 5;  
   unsigned c : 7;  
} test;  
  
int main( void )  
{  
   test.a = 2;  
   test.b = 31;  
   test.c = 0;  
}  
```  
  
 wären die Bits folgendermaßen angeordnet:  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 Da die 80x86\-Prozessoren das niedrige Byte ganzzahliger Werte vor dem hohen Byte speichern, wird die oben stehende Ganzzahl 0x01F2 im physischen Speicher als 0xF2 gefolgt von 0x01 gespeichert.  
  
## Siehe auch  
 [Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)