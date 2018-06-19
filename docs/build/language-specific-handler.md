---
title: Sprachspezifischer Handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6cbfbe6a9b98828a63fb4a092717bfab583e9a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368797"
---
# <a name="language-specific-handler"></a>Sprachspezifischer Handler
Die relative Adresse der sprachspezifischer Handler ist in UNWIND_INFO vorhanden, wenn Flags UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER festgelegt sind. Wie im vorherigen Abschnitt beschrieben wird, wird die sprachspezifischer Handler als Teil der Suche nach einem Ausnahmehandler oder als Teil einer Entladung aufgerufen. Es sind die folgenden Prototyp:  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** gibt einen Zeiger auf einen Ausnahmedatensatz, der standard Win64-Definition aufweist.  
  
 **EstablisherFrame** ist die Adresse der Basis des für diese Funktion den festen stapelzuordnung.  
  
 **ContextRecord** verweist auf den Ausnahmekontext zum Zeitpunkt der Ausnahme (im Fall Handler Ausnahme) ausgelöst wurde oder die aktuelle "abgewickelt" Kontext (im Fall Handler Beendigung).  
  
 **DispatcherContext** an den Verteilerkontext für diese Funktion verweist. Er ist wie folgt definiert:  
  
```  
typedef struct _DISPATCHER_CONTEXT {  
    ULONG64 ControlPc;  
    ULONG64 ImageBase;  
    PRUNTIME_FUNCTION FunctionEntry;  
    ULONG64 EstablisherFrame;  
    ULONG64 TargetIp;  
    PCONTEXT ContextRecord;  
    PEXCEPTION_ROUTINE LanguageHandler;  
    PVOID HandlerData;  
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;  
```  
  
 **ControlPc** ist der Wert des RIP innerhalb dieser Funktion. Dies ist eine Ausnahmeadresse oder die Adresse, an dem Steuerelement die Funktion verlassen. Dies ist die RIP, der verwendet wird, um festzustellen, ob das Steuerelement innerhalb eines überwachten Konstrukts in diese Funktion befindet (z. B. einen __try-Block für \__finally /\__except oder \__finally /\___identifier).  
  
 **"ImageBase"** ist die Anwendungsbasis (Last-Adresse) des Moduls mit dieser Funktion, um die 32-Bit-Offsets, die in den Funktionsstart verwendet hinzugefügt werden und Informationen zum Aufzeichnen von relativer Adressen entladen.  
  
 **FunctionEntry** stellt einen Zeiger auf den RUNTIME_FUNCTION Funktionseinstieg, halten die Funktion und Info Abbildbasis relative Adressen für diese Funktion zu entladen.  
  
 **EstablisherFrame** ist die Adresse der Basis des für diese Funktion den festen stapelzuordnung.  
  
 **TargetIp** liefert eine optionale Anweisungsadresse, die die Fortsetzung Adresse die Entladung angibt. Diese Adresse wird ignoriert, wenn **EstablisherFrame** nicht angegeben wird.  
  
 **ContextRecord** verweist auf den Ausnahmekontext, für die Verwendung durch den Dispatch/entladen System Ausnahmecode.  
  
 **LanguageHandler** verweist auf die sprachspezifische Handlerroutine aufgerufen werden.  
  
 **HandlerData** verweist auf die sprachspezifische Handlerdaten für diese Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung (x64)](../build/exception-handling-x64.md)