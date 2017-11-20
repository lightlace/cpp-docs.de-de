---
title: "-Bigobj (Erhöhen der Anzahl von Abschnitten in. OBJ-Datei) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /bigobj
dev_langs: C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 73e6da121b099bdf6e67cdffe4d7d2bd0892d32a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Erhöhen der Anzahl von Abschnitten in der OBJ-Datei)
**/ bigobj** erhöht die Anzahl von Abschnitten, die eine Objektdatei enthalten kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
/bigobj  
```  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung kann eine Objektdatei bis zu 65.536 (2^16) adressierbare Abschnitte enthalten. Dabei spielt es keine Rolle, welche Zielplattform angegeben ist. **/ bigobj** erhöht diese Adressenkapazität auf 4.294.967.296 (2 ^ 32).  
  
 Von den meisten Modulen werden keine OBJ-Dateien erzeugt, die mehr als 65.536 Abschnitte enthalten. Für computergenerierten Code oder Code, in dem häufig Gebrauch von Vorlagenbibliotheken gemacht wird, sind allerdings unter Umständen OBJ-Dateien erforderlich, die mehr Abschnitte enthalten. **/ bigobj** auf Windows Store-Projekte standardmäßig aktiviert ist, da der computergenerierte XAML-Code viele Header enthält. Wenn Sie diese Option in einem Windows Store-App-Projekt deaktivieren, ist es wahrscheinlich, dass der Compilerfehler C1128 auftritt.  
  
 Linker, die vor Visual C++ 2005 ausgeliefert OBJ-Dateien, die mit erzeugt wurden können nicht gelesen werden **/bigobj**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)