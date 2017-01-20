---
title: "rename (#import)"
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
  - "Rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "rename-Attribut"
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# rename (#import)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Umgeht Probleme mit Namenskonflikten.  
  
## Syntax  
  
```  
rename("OldName","NewName")  
```  
  
#### Parameter  
 `OldName`  
 Alter Name in der Typbibliothek.  
  
 `NewName`  
 Name, der anstelle des alten Namens verwendet werden soll.  
  
## Hinweise  
 Wenn dieses Attribut angegeben wird, ersetzt der Compiler alle Vorkommen von *OldName* in einer Typbibliothek durch den vom Benutzer bereitgestellten *NewName* in den resultierenden Headerdateien.  
  
 Dieses Attribut kann verwendet werden, wenn ein Name in der Typbibliothek einer Makrodefinition in den Systemheaderdateien entspricht.  Wenn diese Situation nicht aufgelöst wird, werden unterschiedliche Syntaxfehler wie [Compilerfehler C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) und [Compilerfehler C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md) generiert.  
  
> [!NOTE]
>  Die Ersetzung erfolgt für einen in der Typbibliothek verwendeten, nicht für einen in der resultierenden Headerdatei verwendeten Namen.  
  
 Angenommen, eine Eigenschaft mit dem Namen `MyParent` ist in einer Typbibliothek vorhanden und das Makro `GetMyParent` wird in einer Headerdatei definiert und vor `#import` verwendet.  Da `GetMyParent` der Standardname einer Wrapperfunktion für die Fehlerbehandlungseigenschaft **get** ist, tritt ein Namenskonflikt auf.  Um das Problem zu umgehen, verwenden Sie das folgende Attribut in der `#import`\-Anweisung:  
  
```  
rename("MyParent","MyParentX")  
```  
  
 das den Namen `MyParent` in der Typbibliothek umbenennt.  Bei dem Versuch, den Wrappernamen `GetMyParent` umzubenennen, tritt ein Fehler auf:  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 Dies ist darauf zurückzuführen, dass der Name `GetMyParent` nur in der resultierenden Typbibliotheksheaderdatei auftritt.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)