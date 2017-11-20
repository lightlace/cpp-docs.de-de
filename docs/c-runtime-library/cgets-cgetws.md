---
title: _cgets, _cgetws | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cgetws
- _cgets
apilocation:
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- cgetws
- _cgetws
- _cgets
dev_langs: C++
helpviewer_keywords:
- _cgetws function
- strings [C++], getting from console
- console, getting strings from
- _cgets function
- cgetws function
- cgets function
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ced8ca3ec392caf29cd3cbc41fe462bd24546f26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cgets-cgetws"></a>_cgets, _cgetws
Ruft eine Zeichenfolge aus der Konsole ab. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar. Dies sicheren Versionen dieser Funktionen, „_cgets_s“ und „_cgetws_s“, stehen noch zur Verfügung. Informationen zu diesen alternativen Funktionen finden Sie unter [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_cgets(   
   char *buffer   
);  
wchar_t *_cgetws(  
   wchar_t *buffer  
);  
template <size_t size>  
char *_cgets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_cgetws(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Speicherort für Daten.  
  
## <a name="return-value"></a>Rückgabewert  
 `_cgets` und `_cgetws` geben bei `buffer[2]` einen Zeiger auf den Anfang der Zeichenfolge zurück. Wenn `buffer` `NULL` ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, wird `NULL` zurückgegeben und `errno` auf `EINVAL`festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen lesen eine Zeichenfolge von der Konsole und speichern die Zeichenfolge und ihre Länge im Speicherort, auf den `buffer`zeigt. Der `buffer` -Parameter muss ein Zeiger auf ein Zeichenarray sein. `buffer[0]`, das erste Element des Arrays, muss die maximale Länge (in Zeichen) der zu lesenden Zeichenfolge enthalten. Das Array muss genügend Elemente enthalten, um die Zeichenfolge, ein abschließendes Nullzeichen ('\0') und zwei zusätzliche Bytes einzuschließen. Die Funktion liest die Zeichen bis zu einer Kombination aus Wagenrücklauf und Zeilenvorschub (CR-LF) oder bis die angegebene Anzahl von Zeichen gelesen ist. Die Zeichenfolge wird ab `buffer[2]`gespeichert. Wenn die Funktion ein CR-LF liest, speichert sie das NULL-Zeichen ('\0'). Die Funktion speichert dann im zweiten Arrayelement `buffer[1]`die tatsächliche Länge der Zeichenfolge.  
  
 Da alle Bearbeitungsschlüssel aktiv sind, wenn `_cgets` oder `_cgetws` in einem Konsolenfenster aufgerufen wird, wird durch Drücken der F3-TASTE der letzte eingegebene Eintrag wiederholt.  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_cgets`|\<conio.h>|  
|`_cgetws`|\<conio.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_cgets.c  
// compile with: /c /W3  
// This program creates a buffer and initializes  
// the first byte to the size of the buffer. Next, the  
// program accepts an input string using _cgets and displays  
// the size and text of that string.  
  
#include <conio.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   char buffer[83] = { 80 };  // Maximum characters in 1st byte  
   char *result;  
  
   printf( "Input line of text, followed by carriage return:\n");  
  
   // Input a line of text:  
   result = _cgets( buffer ); // C4996  
   // Note: _cgets is deprecated; consider using _cgets_s  
   if (!result)  
   {  
      printf( "An error occurred reading from the console:"  
              " error code %d\n", errno);  
   }  
   else  
   {     
      printf( "\nLine length = %d\nText = %s\n",  
              buffer[1], result );  
   }  
}  
```  
  
```Output  
  
      A line of input.Input line of text, followed by carriage return:  
Line Length = 16  
Text = A line of input.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Konsole und Port-E/A](../c-runtime-library/console-and-port-i-o.md)   
 [_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)