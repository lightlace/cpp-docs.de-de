---
title: "Verwaltete Typen und die main-Funktion (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main-Funktion, In verwalteten Anwendungen"
  - "Verwalteter Code, main()-Funktion"
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Verwaltete Typen und die main-Funktion (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Entwickeln von Anwendungen mit **\/clr** darf es sich bei den Argumenten der **main\(\)**\-Funktion nicht um Argumente eines verwalteten Typs handeln.  
  
 Beispiel für eine richtige Signatur:  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## Siehe auch  
 [Verwaltete Typen](../dotnet/managed-types-cpp-cli.md)