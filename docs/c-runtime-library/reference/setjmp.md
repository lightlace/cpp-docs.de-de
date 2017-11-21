---
title: setjmp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: setjmp
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
f1_keywords: setjmp
dev_langs: C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 69704f5c7fd407addef7e886e4509f4f3cce1ebe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [_setjmp3](../../c-runtime-library/setjmp3.md)