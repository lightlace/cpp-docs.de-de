---
title: -Kernelmodus (Kernel erstellen Binary für den Kernelmodus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /kernel
- /kernel-
dev_langs:
- C++
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02c5d8cff2d57a9dc8bfac31c4806a976d58859d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716793"
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel (Binary für den Kernelmodus erstellen)

Erstellt eine Binärdatei, die in der Windows-Kernel ausgeführt werden kann.

## <a name="syntax"></a>Syntax

```
/kernel[-]
```

## <a name="arguments"></a>Argumente

**/kernel**<br/>
Der Code in das aktuelle Projekt wird kompiliert und verknüpft werden anhand eines Satzes von Regeln der C++-Sprache, die auf Code beziehen, die im Kernelmodus ausgeführt werden.

**/Kernel-**<br/>
Der Code in das aktuelle Projekt wird kompiliert und verknüpft werden, ohne die Regeln der C++-Sprache, die auf Code beziehen, die im Kernelmodus ausgeführt werden.

## <a name="remarks"></a>Hinweise

Es gibt keine `#pragma`-Entsprechung, zum Steuern dieser Option.

Angeben der **/Kernel** -Option weist den Compiler und Linker vermitteln konnte, welche Sprachfeatures zulässige im Kernelmodus ausgeführt werden und um sicherzustellen, dass Sie haben genügend Ausdruckskraft Runtime Instabilität zu vermeiden, die eindeutig ist Kernelmodus C++. Dies wird erreicht, indem untersagt die Verwendung von C++-Sprachfunktionen, die sich unterbrechen den Betrieb im Kernelmodus ausgeführt und Warnungen für C++-Sprachfeatures, die potenziell führen zu einer Unterbrechung, aber nicht deaktiviert werden.

Die **/Kernel** Option gilt für Compiler und Linker Phasen eines Builds, und auf Projektebene festgelegt ist. Übergeben Sie die **/Kernel** Switch für den Compiler an, dass die resultierende Binärdatei, nach dem verknüpfen, in der Windows-Kernel geladen werden soll. Der Compiler wird das Spektrum der C++-Sprachfunktionen, um eine Teilmenge zu beschränken, die mit dem Kernel kompatibel ist.

Die folgende Tabelle enthält die Änderungen im Compilerverhalten beim **/Kernel** angegeben ist.

|Verhaltenstyp|**/ Kernel** Verhalten|
|-------------------|---------------------------|
|C++-Ausnahmebehandlung|Deaktiviert. Alle Instanzen der `throw` und `try` Schlüsselwörter ausgeben, einen Compilerfehler (mit Ausnahme der Ausnahmespezifikation `throw()`). Keine **/EH** Optionen sind kompatibel mit **/Kernel**, mit Ausnahme von **/EH-**.|
|LAUFZEITTYPINFORMATIONEN|Deaktiviert. Alle Instanzen der `dynamic_cast` und `typeid` Schlüsselwörter einen Compilerfehler, ausgeben, es sei denn, `dynamic_cast` statisch verwendet wird.|
|`new` und `delete`|Sie müssen explizit definieren die `new()` oder `delete()` Operator; weder die Laufzeit als auch der Compiler stellt eine Default-Definition bereit.|

Benutzerdefinierte Aufrufkonventionen, die [/GS](../../build/reference/gs-buffer-security-check.md) Buildoption und alle Optimierungen sind zulässig, bei der Verwendung der **/Kernel** Option. Inlining ist größtenteils nicht betroffen, von **/Kernel**, mit der gleichen Semantik, die vom Compiler berücksichtigt. Sollten Sie sicherstellen, dass die `__forceinline` inlining Qualifizierer wird berücksichtigt, stellen Sie sicher, dass die Warnung [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) aktiviert ist, damit Sie wissen, wenn eine bestimmte `__forceinline` Funktion ist nicht inline ersetzt.

Wenn der Compiler übergeben wird die **/Kernel** Switch sind ein Präprozessormakro mit dem Namen vordefiniert `_KERNEL_MODE` und hat den Wert **1**. Sie können dies verwenden, zur bedingten Kompilierung von Code je nachdem, ob die ausführungsumgebung im Benutzermodus oder Kernelmodus ist. Der folgende Code gibt beispielsweise, dass die Klasse in einem Segment nicht verwendete nicht ausgelagerte Arbeitsspeicher sein soll, wenn sie für Kernelmodus kompiliert wird.

```cpp
#ifdef _KERNEL_MODE
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))
#else
#define NONPAGESECTION
#endif

class NONPAGESECTION MyNonPagedClass
{
   // ...
};
```

Einige der folgenden Kombinationen von Zielarchitektur und **/arch** Option einen Fehler erzeugen, wenn sie verwendet werden **/Kernel**:

- **/ arch: {SSE&#124;SSE2&#124;AVX}** werden auf X86 nicht unterstützt. Nur **/arch:IA32** unterstützt, auf denen **/Kernel** auf X86.

- **/ arch: AVX** wird nicht unterstützt **/Kernel** auf X64.

Erstellen von Builds mit **/Kernel** übergibt außerdem **/Kernel** an den Linker. Sie ist Auswirkungen linkerverhalten:

- Inkrementelles Verknüpfen ist deaktiviert. Wenn Sie hinzufügen **/ incremental** an die Befehlszeile, gibt der Linker diese schwerwiegenden Fehler:

   **LINK: Schwerwiegender Fehler LNK1295: "/ INCREMENTAL" nicht kompatibel mit "/ KERNEL" Spezifikation; Link ohne "/ INCREMENTAL"**

- Der Linker überprüft jede Objektdatei (oder alle enthalten Archiv-Member von statischen Bibliotheken), um festzustellen, ob es mit kompiliert wurden konnte die **/Kernel** Option wurde jedoch nicht. Wenn alle Instanzen dieses Kriterium erfüllt, wird der Linker immer noch erfolgreich verknüpft, jedoch möglicherweise eine Warnung aus, geben Sie wie in der folgenden Tabelle gezeigt.

   ||**/ Kernel** Obj|**/Kernel-** Obj, MASM-Obj oder Cvtresed|Kombinieren von **/Kernel** und **/kernel-** OBJ-Dateien|
   |-|----------------------|-----------------------------------------------|-------------------------------------------------|
   |**Link/Kernel**|Ja|Ja|Ja, mit der Warnung LNK4257|
   |**Link**|Ja|Ja|Ja|

   **LNK4257 Verknüpfungsobjekt mit/Kernel nicht kompiliert; Image kann möglicherweise nicht ausgeführt.**

Die **/Kernel** Option und die **/Driver** Option unabhängig voneinander ausgeführt und keine wirkt sich auf die andere.

### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>So legen Sie die Compileroption "/ Kernel" in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. In der **zusätzliche Optionen** fügen `/kernel` oder `/kernel-`.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)