---
title: -Z7, - Zi - ZI (Debuginformationsformat) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /zi
- /z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs: C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- -Zl compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- none compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 782420e674d6101f49e2b361c888a8f4b0b4c1ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Debuginformationsformat)
Wählen Sie den Typ der Debuginformationen aus, der für Ihr Programm erstellt wird, und ob diese Informationen als Objektdateien (OBJ) oder in einer Programmdatenbank (PDB) gespeichert werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Z{7|i|I}  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Optionen werden in der folgenden Tabelle beschrieben.  
  
 Keine  
 Erzeugt keine Debuginformationen, sodass die Kompilierung schneller ist.  
  
 **/ Z7**  
 Generiert eine OBJ-Datei mit vollständigen symbolischen Debuginformationen zur Verwendung mit dem Debugger. Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern. Es wird keine PDB-Datei generiert.  
  
 Für die Verteiler von Drittanbieterbibliotheken ist es von Vorteil, keine PDB-Datei zu haben. Die OBJ-Dateien für die vorkompilierten Header sind jedoch während der Linkphase und für das Debuggen erforderlich. Wenn vorhanden ist, geben Sie Informationen (und keinen Code) nur in die PCH-Objektdateien, müssen Sie auch mit Kompilieren [/Yl (PCH-Verweis für Debugbibliothek einfügen)](../../build/reference/yl-inject-pch-reference-for-debug-library.md).  
  
 **/ Zi**  
 Erstellt eine Programmdatenbank (PDB), die Typinformationen und symbolische Debuginformationen für die Verwendung mit dem Debugger enthält. Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern.  
  
 **/ Zi** hat keinen Einfluss auf Optimierungen. Allerdings **/Zi** impliziert **/debug**; finden Sie unter [/Debug (Debuginfo generieren)](../../build/reference/debug-generate-debug-info.md) für Weitere Informationen.  
  
 Typinformationen werden in der PDB-Datei, nicht in der OBJ-Datei abgelegt.  
  
 Sie können [/GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) mit **/Zi**, wohingegen **/GM** ist nicht verfügbar, bei der Kompilierung mit **"/ Z7"**.  
  
 Beim Kompilieren mit **/Zi** und **"/ CLR"**die <xref:System.Diagnostics.DebuggableAttribute> -Attribut nicht in den Assemblymetadaten abgelegt werden; Sie müssen es im Quellcode angeben, bei Bedarf. Dieses Attribut kann Auswirkungen auf die Laufzeitleistung der Anwendung haben. Weitere Informationen wie das Attribut "Debuggable" die Leistung auswirkt, und wie Sie die Auswirkungen auf die Leistung ändern können, finden Sie unter [erleichtern des Debugmodus für ein Abbild](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).  
  
 **/ ZI**  
 Erstellt, wie oben beschrieben, eine Programmdatenbank in einem Format, das die Funktion „Bearbeiten und Fortfahren“ unterstützt. Wenn Sie mit "Bearbeiten und Fortfahren" debuggen möchten, müssen Sie diese Option verwenden. Da die meisten Optimierungen nicht mit bearbeiten und Fortfahren kompatibel sind, verwenden **/Zi** deaktiviert jede `#pragma optimize` Anweisungen in Ihrem Code.  
  
 **/ Zi** bewirkt, dass [/Gy (Funktionslevel Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md) und [/FC (vollständiger Pfad der Quellcodedatei in Diagnostics)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) in der Kompilierung verwendet werden.  
  
 **/ Zi** ist nicht kompatibel mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  **/ Zi** steht nur in X86- und X64 Doppelprozessoren; der Compiler diese Compileroption steht nicht in Compilern ARM-Prozessoren abzielen.  
  
 Der Compiler den Namen der Programmdatenbank *Projekt*PDB-Datei. Wenn Sie eine Datei ohne ein Projekt zu kompilieren, erstellt der Compiler eine Datenbank mit dem Namen VC*x*0.PDB, in denen *x* ist die Hauptversion der [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] verwendet. Der Compiler bettet den Namen der PDB in jede mit dieser Option erstellte OBJ-Datei ein und verweist so den Debugger auf den Standort von symbolischen Informationen und Zeilennummern. Mit dieser Option werden die OBJ-Dateien kleiner, weil die Debuginformationen nicht in OBJ-Dateien, sondern in der PDB-Datei gespeichert werden.  
  
 Wenn Sie eine Bibliothek von Objekten erstellen, die mit dieser Option kompiliert worden sind, muss die zugeordnete PDB-Datei verfügbar sein, wenn die Bibliothek zu einem Programm gelinkt wird. Daher müssen Sie auch die PDB weitergeben, wenn Sie die Bibliothek weitergeben.  
  
 Zum Erstellen einer Bibliothek, die Debuginformationen ohne Verwendung von PDB-Dateien enthält, müssen Sie auswählen, der Compiler C 7.0-kompatibel (**"/ Z7"**) Option. Wenn Sie die Optionen „Vorkompilierte Header“ verwenden, werden Debuginformationen sowohl für den vorkompilierten Header als auch den restlichen Quellcode in der PDB abgelegt. Die **/Yd ablegen** Option wird ignoriert, wenn die Programmdatenbank-Option angegeben wird.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **allgemeine** Eigenschaftenseite.  
  
4.  Ändern der **Debuginformationsformat** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)