---
title: Linkertoolfehler Lnk2022 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2022
dev_langs:
- C++
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7769bc28dc777ef8d7b82b91b9695356db05a682
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300887"
---
# <a name="linker-tools-error-lnk2022"></a>Linkertoolfehler LNK2022  
  
> Fehler beim Metadatenvorgang (*HRESULT*): *Error_message*  
  
Der Linker hat einen Fehler beim Zusammenführen von Metadaten festgestellt. Die Metadatenfehler müssen behoben werden, um erfolgreich zu verknüpfen.  
  
Eine Möglichkeit, dieses Problem zu diagnostizieren ist zum Ausführen **"Ildasm"-Token** auf die Objektdateien zu ermitteln, welche Typen haben die Token in aufgeführten `error_message`, und suchen Sie nach unterschieden.  In den Metadaten zwei verschiedene Arten mit dem gleichen Namen ist ungültig, auch wenn nur LayoutType-Attribut unterscheidet.  
  
Eine Ursache für LNK2022 ist, wenn ein Typ (z. B. eine Struktur) in mehrere Compilands, mit dem gleichen Namen, jedoch mit in Konflikt stehende Definitionen vorhanden ist, und bei der Kompilierung ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).  In diesem Fall stellen Sie sicher, dass der Typ eine identische Definition in jeder Kompiliereinheit aufweist.  Der Typname abgelesen werden `error_message`.  
  
Eine weitere mögliche Ursache für LNK2022 der Linker wird eine Metadatendatei an einem anderen Speicherort als dem Compiler angegeben wurde (mit [#using](../../preprocessor/hash-using-directive-cpp.md) ). Stellen Sie sicher, dass die Metadatendatei (DLL oder NETMODULE-Datei) ist am gleichen Speicherort, wenn an den Linker übergeben wurde, die zuvor für den Compiler übergeben wurde.  
  
Beim Erstellen einer ATL-Anwendung, die Verwendung des Makros `_ATL_MIXED` ist in jeder Kompiliereinheit erforderlich, wenn er in mindestens einer verwendet wird.  
  
## <a name="example"></a>Beispiel  
  
Im folgende Beispiel wird einen leeren Typ definiert.  
  
```cpp  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>Beispiel  
  
Dieses Beispiel zeigt, dass zwei Quellcodedateien verknüpft werden können, die den gleichen Namen, aber unterschiedliche Definitionen enthalten.  
  
Im folgenden Beispiel wird LNK2022 generiert.  
  
```cpp  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```