---
title: "Compilerfehler C2870"
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
  - "C2870"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2870"
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2870
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name' : Eine Namespacedefinition muss entweder im Dateigültigkeitsbereich oder unmittelbar in einer anderen Namespacedefinition angegeben werden  
  
 Der Namespace `name` wurde falsch definiert.  Namespaces müssen im Dateigültigkeitsbereich \(außerhalb aller Blöcke und Klassen\) oder direkt innerhalb eines anderen Namespaces definiert werden.  
  
 Im folgenden Beispiel wird C2870 generiert:  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```