---
title: -ENTRY (Symbol für Einstiegspunkt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
dev_langs:
- C++
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74d7e6e05af98bb3d3175d352fb3d5de1b70b12b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375398"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (Symbol für Einstiegspunkt)
```  
/ENTRY:function  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *function*  
 Eine Funktion, die angibt, eine benutzerdefinierte ab Adresse für eine .exe-Datei oder DLL.  
  
## <a name="remarks"></a>Hinweise  
 Die Option/Entry gibt eine Einstiegspunktfunktion als die Startadresse für eine .exe-Datei oder DLL an.  
  
 Die Funktion definiert werden, damit Sie verwenden die `__stdcall` Aufrufkonvention. Die Parameter und Rückgabewert richten sich nach, wenn das Programm eine Konsolenanwendung, eine Windows-Anwendung oder eine DLL ist. Es wird empfohlen, dass den Linker den Einstiegspunkt so festlegen, dass die C-Laufzeitbibliothek korrekt initialisiert ist und C++-Konstruktoren für statische Objekte ausgeführt werden können.  
  
 Standardmäßig ist die Startadresse einen Funktionsnamen aus der C-Laufzeitbibliothek. Der Linker wählt er gemäß der Attribute des Programms, wie in der folgenden Tabelle gezeigt.  
  
|Funktionsname|Standard für|  
|-------------------|-----------------|  
|**MainCRTStartup** (oder **WmainCRTStartup**)|Eine Anwendung, die/Subsystem: Console verwendet; Aufrufe `main` (oder `wmain`)|  
|**WinMainCRTStartup** (oder **wWinMainCRTStartup**)|Eine Anwendung, die/Subsystem verwendet:**WINDOWS**; Aufrufe `WinMain` (oder `wWinMain`), die muss definiert werden, verwenden `__stdcall`|  
|**_DllMainCRTStartup**|EINE DLL; IGNORIERT Aufrufe `DllMain` , wenn er vorhanden ist, muss die Verwendung definiert `__stdcall`|  
  
 Wenn die [/DLL](../../build/reference/dll-build-a-dll.md) oder [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) Option nicht angegeben wird, wählt des Linkers ein Subsystem und Eintrag je nachdem, ob `main` oder `WinMain` definiert ist.  
  
 Die Funktionen `main`, `WinMain`, und `DllMain` sind die drei Formen des benutzerdefinierten Einstiegspunkts.  
  
 Wenn Sie einem verwalteten Image zu erstellen, benötigen die Funktion angegeben, um/Entry eine Signatur der (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).  
  
 Informationen zum Definieren Sie eigene `DllMain` Einstiegspunkt, finden Sie unter [DLLs und Visual C++-Laufzeitbibliothek Verhalten](../../build/run-time-library-behavior.md) .  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Einstiegspunkt** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)