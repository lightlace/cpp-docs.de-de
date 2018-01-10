---
title: -Zg (Funktionsprototypen generieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /zg
dev_langs: C++
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03e42c32806bbe7142b8d4d03e2f0974eeacdf84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zg-generate-function-prototypes"></a>/Zg (Funktionsprototypen generieren)
Entfernt. Erstellt für jede in der Quelldatei definierte Funktion einen Funktionsprototyp, kompiliert die Quelldatei aber nicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zg  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Compileroption ist nicht mehr verfügbar. Sie wurde in Visual C++ 2015 entfernt. Diese Seite ist für Benutzer von älteren Versionen von Visual C++ vorgesehen.  
  
 Der Funktionsprototyp beinhaltet den Rückgabedatentyp der Funktion und eine Liste der Argumenttypen. Die Liste der Argumenttypen wird anhand der Typen der formalen Parameter der Funktion erstellt. Alle in der Quelldatei bereits vorhandenen Funktionsprototypen werden ignoriert.  
  
 Die Liste der Prototypen wird in die Standardausgabe geschrieben. Mithilfe dieser Liste können Sie prüfen, ob die tatsächlichen und formalen Parameter einer Funktion kompatibel sind. Sie können die Liste speichern, indem Sie die Standardausgabe in eine Datei umleiten. Dann können Sie **#include** verwenden, um die Liste der Funktionsprototypen zu einem Bestandteil Ihrer Quelldatei zu machen. Dadurch wird der Compiler veranlasst, eine Argumenttypüberprüfung auszuführen.  
  
 Wenn Sie die **/Zg** -Option verwenden und Ihr Programm formale Parameter des Typs „struct“, „enum“ oder „union“ (oder Zeiger auf solche Typen) hat, muss die Deklaration für jeden „struct“-, „enum“- oder „union“-Typ einen Tagnamen haben. Im folgenden Beispiel ist der Tagname `MyStruct`.  
  
```C  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 Die **/Zg** Option war in Visual Studio 2005 veraltet und wurde in Visual Studio 2015 entfernt. Visual C++-Compiler wurde die Unterstützung für älteren Code im C-Format entfernt. Eine Liste der veralteten Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
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