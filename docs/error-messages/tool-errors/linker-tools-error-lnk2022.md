---
title: Linkertoolfehler Lnk2022 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2022
dev_langs:
- C++
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6f12c53d7dd1383ad8f994a713c7226ab038cb19
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="linker-tools-error-lnk2022"></a>Linkertoolfehler LNK2022
Metadatenvorgang ist fehlgeschlagen (HRESULT): Error_message  
  
 Der Linker hat einen Fehler beim Zusammenführen von Metadaten festgestellt. Die Metadatenfehler müssen behoben werden, um erfolgreich zu verknüpfen.  
  
 Eine Möglichkeit, dieses Problem zu diagnostizieren ist zum Ausführen **"Ildasm"-Token** auf die Objektdateien zu ermitteln, welche Typen haben die Token in aufgeführten `error_message`, und suchen Sie nach unterschieden.  In den Metadaten zwei verschiedene Arten mit dem gleichen Namen ist ungültig, auch wenn nur LayoutType-Attribut unterscheidet.  
  
 Eine Ursache für LNK2022 ist, wenn ein Typ (z. B. eine Struktur) in mehrere Compilands, mit dem gleichen Namen, jedoch mit in Konflikt stehende Definitionen vorhanden ist, und bei der Kompilierung ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).  In diesem Fall stellen Sie sicher, dass der Typ eine identische Definition in jeder Kompiliereinheit aufweist.  Der Typname abgelesen werden `error_message`.  
  
 Eine weitere mögliche Ursache für LNK2022 der Linker wird eine Metadatendatei an einem anderen Speicherort als dem Compiler angegeben wurde (mit [#using](../../preprocessor/hash-using-directive-cpp.md) ). Stellen Sie sicher, dass die Metadatendatei (DLL oder NETMODULE-Datei) ist am gleichen Speicherort, wenn an den Linker übergeben wurde, die zuvor für den Compiler übergeben wurde.  
  
 Beim Erstellen einer Anwendung die Verwendung von ATL- [_ATL_MIXED](http://msdn.microsoft.com/Library/11b59a83-7098-43e2-9f7b-408299930966) ist in jeder Kompiliereinheit erforderlich, wenn er in mindestens einer verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird einen leeren Typ definiert.  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, dass zwei Quellcodedateien verknüpft werden können, die den gleichen Namen, aber unterschiedliche Definitionen enthalten.  
  
 Im folgenden Beispiel wird LNK2022 generiert.  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```
