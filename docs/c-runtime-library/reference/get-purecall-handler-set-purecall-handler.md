---
title: _get_purecall_handler, _set_purecall_handler | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd6373acbea0f265b40ff3bd1c25e1229014cafa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler
Ruft den Handler für einen rein virtuellen Funktionsaufruf ab oder legt diesen fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `function`  
 Die aufzurufende Funktion, wenn eine rein virtuelle Funktion aufgerufen wird. Eine `_purecall_handler`-Funktion muss einen void-Rückgabetyp haben.  
  
## <a name="return-value"></a>Rückgabewert  
 Der vorherige `_purecall_handler`. Gibt `nullptr`, wenn kein vorheriger Handler vorhanden ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `_get_purecall_handler`- und `_set_purecall_handler`-Funktionen sind Microsoft-spezifisch und gelten nur für C++-Code.  
  
 Ein Aufruf an eine rein virtuelle Funktion ist ein Fehler, da sie keine Implementierung hat. Standardmäßig generiert der Compiler einen Code, um eine Fehlerhandlerfunktion aufzurufen, wenn eine reine virtuelle Funktion aufgerufen wird, womit das Programm beendet wird. Sie können Ihre eigene Fehlerhandlerfunktion für rein virtuelle Funktionsaufrufe installieren, um sie für das Debuggen und für Berichtszwecke abzufangen. Um Ihren eigenen Fehlerhandler zu verwenden, erstellen Sie eine Funktion mit der `_purecall_handler`-Signatur und verwenden Sie anschließend `_set_purecall_handler`, um ihn als den aktuellen Handler festzulegen.  
  
 Da es nur eine `_purecall_handler`-Funktion pro Prozess gibt, werden automatisch alle Threads beim Aufruf von `_set_purecall_handler` beeinflusst. Der letzte Aufrufer in einem beliebigen Thread legt den Handler fest.  
  
 Rufen Sie zum Wiederherstellen des Standardverhaltens `_set_purecall_handler` mit einem `nullptr`-Argument auf.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\<cstdlib> oder \<stdlib.h>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
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
 [Error Handling (Fehlerbehandlung)](../../c-runtime-library/error-handling-crt.md)   
 [_purecall](../../c-runtime-library/reference/purecall.md)