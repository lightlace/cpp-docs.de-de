---
title: Verkettete Entladeinfostrukturen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6da09387595188026d855fb99a49b588e6f21aa3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715025"
---
# <a name="chained-unwind-info-structures"></a>Verkettete Entladeinfostrukturen

Wenn die UNW_FLAG_CHAININFO-Flag festgelegt ist, klicken Sie dann eine Entladung Info-Struktur ist eine sekundäre und die freigegebenen Ausnahme-Handler/verkettet-Info-Adressfeld enthält die primären Entladeinformationen. Der folgende Code Ruft die primären Entladeinformationen, vorausgesetzt, dass `unwindInfo` ist die Struktur, die das UNW_FLAG_CHAININFO flag so festgelegt sein.

```
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

Verkettete Informationen ist in zwei Situationen nützlich. Zunächst können sie für nicht zusammenhängende Codesegmente verwendet werden. Mit verketteten Informationen, können Sie die Größe des erforderlichen Entladeinformationen, reduzieren, da Sie nicht besitzen, das Array Entladung aus den primären Entladeinformationen zu duplizieren.

Sie können auch verketteten Informationen verwenden, um flüchtige registerspeicherungen zu gruppieren. Der Compiler kann eine Verzögerung von einigen volatile Register speichern, bis der Vorgang außerhalb des Funktionsprologs-Eintrag. Sie können dies durch die primäre Entladeinformationen für den Teil der Funktion vor dem gruppierten Code aufzeichnen und anschließendes Einrichten von Informationen mit einer nicht-NULL-Größe von Prolog, in dem die entladungscodes in den verketteten Informationen speichert, der nicht flüchtigen Register wiedergeben verkettet. In diesem Fall sind die entladungscodes alle Instanzen von UWOP_SAVE_NONVOL. Eine Gruppierung, die nicht flüchtige Register speichert, mithilfe einer CLIENTPUSHINSTALLATION oder ändert die RSP-Register mithilfe einer zusätzlichen festen stapelreservierung wird nicht unterstützt.

Ein UNWIND_INFO-Element, das UNW_FLAG_CHAININFO festgelegt ist kann einen RUNTIME_FUNCTION-Eintrag enthalten, dessen Element UNWIND_INFO UNW_FLAG_CHAININFO (mehrfache Komprimierung) festgelegt hat. Die verketteten entladen schließlich Informationen, die Zeiger auf ein Element UNWIND_INFO ankommen werden, das UNW_FLAG_CHAININFO deaktiviert ist; Dies ist das primäre UNWIND_INFO-Element, das auf der tatsächlichen Prozedureinstiegspunkt verweist.

## <a name="see-also"></a>Siehe auch

[Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)