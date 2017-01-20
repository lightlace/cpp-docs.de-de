---
title: "_heapwalk"
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
  - "_heapwalk"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "heapwalk"
  - "_heapwalk"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapwalk-Funktion"
  - "Debuggen [CRT], Heapbezogene Probleme"
  - "heapwalk-Funktion"
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# _heapwalk
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durchläuft den Heap und gibt Informationen zum folgenden Eintrag zurück.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden. Dies gilt nicht für Debug\-Builds.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### Parameter  
 `entryinfo`  
 Der Puffer, der die Heapinformationen enthält.  
  
## Rückgabewert  
 `_heapwalk` gibt eine der folgenden ganzzahligen Manifestkonstanten zurück, die in Malloc.h definiert sind.  
  
 `_HEAPBADBEGIN`  
 Ursprüngliche Headerinformationen ungültig oder nicht gefunden.  
  
 `_HEAPBADNODE`  
 Heap beschädigt oder ungültiger Knoten gefunden.  
  
 `_HEAPBADPTR`  
 Das `_pentry`\-Feld der `_HEAPINFO`\-Struktur enthält keinen gültigen Zeiger im Heap oder `entryinfo` ist ein NULL\-Zeiger.  
  
 `_HEAPEND`  
 Ende des Heaps erfolgreich erreicht.  
  
 `_HEAPEMPTY`  
 Heap wurde nicht initialisiert.  
  
 `_HEAPOK`  
 Keine Fehler bisher; `entryinfo` wird mit Informationen zum nächsten Heapeintrag aktualisiert.  
  
 Wenn ein Fehler auftritt, setzt `_heapwalk``errno` zudem auf `ENOSYS`.  
  
## Hinweise  
 Die `_heapwalk`\-Funktion hilft beim Debuggen heapbezogener Probleme in Programmen.  Die Funktion durchläuft den Heap, durchsucht einen Eintrag pro Aufruf und gibt einen Zeiger auf eine Struktur vom Typ `_HEAPINFO` zurück, die Informationen zum folgenden Heapeintrag enthält.  Der in Malloc.h definierte `_HEAPINFO`\-Typ enthält die folgenden Elemente.  
  
 `int *_pentry`  
 Heapeintragszeiger.  
  
 `size_t _size`  
 Größe des Heapeintrags.  
  
 `int _useflag`  
 Kennzeichnung, die angibt, ob der Heapeintrag verwendet wird.  
  
 Ein Aufruf von `_heapwalk`, der `_HEAPOK` zurückgibt, speichert die Größe des Eintrags im `_size`\-Feld und setzt das `_useflag`\-Feld auf `_FREEENTRY` oder `_USEDENTRY` \(beide Konstanten sind in Malloc.h definiert\).  Zum Abrufen der Informationen über den ersten Eintrag im Heap übergeben Sie einen `_heapwalk`\-Zeiger auf eine `_HEAPINFO`\-Struktur, dessen `_pentry`\-Member `NULL` ist.  Wenn das Betriebssystem nicht `_heapwalk`, \(z Windows 98\) unterstützt, wird `_HEAPEND` zurückgegeben und `errno` auf `ENOSYS` fest.  
  
 Diese Funktion überprüft seine Parameter.  Wenn `entryinfo` ein NULL\-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `_HEAPBADPTR` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_heapwalk`|\<malloc.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_heapwalk.c  
  
// This program "walks" the heap, starting  
// at the beginning (_pentry = NULL). It prints out each  
// heap entry's use, location, and size. It also prints  
// out information about the overall state of the heap as  
// soon as _heapwalk returns a value other than _HEAPOK  
// or if the loop has iterated 100 times.  
  
#include <stdio.h>  
#include <malloc.h>  
  
void heapdump(void);  
  
int main(void)  
{  
    char *buffer;  
  
    heapdump();  
    if((buffer = (char *)malloc(59)) != NULL)  
    {  
        heapdump();  
        free(buffer);  
    }  
    heapdump();  
}  
  
void heapdump(void)  
{  
    _HEAPINFO hinfo;  
    int heapstatus;  
    int numLoops;  
    hinfo._pentry = NULL;  
    numLoops = 0;  
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&  
          numLoops < 100)  
    {  
        printf("%6s block at %Fp of size %4.4X\n",  
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),  
               hinfo._pentry, hinfo._size);  
        numLoops++;  
    }  
  
    switch(heapstatus)  
    {  
    case _HEAPEMPTY:  
        printf("OK - empty heap\n");  
        break;  
    case _HEAPEND:  
        printf("OK - end of heap\n");  
        break;  
    case _HEAPBADPTR:  
        printf("ERROR - bad pointer to heap\n");  
        break;  
    case _HEAPBADBEGIN:  
        printf("ERROR - bad start of heap\n");  
        break;  
    case _HEAPBADNODE:  
        printf("ERROR - bad node in heap\n");  
        break;  
    }  
}  
```  
  
  **Block bei 00310650 der Größe 0100 VERWENDET**  
 **Block bei 00310758 der Größe 0800 VERWENDET**  
 **Block bei 00310F60 der Größe 0800 VERWENDET**  
 **FREIER Block bei 00310FF0 der Größe 0398**  
 **Block bei 0031139 der Größe 000D VERWENDET**  
 **Block bei 003113A8 der Größe 00B4 VERWENDET**  
 **Block bei 00311468 der Größe 0034 VERWENDET**  
 **Block bei 003114A8 der Größe 0039 VERWENDET**  
**...**  
 **Block bei 00312228 der Größe 0010 VERWENDET**  
 **Block bei 00312240 der Größe 1000 VERWENDET**  
 **Freier Block bei 00313250 der Größe 1DB0**  
**OK \- Ende des Heaps**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../../c-runtime-library/heapset.md)