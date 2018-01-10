---
title: Compilerwarnung (Stufe 1) C4691 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4691
dev_langs: C++
helpviewer_keywords: C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17673ee3e65d2e0cd0d989c56759b62de38f5fdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4691"></a>Compilerwarnung (Stufe 1) C4691
'Typ': Typ verwiesen wurde in nicht referenzierte Assembly "File", in der aktuellen Übersetzungseinheit verwendet stattdessen definierten Typ erwartet  
  
 Die Metadatendatei, die die ursprüngliche Typdefinition enthält, wird nicht verwiesen, und der Compiler verwendet eine lokale Definition.  
  
 Im Fall, in dem Sie das Neuerstellen werden *Datei*, C4691 ignoriert oder mit dem Pragma deaktiviert [Warnung](../../preprocessor/warning.md).  Wenn die Datei, die Sie erstellen, in denen der Compiler davon ausgeht, die die Definition, identisch mit der Datei ist, können Sie also C4691 ignorieren.  
  
 Allerdings kann unerwartetes Verhalten auftreten, wenn der Compiler eine Definition verwendet, die nicht aus der gleichen Assembly ist, die in den Metadaten verwiesen wird. CLR-Typen sind nicht nur durch den Namen des Typs, sondern auch von der Assembly stark typisiert.  D. h. unterscheidet sich ein Z-Typ aus der Assembly z.dll ist ein Z-Typ aus der Assembly y.dll.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel enthält die ursprüngliche Typdefinition.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel auf C4691_a.dll verwiesen und eine Feld des Typs Original_Type.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4691 generiert.  Beachten Sie in diesem Beispiel enthält eine Definition für Original_Type und verweist nicht auf C4691a.dll verwiesen wird.  
  
 Verweisen auf die Metadatendatei, die die ursprüngliche Typdefinition enthält, und entfernen Sie die lokalen Deklaration und Definition, um zu beheben.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```