---
title: _outp, _outpw, _outpd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _outpd
- _outp
- _outpw
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _outpw
- _outpd
- _outp
- outpd
dev_langs:
- C++
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
caps.latest.revision: 16
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 3411f2f902a3a7d4dc47a0d9fb00b5e970a1a876
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="outp-outpw-outpd"></a>_outp, _outpw, _outpd
Gibt an einem Port ein Byte (`_outp`), ein Wort (`_outpw`) oder ein Doppelwort (`_outpd`) aus.  
  
> [!IMPORTANT]
>  Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _outp(  
unsigned short port,  
int databyte   
);  
unsigned short _outpw(  
unsigned short port,  
unsigned short dataword   
);  
unsigned long _outpd(  
unsigned short port,  
unsigned long dataword   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *port*  
 Portnummer  
  
 *databyte, dataword*  
 Ausgabewerte  
  
## <a name="return-value"></a>Rückgabewert  
 Die Funktionen geben die Datenausgabe zurück. Es gibt keine Fehlerrückgabe.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `_outp`, `_outpw`und `_outpd` schreiben in den angegebenen Ausgabeport jeweils ein Byte, ein Wort und ein Doppelwort. Das *port*-Argument kann eine beliebige ganzen Zahl ohne Vorzeichen im Bereich 0-65.535 sein, *databyte* kann eine beliebige ganze Zahl im Bereich 0–255 sein und *dataword* kann jeder Wert im Bereich einer ganzen Zahl, einer kurzen ganzen Zahl ohne Vorzeichen bzw. einer langen ganzen Zahl ohne Vorzeichen sein.  
  
 Da diese Funktionen direkt in einen E/A-Port schreiben, können sie in Windows NT, Windows 2000, Windows XP und Windows Server 2003 nicht im Benutzercode verwendet werden. Informationen über die Verwendung von E/A-Ports in diesen Betriebssystemen erhalten Sie, wenn Sie in MSDN nach "serielle Kommunikation in Win32" suchen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_outp`|\<conio.h>|  
|`_outpw`|\<conio.h>|  
|`_outpd`|\<conio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konsole und Port-E/A](../c-runtime-library/console-and-port-i-o.md)   
 [_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)
