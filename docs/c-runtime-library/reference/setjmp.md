---
title: "setjmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setjmp"
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
  - "setjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Programme [C++], Speichern von Zuständen"
  - "Aktueller Zustand"
  - "setjmp-Funktion"
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# setjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rettet den aktuellen Zustand des Programms.  
  
## Syntax  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### Parameter  
 `env`  
 Variable, in der die Umgebung gespeichert wird.  
  
## Rückgabewert  
 EINGABETASTE 0, wenn die Stapelumgebung gespeichert wurde.  Wenn `setjmp` aufgrund eines Aufrufs `longjmp` zurückgibt, wird der `value`\-Argument `longjmp` oder wenn das Argument `value` von `longjmp` 0 ist, `setjmp` gibt 1 zurück. zurück.  Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Die Funktion `setjmp` speichert eine Stapelumgebung, die Sie anschließend wiederherstellen können, mit `longjmp`.  Wenn sie zusammen verwendet werden, führen `setjmp` und `longjmp` eine Methode, nicht lokalen `goto` auszuführen.  Sie werden in der Regel verwendet, um dem Fehlerbehandlungs\- Ablaufsteuerung oder Wiederherstellungscode zuvor in einer aufgerufenen Routine zu übergeben, ohne das normale Aufrufen oder die Rückholkonventionen zu verwenden.  
  
 Ein Aufruf `setjmp` speichert die aktuelle Stapelumgebung in `env`.  Ein nachfolgender Aufruf `longjmp` wird die gespeicherte Umgebung und das Von zum Punkt direkt nach dem entsprechenden `setjmp` Aufruf zurückgesetzt.  Alle Variablen \(außer Registervariablen\) zugänglich zum empfangenden RoutineSteuerelement enthalten die Werte, die sie aufwiesen, als `longjmp` aufgerufen wurde.  
  
 Es ist nicht möglich, `setjmp` verwenden, um aus systemeigenen an verwalteten Code zu springen.  
  
 **Hinweis** `setjmp` und `longjmp` unterstützen keine C\+\+\-Objektsemantik.  In C\+\+\-Programmen verwenden Sie den C\+\+\-Ausnahmebehandlungsmechanismus.  
  
 Weitere Informationen finden Sie unter [Verwenden des setjmp und des longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`setjmp`|\<setjmp.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [\_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [\_setjmp3](../../c-runtime-library/setjmp3.md)