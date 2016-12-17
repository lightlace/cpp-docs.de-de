---
title: "/GH (_pexit-Hookfunktion aktivieren)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_pexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh (Compileroption) [C++]"
  - "_pexit-Funktion"
  - "Gh (Compileroption) [C++]"
  - "-Gh (Compileroption) [C++]"
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# /GH (_pexit-Hookfunktion aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Option wird am Ende jeder Methode oder Funktion die `_pexit` \-Funktion aufgerufen.  
  
## Syntax  
  
```  
/GH  
```  
  
## Hinweise  
 Die `_pexit`\-Funktion gehört zu keiner Bibliothek; Sie müssen daher selbst eine Definition für  angeben.  
  
 Wenn Sie nicht die Absicht haben, \_pexit explizit aufzurufen, brauchen Sie keinen Prototypen bereitzustellen.  Die Funktion muss so angezeigt werden, als hätte sie den folgenden Prototypen, und sie muss den Inhalt aller Register beim Eintritt auf den Stapel legen und den unveränderten Inhalt beim Austritt vom Stapel holen:  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit` ist zu vergleichen mit `_penter`. Ein Beispiel für die Erstellung einer `_pexit`\-Funktion finden Sie unter [\/Gh \(\_penter\-Hookfunktion aktivieren\)](../../build/reference/gh-enable-penter-hook-function.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)