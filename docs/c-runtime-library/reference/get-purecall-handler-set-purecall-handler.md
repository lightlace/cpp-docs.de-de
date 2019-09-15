---
title: _get_purecall_handler, _set_purecall_handler
ms.date: 11/04/2016
api_name:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 73fc2ffe5cd4ed65c8695432b53816090bbc5f8e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955673"
---
# <a name="_get_purecall_handler-_set_purecall_handler"></a>_get_purecall_handler, _set_purecall_handler

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
Die aufzurufende Funktion, wenn eine rein virtuelle Funktion aufgerufen wird. Eine **_purecall_handler** -Funktion muss einen void-Rückgabetyp aufweisen.

## <a name="return-value"></a>Rückgabewert

Der vorherige **_purecall_handler**. Gibt **nullptr** zurück, wenn kein vorheriger Handler vorhanden war.

## <a name="remarks"></a>Hinweise

Die **_get_purecall_handler** -Funktion und die **_set_purecall_handler** -Funktion sind Microsoft-spezifisch C++ und gelten nur für Code.

Ein Aufruf an eine rein virtuelle Funktion ist ein Fehler, da sie keine Implementierung hat. Standardmäßig generiert der Compiler einen Code, um eine Fehlerhandlerfunktion aufzurufen, wenn eine reine virtuelle Funktion aufgerufen wird, womit das Programm beendet wird. Sie können Ihre eigene Fehlerhandlerfunktion für rein virtuelle Funktionsaufrufe installieren, um sie für das Debuggen und für Berichtszwecke abzufangen. Um einen eigenen Fehlerhandler zu verwenden, erstellen Sie eine Funktion, die über die **_purecall_handler** -Signatur verfügt, und verwenden Sie dann **_set_purecall_handler** , um Sie als aktuellen Handler festzulegen.

Da es nur eine **_purecall_handler** für jeden Prozess gibt, wirkt sich das, wenn Sie **_set_purecall_handler** aufruft, sofort auf alle Threads aus. Der letzte Aufrufer in einem beliebigen Thread legt den Handler fest.

Um das Standardverhalten wiederherzustellen, müssen Sie **_set_purecall_handler** mit einem **nullptr** -Argument aufzurufen.

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
