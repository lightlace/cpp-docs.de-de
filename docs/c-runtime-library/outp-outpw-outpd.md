---
title: "_outp, _outpw, _outpd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_outpd"
  - "_outp"
  - "_outpw"
apilocation: 
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_outpw"
  - "_outpd"
  - "_outp"
  - "outpd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_outp-Funktion"
  - "_outpd-Funktion"
  - "_outpw-Funktion"
  - "Bytes, Schreiben zu Ports"
  - "Doppelworte"
  - "Doppelworte, Schreiben zu Ports"
  - "outp-Funktion"
  - "outpd-Funktion"
  - "outpw-Funktion"
  - "Anschlüsse, Schreiben von Bytes auf"
  - "Wörter"
  - "Wörter, Schreiben zu Ports"
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _outp, _outpw, _outpd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an einem Port ein Byte \(`_outp`\), ein Wort \(`_outpw`\) oder ein Doppelwort \(`_outpd`\) aus.  
  
> [!IMPORTANT]
>  Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In \/ZW nicht unterstützte CRT\-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
  
int _outp(unsigned short port,int databyte);unsigned short _outpw(unsigned short port,unsigned short dataword);unsigned long _outpd(unsigned short port,unsigned long dataword);  
```  
  
#### Parameter  
 *Port*  
 Portnummer  
  
 *databyte, dataword*  
 Ausgabewerte  
  
## Rückgabewert  
 Die Funktionen geben die Datenausgabe zurück. Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Die Funktionen `_outp`, `_outpw` und `_outpd` schreiben in den angegebenen Ausgabeport jeweils ein Byte, ein Wort und ein Doppelwort. Das *port*\-Argument kann eine beliebige ganze Zahl ohne Vorzeichen im Bereich 0–65.535 sein, *databyte* kann eine beliebige ganze Zahl im Bereich 0–255 sein, und *dataword* kann jeder Wert im Bereich einer ganzen Zahl, einer kurzen ganzen Zahl ohne Vorzeichen bzw. einer langen ganzen Zahl ohne Vorzeichen sein.  
  
 Da diese Funktionen direkt in einen E\/A\-Port schreiben, können sie in Windows NT, Windows 2000, Windows XP und Windows Server 2003 nicht im Benutzercode verwendet werden. Informationen über die Verwendung von E\/A\-Ports in diesen Betriebssystemen erhalten Sie, wenn Sie in MSDN nach "serielle Kommunikation in Win32" suchen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_outp`|\<conio.h\>|  
|`_outpw`|\<conio.h\>|  
|`_outpd`|\<conio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../c-runtime-library/console-and-port-i-o.md)   
 [\_inp, \_inpw, \_inpd](../c-runtime-library/inp-inpw-inpd.md)