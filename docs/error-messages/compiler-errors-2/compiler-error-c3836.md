---
title: Compiler-Fehler C3836 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 0708b8c9bf59e1c2ea3751fbb91192d6b873d8ec
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3836"></a>Compilerfehler C3836
statischer Konstruktor darf keine Memberinitialisiererliste haben  
  
 Eine verwaltete Klasse kann keinen statischen Konstruktor haben, der auch eine Memberinitialisierungsliste verfügt. Statische Konstruktoren werden von der common Language Runtime Initialisierung Initialisieren von statischen Datenmembern-Klasse aufgerufen.  
  
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

