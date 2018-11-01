---
title: _get_purecall_handler, _set_purecall_handler
ms.date: 11/04/2016
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
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
apitype: DLLExport
f1_keywords:
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
ms.openlocfilehash: 0009b4bc1c7bf70bd84b9a82ecdc8643789e8164
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646359"
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler

Ruft den Handler für einen rein virtuellen Funktionsaufruf ab oder legt diesen fest.

## <a name="syntax"></a>Syntax

```cpp
typedef void (__cdecl* _purecall_handler)(void);
_purecall_handler __cdecl _get_purecall_handler(void);
_purecall_handler __cdecl _set_purecall_handler(
   _purecall_handler function
);
```

### <a name="parameters"></a>Parameter

*function*<br/>
Die aufzurufende Funktion, wenn eine rein virtuelle Funktion aufgerufen wird. Ein **_purecall_handler** Funktion muss einen void-Rückgabetyp aufweisen.

## <a name="return-value"></a>Rückgabewert

Die vorherige **_purecall_handler**. Gibt **"nullptr"** Wenn kein vorheriger Handler vorhanden war.

## <a name="remarks"></a>Hinweise

Die **_get_purecall_handler** und **_set_purecall_handler** Funktionen sind Microsoft-spezifisch und gelten nur für C++-Code.

Ein Aufruf an eine rein virtuelle Funktion ist ein Fehler, da sie keine Implementierung hat. Standardmäßig generiert der Compiler einen Code, um eine Fehlerhandlerfunktion aufzurufen, wenn eine reine virtuelle Funktion aufgerufen wird, womit das Programm beendet wird. Sie können Ihre eigene Fehlerhandlerfunktion für rein virtuelle Funktionsaufrufe installieren, um sie für das Debuggen und für Berichtszwecke abzufangen. Um Ihren eigenen Fehlerhandler zu verwenden, erstellen Sie eine Funktion mit der **_purecall_handler** Signatur verwenden **_set_purecall_handler** , es sich um den aktuellen Handler festzulegen.

Da ist nur ein **_purecall_handler** für jeden Prozess, der beim Aufrufen **_set_purecall_handler** beeinflusst alle Threads. Der letzte Aufrufer in einem beliebigen Thread legt den Handler fest.

Rufen Sie zum Wiederherstellen der Standardverhalten **_set_purecall_handler** mithilfe einer **"nullptr"** Argument.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_purecall_handler**, **_set_purecall_handler**|\<cstdlib> oder \<stdlib.h>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```cpp
// _set_purecall_handler.cpp
// compile with: /W1
#include <tchar.h>
#include <stdio.h>
#include <stdlib.h>

class CDerived;
class CBase
{
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function(void) = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase
{
public:
   CDerived() : CBase(this) {};   // C4355
   virtual void function(void) {};
};

CBase::~CBase()
{
   m_pDerived -> function();
}

void myPurecallHandler(void)
{
   printf("In _purecall_handler.");
   exit(0);
}

int _tmain(int argc, _TCHAR* argv[])
{
   _set_purecall_handler(myPurecallHandler);
   CDerived myDerived;
}
```

```Output
In _purecall_handler.
```

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)<br/>
[_purecall](purecall.md)<br/>
