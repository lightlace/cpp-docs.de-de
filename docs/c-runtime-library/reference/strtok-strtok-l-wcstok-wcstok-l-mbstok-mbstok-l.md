---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs: C++
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
caps.latest.revision: "34"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa20ca680481ffce009a362bf0f4b21923ef572d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
Sucht das nächste Token in einer Zeichenfolge unter Verwendung des angegebenen Gebietsschemas oder eines Gebietsschemas, das übergeben wird. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).  
  
> [!IMPORTANT]
>  `_mbstok` und `_mbstok_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *strtok(  
   char *strToken,  
   const char *strDelimit   
);  
wchar_t *wcstok(  
   wchar_t *strToken,  
   const wchar_t *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `strToken`  
 Zeichenfolge, die mindestens ein Token enthält.  
  
 `strDelimit`  
 Gruppe von Trennzeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das nächste Token zurück, das in `strToken` gefunden wird. Wenn keine weiteren Token gefunden werden, wird `NULL` zurückgegeben. Jeder Aufruf ändert `strToken`, indem er das Trennzeichen, das nach dem zurückgegebenen Token auftritt, durch ein `NULL`-Zeichen ersetzt.  
  
## <a name="remarks"></a>Hinweise  
 Die `strtok`-Funktion sucht das nächste Token in `strToken`. Der Satz von Zeichen in `strDelimit` gibt mögliche Trennzeichen des in `strToken` gefunden Tokens für den aktuellen Aufruf an. `wcstok` und `_mbstok` sind Breitzeichen- und Multibytezeichenversionen von `strtok`. Die Argumente und der Rückgabewert von `wcstok` sind Breitzeichen-Zeichenfolgen; die von `_mbstok` sind Mehrbyte-Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
> [!IMPORTANT]
>  Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar. Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Beim ersten Aufruf von `strtok` überspringt die Funktion vorangestellte Trennzeichen, gibt einen Zeiger auf das erste Token in `strToken` zurück und beendet das Token mit einem NULL-Zeichen. Vom restlichen `strToken` können weitere Token durch mehrere Aufrufe von `strtok` geholt werden. Jeder Aufruf von `strtok` ändert `strToken` durch ein Null-Zeichen nach dem Einfügen der `token` zurückgegebenen. Um das folgende Token von `strToken` zu lesen, rufen Sie `strtok` auf, und geben Sie dabei einen `NULL`-Wert für das `strToken`-Argument an. Das `NULL` `strToken`-Argument bewirkt, dass `strtok` im geänderten `strToken` nach dem nächsten Token sucht. Das `strDelimit`-Argument kann zwischen zwei Aufrufen jeden beliebigen Wert annehmen, damit der Satz von Trennzeichen variieren kann.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  Jede Funktion verwendet eine statische Variable eines lokalen Threads, um die Zeichenfolge in Token zu analysieren. Daher können mehrere Threads diese Funktionen gleichzeitig aufrufen, ohne dass unerwünschte Auswirkungen auftreten. Innerhalb eines einzelnen Threads ist es jedoch wahrscheinlich, dass ein überlappendes Aufrufen von einer dieser Funktionen zu Datenbeschädigung und ungenauen Ergebnissen führt. Beim Analysieren verschiedener Zeichenfolgen sollte zuerst eine Zeichenfolge zu Ende analysiert werden, bevor mit dem Analysieren der nächsten Zeichenfolge begonnen wird. Berücksichtigen Sie auch das mögliche Risiko, wenn Sie eine dieser Funktionen aus einer Schleife heraus aufrufen, in der eine andere Funktion aufgerufen wird. Wenn die andere Funktion eine dieser Funktionen verwendet, kommt es zu einer überlappenden Sequenz von Aufrufen und Datenbeschädigung ist die Folge.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok`|`strtok`|`_mbstok`|`wcstok`|  
|`_tcstok`|`_strtok_l`|`_mbstok_l`|`_wcstok_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`strtok`|\<string.h>|  
|`wcstok`|\<string.h> oder \<wchar.h>|  
|`_mbstok`, `_mbstok_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_strtok.c  
// compile with: /W3  
// In this program, a loop uses strtok  
// to print all the tokens (separated by commas  
// or blanks) in the string named "string".  
//  
#include <string.h>  
#include <stdio.h>  
  
char string[] = "A string\tof ,,tokens\nand some  more tokens";  
char seps[]   = " ,\t\n";  
char *token;  
  
int main( void )  
{  
   printf( "Tokens:\n" );  
  
   // Establish string and get the first token:  
   token = strtok( string, seps ); // C4996  
   // Note: strtok is deprecated; consider using strtok_s instead  
   while( token != NULL )  
   {  
      // While there are tokens in "string"  
      printf( " %s\n", token );  
  
      // Get next token:   
      token = strtok( NULL, seps ); // C4996  
   }  
}  
```  
  
```Output  
Tokens:  
 A  
 string  
 of  
 tokens  
 and  
 some  
 more  
 tokens  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)