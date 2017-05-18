---
title: _heapwalk | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 936ca2f3f4e4f2fb57dd730f5a58927d08d6207f
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="heapwalk"></a>_heapwalk
Durchläuft den Heap und gibt Informationen zum folgenden Eintrag zurück.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Dies gilt nicht für Debug-Builds. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `entryinfo`  
 Der Puffer, der die Heapinformationen enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 `_heapwalk` gibt eine der folgenden ganzzahligen Manifestkonstanten zurück, die in Malloc.h definiert sind.  
  
 `_HEAPBADBEGIN`  
 Ursprüngliche Headerinformationen ungültig oder nicht gefunden.  
  
 `_HEAPBADNODE`  
 Heap beschädigt oder ungültiger Knoten gefunden.  
  
 `_HEAPBADPTR`  
Das  `_pentry`-Feld der `_HEAPINFO`-Struktur enthält keinen gültigen Zeiger im Heap oder `entryinfo` ist ein NULL-Zeiger.  
  
 `_HEAPEND`  
 Ende des Heaps erfolgreich erreicht.  
  
 `_HEAPEMPTY`  
 Heap wurde nicht initialisiert.  
  
 `_HEAPOK`  
 Keine Fehler bisher; `entryinfo` wird mit Informationen zum nächsten Heapeintrag aktualisiert.  
  
 Wenn ein Fehler auftritt, setzt `_heapwalk``errno` zudem auf `ENOSYS`.  
  
## <a name="remarks"></a>Hinweise  
 Die `_heapwalk`-Funktion hilft beim Debuggen heapbezogener Probleme in Programmen. Die Funktion durchläuft den Heap, durchsucht einen Eintrag pro Aufruf und gibt einen Zeiger auf eine Struktur vom Typ `_HEAPINFO` zurück, die Informationen zum folgenden Heapeintrag enthält. Der in Malloc.h definierte `_HEAPINFO`-Typ enthält die folgenden Elemente.  
  
 `int *_pentry`  
 Heapeintragszeiger.  
  
 `size_t _size`  
 Größe des Heapeintrags.  
  
 `int _useflag`  
 Kennzeichnung, die angibt, ob der Heapeintrag verwendet wird.  
  
 Ein Aufruf von `_heapwalk`, der `_HEAPOK` zurückgibt, speichert die Größe des Eintrags im `_size`-Feld und setzt das `_useflag`-Feld auf `_FREEENTRY` oder `_USEDENTRY` (beide Konstanten sind in Malloc.h definiert). Zum Abrufen der Informationen über den ersten Eintrag im Heap übergeben Sie einen `_heapwalk`-Zeiger auf eine `_HEAPINFO`-Struktur, dessen `_pentry`-Member `NULL` ist. Wenn das Betriebssystem `_heapwalk` nicht unterstützt (beispielsweise Windows 98), gibt die Funktion `_HEAPEND` zurück und legt `errno` auf `ENOSYS` fest.  
  
 Diese Funktion überprüft seine Parameter. Wenn `entryinfo` ein NULL-Zeiger ist, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `_HEAPBADPTR` zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_heapwalk`|\<malloc.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
  USED block at 00310650 of size 0100  
  USED block at 00310758 of size 0800  
  USED block at 00310F60 of size 0080  
  FREE block at 00310FF0 of size 0398  
  USED block at 00311390 of size 000D  
  USED block at 003113A8 of size 00B4  
  USED block at 00311468 of size 0034  
  USED block at 003114A8 of size 0039  
...  
  USED block at 00312228 of size 0010  
  USED block at 00312240 of size 1000  
  FREE block at 00313250 of size 1DB0  
OK - end of heap  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)
