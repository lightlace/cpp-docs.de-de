---
title: "_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l"
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
  - "_ismbcpunct_l"
  - "_ismbcblank"
  - "_ismbcprint"
  - "_ismbcgraph_l"
  - "_ismbcblank_l"
  - "_ismbcpunct"
  - "_ismbcprint_l"
  - "_ismbcspace_l"
  - "_ismbcspace"
  - "_ismbcgraph"
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
  - "_ismbcspace"
  - "_ismbcgraph"
  - "_ismbcpunct"
  - "ismbcspace_l"
  - "ismbcgraph"
  - "_ismbcgraph_l"
  - "_ismbcprint"
  - "_ismbcspace_l"
  - "ismbcprint"
  - "ismbcgraph_l"
  - "ismbcspace"
  - "ismbcpunct"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcgraph-Funktion"
  - "_ismbcgraph_l-Funktion"
  - "_ismbcprint-Funktion"
  - "_ismbcprint_l-Funktion"
  - "_ismbcpunct-Funktion"
  - "_ismbcpunct_l-Funktion"
  - "_ismbcspace-Funktion"
  - "_ismbcspace_l-Funktion"
  - "ismbcgraph-Funktion"
  - "ismbcgraph_l-Funktion"
  - "ismbcprint-Funktion"
  - "ismbcprint_l-Funktion"
  - "ismbcpunct-Funktion"
  - "ismbcpunct_l-Funktion"
  - "ismbcspace-Funktion"
  - "ismbcspace_l-Funktion"
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein Zeichen ein Grafikzeichen, ein Anzeigenzeichen, ein Interpunktionszeichen oder ein Leerzeichen ist.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter der Seite zu den [CRT\-Funktionen, die nicht in \/ZW unterstützt werden](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _ismbcgraph(  
   unsigned int c   
);  
int _ismbcgraph_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcprint(  
   unsigned int c   
);  
int _ismbcprint_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcpunct(  
   unsigned int c  
);  
int _ismbcpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcblank(  
   unsigned int c   
);  
int _ismbcblank_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcspace(  
   unsigned int c   
);  
int _ismbcspace_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu bestimmendes Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt.  Wenn `c` \<\= 255 und gibt eine entsprechende `_ismbb` Routine \(beispielsweise, entspricht `_ismbcalnum` in `_ismbbalnum`\), ist, ist das Ergebnis der Rückgabewert der entsprechenden `_ismbb` Routine.  
  
 Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen mit dem `_l`\-Suffix anstelle des aktuellen Gebietsschemas das ihnen übergebene Gebietsschema für ihr vom Gebietsschema abhängiges Verhalten verwenden.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Hinweise  
 Jede dieser Funktionen testet ein angegebenes Mehrbytezeichen auf eine angegebene Bedingung.  
  
|Routine|Testbedingung|Beispiel für Codepage 932|  
|-------------|-------------------|-------------------------------|  
|`_ismbcgraph`|Grafik|Gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine Einzelbytedarstellung jedes beliebigen ASCII\- oder druckbaren Katakana\-Zeichens außer eines Leerzeichens \( \) ist.|  
|`_ismbcprint`|Druckbar|Gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine Einzelbytedarstellung jedes beliebigen ASCII\- oder druckbaren Katakana\-Zeichens einschließlich eines Leerzeichens \( \) ist.|  
|`_ismbcpunct`|Interpunktion|Gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine Einzelbytedarstellung jedes beliebigen ASCII\- oder Katakana\-Interpunktionszeichens ist.|  
|`_ismbcblank`|Leerzeichen oder horizontaler Tabulator|Gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein Leerzeichen oder ein horizontales Tabstoppzeichen ist: `c`\=0x20 oder `c`\=0x09.|  
|`_ismbcspace`|Leerraum|Gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein Leerzeichen ist: `c`\=0x20 oder 0x09\<\=`c`\<\=0x0D.|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ismbcgraph`|\<mbstring.h\>|  
|`_ismbcgraph_l`|\<mbstring.h\>|  
|`_ismbcprint`|\<mbstring.h\>|  
|`_ismbcprint_l`|\<mbstring.h\>|  
|`_ismbcpunct`|\<mbstring.h\>|  
|`_ismbcpunct_l`|\<mbstring.h\>|  
|`_ismbcblank`|\<mbstring.h\>|  
|`_ismbcblank_l`|\<mbstring.h\>|  
|`_ismbcspace`|\<mbstring.h\>|  
|`_ismbcspace_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::Char::IsPunctuation](https://msdn.microsoft.com/en-us/library/system.char.ispunctuation.aspx)  
  
-   [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
-   Bei `_ismbcgraph` und `_ismbcprint` nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_ismbc\-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)