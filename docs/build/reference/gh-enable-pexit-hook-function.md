---
title: -GH (_pexit-Hookfunktion aktivieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _pexit
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57e11c27af36eb539b22f3833a73341ff3065e97
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374504"
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (_pexit-Hookfunktion aktivieren)
Ruft die `_pexit` Funktion am Ende jeder Methode oder Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GH  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `_pexit` Funktion ist nicht Teil einer Bibliothek, und es liegt bei Ihnen, senden eine Definition für `_pexit`.  
  
 Wenn Sie explizit aufrufen möchten `_pexit`, Sie müssen sich nicht um einen Prototyp bereitzustellen. Die Funktion muss angezeigt werden, als ob er den folgenden Prototyp hatte und muss den Inhalt aller Register auf Eintrag push und pop unverändert Inhalt beim Beenden:  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit` ähnelt dem `_penter`; finden Sie unter [/GH (Enable _penter-Hookfunktion)](../../build/reference/gh-enable-penter-hook-function.md) für ein Beispiel zum Schreiben einer `_pexit` Funktion.  
  
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