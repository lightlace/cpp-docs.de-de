---
title: "_CrtIsValidPointer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtIsValidPointer"
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
  - "CrtlsValidPointer"
  - "_CrtIsValidPointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtIsValidPointer-Funktion"
  - "CrtIsValidPointer-Funktion"
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _CrtIsValidPointer
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt sicher, dass ein Zeiger nicht NULL ist.  Überprüft in älteren Versionen der C\-Laufzeitbibliothek als Visual Studio 2010, ob ein angegebener Speicherbereich für Lese\- und Schreibvorgänge gültig ist \(nur Debugversion\).  
  
## Syntax  
  
```  
int _CrtIsValidPointer(   
   const void *address,  
   unsigned int size,  
   int access   
);  
```  
  
#### Parameter  
 Adresse  
 Weist auf den Anfang des Speicherbereichs zum Prüfen der Gültigkeit.  
  
 `size`  
 Die Größe des angegebenen Speicherbereichs \(in Bytes\).  
  
 Zugriff  
 Für den Speicherbereich zu bestimmende Lese\/Schreib\-Barrierefreiheit.  
  
## Rückgabewert  
 `_CrtIsValidPointer` gibt TRUE zurück, wenn ein Zeiger nicht NULL ist.  Gibt in älteren CRT\-Bibliotheksversionen als Visual Studio TRUE zurück, wenn der Speicherbereich für den angegebenen Vorgang bzw. die Vorgänge gültig ist.  Andernfalls gibt die Funktion FALSE zurück.  
  
## Hinweise  
 Ab der CRT\-Bibliothek in Visual Studio 2010 werden die Größen\- und Zugriffsparameter ignoriert, und `_CrtIsValidPointer` überprüft nur, ob die angegebene Adresse nicht NULL ist.  Da sich dieser Test leicht manuell ausführen lässt, wird nicht empfohlen, diese Funktion zu verwenden.  Die Funktion überprüft in älteren Versionen als Visual Studio 2010, ob der Speicherbereich, der bei `size` beginnt und für `address` Bytes erweitert wird, für die angegebenen Barrierefreiheitsvorgänge gültig ist.  Wenn `access` auf TRUE festgelegt ist, wird der Speicherbereich für Lese\- und Schreibvorgänge überprüft.  Wenn `access` auf FALSE festgelegt ist, wird der Speicherbereich nur für Lesevorgänge überprüft.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtIsValidPointer` während der Vorverarbeitung entfernt.  
  
 Da diese Funktion TRUE oder FALSE zurückgibt, kann sie an eine der [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)\-Makros übergeben werden, um einen einfachen Debug\-Fehlerbehandlungsmechanismus zu erstellen.  Im folgenden Beispiel wird eine Assertionsmeldung ausgelöst, wenn der Speicherbereich für Lese\- und Schreibvorgänge ungültig ist:  
  
```  
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );  
```  
  
 Weitere Informationen dazu, wie `_CrtIsValidPointer` mit anderen Debugfunktionen und \-makros verwendet werden kann, finden Sie unter [Makros für die Berichterstellung](../Topic/Macros%20for%20Reporting.md).  Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtIsValidPointer`|\<crtdbg.h\>|  
  
 `_CrtIsValidPointer` ist eine Microsoft\-Erweiterung.  Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Weitere Informationen hierzu finden Sie im Beispiel für das Thema [\_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)