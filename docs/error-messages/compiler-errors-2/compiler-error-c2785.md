---
title: Compilerfehler Fehler C2785 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2785
dev_langs:
- C++
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc0ca6235e0fd4bdd22330e807464e96280ae461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2785"></a>Compilerfehler Fehler C2785
'Deklaration1' und 'Deklaration2' haben unterschiedliche Rückgabetypen  
  
 Der Rückgabetyp der funktionsvorlagenspezialisierung unterscheidet sich von der Rückgabetyp der Hauptfunktion Vorlage.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie alle spezialisierungen der Funktionsvorlage für Konsistenz.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2785 generiert:  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```