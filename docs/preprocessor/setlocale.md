---
title: "setlocale"
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
  - "setlocale_CPP"
  - "vc-pragma.setlocale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Pragmas, setlocale"
  - "setlocale-Pragma"
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# setlocale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert das Gebietsschema \(Sprache und Land\/Region\), das beim Übersetzen von Breitzeichenkonstanten und Zeichenfolgenliteralen verwendet werden soll.  
  
## Syntax  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## Hinweise  
 Da der Algorithmus zum Konvertieren von Multibytezeichen in Breitzeichen möglicherweise je nach Gebietsschema variiert oder die Kompilierung möglicherweise in einem anderen Gebietsschema, in dem eine ausführbare Datei ausgeführt wird, stattfindet, bietet dieses Pragma eine Möglichkeit, das Zielgebietsschema zur Kompilierungszeit festzulegen.  Dadurch wird sichergestellt, dass die Zeichenfolgen mit Breitzeichen im richtigen Format gespeichert werden.  
  
 Die Standard\-*Gebietsschemazeichenfolge* ist "".  
  
 Das Gebietsschema "C" ordnet jedes Zeichen in der Zeichenfolge seinem Wert als  `wchar_t` \(kurze ganze Zahl ohne Vorzeichen\) zu.  Andere Werte, die für `setlocale` gültig sind, sind als Einträge in der [Sprachenzeichenfolgen](../c-runtime-library/language-strings.md)\-Liste zu finden.  Sie können z. B. Folgendes ausgeben:  
  
```  
#pragma setlocale("dutch")  
```  
  
 Die Möglichkeit, eine Sprachenzeichenfolge auszugeben, hängt von der Codepage\- und der Sprachen\-ID\-Unterstützung Ihres Computers ab.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)