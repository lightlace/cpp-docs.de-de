---
title: _putch _putwch | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putwch
- _putch
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
- _putch
- putwch
- _putwch
dev_langs: C++
helpviewer_keywords:
- _putch function
- characters, writing
- putwch function
- _putwch function
- putch function
- console, writing characters to
ms.assetid: 3babc7cf-e333-405d-8449-c788d61d51aa
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fb34c83aede8b97ab1c3fae1afb33a16258daff7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="putch-putwch"></a>_putch, _putwch
Schreibt ein Zeichen in die Konsole.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _putch(  
int c   
);  
wint_t _putwch(  
   wchar_t c  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Auszugebende Zeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg `c` zurück. Wenn `_putch` fehlschlägt, wird `EOF` zurückgegeben. Wenn **_putwch** fehlschlägt, wird **WEOF** zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen schreiben das Zeichen `c` direkt, ohne in die Konsole zu puffern. In Windows NT schreibt **_putwch** Unicodezeichen unter Verwendung der aktuellen Konsolengebietsschemaeinstellung.  
  
 Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter `_putch_nolock` und `_putwch_nolock`.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|**_puttch**|`_putch`|`_putch`|**_putwch**|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_putch`|\<conio.h>|  
|**_putwch**|\<conio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Siehe Beispiel für [_getch](../../c-runtime-library/reference/getch-getwch.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Console and Port I/O (Konsole und Port-E/A)](../../c-runtime-library/console-and-port-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)