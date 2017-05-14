---
title: tmpfile_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpfile_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tmpfile_s
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e66ffa5fdbb1785191865eba92c9d673fb847ada
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="tmpfiles"></a>tmpfile_s
Erstellt eine temporäre Datei. Dies ist eine Version von [tmpfile](../../c-runtime-library/reference/tmpfile.md) mit Sicherheitserweiterungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pFilePtr`  
 Die Adresse eines Zeigers, um die Adresse des generierten Zeigers in einen Stream zu speichern.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg 0 (null) zurück und einen Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`pFilePtr`|**Rückgabewert**|**Inhalte von** `pFilePtr`|  
|----------------|----------------------|---------------------------------|  
|`NULL`|`EINVAL`|nicht geändert|  
  
 Wenn der obengenannte Parametervalidierungsfehler auftritt, wird der ungültige Parameterhandler wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` zu `EINVAL`, und der Rückgabewert ist `EINVAL`.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `tmpfile_s` erstellt eine temporäre Datei und versieht diesen Stream im Argument `pFilePtr` mit einem Zeiger. Die temporäre Datei wird im Stammverzeichnis erstellt. Verwenden Sie zum Erstellen einer temporären Datei in einem anderen Verzeichnis als dem Stammverzeichnis [tmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) oder [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) in Verbindung mit [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Wenn die Datei nicht geöffnet werden kann, schreibt `tmpfile_s` `NULL` in den Parameter `pFilePtr`. Diese temporäre Datei wird automatisch gelöscht, wenn die Datei geschlossen wird, wenn das Programm normal beendet wird oder wenn `_rmtmp` aufgerufen wird, vorausgesetzt, dass sich das aktuelle Arbeitsverzeichnis nicht ändert. Die temporäre Datei wird im (binären Lese-/Schreib-) Modus `w+b` geöffnet.  
  
 Ein Fehler kann auftreten, wenn Sie mehr als `TMP_MAX_S` (siehe STDIO.H) Aufrufe mit `tmpfile_s.` versuchen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`tmpfile_s`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
> [!NOTE]
>  Für dieses Beispiel benötigen Sie Administratorrechte, um es unter Windows Vista auszuführen.  
  
```  
// crt_tmpfile_s.c  
// This program uses tmpfile_s to create a  
// temporary file, then deletes this file with _rmtmp.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char tempstring[] = "String to be written";  
   int  i;  
   errno_t err;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      err = tmpfile_s(&stream);  
      if( err )  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)
