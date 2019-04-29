---
title: /ENTRY (Symbol für Einstiegspunkt)
ms.date: 11/04/2016
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
ms.openlocfilehash: 0f3604ef75ce10928463c088e423615886555eda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293211"
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

Wenn die [/DLL](dll-build-a-dll.md) oder [/Subsystem](subsystem-specify-subsystem.md) Option nicht angegeben ist, wählt der Linker einen Punkt Subsystem und einen Einstiegspunkt, je nachdem, ob `main` oder `WinMain` definiert ist.

Die Funktionen `main`, `WinMain`, und `DllMain` sind die drei Formen des benutzerdefinierten Einstiegspunkts.

Wenn Sie ein verwaltetes Image zu erstellen, der Funktion angegeben, um/Entry müssen eine Signatur der (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).

Informationen zum Definieren Sie eigene `DllMain` Einstiegspunkt, finden Sie unter [DLLs und Visual C++-Laufzeitbibliothek Verhalten](../run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Einstiegspunkt** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
