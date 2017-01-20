---
title: "Compilerfehler C3162"
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
  - "C3162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3162"
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Ein Referenztyp mit einem Destruktor kann nicht als Typ des statischen Datenmembers 'Member' verwendet werden  
  
 Die Common Language Runtime kann nicht feststellen, wann ein benutzerdefinierter Destruktor ausgeführt werden muss, wenn die Klasse zusätzlich statische Memberfunktionen enthält.  
  
 Ein Destruktor wird nie ausgeführt, außer wenn das Objekt explizit gelöscht wird.  
  
 Weitere Informationen finden Sie unter  
  
-   [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Häufig auftretende 64\-Bit\-Migrationsprobleme bei Visual C\+\+](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Beispiel  
 Im folgenden Beispiel wird C3162 generiert.  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```