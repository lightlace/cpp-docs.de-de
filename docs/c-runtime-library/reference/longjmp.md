---
title: "longjmp"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "longjmp"
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
  - "longjmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "longjmp-Funktion"
  - "Wiederherstellen der Stapelumgebung und des Ausführungsgebietschemas"
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# longjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wiederherstellungsstapelumgebung und Ausführungsgebietsschema.  
  
## Syntax  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### Parameter  
 `env`  
 Variable, in der die Umgebung gespeichert wird.  
  
 *Wert*  
 Um `setjmp` Aufruf zurückgegeben werden, Wert.  
  
## Hinweise  
 `longjmp` Die Funktion stellt einen Stapelumgebungs\- und \-ausführungsgebietsschema zurückgesetzt, das zuvor in `env` vom `setjmp` gespeichert wird.  `setjmp` und `longjmp` bieten eine Möglichkeit, nicht lokalen `goto` auszuführen; Sie werden in der Regel verwendet, um dem Fehlerbehandlungs\- Ablaufsteuerung oder Wiederherstellungscode zuvor in einer aufgerufenen Routine zu übergeben, ohne die Aufrufs\- normalen und Rückholkonventionen zu verwenden.  
  
 Ein Aufruf von `setjmp` wird die aktuelle Stapelumgebung, in `env` gespeichert.  Ein nachfolgender Aufruf `longjmp` wird die gespeicherte Umgebung und das Von zum Punkt direkt nach dem entsprechenden `setjmp` Aufruf zurückgesetzt.  Ausführungszusammenfassungen, als ob *Wert* gerade durch den Aufruf `setjmp` zurückgegeben wurde.  Die Werte aller Variablen \(außer Registervariablen\) das dem RoutineSteuerelement empfangenden zugänglich sind, enthalten die Werte, die sie aufwiesen, als `longjmp` aufgerufen wurde.  Die Werte von Registervariablen sind unvorhersehbar.  Der Wert, der von `setjmp` zurückgegeben, muss ungleich 0 \(null\) sein.  Wenn als *Wert* 0 übergeben wird, wird der Wert 1 in der eigentlichen Beendigung ersetzt.  
  
 Rufen Sie `longjmp` vor der Funktion, die `setjmp` zurückgibt aufgerufen hat; andernfalls sind die Ergebnisse unvorhersehbar.  
  
 Beachten Sie die folgenden Einschränkungen, wenn `longjmp` verwendet wird:  
  
-   Nehmen Sie nicht an, dass die Werte der Registervariablen gleich bleiben.  Die Werte von Registervariablen aufrufenden nicht in `setjmp` werden den richtigen Werten wiederhergestellt werden, nachdem `longjmp` ausgeführt.  
  
-   Verwenden Sie `longjmp` nicht zur Steuerung aus einer UnterbrechungBehandlungsroutine out, es sei denn, die Unterbrechung durch eine Gleitkommaausnahme verursacht wird.  In diesem Fall kehrt ein Programm möglicherweise von einem Unterbrechungssteuerungsprogramm zu `longjmp` zurück, wenn es zuerst das mathematische GleitkommaPaket initialisiert, indem Sie `_fpreset` aufrufen.  
  
     **Notiz** gibt acht, wenn `setjmp` und `longjmp` in C\+\+\-Programmen verwendet.  Da diese Funktionen nicht C\+\+\-Objektsemantik unterstützen, ist es sicherer, den C\+\+\-Ausnahmebehandlungsmechanismus zu verwenden.  
  
 Weitere Informationen finden Sie unter [Verwenden des setjmp und des longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`longjmp`|\<setjmp.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Im Beispiel für [\_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)