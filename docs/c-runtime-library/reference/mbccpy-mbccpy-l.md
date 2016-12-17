---
title: "_mbccpy, _mbccpy_l"
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
  - "_mbccpy"
  - "_mbccpy_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbccpy"
  - "tccpy"
  - "ftccpy"
  - "mbccpy"
  - "_tccpy"
  - "_ftccpy"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbccpy-Funktion"
  - "_mbccpy_l-Funktion"
  - "_tccpy-Funktion"
  - "_tccpy_l-Funktion"
  - "mbccpy-Funktion"
  - "mbccpy_l-Funktion"
  - "tccpy-Funktion"
  - "tccpy_l-Funktion"
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# _mbccpy, _mbccpy_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopiert ein Multibytezeichen von einer Zeichenfolge in eine andere Zeichenfolge.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_mbccpy\_s, \_mbccpy\_s\_l](../../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
void _mbccpy(  
   unsigned char *dest,  
   const unsigned char *src   
);  
void _mbccpy_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `dest`  
 Kopierziel.  
  
 `src`  
 Zu kopierendes Multibytezeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Hinweise  
 Die `_mbccpy`\-Funktion kopiert ein Multibytezeichen von `src` in `dest`.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `_mbccpy` ein NULL\-Zeiger für `dest` oder `src` übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt.  
  
 `_mbccpy` verwendet das aktuelle Gebietsschema für jedes gebietsschemaabhängige Verhalten.  `_mbccpy_l` ist mit `_mbccpy` identisch, außer dass `_mbccpy_l` das Gebietsschema verwendet, das für jedes gebietsschemaabhängige Verhalten übergeben wurde.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 **Sicherheitshinweis** Verwenden Sie eine mit NULL endende Zeichenfolge.  Die mit NULL endende Zeichenfolge darf die Größe des Zielpuffers nicht überschreiten.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tccpy`|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|`_mbccpy`|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|  
|`_tccpy_l`|nicht verfügbar|`_mbccpy_l`|nicht verfügbar|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbccpy`|\<mbctype.h\>|  
|`_mbccpy_l`|\<mbctype.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Entsprechung in .NET Framework  
 Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)