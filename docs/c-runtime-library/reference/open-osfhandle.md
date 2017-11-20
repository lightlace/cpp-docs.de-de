---
title: _open_osfhandle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _open_osfhandle
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
- _open_osfhandle
- open_osfhandle
dev_langs: C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8d214df5d1e1cd3a48336723cecbf530402eafe3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="openosfhandle"></a>_open_osfhandle
Ordnet den C-Laufzeit-Dateideskriptor einem vorhandenen Betriebssystem-Dateihandle zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `osfhandle`  
 Betriebssystem-Dateihandle.  
  
 `flags`  
 Zulässige Vorgangsarten.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `_open_osfhandle` einen C-Laufzeit-Dateideskriptor zurück. Andernfalls wird-1 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die `_open_osfhandle`-Funktion weist einen C-Laufzeit-Dateideskriptor zu und ordnet diesen der von `osfhandle` angegebenen Betriebssystem-Dateihandle zu. Das `flags`-Argument ist ein Ganzzahlausdruck, der von einer oder mehreren der folgenden Manifestkonstanten gebildet wurde, die in Fcntl.h definiert sind. Wenn zwei oder mehr Manifestkonstanten verwendet werden, um das `flags`-Argument zu bilden, werden die Konstanten mit dem bitweisen OR-Operator kombiniert ( **&#124;** ).  
  
 Fcntl.h definiert die folgenden Manifestkonstanten.  
  
 **_O_APPEND**  
 Positioniert einen Dateizeiger vor jedem Schreibvorgang am Ende der Datei.  
  
 **_O_RDONLY**  
 Öffnet eine Datei nur zum Lesen.  
  
 **_O_TEXT**  
 Öffnet eine Datei im Textmodus (übersetzt).  
  
 **_O_WTEXT**  
 Öffnet eine Datei in Unicode (übersetzt UTF-16).  
  
 Rufen Sie `_close` auf, um eine mit `_open_osfhandle` geöffnete Datei zu schließen. Durch einen Aufruf von `_close` wird auch das zugrunde liegende Handle geschlossen; daher ist es nicht notwendig die Win32-Funktion `CloseHandle` am ursprünglichen Handle aufzurufen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_open_osfhandle`|\<io.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)