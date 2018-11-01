---
title: _heapwalk
ms.date: 11/04/2016
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
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
ms.openlocfilehash: cc2a49d9032746cc6c82c9dc401fc96baabbe2e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454898"
---
# <a name="heapwalk"></a>_heapwalk

Durchläuft den Heap und gibt Informationen zum folgenden Eintrag zurück.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Dies gilt nicht für Debug-Builds. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>Parameter

*entryinfo*<br/>
Der Puffer, der die Heapinformationen enthält.

## <a name="return-value"></a>Rückgabewert

**_heapwalk** gibt einen der folgenden ganzzahligen Manifestkonstanten in Malloc.h definiert sind.

|Rückgabewert|Bedeutung|
|-|-|
|**_HEAPBADBEGIN**| Ursprüngliche Headerinformationen ungültig oder nicht gefunden.|
|**_HEAPBADNODE**| Heap beschädigt oder ungültiger Knoten gefunden.|
|**_HEAPBADPTR**| Die **_pentry** Feld der **_HEAPINFO** -Struktur enthält keinen gültigen Zeiger im Heap oder *Entryinfo* ist ein null-Zeiger.|
|**_HEAPEND**| Ende des Heaps erfolgreich erreicht.|
|**_HEAPEMPTY**| Heap wurde nicht initialisiert.|
|**_HEAPOK**| Keine Fehler bisher; *Entryinfo* mit Informationen zum nächsten heapeintrag aktualisiert.|

Darüber hinaus, wenn ein Fehler auftritt **_heapwalk** legt **Errno** zu **ENOSYS**.

## <a name="remarks"></a>Hinweise

Die **_heapwalk** Funktion hilft beim Debuggen heapbezogener Probleme in Programmen. Die Funktion durchläuft den Heap, durchsucht einen Eintrag pro Aufruf und gibt einen Zeiger auf eine Struktur des Typs **_HEAPINFO** , die Informationen zum nächsten heapeintrag enthält. Die **_HEAPINFO** Typ, der in Malloc.h definiert, enthält die folgenden Elemente.

|Feld|Bedeutung|
|-|-|
|`int *_pentry`|Heapeintragszeiger.|
|`size_t _size`|Größe des Heapeintrags.|
|`int _useflag`|Kennzeichnung, die angibt, ob der Heapeintrag verwendet wird.|

Ein Aufruf von **_heapwalk** zurückgibt **_HEAPOK** speichert die Größe des Eintrags in der **_Größe** -Feld und setzt die **_useflag** -Feld auf **_FREEENTRY** oder **_USEDENTRY** (beide sind Konstanten, die in Malloc.h definiert sind). Zum Abrufen dieser Informationen zu den ersten Eintrag im Heap übergeben **_heapwalk** ein Zeiger auf eine **_HEAPINFO** Struktur, deren **_pentry** angehört **NULL** . Wenn das Betriebssystem nicht unterstützt **_heapwalk**(z. B. Windows 98), die Funktion gibt **_HEAPEND** und **Errno** zu **ENOSYS**.

Diese Funktion überprüft seine Parameter. Wenn *Entryinfo* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **_HEAPBADPTR**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
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
        printf("%8s block at %Fp of size %4.4X\n",
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

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
