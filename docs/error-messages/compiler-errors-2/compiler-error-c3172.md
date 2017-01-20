---
title: "Compilerfehler C3172"
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
  - "C3172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3172"
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Modulname': Unterschiedliche idl\_module\-Attribute können in einem Projekt nicht bestimmt werden  
  
 In zwei Dateien einer Kompilierung wurden [idl\_module](../../windows/idl-module.md)\-Attribute mit demselben Namen, aber unterschiedlichen Parametern für `dllname` oder `version`gefunden.  Pro Kompilierung kann nur ein eindeutiges `idl_module`\-Attribut angegeben werden.  
  
 Identische `idl_module`\-Attribute können in mehr als einer Quellcodedatei angegeben werden.  
  
 Werden z. B. die folgenden `idl_module`\-Attribute gefunden:  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 und anschließend  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 erzeugt der Compiler den Fehler C3172 \(beachten Sie die unterschiedlichen Versionswerte\).