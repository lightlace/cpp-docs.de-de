---
title: btowc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- btowc
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
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
ms.openlocfilehash: ce9c4250fef70323b4e1b899efc1e5fe2e593881
ms.lasthandoff: 02/24/2017

---
# <a name="btowc"></a>btowc
Bestimmt, ob eine ganze Zahl ein gültiges Einzelbytezeichen im ersten Umschaltzustand darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Breitzeichendarstellung des Zeichens zurück, wenn die ganze Zahl ein gültiges Einzelbytezeichen im ersten Umschaltzustand darstellt. Gibt WEOF zurück, wenn die ganze Zahl ein EOF oder kein gültiges Einzelbytezeichen im ersten Umschaltzustand ist. Die Ausgabe dieser Funktion wird durch das aktuelle `LC_TYPE`-Gebietsschema beeinflusst.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`btowc`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)
