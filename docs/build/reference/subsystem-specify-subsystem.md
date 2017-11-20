---
title: -SUBSYSTEM (Subsystem angeben) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
dev_langs: C++
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bfdb54ece1669a2e3630fecad2d23ee55c2ac823
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (Subsystem angeben)
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT_APPLICATION  
 Eine in der Windows-Startumgebung ausgeführte Anwendung. Weitere Informationen zu startanwendungen finden Sie unter [Informationen zu BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639).  
  
 CONSOLE  
 Win32-Zeichenmodusanwendung. Im Betriebssystem wird eine Konsole für Konsolenanwendungen zur Verfügung gestellt. Wenn `main` oder `wmain` für systemeigenen Code definiert ist, ist `int main(array<String ^> ^)` für verwalteten Code definiert. Sie können die Anwendung auch nur mithilfe von `/clr:safe` erstellen. CONSOLE ist der Standardwert.  
  
 Extensible Firmware Interface  
 Die EFI_*-Subsysteme. Weitere Informationen finden Sie in der EFI-Spezifikation. Siehe z. B. die Intel-Website. Die erforderliche Mindest- und Standardversion ist Version 1.0.  
  
 NATIVE  
 Kernelmodustreiber für Windows NT. Diese Option ist üblicherweise für Windows-Systemkomponenten reserviert. Wenn [/Driver: WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md) angegeben ist, ist NATIVE lautet die Standardeinstellung.  
  
 POSIX  
 Anwendung, die mit dem POSIX-Subsystem unter Windows NT ausgeführt wird.  
  
 WINDOWS  
 Für die Anwendung ist keine Konsole erforderlich, wahrscheinlich da für die Interaktion mit dem Benutzer eigene Fenster erstellt werden. Wenn `WinMain` oder `wWinMain` für systemeigenen Code definiert ist oder `WinMain(HISTANCE *, HINSTANCE *, char *, int)` oder `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` für verwalteten Code definiert ist, ist WINDOWS der Standardwert.  
  
 `Major` und `minor` (optional)  
 Geben Sie die mindestens erforderliche Version des Subsystems an. Die Argumente sind Dezimalzahlen im Bereich 0 bis 65.535. Weitere Informationen finden Sie in den Hinweisen. Für die Versionsnummern sind keine Obergrenzen festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die /SUBSYSTEM-Option gibt die Umgebung für die ausführbare Datei an.  
  
 Die Wahl des Subsystems hat Einfluss auf das Einstiegspunktsymbol bzw. die Einstiegspunktfunktion, das/die vom Linker ausgewählt wird.  
  
 Die optionalen Minimum- und Standardversionsnummern `major` und `minor` für die Subsysteme sind die folgenden.  
  
|Subsystem|Minimum|Standard|  
|---------------|-------------|-------------|  
|BOOT_APPLICATION|1.0|1.0|  
|CONSOLE|5.01 (x86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|WINDOWS|5.01 (x86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|NATIVE (mit DRIVER:WDM)|1.00 (x86) 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|1.00 (x86) 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|  
|NATIVE (ohne /DRIVER:WDM)|4.00 (x86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|4.00 (x86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|POSIX|1.0|19.90|  
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner Linker aus.  
  
3.  Wählen Sie die **System** Eigenschaftenseite.  
  
4.  Ändern Sie die `SubSystem`-Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)