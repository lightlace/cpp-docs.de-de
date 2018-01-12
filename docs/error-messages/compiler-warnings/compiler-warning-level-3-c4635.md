---
title: Compilerwarnung (Stufe 3) C4635 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4635
dev_langs: C++
helpviewer_keywords: C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 16b6a19618afeed952cfa594961a0e4ccb777d26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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