---
title: _cgets_s, _cgetws_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 267963b8f9344cef67788726bd2c6f082c7953ac
ms.lasthandoff: 02/24/2017

---
# <a name="cgetss-cgetwss"></a>_cgets_s, _cgetws_s
Ruft eine Zeichenfolge aus der Konsole ab. Diese Versionen von [_cgets und _cgetws](../../c-runtime-library/cgets-cgetws.md) enthalten Sicherheitserweiterungen, wie dies unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _cgets_s(   
   char *buffer,  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
errno_t _cgetws_s(  
   wchar_t *buffer  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
template <size_t size>  
errno_t _cgets_s(   
   char (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
template <size_t size>  
errno_t _cgetws_s(  
   wchar_t (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `buffer`  
 Speicherort für Daten.  
  
 [in] `numberOfElements`  
 Die Größe des Puffers in Einzelbyte- oder Breitzeichen. Hierbei handelt es sich auch um die maximale Anzahl der zu lesenden Zeichen.  
  
 [in] `pSizeRead`  
 Die Anzahl der tatsächlich gelesenen Zeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist im Erfolgsfall „0“, andernfalls wird ein Fehlercode ausgegeben, wenn ein Fehler auftritt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`pSizeRead`|Zurück|Inhalt von `buffer`|  
|--------------|------------------------|-----------------|------------|--------------------------|  
|`NULL`|any|any|`EINVAL`|nicht verfügbar|  
|nicht `NULL`|Null|alle|`EINVAL`|nicht geändert|  
|nicht `NULL`|alle|`NULL`|`EINVAL`|Zeichenfolge mit der Länge&0;|  
  
## <a name="remarks"></a>Hinweise  
 `_cgets_s` und `_cgetws_s` lesen eine Zeichenfolge aus der Konsole und kopieren die Zeichenfolge (mit einem NULL-Terminator) in `buffer`. `_cgetws_s` ist die Breitzeichenversion der Funktion. Im Gegensatz zur Zeichengröße ist das Verhalten dieser zwei Funktionen identisch. Die maximale Größe der zu lesenden Zeichenfolge wird als `numberOfElements`-Parameter übergeben. Diese Größe sollte ein zusätzliches Zeichen für das abschließende Nullzeichen enthalten. Die tatsächliche Anzahl der gelesenen Zeichen wird in `pSizeRead` platziert.  
  
 Wenn während des Vorgangs oder im Zuge der Validierung der Parameter ein Fehler auftritt, wird der Handler für ungültige Parameter aufgerufen, wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt und `EINVAL` zurückgegeben.  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht. Die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein „size“-Argument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_cgetts_s`|`_cgets_s`|`_cgets_s`|`_cgetws_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_cgets_s`|\<conio.h>|  
|`_cgetws_s`|\<conio.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Konsole und Port-E/A](../../c-runtime-library/console-and-port-i-o.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)
