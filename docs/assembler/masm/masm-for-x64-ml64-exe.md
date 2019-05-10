---
title: MASM für x64 (ml64.exe)
ms.date: 08/30/2018
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
ms.openlocfilehash: 1a92d2a22e8aa9df29c18fa36ff4508eb8eec57f
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65445869"
---
# <a name="masm-for-x64-ml64exe"></a>MASM für x64 (ml64.exe)

Visual Studio enthält sowohl die 32-Bit-als auch die 64-Bit-gehostete Versionen der Microsoft-Assembler (MASM) Code des ereignisdateiziels X64. Mit dem Namen ml64.exe, dies ist der Assembler, die akzeptiert X64 Assembler-Sprache. Die MASM-Befehlszeilentools werden installiert, wenn Sie eine C++-Workload während der Installation von Visual Studio auswählen. Die MASM-Tools sind nicht als separater Download zur Verfügung. Anweisungen zum Herunterladen und installieren Sie eine Kopie von Visual Studio, finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio). Wenn Sie nicht die vollständige Visual Studio-IDE installieren möchten, sondern nur die Befehlszeilentools möchten, laden Sie die [Build-Tools für Visual Studio](https://visualstudio.microsoft.com/downloads/).

MASM verwenden, erstellen Sie Code für X64 ausgerichtet ist, in der Befehlszeile, müssen Sie eine Developer-Eingabeaufforderung für X64 Ziele, wodurch der erforderliche Pfad und andere Umgebungsvariablen festgelegt. Informationen zum Developer-Eingabeaufforderung zu starten, finden Sie unter [Erstellen von C/C++-Code, in der Befehlszeile](../../build/building-on-the-command-line.md).

Weitere Informationen zu Befehlszeilenoptionen ml64.exe, finden Sie unter [ml- und ML64-Befehlszeilenreferenz](../../assembler/masm/ml-and-ml64-command-line-reference.md).

Inlineassembler oder das ASM-Schlüsselwort wird nicht für X64 oder ARM-Ziele unterstützt. So portieren Sie Ihre X86, Inlineassembler verwendet code X64 "oder" ARM ", Sie können Ihren Code in C++ zu konvertieren, intrinsische Compilerfunktionen zu verwenden oder Assembler-Sprache-Quelldateien erstellen. Microsoft C++ -Compiler unterstützt die systeminternen Funktionen, damit Sie spezielle-Function-Anweisungen können für beispielsweise privilegiert, Überprüfung/Test, interlocked usw., in wie nahe wie möglich eine plattformübergreifend bit. Weitere Informationen zu verfügbaren systeminternen Funktionen, finden Sie unter [intrinsische Compilerfunktionen](../../intrinsics/compiler-intrinsics.md).

## <a name="add-an-assembler-language-file-to-a-visual-studio-c-project"></a>Fügen Sie eine Assembler-Language-Datei eine Visual Studio- C++ Projekt

Das Visual Studio-Projektsystem unterstützt Assembler-Language-Dateien, die mithilfe von MASM in C++-Projekten erstellt. Sie können erstellen X64 Assembler-Quelle von Dateien und in Objektdateien mit MASM, die X64 vollständig unterstützt. Anschließend können Sie diese Objektdateien verknüpfen, um C++-Code für die X64 Ziele. Dies ist eine Möglichkeit zum Umgehen des Mangel an x X64 Inlineassembler.

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-studio-c-project"></a>Zum Hinzufügen einer Assembler-Language-Datei zu einer vorhandenen Visual Studio C++ Projekt

1. Wählen Sie das Projekt im **Projektmappen-Explorer** aus. Wählen Sie auf der Menüleiste **Projekt**, **Buildanpassungen**.

1. In der **Visual C++ für Buildanpassungsdateien** Dialogfeld Feld, aktivieren Sie das Kontrollkästchen neben **masm(.targets,.props)**. Wählen Sie **OK** Ihre Auswahl zu speichern und schließen Sie das Dialogfeld.

1. Wählen Sie auf der Menüleiste **Projekt**, **neues Element hinzufügen**.

1. In der **neues Element hinzufügen** wählen Sie im Dialogfeld **C++-Datei (.cpp)** im mittleren Bereich. In der **Namen** Steuerelement bearbeiten, geben Sie einen neuen Dateinamen ein, die eine **.asm** anstatt cpp. Wählen Sie **hinzufügen** zu Ihrem Projekt die Datei hinzu, und schließen Sie das Dialogfeld.

Erstellen Sie Ihren Assembler-Language-Code in die ASM-Datei, die Sie hinzugefügt haben. Wenn Sie die Projektmappe erstellen, wird der MASM-Assembler aufgerufen, um die ASM-Datei in eine Objektdatei zusammenstellen, die dann in Ihr Projekt verknüpft ist. Deklarieren Sie um Symbol den Zugriff zu vereinfachen, die Assembler-Funktionen als `extern "C"` in C++-Quellcode, anstatt mit C++ weisen Konventionen in Ihrer Assembler-Sprache für die namensergänzung Quelldateien.

## <a name="ml64-specific-directives"></a>ml64-spezifische Anweisungen

Sie können die folgenden ml64-spezifische Anweisungen im Quellcode-Assembler-Sprache verwenden, die x64 zu abzielt:

- [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)

- [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)

- [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)

- [.PUSHREG](../../assembler/masm/dot-pushreg.md)

- [.SAVEREG](../../assembler/masm/dot-savereg.md)

- [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)

- [.SETFRAME](../../assembler/masm/dot-setframe.md)

Darüber hinaus die [PROC](../../assembler/masm/proc.md) Richtlinie wurde für die Verwendung mit ml64.exe aktualisiert.

## <a name="32-bit-address-mode-address-size-override"></a>32-Bit-Adressmodus (Außerkraftsetzung des Adresse Größe)

MASM gibt den 0 x 67 Größe außer Kraft setzen, wenn eine arbeitsspeicheroperanden 32-Bit-Register enthält. Beispielsweise dazu führen, dass in den folgenden Beispielen die Adresse Größe außer Kraft setzen, die ausgegeben werden:

```asm
mov rax, QWORD PTR [ecx]
mov eax, DWORD PTR [ecx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10d+0100h]
prefetch [eax]
movnti rax, QWORD PTR [r8d]
```

MASM wird davon ausgegangen, dass wenn eine 32-Bit-Verschiebung als Speicheroperand allein angezeigt wird, 64-Bit-Adressierung vorgesehen ist. Es gibt derzeit keine Unterstützung für 32-Bit-Adressierung mit solchen Operanden.

Schließlich generiert das Mischen von Register-Größen in einen Speicheroperanden aus, wie im folgenden Code veranschaulicht einen Fehler aus.

```asm
mov eax, DWORD PTR [rcx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10+0100h]
```

## <a name="see-also"></a>Siehe auch

[Referenz zum Microsoft-Makroassembler](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>