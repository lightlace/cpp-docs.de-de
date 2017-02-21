---
title: "_CrtSetAllocHook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetAllocHook"
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
  - "_CrtSetAllocHook"
  - "CrtSetAllocHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetAllocHook-Funktion"
  - "CrtSetAllocHook-Funktion"
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _CrtSetAllocHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installiert eine clientdefinierte Zuordnungsfunktion, indem sie mit dem C\-Laufzeit\-Debugspeicherbelegungsprozess verknüpft wird \(nur Debugversion\).  
  
## Syntax  
  
```  
_CRT_ALLOC_HOOK _CrtSetAllocHook(  
   _CRT_ALLOC_HOOK allocHook   
);  
```  
  
#### Parameter  
 `allocHook`  
 Die neue clientdefinierte Zuordnungsfunktion, die mit dem C\-Laufzeit\-Debugspeicherbelegungsprozess verknüpft werden soll.  
  
## Rückgabewert  
 Gibt die zuvor definierte Zuordnungshookfunktion oder `NULL` zurück, wenn `allocHook` den Wert `NULL` hat.  
  
## Hinweise  
 `_CrtSetAllocHook` ermöglicht es einer Anwendung, eine eigene Zuordnungsfunktion in den Speicherbelegungsprozess der C\-Laufzeit\-Debugbibliothek einzubinden.  Daher löst jeder Aufruf einer Debugzuordnungsfunktion für die Belegung, erneute Belegung oder Freigabe eines Speicherblocks einen Aufruf der Hookfunktion der Anwendung aus.  Die `_CrtSetAllocHook`\-Funktion bietet einer Anwendung eine einfache Methode, mit der getestet werden kann, wie die Anwendung Speichermangel behandelt. Darüber hinaus erhält die Anwendung die Möglichkeit, Reservierungsmuster zu überprüfen und Reservierungsinformationen für die spätere Analyse zu protokollieren.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetAllocHook` während der Vorverarbeitung entfernt.  
  
 Die `_CrtSetAllocHook`\-Funktion installiert die neue clientdefinierte Zuordnungsfunktion, die in `allocHook` angegeben ist, und gibt die zuvor definierte Hookfunktion zurück.  Das folgende Beispiel zeigt, wie ein Prototyp einer clientdefinierten Hookfunktion für Zuordnungen entwickelt werden soll:  
  
```  
int YourAllocHook( int allocType, void *userData, size_t size, int   
blockType, long requestNumber, const unsigned char *filename, int   
lineNumber);  
```  
  
 Das `allocType`\-Argument gibt den Typ des Zuordnungsvorgangs `(_HOOK_ALLOC`, `_HOOK_REALLOC` und `_HOOK_FREE` an, das den Aufruf der Hookfunktion der Zuordnung ausgelöst hat.  Wenn der Typ der auslösenden Zuordnung vom Typ `_HOOK_FREE` ist, ist `userData` ein Zeiger zum Benutzerdatenabschnitt des freizugebenden Speicherblocks.  Wenn der Typ der auslösenden Zuordnung jedoch vom Typ `_HOOK_ALLOC` oder `_HOOK_REALLOC` ist, entspricht `userData` `NULL`, da der Speicherblock noch nicht belegt wurde.  
  
 `size` gibt die Größe des Speicherblocks in Bytes an, `blockType` den Typ des Speicherblocks, `requestNumber` ist die Befehlsnummer der Objektzuordnung für den Speicherblock, und `filename` und `lineNumber`, sofern verfügbar, geben den Quelldateinamen und die Zeilennummer an, in der die auslösende Zuordnung initiiert wurde.  
  
 Nachdem die Hookfunktion verarbeitet wurde, muss sie einen booleschen Wert zurückgeben, der den C\-Laufzeit\-Hauptzuordnungsprozess anweist, wie das Verfahren fortgesetzt werden soll.  Wenn die Hookfunktion den Hauptzuordnungsprozess anweist, das Verfahren so fortzusetzen, als ob die Hookfunktion nie aufgerufen wurde, sollte die Hookfunktion den Wert `TRUE` zurückgeben.  Dadurch wird die ursprüngliche auslösende Zuordnung ausgeführt.  Mit dieser Implementierung kann die Hookfunktion Zuordnungsinformationen zur späteren Analyse erfassen und speichern, ohne das aktuelle Zuordnungsverfahren oder den Zustand des Debugheaps zu beeinträchtigen.  
  
 Wenn die Hookfunktion den Hauptzuordnungsprozess anweist, das Verfahren so fortzusetzen, als ob das auslösende Zuordnungsverfahren aufgerufen wurde und fehlgeschlagen ist, sollte die Hookfunktion den Wert `FALSE` zurückgeben.  Mit dieser Implementierung kann die Hookfunktion eine Vielzahl von Speicherbedingungen und Debugheapzuständen simulieren, um zu testen, wie die Anwendung die jeweilige Situation behandelt.  
  
 Um die Hookfunktion zu löschen, leiten Sie `NULL` an `_CrtSetAllocHook` weiter.  
  
 Weitere Informationen dazu, wie `_CrtSetAllocHook` mit anderen Speicherverwaltungsfunktionen verwendet werden kann oder wie eigene clientdefinierte Hookfunktionen geschrieben werden, finden Sie unter [Schreiben von Hookfunktionen zum Debuggen](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
> [!NOTE]
>  `_CrtSetAllocHook` wird nicht von `/clr:pure` unterstützt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtSetAllocHook`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `_CrtSetAllocHook` finden Sie unter [crt\_dbg2](assetId:///21e1346a-6a17-4f57-b275-c76813089167).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_CrtGetAllocHook](../../c-runtime-library/reference/crtgetallochook.md)