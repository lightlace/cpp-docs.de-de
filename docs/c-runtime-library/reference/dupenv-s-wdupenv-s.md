---
title: _dupenv_s, _wdupenv_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dupenv_s
- _wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
dev_langs: C++
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c42da9004dc5ea63179d94a36335db3932f5d23b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s, _wdupenv_s
Ruft einen Wert aus der aktuellen Umgebung ab.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _dupenv_s(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname  
);  
errno_t _wdupenv_s(  
   wchar_t **buffer,  
   size_t *numberOfElements,  
   const wchar_t *varname  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Puffer zum Speichern des Variablenwerts.  
  
 `numberOfElements`  
 Größe von `buffer`.  
  
 `varname`  
 Umgebungsvariablenname.  
  
## <a name="return-value"></a>Rückgabewert  
 Null bei Erfolg, ein Fehlercode, wenn ein Fehler auftritt.  
  
 Diese Funktionen überprüfen ihre Parameter; wenn `buffer` oder `varname` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legen die Funktionen `errno` auf `EINVAL` fest und geben `EINVAL` zurück.  
  
 Wenn diese Funktionen nicht genug Arbeitsspeicher zuordnen können, legen sie `buffer` auf `NULL` und `numberOfElements` auf 0 fest und geben `ENOMEM` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_dupenv_s`-Funktion sucht die Liste von Umgebungsvariablen für `varname`. Wenn die Variable gefunden wird, ordnet `_dupenv_s` einen Puffer zu und kopiert den Wert der Variablen in den Puffer. Die Adresse und die Länge des Puffers werden in `buffer` und `numberOfElements` zurückgegeben. Durch die Selbstzuweisung des Puffers stellt `_dupenv_s` eine zweckmäßigere Alternative zu [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md) dar.  
  
> [!NOTE]
>  Das aufrufende Programm ist dafür zuständig, den Arbeitsspeicher durch Aufruf von [free](../../c-runtime-library/reference/free.md) zu leeren.  
  
 Wenn die Variable nicht gefunden wird, dann werden `buffer` auf `NULL` und `numberOfElements` auf 0 festgelegt, und der Rückgabewert ist 0, da diese Situation nicht als Fehlerzustand betrachtet wird.  
  
 Wenn die Größe des Puffers nicht relevant ist, können Sie `NULL` für `numberOfElements` übergeben.  
  
 Für `_dupenv_s` wird im Windows-Betriebssystem die Groß-/Kleinschreibung nicht beachtet. `_dupenv_s` verwendet die Kopie der Umgebung, auf die die globale Variable `_environ` verweist, um auf die Umgebung zuzugreifen. Erläuterungen zu `_environ` finden Sie in den Hinweisen unter [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
 Der Wert in `buffer` ist eine Kopie des Werts der Umgebungsvariablen. Das Ändern dieses Wertes hat keine Auswirkungen auf die Umgebung. Verwenden Sie die Funktion [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md), um den Wert einer Umgebungsvariablen zu ändern.  
  
 `_wdupenv_s` ist eine Breitzeichenversion von `_dupenv_s`. Die Argumente von `_wdupenv_s` sind Zeichenfolgen mit Breitzeichen. Die globale `_wenviron`-Variable ist eine Breitzeichen-Version von `_environ`. Weitere Informationen zu `_wenviron` finden Sie in den Hinweisen unter [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tdupenv_s`|`_dupenv_s`|`_dupenv_s`|`_wdupenv_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_dupenv_s`|\<stdlib.h>|  
|`_wdupenv_s`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_dupenv_s.c  
#include  <stdlib.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [Environmental Constants (Umgebungskonstanten)](../../c-runtime-library/environmental-constants.md)   
 [_dupenv_s_dbg, _wdupenv_s_dbg](../../c-runtime-library/reference/dupenv-s-dbg-wdupenv-s-dbg.md)   
 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)