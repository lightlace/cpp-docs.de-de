---
title: Compilerfehler C3153 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3153
dev_langs:
- C++
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9d6a2ad948ae8d5517f7b98316b4e3c67bea5afb
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3153"></a>Compilerfehler C3153
'Schnittstelle': Sie können keine Instanz einer Schnittstelle erstellen  
  
 Eine Schnittstelle kann nicht instanziiert werden. Um die Member einer Schnittstelle zu verwenden, leiten Sie eine Klasse von der Schnittstelle, implementieren Sie die Schnittstellenmember und verwenden Sie die Elemente.  
  
 Im folgenden Beispiel wird C3153 generiert:  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  

