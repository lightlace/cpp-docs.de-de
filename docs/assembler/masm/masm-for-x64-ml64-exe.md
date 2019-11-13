---
title: MASM für x64 (ml64.exe)
ms.date: 08/30/2018
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
ms.openlocfilehash: d9b550313c8e65e47db70dc81519abce7db95da5
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050196"
---
# <a name="masm-for-x64-ml64exe"></a>MASM für x64 (ml64.exe)

Visual Studio enthält sowohl 32-Bit-als auch 64-Bit-gehostete Versionen von Microsoft Assembler (MASM), um x64-Code als Ziel zu haben. Mit dem Namen ml64. exe ist dies der Assembler, der die Sprache x64 Assembler akzeptiert. Die MASM-Befehlszeilen Tools werden installiert, wenn Sie eine C++ Arbeitsauslastung während der Installation von Visual Studio auswählen. Die MASM-Tools sind nicht als separater Download verfügbar. Anweisungen zum herunterladen und Installieren einer Kopie von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio). Wenn Sie die komplette Visual Studio-IDE nicht installieren möchten, aber nur die Befehlszeilen Tools verwenden möchten, laden Sie die [Buildtools für Visual Studio](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)herunter.

Wenn Sie MASM verwenden möchten, um Code für x64-Ziele in der Befehlszeile zu erstellen, müssen Sie eine Developer-Eingabeaufforderung für x64-Ziele verwenden, mit der der erforderliche Pfad und andere Umgebungsvariablen festgelegt werden. Informationen zum Starten einer Developer-Eingabeaufforderung finden Sie unter [Build C/C++ Code in der Befehlszeile](../../build/building-on-the-command-line.md).

Informationen zu den Befehlszeilenoptionen von ml64. exe finden Sie unter [ml-und ML64-Befehlszeilen Referenz](../../assembler/masm/ml-and-ml64-command-line-reference.md).

Der Inline Assembler oder die Verwendung des ASM-Schlüssel Worts wird für x64-oder arm-Ziele nicht unterstützt. Um Ihren x86-Code, der den Inline Assembler verwendet, auf x64 oder Arm zu portieren, C++können Sie Ihren Code in konvertieren, systeminterne Compilerfunktionen verwenden oder Quelldateien in Assemblersprache erstellen. Der Microsoft C++ -Compiler unterstützt systeminterne Funktionen, um Ihnen die Verwendung von speziellen Funktions Anweisungen (z. b. privilegiert, bitscan/Test, Interlocked usw.) in so nah wie möglich zu ermöglichen. Informationen zu verfügbaren systeminternen Funktionen finden Sie unter systeminterne [Compilerfunktionen](../../intrinsics/compiler-intrinsics.md).

## <a name="add-an-assembler-language-file-to-a-visual-studio-c-project"></a>Hinzufügen einer Assembler Sprachdatei zu einem Visual Studio C++ -Projekt

Das Visual Studio-Projekt System unterstützt assemblysprachdateien, die mithilfe von C++ MASM in Ihren Projekten erstellt wurden. Sie können x64-Assemblyquelldateien erstellen und diese in Objektdateien erstellen, indem Sie MASM verwenden, das x64 vollständig unterstützt. Anschließend können Sie diese Objektdateien mit dem Code C++ verknüpfen, der für x64-Ziele erstellt wurde. Dies ist eine Möglichkeit, das Fehlen eines x64-Inline Assemblers zu überwinden.

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-studio-c-project"></a>So fügen Sie einem vorhandenen Visual Studio C++ -Projekt eine Assembler Sprachdatei hinzu

1. Wählen Sie das Projekt im **Projektmappen-Explorer** aus. Wählen Sie in der Menüleiste **Projekt**und dann **Anpassungen erstellen**aus.

1. Aktivieren Sie im Dialogfeld **Visual C++ Build-Anpassungs Dateien** das Kontrollkästchen neben **MASM (. targets,.** -Eigenschaften). Wählen Sie **OK** aus, um die Auswahl zu speichern und das Dialogfeld zu schließen.

1. Wählen Sie in der Menüleiste **Projekt**, **Neues Element hinzufügen**aus.

1. Wählen Sie **C++** im mittleren Bereich im Dialogfeld Neues Element hinzufügen die Option Datei (. cpp) aus. Geben Sie im Steuerelement für die **namens** Bearbeitung einen neuen Dateinamen ein, der eine **ASM** -Erweiterung anstelle von cpp enthält. Wählen Sie **Hinzufügen** aus, um die Datei Ihrem Projekt hinzuzufügen und das Dialogfeld zu schließen.

Erstellen Sie den Assembler-Sprachcode in der ASM-Datei, die Sie hinzugefügt haben. Wenn Sie die Projekt Mappe erstellen, wird der MASM-Assembler aufgerufen, um die ASM-Datei in einer Objektdatei zusammenzufassen, die dann mit dem Projekt verknüpft wird. Um den Symbol Zugriff zu vereinfachen, deklarieren Sie die Assemblyfunktionen als `extern "C"` im C++ Quellcode, anstatt C++ die namens Ergänzung Konventionen in den Quelldateien der Assembler-Sprache zu verwenden.

## <a name="ml64-specific-directives"></a>ml64-spezifische Direktiven

Sie können die folgenden ml64-spezifischen Direktiven in Ihrem assemblyquellcode verwenden, der x64 als Ziel verwendet:

- [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)

- [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)

- [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)

- [.PUSHREG](../../assembler/masm/dot-pushreg.md)

- [.SAVEREG](../../assembler/masm/dot-savereg.md)

- [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)

- [.SETFRAME](../../assembler/masm/dot-setframe.md)

Außerdem wurde die [proc](../../assembler/masm/proc.md) -Direktive für die Verwendung mit ml64. exe aktualisiert.

## <a name="32-bit-address-mode-address-size-override"></a>32-Bit-Adress Modus (Adressgröße außer Kraft Setzung)

MASM gibt die Adress Größen Überschreitung von 0x67 aus, wenn ein Speicher Operand 32-Bit-Register umfasst. In den folgenden Beispielen wird beispielsweise die außer Kraft setzung der Adressgröße ausgegeben:

```asm
mov rax, QWORD PTR [ecx]
mov eax, DWORD PTR [ecx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10d+0100h]
prefetch [eax]
movnti rax, QWORD PTR [r8d]
```

MASM geht davon aus, dass eine 64-Bit-Adressierung beabsichtigt ist, wenn eine 32-Bit-Verschiebung allein als Speicher Operand angezeigt wird. Es gibt zurzeit keine Unterstützung für die 32-Bit-Adressierung mit diesen Operanden.

Zum Schluss generiert das Mischen von Register Größen in einem Arbeitsspeicher Operanden, wie im folgenden Code gezeigt, einen Fehler.

```asm
mov eax, DWORD PTR [rcx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10+0100h]
```

## <a name="see-also"></a>Siehe auch

[Referenz zum Microsoft-Makroassembler](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>