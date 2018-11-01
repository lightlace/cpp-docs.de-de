---
title: Verkettete Entladeinfostrukturen
ms.date: 11/04/2016
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
ms.openlocfilehash: 19d0beb8c3438183fa594d7ec3cab4929b3a491a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502140"
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