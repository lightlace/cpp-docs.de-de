---
title: -GH (_pexit-Hookfunktion aktivieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02cfdd783a698a3397e84fa62b7252399570dc84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
 `_pexit`ähnelt dem `_penter`; finden Sie unter [/GH (Enable _penter-Hookfunktion)](../../build/reference/gh-enable-penter-hook-function.md) für ein Beispiel zum Schreiben einer `_pexit` Funktion.  
  
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