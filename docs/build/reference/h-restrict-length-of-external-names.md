---
title: -H (Länge externer Namen beschränken) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /h
dev_langs:
- C++
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0859c6770da56023df7ba7ba24094bea2e889319
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377560"
---
# <a name="h-restrict-length-of-external-names"></a>/H (Länge externer Namen beschränken)
Veraltet. Beschränkt die Länge externer Namen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Hnumber  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Gibt die maximale Länge externer Namen in einem Programm zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig ist die Länge externer (öffentlicher) Namen 2.047 Zeichen. Dies gilt für C- und C++-Programme. Mit **/h** nur verringern Sie die maximale zulässige Länge von Bezeichnern, nicht erhöht werden kann. Ein Leerzeichen zwischen **/h** und `number` ist optional.  
  
 Wenn ein Programm Namen mit mehr als enthält `number`, die zusätzlichen Zeichen werden ignoriert. Wenn Sie ein Programm ohne Kompilieren **/h** und ein Bezeichner maximal 2.047 Zeichen enthält, generiert der Compiler [Schwerwiegender Fehler C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md).  
  
 Die zulässige Länge enthält alle vom Compiler erstellten führenden Unterstrich (_) oder at-Zeichen (@). Diese Zeichen sind Teil des Bezeichners und nehmen einen erheblichen Speicherort.  
  
-   Der Compiler Fügt einen führenden Unterstrich (_), Namen, die geändert, indem die `__cdecl` (Standard) und `__stdcall` aufrufen, und ein führendes Aufrufkonventionen at-Zeichen (@) Namen geändert, indem die `__fastcall` Aufrufkonvention.  
  
-   Der Compiler Fügt Informationen über die Argumentgröße an Namen geändert, indem die `__fastcall` und `__stdcall` Aufrufkonventionen und C++-Namen Typinformationen hinzugefügt.  
  
 Sie können möglicherweise **/h** nützlich:  
  
-   Wenn Sie gemischten Sprachen oder tragbaren Programme erstellen.  
  
-   Wenn Sie Tools verwenden, die Grenzwerte für die Länge der externen Bezeichnern vorgeben.  
  
-   Wenn Sie den Umfang des Speicherplatzes zu beschränken, die Symbole in einem Debugbuild verwenden möchten.  
  
 Das folgende Beispiel zeigt Verwendung **/h** können tatsächlich Fehler verursachen, wenn zu viele Bezeichnerlängen begrenzt sind:  
  
```cpp  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 Auch Achten Sie bei Verwendung der **/h** Option aufgrund von vordefinierten Compilerbezeichner. Wenn die maximale Bezeichnerlänge zu klein ist, werden bestimmte vordefinierte Bezeichner Funktionsaufrufe nicht aufgelöste sowie bestimmte Bibliothek. Z. B. wenn die `printf` -Funktion wird verwendet, und die Option **/H5** angegeben ist, zum Zeitpunkt der Kompilierung auf das Symbol **_prin als** erstellt werden, um verweisen `printf`, und dies nicht gefunden werden in der Bibliothek.  
  
 Verwenden von **/h** ist inkompatibel mit [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).  
  
 Die **/h** Option ist seit Visual Studio 2005 veraltet; die maximale Länge wurde erhöht und **/h** wird nicht mehr benötigt. Eine Liste der veralteten Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
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