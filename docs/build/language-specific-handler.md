---
title: Sprachspezifischer Handler | Microsoft-Dokumentation
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
ms.openlocfilehash: 678f5695523751ebc1ef3c5dba2b63154b21833c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714947"
---
# <a name="language-specific-handler"></a>Sprachspezifischer Handler

Die relative Adresse der sprachspezifischer Handler ist in UNWIND_INFO vorhanden, wenn Flags UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER festgelegt sind. Wie im vorherigen Abschnitt beschrieben wird, wird die sprachspezifischer Handler als Teil der Suche nach einem Ausnahmehandler oder als Teil des eine Entladung aufgerufen. Er hat den folgenden Prototyp:

```
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** gibt einen Zeiger auf einen Ausnahmedatensatz, der die standard-Win64-Definition aufweist.

**EstablisherFrame** ist die Adresse der Basis der Zuordnung fester Stack für diese Funktion.

**ContextRecord** verweist auf den Ausnahmekontext auf die Zeit, die die Ausnahme (bei einer Ausnahme-Handler ausgelöst wurde) oder die aktuelle "abgewickelt" Kontext (im Fall Handler beenden).

**DispatcherContext** verweist auf die Dispatcher-Kontext für diese Funktion. Sie weist die folgende Definition:

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

**ControlPc** ist der Wert des RIP innerhalb dieser Funktion. Dies ist entweder eine Ausnahmeadresse oder die Adresse, an dem Steuerelement die Funktion verlassen. Dies ist die RIP, die verwendet wird, um festzustellen, ob das Steuerelement innerhalb eines überwachten Konstrukts in diese Funktion befindet (z. B. einen __try-Block für \__finally /\__except oder \__finally /\___identifier).

**ImageBase** ist die Anwendungsbasis (Ladeadresse) des Moduls mit dieser Funktion, die 32-Bit-Offsets, die in der Funktion-Eintrag verwendet hinzugefügt werden und Entladeinformationen um relative Adressen aufzuzeichnen.

**FunctionEntry** stellt einen Zeiger auf die RUNTIME_FUNCTION Funktionseinstieg, enthält die Funktion und entladen, Informationen zur Basis-Image relative Adressen für diese Funktion.

**EstablisherFrame** ist die Adresse der Basis der Zuordnung fester Stack für diese Funktion.

**TargetIp** liefert eine optionale Anweisungsadresse, die Fortsetzung Adresse die Entladung angibt. Diese Adresse wird ignoriert, wenn **EstablisherFrame** nicht angegeben ist.

**ContextRecord** verweist auf den Ausnahmekontext, für die Verwendung durch den Verteiler/entladen System Ausnahmecode.

**LanguageHandler** verweist auf die sprachspezifische Handlerroutine aufgerufen wird.

**HandlerData** zeigt auf die Handlerdaten sprachspezifischer für diese Funktion.

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung (x64)](../build/exception-handling-x64.md)