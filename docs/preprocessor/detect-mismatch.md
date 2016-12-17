---
title: "detect_mismatch"
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
  - "vc-pragma.detect_mismatch"
  - "detect_mismatch_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "detect_mismatch-Pragma"
  - "Pragmas, detect_mismatch"
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# detect_mismatch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Platziert einen Datensatz in einem Objekt.  Der Linker überprüft diese Datensätze auf potenzielle Konflikte.  
  
## Syntax  
  
```  
#pragma detect_mismatch( "name", "value"))  
```  
  
## Hinweise  
 Wenn Sie das Projekt verknüpfen, löst der Linker einen `LNK2038`\-Fehler aus, wenn das Projekt zwei Objekte enthält, die den gleichen `name`, jedoch einen unterschiedlichen `value` aufweisen.  Verwenden Sie dieses Pragma, um zu verhindern, dass inkonsistente Objektdateien verknüpft werden.  
  
 Name und Wert sind Zeichenfolgenliterale und befolgen im Zusammenhang mit Escapezeichen und Verkettungen die Regeln für Zeichenfolgenliterale.  Es muss die Groß\-\/Kleinschreibung beachtet werden. Außerdem können Kommas, Gleichheitszeichen, Anführungszeichen oder das `null`\-Zeichen enthalten sein.  
  
## Beispiel  
 Dieses Beispiel erstellt zwei Dateien, die unterschiedliche Versionsnummern für die gleiche Versionsbezeichnung aufweisen.  
  
```  
// pragma_directive_detect_mismatch_a.cpp  
#pragma detect_mismatch("myLib_version", "9")  
int main ()  
{  
   return 0;  
}  
  
// pragma_directive_detect_mismatch_b.cpp  
#pragma detect_mismatch("myLib_version", "1")  
```  
  
 Wenn Sie beide Dateien kompilieren, indem Sie die Befehlszeile `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` verwenden, erhalten Sie den Fehler `LNK2038`.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)