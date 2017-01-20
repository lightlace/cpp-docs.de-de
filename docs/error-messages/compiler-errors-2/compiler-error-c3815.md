---
title: "Compilerfehler C3815"
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
  - "C3815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3815"
ms.assetid: c5a3b404-6341-4fd3-92af-152b404c4dde
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Rückgabetyp der Methode 'get\_accessor' muss mit dem Typ des letzten Parameters des Setter übereinstimmen  
  
 Bei der Deklaration von [Eigenschaften](../../misc/property.md) muss der Rückgabewert der `get_accessor`\-Methode mit dem letzten Parameter in der Deklaration der set accessor\-Methode übereinstimmen.  
  
 C3815 ist nur mit **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C3815 generiert:  
  
```  
// C3815.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
__gc class X  
{  
public:  
   __property char get_N()  
   // try the following line instead  
   // __property int get_N()  
   {  
      return m_val;  
   }  
  
   __property void set_N( int val)  
   {  
      m_val = val;  
   }  
  
private:  
   int m_val;  
};   // C3815  
```  
  
 Das folgende Beispiel veranschaulicht, wie Sie Eigenschaften überladen können, sodass der Rückgabetyp des Getters nicht mehr dem letzten Parameters des Setters entspricht.  
  
```  
// C3815b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
public __gc class MyClass {  
public:  
// 1st property:  
   __property System::Int32 get_p1();  
   __property void set_p1(System::Int32 i);  
  
// 2nd property (only setter):  
   __property void set_p1(System::Int32* i);  
  
};  
```