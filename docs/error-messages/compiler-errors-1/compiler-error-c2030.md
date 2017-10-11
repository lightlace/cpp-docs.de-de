---
title: Compilerfehler C2030 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a2efd868160e3ec7e5bf356603cc821a0b07f149
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2030"></a>Compilerfehler C2030
ein Destruktor mit "protected private"-Zugriffsmöglichkeiten kann kein Member einer Klasse sein, die als "sealed" deklariert wurde  
  
 Eine Windows-Runtime-Klasse, die als `sealed` deklariert wird, kann nicht über einen geschützten privaten Destruktor verfügen. Nur öffentliche virtuelle und private nicht virtuelle Destruktoren sind für versiegelte Typen zulässig. Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](../../cppcx/ref-classes-and-structs-c-cx.md).  
  
 Um diesen Fehler zu beheben, ändern Sie den Zugriff auf den Destruktor.
