---
title: setjmp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- setjmp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d13a24974a6c722301c6361a13f9d9178cd70220
ms.lasthandoff: 02/24/2017

---
# <a name="setjmp"></a>setjmp
Speichert den aktuellen Zustand des Programms.  
  
## <a name="syntax"></a>Syntax  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `env`  
 Variable, in der die Umgebung gespeichert wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 zurück, wenn die Stapelumgebung gespeichert wurde. Wenn `setjmp` als Ergebnis eines `longjmp`-Aufrufs zurückgibt, gibt es das `value`-Argument von `longjmp` zurück. Wenn das `value`-Argument von `longjmp` 0 ist, gibt `setjmp` 1 zurück. Es gibt keine Fehlerrückgabe.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `setjmp` speichert eine Stapelumgebung, die Sie anschließend mit `longjmp` wiederherstellen können. Wenn Sie `setjmp` und `longjmp` zusammen verwenden, können Sie ein nichtlokales `goto` ausführen. Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die normalen Aufruf- oder Rückgabekonventionen zu verwenden.  
  
 Ein Aufruf von `setjmp` speichert die aktuelle Stapelumgebung in `env`. Ein nachfolgender Aufruf von `longjmp` stellt die gespeicherte Umgebung wieder her und übergibt die Steuerung an den Punkt direkt nach dem entsprechenden `setjmp`-Aufruf. Alle Variablen (mit Ausnahme der Variablen „register“), die für die für das Steuerelement zur Routineerfassung zugänglich sind, erhalten die ursprünglichen Werte des `longjmp`-Aufrufs.  
  
 Es ist nicht möglich, `setjmp` zu verwenden, um von nativen in verwalteten Code zu springen.  
  
 **Hinweis** `setjmp` und `longjmp` unterstützen keine Semantik für C++-Objekte. Verwenden Sie den C++-Mechanismus für die Ausnahmebehandlung in C++-Programmen.  
  
 Weitere Informationen finden Sie unter [Verwenden von „setjmp/longjmp“](../../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`setjmp`|\<setjmp.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [_setjmp3](../../c-runtime-library/setjmp3.md)
