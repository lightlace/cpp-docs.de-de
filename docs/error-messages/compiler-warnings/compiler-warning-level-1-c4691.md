---
title: "Compilerwarnung (Stufe 1) C4691"
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
  - "C4691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4691"
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Der Typ, auf den verwiesen wird, wurde in der Assembly 'Datei' erwartet, auf die nicht verwiesen wird. Es wird stattdessen der in der aktuellen Übersetzungseinheit definierte Typ verwendet.  
  
 Auf die Metadatendatei, die die urprüngliche Typdefinition enthält, wird nicht verwiesen, und der Compiler verwendet eine lokale Typdefinition.  
  
 Im Fall, in dem Sie *file* neu erstellen, kann C4691 [warning](../../preprocessor/warning.md)\- Pragma ignoriert oder deaktiviert werden.  D. h. wenn die erstellte Datei dieselbe Datei ist, in der der Compiler nach der Typdefinition sucht, kann C4691 ignoriert werden.  
  
 Wenn der Compiler jedoch eine Definition verwendet, die nicht aus der gleichen Assembly stammt, auf die in den Metadaten verwiesen wird, so kann dies zu unerwartetem Verhalten führen. CLR\-Typen werden nicht nur nach Typ klassifiziert, sondern auch nach Assembly.  Das heißt, ein Z\-Typ aus der Assembly z.dll ist verschieden von einem Z\-Typ aus der Assembly y.dll.  
  
## Beispiel  
 In diesem Beispiel wird die ursprüngliche Typdefinition verwendet.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## Beispiel  
 In diesem Beispiel wird auf C4691\_a.dll verwiesen und ein Feld des Typs Original\_Type deklariert.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4691 generiert.  Beachten Sie, dass dieses Beispiel eine Definition für Original\_Type enthält und nicht auf C4691a.dll verwiesen wird.  
  
 Um das Problem zu beheben, verweisen Sie auf die Metadatendatei, die die ursprüngliche Typdefinition enthält, und entfernen Sie die lokale Deklaration und Definition.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```