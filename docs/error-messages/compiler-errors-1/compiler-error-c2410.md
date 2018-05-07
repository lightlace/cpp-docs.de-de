---
title: Compilerfehler C2410 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9c2a2df0941130c4f2416806a05ce0378373eb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2410"></a>Compilerfehler C2410
'Bezeichner': mehrdeutigen Membernamen in 'Kontext'  
  
 Der Bezeichner ist ein Mitglied von mehr als eine Struktur oder Union in diesem Kontext.  
  
 Verwenden Sie einen Struktur oder Union-Spezifizierer für den Operanden, der den Fehler verursacht hat. Eine Struktur oder Union ist ein Bezeichner des Typs `struct` oder `union` (eine `typedef` Name oder eine Variable des gleichen Typs wie die Struktur oder Union, die auf die verwiesen wird). Der Bezeichner muss der linke Operand des ersten Memberauswahl Operators (.), der der Operand verwendet werden.