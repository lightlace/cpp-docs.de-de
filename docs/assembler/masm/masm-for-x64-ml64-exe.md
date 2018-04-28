---
title: MASM für X64 (ml64.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b17771239ff9c89b765576ba49515463db42386f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="masm-for-x64-ml64exe"></a>MASM für x64 (ml64.exe)

Visual Studio enthält 32-Bit und 64-Bit-gehostete Versionen MASM auf Zielcode X64. Mit dem Namen ml64.exe, dies ist der Assembler X64 akzeptiert, die Assembler-Sprache. Die Befehlszeilentools MASM werden installiert, wenn Sie eine C++-arbeitsauslastung während der Installation von Visual Studio auswählen. Diese Tools sind nicht als separater Download verfügbar. Zum Herunterladen und installieren eine Kopie von Visual Studio, finden Sie unter [ https://www.visualstudio.com/ ](https://www.visualstudio.com/). Wenn Sie nicht, installieren Sie Visual Studio-IDE möchten, sondern nur die Befehlszeilentools benötigen, finden Sie unter der **Build-Tools für Visual Studio-2017** option die [Visual Studio-Downloads](https://www.visualstudio.com/downloads/) Seite.

Mit MASM erstellen Code für X64 ausgerichtet ist, in der Befehlszeile angegeben, müssen Sie eine Developer-Eingabeaufforderung für X64 Ziele, die den erforderlichen Pfad und andere Umgebungsvariablen festlegt. Informationen zum Starten einer Developer-Eingabeaufforderung finden Sie unter [Erstellen von C/C++-Code in der Befehlszeile](../../build/building-on-the-command-line.md).

Informationen zu Befehlszeilenoptionen ml64.exe, finden Sie unter [ml- und ML64-Befehlszeilenreferenz](../../assembler/masm/ml-and-ml64-command-line-reference.md).  
  
Inlineassembler oder das ASM-Schlüsselwort verwendet, wird nicht für X64 oder ARM-Ziele unterstützt. So portieren Sie Ihre X86 code diese Inlineassembler verwendet X64 oder ARM Codes in C++ zu konvertieren, verwenden die systeminternen Funktionen des Compilers oder Assembler-Sprache Quelldateien erstellen. Visual C++-Compiler unterstützt die systeminternen Funktionen, damit Sie spezielle Funktion-Anweisungen verwenden, können für beispielsweise privilegierte, Scan/Test interlocked usw., in als nahe wie möglich eine plattformübergreifend bit. Weitere Informationen zu verfügbaren systeminternen Funktionen, finden Sie unter [Compilerfunktionen](../../intrinsics/compiler-intrinsics.md).  

## <a name="add-an-assembler-language-file-to-a-visual-c-project"></a>Eine Assembler-Datei in ein Visual C++-Projekt hinzufügen  
  
Das Visual Studio-Projektsystem unterstützt Assembler-Sprachdateien MASM in C++-Projekten mit erstellt haben. Sie können erstellen X64 Assembler-Quellcode Dateien und erstellen sie in Objektdateien mithilfe von MASM, die X64 vollständig unterstützt. Anschließend können Sie diese Objektdateien verknüpfen, um C++-Code für X64 erstellten Ziele. Dies ist eine Möglichkeit zum Umgehen der Mangel an eine X64 Inlineassembler.  

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-c-project"></a>Eine Assembler-Language-Datei zu einem vorhandenen Visual C++-Projekt hinzufügen

1. Wählen Sie das Projekt in **Projektmappen-Explorer**. Wählen Sie in der Menüleiste **Projekt**, **Anpassungen erstellen**.

1. In der **Visual C++ erstellen Anpassungsdateien** Dialogfeld Feld, aktivieren Sie das Kontrollkästchen neben **masm(.targets,.props)**. Wählen Sie **OK** Ihre Auswahl zu speichern und das Dialogfeld zu schließen.

1. Wählen Sie in der Menüleiste **Projekt**, **neues Element hinzufügen**. 

1. In der **neues Element hinzufügen** wählen Sie im Dialogfeld **C++-Datei (.cpp)** im mittleren Bereich. In der **Namen** Steuerelement bearbeiten, geben Sie einen neuen Dateinamen ein, die verfügt über eine **ASM** -Erweiterung anstelle von cpp. Wählen Sie **hinzufügen** auf die Datei dem Projekt hinzufügen und das Dialogfeld zu schließen.

Erstellen Sie den Assembler-Language-Code in der ASM-Datei, die Sie hinzugefügt haben. Wenn Sie die Projektmappe erstellen, wird der MASM-Assembler aufgerufen, um die ASM-Datei in einer Objektdatei zusammenstellen, die dann in Ihr Projekt verknüpft ist. Symbol für den Zugriff zu vereinfachen, deklarieren Sie die Assembler-Funktionen als `extern "C"` in Ihrem C++-Quellcode, anstatt die C++ benennen Konventionen in der Assembler-Sprache für die namensergänzung Quelldateien.
  
## <a name="ml64-specific-directives"></a>ml64-Direktiven  

Sie können die folgenden ml64-spezifische Anweisungen im Quellcode für die Assembler-Sprache verwenden, die x64 abzielt:  
  
-   [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)  
  
-   [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../../assembler/masm/dot-pushreg.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
Darüber hinaus die [PROC](../../assembler/masm/proc.md) Richtlinie wurde für die Verwendung mit ml64.exe aktualisiert.  
  
## <a name="32-bit-address-mode-address-size-override"></a>32-Bit-Adressmodus (Adresse Größe überschreiben)  

MASM gibt die Adresse 0 x 67 Größe Außerkraftsetzung aus, wenn eine arbeitsspeicheroperanden 32-Bit-Register enthält. In den folgenden Beispielen würde z. B. bei der Adresse Größe Außerkraftsetzung ausgegeben werden:  
  
```MASM  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
MASM wird davon ausgegangen, dass wenn eine 32-Bit-Verschiebung allein als eine arbeitsspeicheroperanden angezeigt wird, 64-Bit-Adressierung vorgesehen ist. Es gibt derzeit keine Unterstützung für 32-Bit-Adressierung mit solchen Operanden.  
  
Schließlich generiert das Register Größen innerhalb einer arbeitsspeicheroperanden mischen, wie im folgenden Code veranschaulicht einen Fehler aus.  
  
```MASM  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## <a name="see-also"></a>Siehe auch  

[Referenz zum Microsoft-Makroassembler](../../assembler/masm/microsoft-macro-assembler-reference.md)