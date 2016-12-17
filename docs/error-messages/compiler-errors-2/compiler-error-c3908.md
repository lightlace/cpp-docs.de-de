---
title: "Compilerfehler C3908"
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
  - "C3908"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3908"
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3908
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Zugriffsebene ist weniger restriktiv als 'Konstrukt'  
  
 Die Accessormethode einer Eigenschaft \(get oder set\) kann nicht über weniger restriktiven Zugriff verfügen als der Zugriff auf die Eigenschaft selbst.  Dies gilt ebenso für Ereignis\-Accessormethoden.  
  
 Weitere Informationen finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md) und [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3908 generiert:  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```