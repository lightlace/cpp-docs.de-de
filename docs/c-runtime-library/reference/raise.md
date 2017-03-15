---
title: raise | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- raise
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- Raise
dev_langs:
- C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
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
ms.openlocfilehash: ff8b387b81487e0c39ba5018487a1b8045bd0574
ms.lasthandoff: 02/24/2017

---
# <a name="raise"></a>raise
Sendet ein Signal an das ausführende Programm.  
  
> [!NOTE]
>  Verwenden Sie diese Methode nicht, um eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-App zu schließen, außer bei Tests oder in Debugszenarios. Programmgesteuerte oder UI-Methoden zum Schließen einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-App sind gemäß Abschnitt 3.6 der [Zertifizierungsanforderungen für Windows 8-Apps](http://go.microsoft.com/fwlink/?LinkId=262889) nicht zulässig. Weitere Informationen finden Sie unter [Anwendungslebenszyklus (Windows Store-Apps)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *sig*  
 Auszulösendes Signal.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg gibt **raise** 0 zurück . Andernfalls gibt es einen Wert ungleich&0; (null) zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die **raise**-Funktion sendet *sig* an das ausführende Programm. Wenn ein vorheriger Aufruf von **signal** eine Signalverarbeitungsfunktion für *sig* installiert hat, führt **raise** diese Funktion aus. Wenn keine Handlerfunktion installiert wurde, wird die dem Signalwert *sig* zugeordnete Standardaktion wie folgt ausgeführt.  
  
|Signal|Bedeutung|Default|  
|------------|-------------|-------------|  
|`SIGABRT`|Nicht ordnungsgemäße Beendigung|Beendet das aufrufende Programm mit Exitcode 3|  
|`SIGFPE`|Gleitkommafehler|Beendet das aufrufende Programm|  
|`SIGILL`|Ungültige Anweisung|Beendet das aufrufende Programm|  
|`SIGINT`|STRG+C-Unterbrechung|Beendet das aufrufende Programm|  
|`SIGSEGV`|Ungültiger Speicherzugriff|Beendet das aufrufende Programm|  
|`SIGTERM`|An das Programm gesendete Beendigungsanforderung|Ignoriert das Signal|  
  
 Wenn das Argument kein gültiges Signal gemäß den oberen Angaben ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Falls keine Behandlung erfolgt, legt die Funktion `errno` auf `EINVAL` fest und gibt einen Wert ungleich&0; (null) zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|**raise**|\<signal.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [signal](../../c-runtime-library/reference/signal.md)
