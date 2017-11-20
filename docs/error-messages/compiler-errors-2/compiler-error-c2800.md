---
title: Compilerfehler C2800 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2800
dev_langs: C++
helpviewer_keywords: C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 330b859b4b24f741388be716fb464fc33c3abaa3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2800"></a>Compilerfehler C2800
'Operator Operator' kann nicht überladen werden  
  
 Die folgenden Operatoren können nicht überladen werden: Klasse Memberzugriff (`.`), Zeiger auf Member (`.*`), Bereich Auflösung (`::`), bedingte Ausdruck (`? :`), und `sizeof`.  
  
 Im folgenden Beispiel wird C2800 generiert:  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```