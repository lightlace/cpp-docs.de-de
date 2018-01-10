---
title: longjmp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: longjmp
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
f1_keywords: longjmp
dev_langs: C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 864aacbc30d9d50e1d0335d0d74c7ed63119d132
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="longjmp"></a>longjmp
Stellt die Stapelumgebung und das Ausführungsgebietschema wieder her  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `env`  
 Variable, in die die Umgebung gespeichert wird  
  
 *Wert*  
 Der Wert, der dem Aufruf `setjmp` zurückgegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `longjmp` stellt eine Stapelumgebung und das Ausführungsgebietsschema wieder her, was zuvor von `setjmp` in `env` gespeichert wurde. `setjmp` und `longjmp` können in der Regel eine nicht lokale `goto`-Variable ausführen. Diese werden normalerweise verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die standardmäßigen Aufruf- oder Rückgabekonventionen zu verwenden.  
  
 Ein Aufruf von `setjmp` speichert die aktuelle Stapelumgebung in `env`. Ein nachfolgender Aufruf von `longjmp` stellt die gespeicherte Umgebung wieder her und übergibt die Steuerung an den Punkt sofort nach dem entsprechenden `setjmp`-Aufruf. Die Ausführung wird fortgesetzt, als ob der *Wert* gerade vom `setjmp`-Aufruf zurückgegeben worden wäre. Die Werte aller Variablen (mit Ausnahme der Variablen „register“), die für die für das Steuerelement zur Routineerfassung zugänglich sind, erhalten die ursprünglichen Werte des `longjmp`-Aufrufs. Die Werte der Registervariablen sind unvorhersehbar. Der Wert, der von `setjmp` zurückgegeben wird, muss ungleich null sein. Wenn der *Wert* als 0 übergeben wird, wird der Wert 1 in der tatsächlichen Rückgabe ersetzt.  
  
 Rufen Sie `longjmp` auf, bevor die Funktion zurückgegeben wird, die `setjmp` aufruft. Andernfalls sind die Ergebnisse unvorhersehbar.  
  
 Beachten Sie außerdem die folgenden Einschränkungen, wenn Sie `longjmp` verwenden:  
  
-   Gehen Sie nicht davon aus, dass die Werte der Registervariablen unverändert bleiben. Die Werte der Registervariablen in der Routine, die `setjmp` aufrufen, können nicht mehr auf die richtigen Werte wiederhergestellt werden, nachdem `longjmp` ausgeführt wurde.  
  
-   Verwenden Sie nicht `longjmp`, um das Steuerelement aus einer Interruptbehandlungsroutine zu übertragen, es sei denn, der Interrupt wurde durch eine Gleitkommaausnahme hervorgerufen. In diesem Fall kann ein Programm aus einem Interrupthandler über `longjmp` zurückgegeben werden, wenn das mathematische Gleitkommazahlpaket durch Aufrufen von `_fpreset` erneut initialisiert wird.  
  
     **Hinweis**: Vorsicht bei der Verwendung von `setjmp` und `longjmp` in C++-Programmen. Da diese Funktionen keine C++-Objektsemantik unterstützt, ist es sicherer, den C++-Mechanismus zur Behandlung von Ausnahmen zu verwenden.  
  
 Weitere Informationen finden Sie unter [Verwenden von „setjmp/longjmp“](../../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`longjmp`|\<setjmp.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)