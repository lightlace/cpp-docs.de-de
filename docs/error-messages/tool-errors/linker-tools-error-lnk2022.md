---
title: "Linkertoolfehler LNK2022"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2022"
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler bei Metadatenoperation \(HRESULT\): Fehlermeldung  
  
 Der Linker hat beim Zusammenführen von Metadaten einen Fehler ermittelt.  Um eine erfolgreiche Verknüpfung zu gewährleisten, müssen die Metadatenfehler aufgelöst werden.  
  
 In diesem Fall können Sie eine Fehlerdiagnose durchführen, indem Sie **ildasm –tokens** für die Objektdateien auszuführen. Suchen Sie nach den Typen, deren Token in `error_message` aufgeführt sind, und vergleichen Sie diese.  In den Metadaten sind zwei verschiedene Typen mit demselben Namen ungültig – auch dann, wenn lediglich das Layouttyp\-Attribut verschieden ist.  
  
 LNK2022 wird z. B. ausgegeben, wenn ein Typ \(z. B. eine Struktur\) in mehreren Kompiliereinheiten mit demselben Namen vorhanden ist, die jedoch miteinander in Konflikt stehende Definitionen enthalten, und wenn Sie die Kompilierung mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) durchführen.  Stellen Sie in diesem Fall sicher, dass der Typ in allen Kompiliereinheiten identisch definiert ist.  Der Typname wird in `error_message` aufgeführt.  
  
 Eine weitere mögliche Ursache für LNK2022 besteht darin, dass vom Linker eine Metadatendatei an einem Speicherort erkannt wird, der sich von dem Speicherort unterscheidet, der für den Compiler angegeben wurde \(mit [\#using](../../preprocessor/hash-using-directive-cpp.md)\).  Stellen Sie sicher, dass die Metadatendatei \(.dll oder .netmodule\) im selben Speicherort befindet, wenn sie den Linker übergeben wird, da es war, als es den Compiler.  
  
 Wenn Sie eine ATL\-Anwendung erstellen und in wenigstens einer Kompiliereinheit [\_ATL\_MIXED](../Topic/_ATL_MIXED.md) verwenden, müssen Sie [\_ATL\_MIXED](../Topic/_ATL_MIXED.md) in jeder Kompiliereinheit verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein leerer Typ definiert.  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## Beispiel  
 In diesem Beispiel wird verdeutlicht, dass zwei Quellcodedateien nicht verknüpft werden können, wenn diese Dateien Typen mit gleichem Namen aber verschiedenen Definitionen enthalten.  
  
 Im folgenden Beispiel wird LNK2022 generiert.  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```