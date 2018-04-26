---
title: _endthread, _endthreadex | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea85337ad22675a9cd7726fa5880d4d565ed9f14
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex

Beendet einen Thread; **_endthread** beendet einen Thread durch die erstellte **_beginthread** und **_endthreadex** beendet einen Thread durch die erstellte **_beginthreadex**.

## <a name="syntax"></a>Syntax

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>Parameter

*Retval* threadbeendigungscode.

## <a name="remarks"></a>Hinweise

Sie erreichen **_endthread** oder **_endthreadex** ausdrücklich auf einen Thread zu beenden jedoch **_endthread** oder **_endthreadex** wird aufgerufen automatisch, wenn der Thread aus der Routine zurückgegeben als Parameter an übergeben **_beginthread** oder **_beginthreadex**. Das Beenden eines Threads durch Aufruf von **Endthread** oder **_endthreadex** stellt die ordnungsgemäße Wiederherstellung der dem Thread zugeordneten Ressourcen sicher.

> [!NOTE]
> Rufen Sie für eine mit „Libcmt.lib“ verknüpfte ausführbare Datei die [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) -Win32-API nicht auf, damit das Laufzeitsystem nicht an der Freigabe von zugeordneten Ressourcen gehindert wird. **_endthread** und **_endthreadex** zugeordnete Threadressourcen und rufen dann **ExitThread**.

**_endthread** schließt das Threadhandle automatisch. (Dieses Verhalten unterscheidet sich von der Win32 **ExitThread** API.) Aus diesem Grund bei Verwendung von **_beginthread** und **_endthread**, nicht explizit schließen Sie das Threadhandle durch Aufrufen von Win32 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API.

Wie die Win32 **ExitThread** -API, **_endthreadex** wird nicht das Threadhandle geschlossen. Aus diesem Grund bei Verwendung von **_beginthreadex** und **_endthreadex**, schließen Sie das Threadhandle durch Aufrufen von Win32 **CloseHandle** API.

> [!NOTE]
> **_endthread** und **_endthreadex** dazu führen, dass ausstehende C++-Destruktoren im Thread nicht aufgerufen werden.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Multithread-Versionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [_beginthread](beginthread-beginthreadex.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
