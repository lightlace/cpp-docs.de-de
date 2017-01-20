---
title: "Compilerfehler C2813"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2813"
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import wird mit "\/MP" nicht unterstützt.  
  
 C2813 wird ausgegeben, wenn Sie in einem Compilerbefehl die **\/MP**\-Compileroption und zwei oder mehr zu kompilierende Dateien angeben, von denen mindestens eine Datei die [\#import](../../preprocessor/hash-import-directive-cpp.md)\-Präprozessordirektive enthält. Die [\#import](../../preprocessor/hash-import-directive-cpp.md)\-Direktive generiert C\+\+\-Klassen aus den Typen in der angegebenen Typbibliothek und schreibt diese Klassen dann in zwei Headerdateien. Die [\#import](../../preprocessor/hash-import-directive-cpp.md)\-Direktive wird nicht unterstützt. Wenn mehrere Kompilierungseinheiten dieselbe Typbibliothek importieren, tritt zwischen diesen Einheiten ein Konflikt auf, wenn sie versuchen, die gleichen Headerdateien zur gleichen Zeit zu schreiben.  
  
 Dieser Compilerfehler und die **\/MP**\-Compileroption sind neu in [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)].  
  
## Beispiel  
 Im folgenden Beispiel wird C2813 generiert. Die Befehlszeile im "compile with:"\-Kommentar weist den Compiler an, die Compileroptionen **\/MP** und **\/c** zum Kompilieren mehrerer Dateien zu verwenden. Mindestens eine der Dateien enthält die [\#import](../../preprocessor/hash-import-directive-cpp.md)\-Direktive. Zum Testen dieses Beispiels wird die gleiche Datei zweimal verwendet.  
  
```  
// C2813.cpp // compile with: /MP /c C2813.cpp C2813.cpp #import "C:\windows\system32\stdole2.tlb"   // C2813 int main() { }  
```