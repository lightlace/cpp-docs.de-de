---
title: Compilerfehler Fehler C2032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1db268222f3b9f7ca6f9ce297680866185e6661d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167215"
---
# <a name="compiler-error-c2032"></a>Compilerfehler Fehler C2032
'Bezeichner': Funktion kann nicht Mitglied der 'StrukturOderUnion' Struct/Union sein  
  
 Die Struktur oder Union verfügt über eine Memberfunktion, die in C++ jedoch in c nicht zulässig ist Als ein C++-Programm kompilieren Sie, oder entfernen Sie die Member-Funktion, um den Fehler zu beheben.  
  
 Im folgende Beispiel wird C2032 generiert:  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```