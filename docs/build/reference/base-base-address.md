---
title: -BASE (Basisadresse) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4090a3e8d2f9f3bdcb68875d94a1b84e7bff0f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="base-base-address"></a>/BASE (Basisadresse)
```  
/BASE:{address[,size] | @filename,key}  
```  
  
 Die/BASE-Option legt eine Basisadresse für das Programm mit den Standardspeicherort für eine .exe oder DLL-Datei zu überschreiben. Die Standard-Basisadresse für eine .exe-Datei ist 0 x 400000 für 32-Bit-Images oder 0x140000000 für 64-Bit-Images. Für eine DLL ist die Basisadresse der Standardeinstellung 0 x 10000000 für 32-Bit-Images oder 0x180000000 für 64-Bit-Images. Unter Betriebssystemen, die keine Adresse Space Layout Randomization (ASLR) unterstützen, oder wenn die /DYNAMICBASE:NO-Option festgelegt wurde versucht das Betriebssystem zuerst, ein Programm zur angegebenen oder den Standard-Basisadresse zu laden. Wenn ausreichend Speicherplatz vorhanden nicht verfügbar ist, verschiebt das System das Programm an. Verwenden, um zu verhindern, dass die Verschiebung der [/festen](../../build/reference/fixed-fixed-base-address.md) Option.  
  
 Der Linker gibt einen Fehler aus, wenn *Adresse* ist kein Vielfaches von 64 KB. Sie können optional die Größe des Programms angeben. der Linker gibt eine Warnung aus, wenn das Programm nicht in der Größe passen, die Sie angegeben haben.  
  
 Alternative Möglichkeit zum Angeben der Basisadresse wird in der Befehlszeile mithilfe einer Antwortdatei Basisadresse. Eine Basisadresse Antwortdatei ist eine Textdatei, die die Basisadressen und optionale Größen enthält alle Ihr Programm verwendeten DLLs und einem eindeutigen Text-Schlüssel für alle Basisadressen. Verwenden Sie zum Angeben einer Basisadresse mithilfe einer Antwortdatei ein at-Zeichen (@) gefolgt vom Namen der Antwortdatei, *Filename*, gefolgt von einem Komma und dann die `key` Wert für die Basisadresse für die Verwendung in der Datei. Der Linker sucht nach *Filename* in entweder dem angegebenen Pfad, oder wenn kein Pfad angegeben wird, die in der LIB-Umgebungsvariablen angegebenen Verzeichnisse. Jede Zeile in *Filename* entspricht einer DLL und hat die folgende Syntax:  
  
```  
  
key address [size] ;comment  
```  
  
 Die `key` ist eine Zeichenfolge aus alphanumerischen Zeichen und ist nicht in der Groß-/Kleinschreibung beachtet. Es ist normalerweise der Name einer DLL, aber nicht zwingend erforderlich. Die `key` gefolgt von einer Basis *Adresse* in der Programmiersprache C, hexadezimalen oder dezimalen Notation und optional eine maximale Größe `size`. Alle drei Argumente werden durch Leerzeichen oder Tabstopps getrennt. Der Linker gibt eine Warnung aus, wenn das angegebene `size` ist kleiner als der virtuelle Adressraum, der von der Anwendung erforderlich sind. Ein `comment` wird durch ein Semikolon (;) angegeben und kann auf demselben oder auf einer separaten Zeile. Der Linker ignoriert den gesamten Text vom Semikolon am Ende der Zeile. In diesem Beispiel wird eine solche Datei:  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 Wenn die Datei, die folgenden Zeilen enthält DLLS.txt aufgerufen wird, gilt der folgende Beispielbefehl diese Informationen an:  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## <a name="remarks"></a>Hinweise  
 Aus Sicherheitsgründen empfiehlt Microsoft Sie verwenden die ["/ DynamicBase"](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) Option Basisadressen für die ausführbaren Dateien angeben, statt. Dadurch wird ein ausführbares Image, das nach dem Zufallsprinzip zur Ladezeit ein REBASE werden kann Address Space Layout Randomization (ASLR)-Funktion von Windows. Die Option "/ DynamicBase" ist standardmäßig aktiviert.  
  
 Eine weitere Möglichkeit zum Festlegen der Basisadresse ist die Verwendung der *Basis* Argument in einen [Namen](../../build/reference/name-c-cpp.md) oder [Bibliothek](../../build/reference/library.md) Anweisung. Die Base und [/DLL](../../build/reference/dll-build-a-dll.md) Optionen beieinander liegen, entspricht die **Bibliothek** Anweisung.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Basisadresse** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)