---
title: Compilerfehler C2410 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3d2f8f9b21d44c2fce92c526de0f6d53b99930b8
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2410"></a>Compilerfehler C2410
'Bezeichner': mehrdeutigen Membernamen in 'Kontext'  
  
 Der Bezeichner ist ein Mitglied von mehr als eine Struktur oder Union in diesem Kontext.  
  
 Verwenden Sie einen Struktur oder Union-Spezifizierer für den Operanden, der den Fehler verursacht hat. Eine Struktur oder Union ist ein Bezeichner des Typs `struct` oder `union` (eine `typedef` Name oder eine Variable des gleichen Typs wie die Struktur oder Union, die auf die verwiesen wird). Der Bezeichner muss der linke Operand des ersten Memberauswahl Operators (.), der der Operand verwendet werden.
