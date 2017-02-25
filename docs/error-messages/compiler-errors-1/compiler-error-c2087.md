---
title: "Compilerfehler C2087 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2087"
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Feldindex fehlt  
  
 Bei der Definition eines Arrays mit mehreren Indizes fehlt ein Indexwert für eine Größe über 1.  
  
 Im folgenden Beispiel wird C2087 generiert:  
  
```  
// C2087.cpp  
int main() {  
   char a[10][];   // C2087  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2087b.cpp  
int main() {  
   char b[4][5];  
}  
```