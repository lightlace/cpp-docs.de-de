---
title: Call_in_appdomain-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- call_in_appdomain
dev_langs:
- C++
helpviewer_keywords:
- call_in_appdomain function
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a8689254120416e5b2bf5de617fc3f3ef466abb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 `appdomainId`  
 Die Anwendungsdomäne, in dem die Funktion aufgerufen werden soll.  
  
 `voidFunc`  
 Zeiger auf eine `void` Funktion, die N-Parameter akzeptiert (0 < = N < = 15).  
  
 `nonvoidFunc`  
 Zeiger auf einen nicht-`void` Funktion, die N-Parameter akzeptiert (0 < = N < = 15).  
  
 `arg1...argN`  
 Null bis 15 Parameter zu übergebenden `voidFunc` oder `nonvoidFunc` in der anderen Anwendungsdomäne.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Ausführung `voidFunc` oder `nonvoidFunc` in die angegebene Anwendungsdomäne.  
  
## <a name="remarks"></a>Hinweise  
 Die Argumente der Funktion zu übergeben, um `call_in_appdomain` CLR-Typen nicht sein.  
  
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
  
## <a name="output"></a>Ausgabe  
  
```  
default appdomain: msl_call_in_appdomain.exe  
in appDomain1: First Domain  
default appdomain id = 1  
appDomain1 id = 2  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\appdomain.h >  
  
 **Namespace** Msclr