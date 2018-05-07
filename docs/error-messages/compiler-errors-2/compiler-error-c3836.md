---
title: Compilerfehler C3836 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45a2eda2567e63771ed4c8919945e34ee41be1cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3836"></a>Compilerfehler C3836
statischer Konstruktor ist nicht zulässig, eine Memberinitialisiererliste haben  
  
 Eine verwaltete Klasse kann keinen statischen Konstruktor verfügen, das ebenfalls eine Member-Initialisierungsliste. Konstruktoren von statischen Klassen heißen durch die common Language Runtime auf Initialisierung Initialisieren von statischen Datenmembern.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3836 generiert:  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  
