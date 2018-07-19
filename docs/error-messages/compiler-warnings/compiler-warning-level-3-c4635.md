---
title: Compilerwarnung (Stufe 3) C4635 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2dcc4b7466ed53a187b7f34ec45084a94adb59b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291771"
---
# <a name="compiler-warning-level-3-c4635"></a>Compilerwarnung (Stufe 3) C4635
XML-Dokumentkommentarziel: Ungültige XML: Grund  
  
 Der Compiler hat ein Problem mit XML-Tags gefunden.  Beheben Sie das Problem, und führen Sie die Kompilierung erneut durch.  
  
 Im folgenden Beispiel wird C4635 generiert:  
  
```  
// C4635.cpp  
// compile with: /doc /clr /W3 /c  
/// <summary>     
/// The contents of the folder have changed.  
/// <summary/>   // C4635  
  
// try the following line instead  
// /// </summary>  
public ref class Test {};  
```  
  
 Beachten Sie, dass die Ausgabe für dieses Beispiel wie folgt lautet: **Das Endtag 'member' stimmt nicht mit dem Starttag 'summary' überein.**  
  
 Das Problem bei diesem Beispiel wird das Endtag für \<Zusammenfassung > nicht ordnungsgemäß formuliert ist, und der Compiler erkennt es als jedoch nicht die \<Zusammenfassung >-Endtag.  Die \<Member >-Tag wird vom Compiler in jeder/doc-Kompilierung in der XDC-Datei eingebettet.  Daher hier ist das Problem, das das Endtag \</member >, entspricht nicht das vorherigen Starttag, die vom Compiler verarbeitet wurde (\<summary >.