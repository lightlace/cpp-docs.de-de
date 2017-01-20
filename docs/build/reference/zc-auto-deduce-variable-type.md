---
title: "/Zc:auto (Variablentyp ableiten)"
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
  - "/Zc:auto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (Compileroptionen) [C++]"
  - "Ableiten des Variablentyps (C++)"
  - "Zc (Compileroptionen) [C++]"
  - "-Zc (Compileroptionen) [C++]"
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:auto (Variablentyp ableiten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Compileroption **\/Zc:auto\[\-\]** teilt dem Compiler mit, wie das [auto\-Schlüsselwort](../../cpp/auto-keyword.md) verwendet wird, um Variablen zu deklarieren.  Wenn Sie die Standardoption, **\/Zc:auto**, angeben, leitet der Compiler den Typ der deklarierten Variable von seinem Initialisierungsausdruck ab.  Wenn Sie  **\/Zc:auto\-** angeben, weist der Compiler die Variable der automatischen Speicherklasse zu.  
  
## Syntax  
  
```  
/Zc:auto[-]  
```  
  
## Hinweise  
 Der C\+\+\-Standard definiert eine ursprüngliche und eine überarbeitete Bedeutung für das `auto`\-Schlüsselwort.  Vor [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)] deklariert das Schlüsselwort eine Variable in der automatischen Speicherklasse, d. h. eine Variable, die über eine lokale Lebensdauer verfügt.  Ab [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)] leitet das Schlüsselwort den Typ einer Variable vom Initialisierungsausdruck der Deklaration ab. Verwenden Sie die Compileroption **\/Zc:auto\[\-\]**, um dem Compiler mitzuteilen, die ursprüngliche oder überarbeitete Bedeutung des `auto`\-Schlüsselworts zu verwenden.  
  
 Der Compiler gibt eine entsprechende Diagnosemeldung aus, wenn Ihre Verwendung des `auto`\-Schlüsselworts der aktuellen Compileroption widerspricht.  Weitere Informationen finden Sie unter [Auto\-Schlüsselwort](../../cpp/auto-keyword.md).  Weitere Informationen über Konformitätsprobleme mit Visual C\+\+ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).  
  
### So legen Sie diese Compileroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Knoten **Konfigurationseigenschaften**.  
  
3.  Klicken Sie auf den Knoten **C\/C\+\+**.  
  
4.  Klicken Sie auf den Knoten **Befehlszeile**.  
  
5.  Fügen Sie **\/Zc:auto** oder **\/Zc:auto\-** zum Bereich **Zusätzliche Optionen:** hinzu.  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)   
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)