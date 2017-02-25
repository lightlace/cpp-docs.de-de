---
title: "_get_purecall_handler _set_purecall_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "_get_purecall_handler"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "set_purecall_handler_m"
  - "set_purecall_handler"
  - "stdlib/_set_purecall_handler"
  - "stdlib/_get_purecall_handler"
  - "_get_purecall_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_purecall_handler-Funktion"
  - "set_purecall_handler-Funktion"
  - "purecall_handler"
  - "set_purecall_handler_m-Funktion"
  - "_purecall_handler"
  - "_set_purecall_handler_m-Funktion"
  - "_get_purecall_handler-Funktion"
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _get_purecall_handler _set_purecall_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft ab oder legt den Fehlerhandler für einen rein virtuellen Funktionsaufruf fest.  
  
## Syntax  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### Parameter  
 `function`  
 Die aufzurufende Funktion, wenn eine rein virtuelle Funktion aufgerufen wird. Eine `_purecall_handler`\-Funktion muss einen void\-Rückgabetyp haben.  
  
## Rückgabewert  
 Der vorherige `_purecall_handler`. Gibt `nullptr`, wenn kein vorheriger Handler vorhanden ist.  
  
## Hinweise  
 Die `_get_purecall_handler` und `_set_purecall_handler` Funktionen sind Microsoft\-spezifisch und gelten nur für C\+\+\-Code.  
  
 Ein Aufruf einer rein virtuelle Funktion ist ein Fehler auf, da sie keine Implementierung hat. Standardmäßig generiert der Compiler Code um eine Fehler\-Handler\-Funktion aufzurufen, wenn eine reine virtuelle Funktion aufgerufen wird, mit dem das Programm beendet wird. Sie können Ihre eigenen fehlerhandlerfunktion für rein virtuelle Funktionsaufrufen, um sie für das Debuggen und Berichtszwecke abfangen installieren. Um Ihre eigenen Fehler\-Handler zu verwenden, erstellen Sie eine Funktion mit der `_purecall_handler` Signatur verwenden `_set_purecall_handler` den aktuellen Handler machen.  
  
 Da nur ein `_purecall_handler` für jeden Prozess, der beim Aufruf von `_set_purecall_handler` es sofort wirkt sich auf alle Threads. Der letzte Aufrufer in einem beliebigen Thread legt den Handler fest.  
  
 Rufen Sie zum Wiederherstellen der Standardverhalten `_set_purecall_handler` mithilfe einer `nullptr` Argument.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\< Cstdlib \> oder \< stdlib.h \>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
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
  
## Siehe auch  
 [Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)   
 [\_purecall](../../c-runtime-library/reference/purecall.md)