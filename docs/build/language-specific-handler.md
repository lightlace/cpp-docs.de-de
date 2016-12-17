---
title: "Sprachspezifischer Handler"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Sprachspezifischer Handler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die relative Adresse des sprachspezifischen Handlers ist in UNWIND\_INFO vorhanden, wenn die Flags UNW\_FLAG\_EHANDLER oder UNW\_FLAG\_UHANDLER festgelegt sind.  Wie im vorherigen Abschnitt beschrieben, wird der sprachspezifische Handler als Teil der Suche nach einem Ausnahmehandler oder als Teil eines Entladevorgangs aufgerufen.  Er besitzt folgenden Prototyp:  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** gibt einen Zeiger auf einen Ausnahmedatensatz an, der die Standard\-Win64\-Definition aufweist.  
  
 **EstablisherFrame** ist die Adresse der Basis der festen Stapelzuweisung für diese Funktion.  
  
 **ContextRecord** verweist auf den Ausnahmekontext zur Zeit der Auslösung der Ausnahme \(im Fall eines Ausnahmehandlers\) oder auf den aktuellen Entladekontext \(im Fall eines Beendigungshandlers\).  
  
 **DispatcherContext** verweist auf den Verteilerkontext für diese Funktion.  Er hat folgende Definition:  
  
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
  
 **ControlPc** ist der Wert des RIP innerhalb dieser Funktion.  Dabei handelt es sich entweder um eine Ausnahmeadresse oder die Adresse, an der die Funktion verlassen wurde.  Dieser RIP dient zur Feststellung, ob sich die Steuerung innerhalb eines überwachten Konstrukts in dieser Funktion befindet \(z. B. \_\_try\-Block für \_\_try\/\_\_except oder \_\_try\/\_\_finally\).  
  
 **ImageBase** ist die Anwendungsbasis \(Ladeadresse\) des Moduls, das diese Funktion enthält. Sie wird den 32\-Bit\-Offsets im Funktionseintrag und in den Entladeinformationen hinzugefügt, um relative Adressen aufzuzeichnen.  
  
 **FunctionEntry** enthält einen Zeiger auf den RUNTIME\_FUNCTION\-Funktionseintrag, der die auf die Anwendungsbasis bezogenen relativen Adressen der Funktion und der Entladeinformationen für diese Funktion enthält.  
  
 **EstablisherFrame** ist die Adresse der Basis der festen Stapelzuweisung für diese Funktion.  
  
 **TargetIp** enthält eine optionale Anweisungsadresse, die die Fortsetzungsadresse des Entladevorgangs angibt.  Diese Adresse wird ignoriert, wenn **EstablisherFrame** nicht angegeben ist.  
  
 **ContextRecord** verweist auf den Ausnahmekontext, zur Verwendung durch den Systemausnahmeauslösungs\-\/Entladecode.  
  
 **LanguageHandler** verweist auf die sprachspezifische Sprachhandlerroutine, die aufgerufen wird.  
  
 **HandlerData** verweist auf die sprachspezifischen Handlerdaten für diese Funktion.  
  
## Siehe auch  
 [Ausnahmebehandlung \(x64\)](../build/exception-handling-x64.md)