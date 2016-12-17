---
title: "offsetof-Makro"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "offsetof"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "offsetof-Makro"
  - "Strukturmember, Offset"
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# offsetof-Makro
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Offset eines Elements vom Anfang seiner übergeordneten Struktur ab.  
  
## Syntax  
  
```  
  
        size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### Parameter  
 *structName*  
 Der Name der übergeordneten Datenstruktur.  
  
 `memberName`  
 Der Name des Elements in der übergeordneten Datenstruktur, für das der Offset bestimmt werden soll.  
  
## Rückgabewert  
 `offsetof` gibt den Offset des angegebenen Elements vom Anfang seiner übergeordneten Datenstruktur in Bytes zurück.  Ist für Bitfelder nicht definiert.  
  
## Hinweise  
 Der `offsetof`\-Makro gibt den Offset von `memberName` vom Anfang der Struktur, die von *StructName* als ein Wert vom Typ `size_t` festgelegt ist, in Bytes zurück.  Sie können Typen mit dem `struct`\-Schlüsselwort angeben.  
  
> [!NOTE]
>  `offsetof` ist keine Funktion und kann nicht mit einem C\-Prototyp beschrieben werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`offsetof`|\<stddef.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)