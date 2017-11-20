---
title: _inp, _inpw, _inpd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _inp
- _inpw
- _inpd
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
dev_langs: C++
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 983efc1f3341ca334415e8cdd37f96f12fbb3e11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="inp-inpw-inpd"></a>_inp, _inpw, _inpd
Eingaben von einem Port, einem Byte (`_inp`), einem Wort (`_inpw`) oder von einem Doppelwort (`_inpd`).  
  
> [!IMPORTANT]
>  Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _inp(   
   unsigned short port   
);  
unsigned short _inpw(   
   unsigned short port   
);  
unsigned long _inpd(   
   unsigned short port   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `port`  
 E/A-Portnummer.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Funktionen geben das aus `port`gelesene Byte, Wort oder Doppelwort zurück. Es gibt keine Fehlerrückgabe.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `_inp`, `_inpw`und `_inpd` lesen aus dem angegebenen Eingangsport jeweils ein Byte, ein Wort und ein Doppelwort. Der Eingabewert kann jede beliebige kurze ganze Zahl ohne Vorzeichen im Bereich von 0 bis 65.535 sein.  
  
 Da diese Funktionen direkt von einem E/A-Port lesen, können sie möglicherweise in Windows NT, Windows 2000, Windows XP und Windows Server 2003 nicht im Benutzercode verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_inp`|\<conio.h>|  
|`_inpw`|\<conio.h>|  
|`_inpd`|\<conio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konsole und Port-E/A](../c-runtime-library/console-and-port-i-o.md)   
 [_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)