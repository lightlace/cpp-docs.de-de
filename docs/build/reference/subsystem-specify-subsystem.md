---
title: /SUBSYSTEM (Subsystem angeben)
ms.date: 11/04/2016
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
ms.openlocfilehash: ecda3443d0422af4d5ceec9282d86590c53af2f5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821260"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (Subsystem angeben)

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|
            POSIX|WINDOWS)
            [,major[.minor]]
```

## <a name="arguments"></a>Argumente

**BOOT_APPLICATION**<br/>
Eine in der Windows-Startumgebung ausgeführte Anwendung. Weitere Informationen zu startanwendungen finden Sie unter [Informationen zu BCD](/previous-versions/windows/desktop/bcd/about-bcd).

**VERWALTUNGSKONSOLE**<br/>
Win32-Zeichenmodusanwendung. Im Betriebssystem wird eine Konsole für Konsolenanwendungen zur Verfügung gestellt. Wenn `main` oder `wmain` für nativen Code definiert ist, ist `int main(array<String ^> ^)` für verwalteten Code definiert. Sie können die Anwendung auch nur mithilfe von `/clr:safe` erstellen. CONSOLE ist der Standardwert.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Die Extensible Firmware Interface-Subsysteme. Weitere Informationen finden Sie in der EFI-Spezifikation. Beispiele finden Sie unter der Intel-Website. Die erforderliche Mindest- und Standardversion ist Version 1.0.

**NATIVE**<br/>
Kernelmodustreiber für Windows NT. Diese Option ist üblicherweise für Windows-Systemkomponenten reserviert. Wenn [/Driver: WDM](driver-windows-nt-kernel-mode-driver.md) angegeben ist, ist NATIVE der Standardwert ist.

**POSIX**<br/>
Anwendung, die mit dem POSIX-Subsystem unter Windows NT ausgeführt wird.

**WINDOWS**<br/>
Für die Anwendung ist keine Konsole erforderlich, wahrscheinlich da für die Interaktion mit dem Benutzer eigene Fenster erstellt werden. Wenn `WinMain` oder `wWinMain` für nativen Code definiert ist oder `WinMain(HISTANCE *, HINSTANCE *, char *, int)` oder `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` für verwalteten Code definiert ist, ist WINDOWS der Standardwert.

*wichtige* und *kleinere*<br/>
(Optional) Geben Sie die erforderliche Mindestversion des Subsystems an. Die Argumente sind Dezimalzahlen im Bereich 0 bis 65.535. Weitere Informationen finden Sie in den Hinweisen. Für die Versionsnummern sind keine Obergrenzen festgelegt.

## <a name="remarks"></a>Hinweise

Die **/Subsystem** Option gibt die Umgebung für die ausführbare Datei.

Die Wahl des Subsystems hat Einfluss auf das Einstiegspunktsymbol bzw. die Einstiegspunktfunktion, das/die vom Linker ausgewählt wird.

Die optionalen Minimum- und Standardversionsnummern *wichtigen* und *kleinere* Versionsnummern für die Subsysteme sind wie folgt.

|Subsystem|Minimum|Standard|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1.0|1.0|
|CONSOLE|5.01 (x86) 5.02 (x64) 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|
|WINDOWS|5.01 (x86) 5.02 (x64) 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|
|NATIVE (mit DRIVER:WDM)|1.00 (x86) 1.10 (x64, ARM)|1.00 (x86) 1.10 (x64, ARM)|
|NATIVE (ohne /DRIVER:WDM)|4.00 (x86) 5.02 (x64) 6.02 (ARM)|4.00 (x86) 5.02 (x64) 6.02 (ARM)|
|POSIX|1.0|19.90|
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie den Ordner Linker aus.

1. Wählen Sie die **System** Eigenschaftenseite.

1. Ändern Sie die `SubSystem`-Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
