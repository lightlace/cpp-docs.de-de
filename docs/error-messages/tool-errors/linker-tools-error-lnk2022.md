---
title: Linkertoolfehler Lnk2022 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 91fb85679fd6c66bc97974912a2de688f494d5e9
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2022"></a>Linkertoolfehler LNK2022
Fehler bei der Metadatenoperation (HRESULT): Error_message  
  
 Der Linker hat einen Fehler beim Zusammenführen von Metadaten. Die Metadatenfehler müssen behoben werden, um erfolgreich zu verknüpfen.  
  
 Eine Möglichkeit zur diagnose dieses Problems ist die Ausführung **Ildasm – Tokens** auf die Objektdateien welche haben die Token aufgeführt, `error_message`, und suchen Sie nach unterschieden.  In den Metadaten zwei verschiedene Typen mit demselben Namen ist ungültig, auch wenn nur Layouttyp-Attribut unterscheidet.  
  
 Eine Ursache für LNK2022 ist, wenn ein Typ (z. B. eine Struktur) in mehrere Kompiliereinheit mit dem gleichen Namen, jedoch mit in Konflikt stehende Definitionen vorhanden ist und beim Kompilieren mit [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  In diesem Fall stellen Sie sicher, dass der Typ in jeder Kompiliereinheit identisch ist.  Der Typname steht in `error_message`.  
  
 Eine weitere mögliche Ursache für LNK2022 wird der Linker eine Metadatendatei an einem anderen Speicherort für den Compiler angegeben wurde (mit [#using](../../preprocessor/hash-using-directive-cpp.md) ). Stellen Sie sicher, dass die Metadatendatei (.dll oder .netmodule) am gleichen Speicherort, an den Linker übergeben wird, wie bei der Übergabe an den Compiler.  
  
 Beim Erstellen einer ATL-Anwendung, die Verwendung von [_ATL_MIXED](http://msdn.microsoft.com/Library/11b59a83-7098-43e2-9f7b-408299930966) ist in jeder Kompiliereinheit erforderlich, wenn er in mindestens einer verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird einen leeren Typ definiert.  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, dass zwei Quellcodedateien verknüpft werden können, die den gleichen Namen, aber unterschiedliche Definitionen enthalten.  
  
 Im folgende Beispiel wird LNK2022 generiert.  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```
