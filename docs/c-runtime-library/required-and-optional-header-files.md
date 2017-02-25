---
title: "Erforderliche und optionale Headerdateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.headers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Headerdateien, erforderlich zur Laufzeit"
  - "Includedateien, erforderlich zur Laufzeit"
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erforderliche und optionale Headerdateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Beschreibung jeder Ablaufroutine enthält eine Liste der erforderlichen und optionalen gehören oder Header \(. H\), Dateien für diese Routine.  Erforderliche Headerdateien müssen vorhanden sein, um die Funktionsdeklaration für die Routine oder eine Definition zu erhalten, die von einer anderen Routine verwendet wird, die intern aufgerufen wird.  Optionale Headerdateien werden normalerweise enthalten, um vordefinierter Konstanten, Typdefinitionen oder inline Makros zu nutzen.  Die folgende Tabelle zeigt einige Beispiele des optionalen Headerdateiinhalts auf:  
  
|Definition|Beispiel|  
|----------------|--------------|  
|Makrodefinition|Wenn eine Bibliotheksroutine als Makro implementiert wird, könnte die Makrodefinition in einer Headerdatei anders die Headerdatei für die ursprüngliche Routine.  Beispielsweise wird das `_toupper`\-Makro in der Headerdatei definiert CTYPE.H, während die Funktion `toupper` in STDLIB.H. deklariert wird.|  
|Vordefinierte Konstante|Viele Bibliotheksroutinen verweisen auf Konstanten an, die in den Headerdateien definiert werden.  Beispielsweise die Konstanten `_open` routinemäßiger Einsätze wie `_O_CREAT`, die in der Headerdatei FCNTL.H. definiert wird.|  
|Typdefinition|Einige Bibliotheksroutinen geben eine Struktur zurück oder nehmen eine Struktur als Argument.  Beispielsweise verwenden Streameingabe\/ausgabe\-Routinen eine Struktur des Typs `FILE`, der in STDIO.H. definiert wird.|  
  
 Die Laufzeitbibliotheksheaderdateien stellen Funktionsdeklarationen empfohlenen im Format ANSI\/ISO C Standard.  Der Compiler führt Typüberprüfung auf jedem Routineverweis aus, der nach der zugeordneten Funktionsdeklaration auftritt.  sind für Funktionsdeklarationen Routinen besonders wichtig, die einen Wert eines Typs als `int` zurückgeben, Standard.  Routinen, die nicht den entsprechenden Rückgabewert in ihrer Deklaration angeben, werden vom Compiler betrachtet, `int` zurückzugeben, die unerwartete Ergebnisse verursachen kann.  Weitere Informationen finden Sie unter [Typüberprüfung](../c-runtime-library/type-checking-crt.md).  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)