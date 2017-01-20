---
title: "_cgets_s, _cgetws_s"
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
  - "_cgetws_s"
  - "_cgets_s"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_cgets_s"
  - "cgets_s"
  - "cgetws_s"
  - "_cgetws_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cgets_s-Funktion"
  - "_cgetws_s-Funktion"
  - "cget_s-Funktion"
  - "cgetws_s-Funktion"
  - "Konsole, Abrufen von Zeichenfolgen aus"
  - "Zeichenfolgen [C++], Abrufen aus Konsole"
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
caps.latest.revision: 31
caps.handback.revision: "31"
ms.author: "corob"
manager: "ghogen"
---
# _cgets_s, _cgetws_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft eine Zeichenfolge aus der Konsole ab.  Diese Versionen von [\_cgets und \_cgetws](../../c-runtime-library/cgets-cgetws.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
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
  
#### Parameter  
 \[out\] `buffer`  
 Speicherort für Daten.  
  
 \[in\] `numberOfElements`  
 Die Größe des Puffers in Einzelbyte\- oder Breitzeichen. Hierbei handelt es sich auch um die maximale Anzahl der zu lesenden Zeichen.  
  
 \[in\] `pSizeRead`  
 Die Anzahl der tatsächlich gelesenen Zeichen.  
  
## Rückgabewert  
 Der Rückgabewert ist im Erfolgsfall „0“, andernfalls wird ein Fehlercode ausgegeben, wenn ein Fehler auftritt.  
  
### Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`pSizeRead`|Zurück|Inhalt von `buffer`|  
|--------------|------------------------|-----------------|------------|-------------------------|  
|`NULL`|alle|alle|`EINVAL`|n\/v|  
|nicht `NULL`|Null|alle|`EINVAL`|nicht geändert|  
|nicht `NULL`|alle|`NULL`|`EINVAL`|Zeichenfolge mit der Länge 0|  
  
## Hinweise  
 `_cgets_s` und `_cgetws_s` lesen eine Zeichenfolge aus der Konsole und kopieren die Zeichenfolge \(mit einem NULL\-Terminator\) in `buffer`.  `_cgetws_s` ist die Breitzeichenversion der Funktion. Im Gegensatz zur Zeichengröße ist das Verhalten dieser zwei Funktionen identisch.  Die maximale Größe der zu lesenden Zeichenfolge wird als `numberOfElements`\-Parameter übergeben.  Diese Größe sollte ein zusätzliches Zeichen für das abschließende Nullzeichen enthalten.  Die tatsächliche Anzahl der gelesenen Zeichen wird in `pSizeRead` platziert.  
  
 Wenn während des Vorgangs oder im Zuge der Überprüfung der Parameter ein Fehler auftritt, wird der Handler für ungültige Parameter aufgerufen, wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt und `EINVAL` zurückgegeben.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht. Die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein „size“\-Argument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_cgetts_s`|`_cgets_s`|`_cgets_s`|`_cgetws_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_cgets_s`|\<conio.h\>|  
|`_cgetws_s`|\<conio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../../c-runtime-library/console-and-port-i-o.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)