---
title: -ENTRY (Symbol für Einstiegspunkt) | Microsoft-Dokumentation
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
ms.openlocfilehash: 53f5a18b061cbd956731ced6788e86f871ea97bd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719575"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (Symbol für Einstiegspunkt)

```
/ENTRY:function
```

## <a name="arguments"></a>Argumente

*function*<br/>
Eine Funktion, die angibt, ein benutzerdefiniertes ab Adresse für eine .exe-Datei oder DLL.

## <a name="remarks"></a>Hinweise

Die/Entry-Option gibt eine Einstiegspunktfunktion als Startadresse für eine .exe-Datei oder DLL an.

Die Funktion definiert werden, um Sie verwenden die `__stdcall` Aufrufkonvention. Die Parameter und Rückgabewert richten sich nach, wenn das Programm eine Konsolenanwendung, einer Windows-Anwendung oder eine DLL-Datei ist. Es wird empfohlen, dass den Linker, die den Einstiegspunkt festlegen, damit die C-Laufzeitbibliothek fehlerfrei initialisiert wird, und C++-Konstruktoren für statische Objekte ausgeführt werden können.

Standardmäßig ist die Startadresse für den Namen einer Funktion aus der C-Laufzeitbibliothek. Der Linker wählt er entsprechend die Attribute des Programms, wie in der folgenden Tabelle gezeigt.

|Funktionsname|Standardwert für|
|-------------------|-----------------|
|**MainCRTStartup** (oder **WmainCRTStartup**)|Einer Anwendung, die Subsystem: Console verwendet. Aufrufe `main` (oder `wmain`)|
|**WinMainCRTStartup** (oder **wWinMainCRTStartup**)|Eine Anwendung, die/Subsystem:**WINDOWS**; Aufrufe `WinMain` (oder `wWinMain`), die muss definiert werden, verwenden `__stdcall`|
|**_DllMainCRTStartup**|EINE DLL; IGNORIERT Aufrufe `DllMain` , wenn er vorhanden ist, muss der Verwendung definiert werden `__stdcall`|

Wenn die [/DLL](../../build/reference/dll-build-a-dll.md) oder [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) Option nicht angegeben ist, wählt der Linker einen Punkt Subsystem und einen Einstiegspunkt, je nachdem, ob `main` oder `WinMain` definiert ist.

Die Funktionen `main`, `WinMain`, und `DllMain` sind die drei Formen des benutzerdefinierten Einstiegspunkts.

Wenn Sie ein verwaltetes Image zu erstellen, der Funktion angegeben, um/Entry müssen eine Signatur der (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).

Informationen zum Definieren Sie eigene `DllMain` Einstiegspunkt, finden Sie unter [DLLs und Visual C++-Laufzeitbibliothek Verhalten](../../build/run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Einstiegspunkt** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)