---
title: "/SAFESEH (Abbild verf&#252;gt &#252;ber sichere Ausnahmehandler) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/SAFESEH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SAFESEH (Linkeroption)"
  - "-SAFESEH (Linkeroption)"
  - "SAFESEH (Linkeroption)"
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /SAFESEH (Abbild verf&#252;gt &#252;ber sichere Ausnahmehandler)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SAFESEH[:NO]  
```  
  
 Wenn **\/SAFESEH** angegeben ist, erstellt der Linker nur dann ein Image, wenn auch eine Tabelle mit den sicheren Ausnahmehandlern des Images erstellt werden kann.  In dieser Tabelle ist für das Betriebssystem angegeben, welche Ausnahmehandler für das Image gültig sind.  
  
 **\/SAFESEH** gilt nur für Verknüpfungen mit x86\-Zielen.  **\/SAFESEH** wird nicht für Plattformen unterstützt, auf denen die Ausnahmehandler bereits aufgeführt werden.  Für [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] und ARM sind beispielsweise alle Ausnahmehandler in PDATA aufgeführt.  ML64.exe unterstützt das Hinzufügen von Anmerkungen, die SEH\-Informationen \(XDATA und PDATA\) an das Image ausgeben, sodass Entladung mithilfe von ml64\-Funktionen möglich ist.  Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 Wenn **\/SAFESEH** nicht angegeben wird, erstellt der Linker ein Image mit einer Tabelle sicherer Ausnahmehandler, sofern alle Module mit der sicheren Ausnahmebehandlung kompatibel sind.  Falls einige Module nicht mit der sicheren Ausnahmebehandlung kompatibel sind, enthält das resultierende Image keine Tabelle mit sicheren Ausnahmehandlern.  Wenn durch [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) WINDOWSCE oder eine der EFI\_\*\-Optionen festgelegt wird, unternimmt der Linker keinen Versuch, ein Image mit einer Tabelle sicherer Ausnahmehandler zu erstellen, da die Informationen von keinem dieser Subsysteme genutzt werden können.  
  
 Wenn **\/SAFESEH:NO** angegeben wird, erstellt der Linker kein Image mit einer Tabelle sicherer Ausnahmehandler, auch wenn alle Module mit der sicheren Ausnahmebehandlung kompatibel sind.  
  
 Der häufigste Grund dafür, dass der Linker kein Image erstellen kann, besteht darin, dass mindestens eine der Eingabedateien \(Module\) für den Linker nicht mit der sicheren Ausnahmebehandlung kompatibel sind.  Eine häufige Ursache dafür, dass ein Module nicht mit sicheren Ausnahmehandlern kompatibel ist, besteht darin, dass es mit einem Compiler aus einer früheren Visual C\+\+\-Version erstellt wurden.  
  
 Sie können auch eine Funktion als strukturierte Ausnahmehandler registrieren, indem Sie [.SAFESEH](../../assembler/masm/dot-safeseh.md) verwenden.  
  
 Es ist nicht möglich, vorhandene Binärdateien als sichere \(oder keine\) Ausnahmehandler besitzend zu markieren. Informationen zur sicheren Ausnahmebehandlung müssen beim Erstellen hinzugefügt werden.  
  
 Ob der Linker in der Lage ist, eine Tabelle sicherer Ausnahmehandler zu generieren, richtet sich nach der Anwendung, von der die C\-Laufzeitbibliothek verwendet wird.  Wenn Sie mit [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) linken und eine Tabelle sicherer Ausnahmehandler generieren möchten, müssen Sie eine Ladekonfigurationsstruktur \(wie sie beispielsweise in der CRT\-Quelldatei "loadcfg.c" enthalten ist\) bereitstellen, die alle für Visual C\+\+ definierten Einträge enthält.  Beispiel:  
  
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
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)