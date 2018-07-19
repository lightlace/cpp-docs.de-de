---
title: -SAFESEH (Abbild verfügt über sichere Ausnahmehandler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54d13e6922650f0193d4bbc3469d4acf25904234
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377908"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH (Abbild verfügt über sichere Ausnahmehandler)
```  
/SAFESEH[:NO]  
```  
  
 Wenn **/SAFESEH** angegeben wird, erstellt der Linker nur ein Bild, eine Tabelle mit sicheren ausnahmehandlern des Bilds auch erstellt werden kann. In dieser Tabelle ist für das Betriebssystem angegeben, welche Ausnahmehandler für das Image gültig sind.  
  
 **/ SAFESEH** ist nur gültig, beim Verknüpfen von X86 Ziele. **/ SAFESEH** wird nicht für Plattformen, die bereits die Ausnahmehandler bereits erwähnt unterstützt. Für [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] und ARM sind beispielsweise alle Ausnahmehandler in PDATA aufgeführt. ML64.exe unterstützt das Hinzufügen von Anmerkungen, die SEH-Informationen (XDATA und PDATA) an das Image ausgeben, sodass Entladung mithilfe von ml64-Funktionen möglich ist. Finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) für Weitere Informationen.  
  
 Wenn **/SAFESEH** nicht angegeben ist, wird der Linker ein Image mit einer Tabelle sicherer Ausnahmehandler, sofern alle Module mit der sicheren Ausnahmebehandlung kompatibel sind. Falls einige Module nicht mit der Funktion für die sichere Ausnahmebehandlung kompatibel sind, enthält das resultierende Image keine Tabelle mit sicheren Ausnahmehandlern. Wenn [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) WINDOWSCE oder eine der EFI_ * Optionen, gibt der Linker wird nicht um ein Image mit einer Tabelle sicherer Ausnahmehandler zu erstellen versuchen, während dieser Subsysteme vornehmen können die Informationen.  
  
 Wenn **/SAFESEH:NO** angegeben ist, wird der Linker kein Image mit einer Tabelle sicherer Ausnahmehandler, auch wenn alle Module mit der sicheren Ausnahmebehandlung kompatibel sind.  
  
 Der häufigste Grund dafür, dass der Linker kein Image erstellen kann, besteht darin, dass mindestens eine der Eingabedateien (Module) für den Linker nicht mit der Funktion für die sichere Ausnahmebehandlung kompatibel sind. Eine häufige Ursache dafür, dass ein Module nicht mit sicheren Ausnahmehandlern kompatibel ist, besteht darin, dass es mit einem Compiler aus einer früheren Visual C++-Version erstellt wurden.  
  
 Sie können auch eine Funktion als strukturierte Ausnahmehandler registrieren, mit [. SAFESEH](../../assembler/masm/dot-safeseh.md).  
  
 Es ist nicht möglich, vorhandene Binärdateien als sichere (oder keine) Ausnahmehandler besitzend zu markieren. Informationen zur sicheren Ausnahmebehandlung müssen beim Erstellen hinzugefügt werden.  
  
 Ob der Linker in der Lage ist, eine Tabelle sicherer Ausnahmehandler zu generieren, richtet sich nach der Anwendung, von der die C-Laufzeitbibliothek verwendet wird. Wenn Sie mit [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) und eine Tabelle mit sicheren ausnahmehandlern werden sollen, müssen Sie eine Ladekonfigurationsstruktur (z. B. in loadcfg.c enthalten ist, CRT-Quelldatei gefunden werden kann) bereitstellen, die alle für Visual C++ definierten Einträge enthält. Zum Beispiel:  
  
```  
#include <windows.h>  
extern DWORD_PTR __security_cookie;  /* /GS security cookie */  
  
/*  
 * The following two names are automatically created by the linker for any  
 * image that has the safe exception table present.  
*/  
  
extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */  
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is  
                                           the count of table entries */  
typedef struct {  
    DWORD       Size;  
    DWORD       TimeDateStamp;  
    WORD        MajorVersion;  
    WORD        MinorVersion;  
    DWORD       GlobalFlagsClear;  
    DWORD       GlobalFlagsSet;  
    DWORD       CriticalSectionDefaultTimeout;  
    DWORD       DeCommitFreeBlockThreshold;  
    DWORD       DeCommitTotalFreeThreshold;  
    DWORD       LockPrefixTable;            // VA  
    DWORD       MaximumAllocationSize;  
    DWORD       VirtualMemoryThreshold;  
    DWORD       ProcessHeapFlags;  
    DWORD       ProcessAffinityMask;  
    WORD        CSDVersion;  
    WORD        Reserved1;  
    DWORD       EditList;                   // VA  
    DWORD_PTR   *SecurityCookie;  
    PVOID       *SEHandlerTable;  
    DWORD       SEHandlerCount;  
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;  
  
const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {  
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    &__security_cookie,  
    __safe_se_handler_table,  
    (DWORD)(DWORD_PTR) &__safe_se_handler_count  
};  
```  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)