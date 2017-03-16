---
title: _get_output_format | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_output_format
apilocation:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- get_output_format
- _get_output_format
dev_langs:
- C++
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 13
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
translationtype: Human Translation
ms.sourcegitcommit: aadbf7d2c6fece48ab29c1b818995464a790c38b
ms.openlocfilehash: 23646d03e920ae187286885dbd24e1d312973048
ms.lasthandoff: 03/07/2017

---
# <a name="getoutputformat"></a>_get_output_format
Ruft den aktuellen Wert des Ausgabeformatkennzeichens ab.  
  
> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned int _get_output_format();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der aktuelle Wert des Ausgabeformatkennzeichens.  
  
## <a name="remarks"></a>Hinweise  
 Das Ausgabeformatkennzeichen steuert Funktionen von formatierter E/A. Derzeit hat das Kennzeichen zwei mögliche Werte: 0 und `_TWO_DIGIT_EXPONENT`. Wenn `_TWO_DIGIT_EXPONENT` festgelegt ist, werden Gleitkommazahlen mit nur zwei Stellen im Exponenten gedruckt, es sei denn, eine dritte Stelle ist aufgrund der Größe des Exponenten erforderlich. Wenn das Kennzeichen den Wert&0; hat, wird in der Gleitkommadarstellung ein dreistelliger Exponent angezeigt, der ggf. mit Nullen aufgefüllt wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_output_format`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
[Syntax der Formatangabe: printf- und wprintf-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)  
 [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [_set_output_format](../c-runtime-library/set-output-format.md)  

