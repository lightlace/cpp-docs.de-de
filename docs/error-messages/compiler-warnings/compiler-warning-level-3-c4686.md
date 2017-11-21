---
title: Compilerwarnung (Stufe 3) C4686 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4686
dev_langs: C++
helpviewer_keywords: C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 576e714937f0066a7b60ebf38d821715d4157b11
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="compiler-warning-level-3-c4686"></a>Compilerwarnung (Stufe 3) C4686
**'**   
 ***einen benutzerdefinierten Typ* ': mögliche Änderung im Verhalten in der UDT gibt Aufrufkonvention zurück**  
  
 Eine Spezialisierung einer Klassenvorlage wurde nicht definiert ist, bevor sie in einem Rückgabetyp verwendet wurde. Elemente, die die Klasse instanziiert werden C4686 aufgelöst; Deklarieren Sie eine Instanz von oder zugreifen auf einen Member (C\<Int >:: nichts) sind auch Optionen.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Verwenden stattdessen Sie die folgenden,  
  
```  
// C4686.cpp  
// compile with: /W3  
#pragma warning (default : 4686)  
template <class T>  
class C;  
  
template <class T>  
C<T> f(T);  
  
template <class T>  
class C {};  
  
int main() {  
   f(1);   // C4686  
}  
  
template <class T>  
C<T> f(T) {  
   return C<int>();  
}  
```