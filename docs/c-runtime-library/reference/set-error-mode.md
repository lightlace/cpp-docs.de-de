---
title: "_set_error_mode"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_set_error_mode"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_error_mode"
  - "_set_error_mode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_error_mode-Funktion"
  - "set_error_mode-Funktion"
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _set_error_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert `__error_mode`, um einen nicht standardmäßigen Speicherort zu bestimmen, an dem die C\-Laufzeit eine Fehlermeldung für einen Fehler schreibt, der das Programm beenden kann.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### Parameter  
 `modeval`  
 Ziel der Fehlermeldungen.  
  
## Rückgabewert  
 Gibt die alte Einstellung oder \-1 zurück, wenn ein Fehler auftritt.  
  
## Hinweise  
 Steuert die Fehlerausgabesenke durch Festlegen des Werts von `__error_mode`.  Sie können z. B. die Ausgabe in einen Standardfehler umleiten oder die `MessageBox`\-API verwenden.  
  
 Der Parameter `modeval` kann auf einen der folgenden Werte festgelegt werden:  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`_OUT_TO_DEFAULT`|Fehlersenke wird durch `__app_type` bestimmt.|  
|`_OUT_TO_STDERR`|Fehlersenke ist ein Standardfehler.|  
|`_OUT_TO_MSGBOX`|Fehlersenke ist ein Meldungsfeld.|  
|`_REPORT_ERRMODE`|Melden Sie den aktuellen `__error_mode`\-Wert.|  
  
 Wenn ein anderer Wert als die aufgeführten übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt `_set_error_mode` `errno` auf `EINVAL` fest und gibt \-1 zurück.  
  
 Bei Verwendung mit [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) zeigt `_set_error_mode` die fehlerhafte Anweisung im Dialogfeld an und bietet Ihnen die Möglichkeit, die `Ignore`\-Schaltfläche auszuwählen, sodass Sie das Programm weiter ausführen können.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_set_error_mode`|\<stdlib.h\>|  
  
## Beispiel  
  
```  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
  **Assertionsfehler: 2\+2\=\=5, file crt\_set\_error\_mode.c, line 8**  
**Diese Anwendung hat ein nicht ordnungsgemäßes Beenden der Runtime angefordert.  Weitere Informationen erhalten Sie von dem für die Anwendung zuständigen Supportteam.**    
## Siehe auch  
 [assert\-Makro, \_assert, \_wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)