---
title: "_inp, _inpw, _inpd"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_inp"
  - "_inpw"
  - "_inpd"
apilocation: 
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "inpd"
  - "_inp"
  - "_inpw"
  - "_inpd"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_inp-Funktion"
  - "_inpd-Funktion"
  - "_inpw-Funktion"
  - "E/A [CRT], Port"
  - "inp-Funktion"
  - "inpd-Funktion"
  - "inpw-Funktion"
  - "Anschlüsse, E/A-Routinen"
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _inp, _inpw, _inpd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eingaben von einem Port, einem Byte \(`_inp`\), einem Wort \(`_inpw`\) oder von einem Doppelwort \(`_inpd`\).  
  
> [!IMPORTANT]
>  Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In \/ZW nicht unterstützte CRT\-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
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
  
#### Parameter  
 `port`  
 E\/A\-Portnummer.  
  
## Rückgabewert  
 Die Funktionen geben das aus `port` gelesene Byte, Wort oder Doppelwort zurück. Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Die Funktionen `_inp`, `_inpw` und `_inpd` lesen aus dem angegebenen Eingangsport jeweils ein Byte, ein Wort und ein Doppelwort. Der Eingabewert kann jede beliebige kurze ganze Zahl ohne Vorzeichen im Bereich von 0 bis 65535 sein.  
  
 Da diese Funktionen direkt von einem E\/A\-Port lesen, können sie möglicherweise in Windows NT, Windows 2000, Windows XP und Windows Server 2003 nicht im Benutzercode verwendet werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_inp`|\<conio.h\>|  
|`_inpw`|\<conio.h\>|  
|`_inpd`|\<conio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../c-runtime-library/console-and-port-i-o.md)   
 [\_outp, \_outpw, \_outpd](../c-runtime-library/outp-outpw-outpd.md)