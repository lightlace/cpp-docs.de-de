---
title: "Compilerfehler C3537"
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
  - "C3537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3537"
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Sie können keine Umwandlung zu einem Typ durchführen, der "Auto" enthält  
  
 Sie können keine Variable in den angegebenen Typ umwandeln, da der Typ das `auto`\-Schlüsselwort enthält und die standardmäßige [\/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)\-Compileroption gültig ist.  
  
## Beispiel  
 Im folgenden Code wird C3537 erzeugt, da die Variablen in einen Typ umgewandelt werden, der das `auto`\-Schlüsselwort enthält.  
  
```  
// C3537.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int value = 123;  
   auto(value);                        // C3537  
   (auto)value;                        // C3537  
   auto x1 = auto(value);              // C3537  
   auto x2 = (auto)value;              // C3537  
   auto x3 = static_cast<auto>(value); // C3537  
   return 0;  
}  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)