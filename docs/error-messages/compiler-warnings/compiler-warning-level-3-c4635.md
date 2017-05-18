---
title: Compilerwarnung (Stufe 3) C4635 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d4c85ca32903e20ea18a731872c25ee999b67f89
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

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
  
 Das Problem bei diesem Beispiel wird das Endtag für \<Zusammenfassung > formuliert ist, und der Compiler erkennt es als jedoch nicht die \<Zusammenfassung > Endtag.  Die \<Member >-Tag wird vom Compiler in jeder/doc-Kompilierung in der XDC-Datei eingebettet.  Daher hier ist das Problem, das das Endtag \</member >, entspricht nicht das vorherigen Starttag, die vom Compiler verarbeitet wurde (\<Zusammenfassung >.
