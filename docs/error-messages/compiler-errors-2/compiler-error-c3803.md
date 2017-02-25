---
title: "Compilerfehler C3803 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3803"
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Eigenschaft': Eigenschaft hat einen Typ, der mit einem seiner Accessoren 'Accessor' inkompatibel ist  
  
 Der Typ einer mit [property](../../cpp/property-cpp.md) definierten Eigenschaft stimmt nicht mit dem Rückgabetyp für eine ihrer Accessorfunktionen überein.  
  
 Im folgenden Beispiel wird C3803 generiert:  
  
```  
// C3803.cpp  
struct A  
{  
   __declspec(property(get=GetIt)) int i;  
   char GetIt()  
   {  
      return 0;  
   }  
  
   /*  
   // try the following definition instead  
   int GetIt()  
   {  
      return 0;  
   }  
   */  
}; // C3803  
  
int main()  
{  
}  
```