---
title: "Compilerwarnung (Stufe 1) C4172"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4172"
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Adresse einer lokalen Variablen oder eines temporären Werts wird zurückgegeben  
  
 Eine Funktion gibt die Adresse einer lokalen Variablen oder eines temporären Objekts zurück.  Lokale Variablen und temporäre Objekte werden zerstört, wenn eine Funktion eine Adresse zurückgibt. Demzufolge ist die zurückgegebene Adresse ungültig.  
  
 Wandeln Sie die Funktion so um, dass sie nicht die Adresse eines lokalen Objekts zurückgibt.  
  
 Im folgenden Beispiel wird C4172 generiert:  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```