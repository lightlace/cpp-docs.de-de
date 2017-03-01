---
title: Compilerfehler C2030 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: b38e76d73cf6e933145d8d382b653b8a5ed1892e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2030"></a>Compilerfehler C2030
ein Destruktor mit "protected private"-Zugriffsmöglichkeiten kann kein Member einer Klasse sein, die als "sealed" deklariert wurde  
  
 Eine Windows-Runtime-Klasse, die als `sealed` deklariert wird, kann nicht über einen geschützten privaten Destruktor verfügen. Nur öffentliche virtuelle und private nicht virtuelle Destruktoren sind für versiegelte Typen zulässig. Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](http://msdn.microsoft.com/Library/3d736b82-0bf0-48cf-bac1-cc9d110b70d1).  
  
 Um diesen Fehler zu beheben, ändern Sie den Zugriff auf den Destruktor.
