---
title: "SEGMENT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEGMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SEGMENT directive"
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# SEGMENT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert ein Programm segment, das *den Namen* aufgerufen wird, der Segmentattribute hat  
  
## Syntax  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### Parameter  
 *align*  
 Der Bereich Speicherorte, von denen eine Startadresse für das Segment ausgewählt werden kann.  Der Typ der Ausrichtung kann einer der folgenden Werte sein:  
  
|Ausrichten Typ aus|Startadresse|  
|------------------------|------------------|  
|**BYTE**|Der nächste verfügbare Byte adresse.|  
|**WORD**|Der nächste verfügbare Wort adresse \(2 Bytes pro Wort.\)|  
|**DWORD**|Der nächste verfügbare Doppelwort adresse \(4 Bytes pro Doppelwort\).|  
|**PARA**|Der nächste verfügbare Absatz adresse \(16 Bytes pro Absatz\).|  
|**PAGE**|Der nächste verfügbare Seiten adresse \(256 Byte pro Seite\).|  
|**AUSRICHTEN**\(N\)|Der nächste verfügbare *N\-ten*Byte adresse.  Weitere Informationen finden Sie in Abschnitt " Hinweise ".|  
  
 Wenn dieser Parameter nicht angegeben, wird standardmäßig **PARA** verwendet.  
  
 *In Kombination*  
 **ÖFFENTLICH**, **STAPEL**, **ALLGEMEIN**, **ARBEITSSPEICHER**, **ON***Adresse*, **PRIVATE**  
  
 *Verwendung*  
 **USE16**, **USE32**, **FLAT**  
  
 `characteristics`  
 INFORMATION, **READ**, **WRITE**, **AUSFÜHREN**, **SHARED**, **NOPAGE**, **NOCACHE**und **DISCARD**  
  
 Diese sind ausschließlich für das COFF\-Format unterstützt und entsprechen den COFF\-Abschnitts ähnliche Eigenschaften des Namens \(zum Beispiel entspricht **SHARED** zu IMAGE\_SCN\_MEM\_SHARED\).  READ IMAGE\_SCN\_MEM\_READ\-Flag legt dieses fest.  Die veraltete SCHREIBGESCHÜTZTE Flag, das den Abschnitt des IMG\_SCN\_MEM\_WRITE\-Flag zu löschen.  Wenn eine werden `characteristics` festgelegt, werden die Standardeigenschaften nicht verwendet und werden nur die vom Programmierer bereitgestellten Flags sind in Kraft.  
  
 `ALIAS(` `string` `)`  
 Diese Zeichenfolge wird als der Abschnittsname im ausgegebenen COFF\-Objekt verwendet.  Erstellt mehrere Abschnitte, externe Namen mit demselben Namen einer anderen MASM\-Segment.  
  
 Unterstützt nicht mit **\/omf**.  
  
 `class`  
 Legt fest, wie Segmente in der Datei assemblierten kombiniert und geordnet werden sollen.  Typische Werte sind `'DATA'`, `'CODE'`, `'CONST'` und `'STACK'`  
  
## Hinweise  
 Für `ALIGN(``n``)`, `n` kann eine Potenz von 2 bis 8192, wobei 1 **\/omf**nicht unterstützt.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)