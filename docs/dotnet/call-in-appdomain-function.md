---
title: call_in_appdomain-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- call_in_appdomain
helpviewer_keywords:
- call_in_appdomain function
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
ms.openlocfilehash: a7ee0ef9c98ee940ab810abd82f6220da95d7346
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452131"
---
# <a name="callinappdomain-function"></a>call_in_appdomain-Funktion

Führt eine Funktion in einer angegebenen Anwendungsdomäne aus.

## <a name="syntax"></a>Syntax

```
template <typename ArgType1, ...typename ArgTypeN>
void call_in_appdomain(
   DWORD appdomainId,
   void (*voidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
template <typename RetType, typename ArgType1, ...typename ArgTypeN>
RetType call_in_appdomain(
   DWORD appdomainId,
   RetType (*nonvoidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
```

#### <a name="parameters"></a>Parameter

*appdomainId*<br/>
Die Anwendungsdomäne, in dem die Funktion aufgerufen werden soll.

*voidFunc*<br/>
Zeiger auf eine `void` -Funktion, die N-Parameter akzeptiert (0 < = N < = 15).

*nonvoidFunc*<br/>
Zeiger auf einen nicht-`void` -Funktion, die N-Parameter akzeptiert (0 < = N < = 15).

*arg1... ArgN*<br/>
0 (null), um 15 Parameter übergeben werden soll `voidFunc` oder `nonvoidFunc` in der anderen Anwendungsdomäne.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Ausführung `voidFunc` oder `nonvoidFunc` in die angegebene Anwendungsdomäne.

## <a name="remarks"></a>Hinweise

Die Argumente der Funktion übergeben wird, um `call_in_appdomain` muss sich nicht auf CLR-Typen.

## <a name="example"></a>Beispiel

```
// msl_call_in_appdomain.cpp
// compile with: /clr

// Defines two functions: one takes a parameter and returns nothing,
// the other takes no parameters and returns an int.  Calls both
// functions in the default appdomain and in a newly-created
// application domain using call_in_appdomain.

#include <msclr\appdomain.h>

using namespace System;
using namespace msclr;

void PrintCurrentDomainName( char* format )
{
   String^ s = gcnew String(format);
   Console::WriteLine( s, AppDomain::CurrentDomain->FriendlyName );
}

int GetDomainId()
{
   return AppDomain::CurrentDomain->Id;
}

int main()
{
   AppDomain^ appDomain1 = AppDomain::CreateDomain( "First Domain" );

   call_in_appdomain( AppDomain::CurrentDomain->Id,
                   &PrintCurrentDomainName,
                   (char*)"default appdomain: {0}" );
   call_in_appdomain( appDomain1->Id,
                   &PrintCurrentDomainName,
                   (char*)"in appDomain1: {0}" );

   int id;
   id = call_in_appdomain( AppDomain::CurrentDomain->Id, &GetDomainId );
   Console::WriteLine( "default appdomain id = {0}", id );
   id = call_in_appdomain( appDomain1->Id, &GetDomainId );
   Console::WriteLine( "appDomain1 id = {0}", id );
}
```

## <a name="output"></a>Output

```
default appdomain: msl_call_in_appdomain.exe
in appDomain1: First Domain
default appdomain id = 1
appDomain1 id = 2
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\appdomain.h >

**Namespace** Msclr