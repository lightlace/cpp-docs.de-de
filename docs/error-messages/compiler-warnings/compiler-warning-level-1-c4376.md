---
title: "Compilerwarnung (Stufe 1) C4376"
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
  - "C4376"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4376"
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4376
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zugriffsspezifizierer 'old\_specifier:' wird nicht mehr unterstützt: Verwenden Sie stattdessen 'new\_specifier:'  
  
 Weitere Informationen über die Zugriffsmöglichkeit auf Typen und Member in Metadaten finden Sie unter [Typsichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [Membersichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) in [Gewusst wie: Definieren und Verarbeiten von Klassen und Strukturen](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4376 generiert.  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```