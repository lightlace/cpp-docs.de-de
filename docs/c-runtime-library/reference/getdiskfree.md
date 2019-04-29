---
title: _getdiskfree
ms.date: 11/04/2016
apiname:
- _getdiskfree
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getdiskfree
- _getdiskfree
helpviewer_keywords:
- diskfree_t type
- _getdiskfree function
- _diskfree_t type
- disk size
- getdiskfree function
ms.assetid: 47a3f6cf-4816-452a-8f3d-1c3ae02a0f2a
ms.openlocfilehash: 03c39802301406bc4250328983c8cf8bad94497f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331765"
---
# <a name="getdiskfree"></a>_getdiskfree

Verwendet die Informationen über ein Laufwerk zum Auffüllen einer **_diskfree_t** Struktur.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
unsigned _getdiskfree(
   unsigned drive,
   struct _diskfree_t * driveinfo
);
```

### <a name="parameters"></a>Parameter

*drive*<br/>
Das Laufwerk, zu dem Sie Informationen abrufen möchten.

*driveinfo*<br/>
Ein **_diskfree_t** -Struktur, die mit Informationen über das Laufwerk aufgefüllt wird.

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert „0“. Wenn die Funktion fehlerhaft ist, wird der Fehlercode als Rückgabewert ausgegeben. Der Wert **Errno** festgelegt ist, Fehler, die vom Betriebssystem zurückgegeben werden. Weitere Informationen zu fehlerbedingungen, die angegeben wurden **Errno**, finden Sie unter [Errno-Konstanten](../../c-runtime-library/errno-constants.md).

## <a name="remarks"></a>Hinweise

Die **_diskfree_t** Struktur wird in "Direct.h" definiert.

```C
struct _diskfree_t {
   unsigned total_clusters;      // The total number of clusters, both used and available, on the disk.
   unsigned avail_clusters;      // The number of unused clusters on the disk.
   unsigned sectors_per_cluster; // The number of sectors in each cluster.
   unsigned bytes_per_sector;    // The size of each sector in bytes.
};
```

Diese Funktion überprüft ihre Parameter. Wenn die *Driveinfo* Zeiger **NULL** oder *Laufwerk* ein ungültiges Laufwerk angibt, wie in beschrieben, ruft diese Funktion einen Handler für ungültige Parameter [ Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion **EINVAL** und **Errno** zu **EINVAL**. Der gültige Laufwerksbereich liegt zwischen 0 und 26. Ein *Laufwerk* Wert 0 gibt an, das aktuelle Laufwerk werden danach Zahlen Buchstaben des englischen Alphabets, 1 gibt Laufwerk A, 3 Laufwerk C, und So weiter.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_getdiskfree**|\<direct.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getdiskfree.c
// compile with: /c
#include <windows.h>
#include <direct.h>
#include <stdio.h>
#include <tchar.h>

TCHAR   g_szBorder[] = _T("======================================================================\n");
TCHAR   g_szTitle1[] = _T("|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|\n");
TCHAR   g_szTitle2[] = _T("|=====|==============|==============|=================|==============|\n");
TCHAR   g_szLine[]   = _T("|  A: |              |              |                 |              |\n");

void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal);

int main(int argc, char* argv[]) {
   TCHAR szMsg[4200];
   struct _diskfree_t df = {0};
   ULONG uDriveMask = _getdrives();
   unsigned uErr, uLen, uDrive;

   printf(g_szBorder);
   printf(g_szTitle1);
   printf(g_szTitle2);

   for (uDrive=1; uDrive<=26; ++uDrive) {
      if (uDriveMask & 1) {
         uErr = _getdiskfree(uDrive, &df);
         memcpy(szMsg, g_szLine, sizeof(g_szLine));
         szMsg[3] = uDrive + 'A' - 1;

         if (uErr == 0) {
            utoiRightJustified(szMsg+8,  szMsg+19, df.total_clusters);
            utoiRightJustified(szMsg+23, szMsg+34, df.avail_clusters);
            utoiRightJustified(szMsg+38, szMsg+52, df.sectors_per_cluster);
            utoiRightJustified(szMsg+56, szMsg+67, df.bytes_per_sector);
         }
         else {
            uLen = FormatMessage(FORMAT_MESSAGE_FROM_SYSTEM, NULL,
                            uErr, 0, szMsg+8, 4100, NULL);
            szMsg[uLen+6] = ' ';
            szMsg[uLen+7] = ' ';
            szMsg[uLen+8] = ' ';
         }

         printf(szMsg);
      }

      uDriveMask >>= 1;
   }

   printf(g_szBorder);
}

void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal) {
   TCHAR* szCur = szRight;
   int nComma = 0;

   if (uVal) {
      while (uVal && (szCur >= szLeft)) {
         if   (nComma == 3) {
            *szCur = ',';
            nComma = 0;
         }
         else {
            *szCur = (uVal % 10) | 0x30;
            uVal /= 10;
            ++nComma;
         }

         --szCur;
      }
   }
   else {
      *szCur = '0';
      --szCur;
   }

   if (uVal) {
      szCur = szLeft;

      while   (szCur <= szRight) {
         *szCur = '*';
         ++szCur;
      }
   }
}
```

```Output
======================================================================
|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|
|=====|==============|==============|=================|==============|
|  A: | The device is not ready.    |                 |              |
|  C: |    4,721,093 |    3,778,303 |               8 |          512 |
|  D: |    1,956,097 |    1,800,761 |               8 |          512 |
|  E: | The device is not ready.    |                 |              |
======================================================================
```

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
