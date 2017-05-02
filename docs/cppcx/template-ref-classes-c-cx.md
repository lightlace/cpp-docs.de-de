---
title: "Vorlagenverweisklassen (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# Vorlagenverweisklassen (C++/CX)
C\+\+\-Vorlagen werden nicht in Metadaten veröffentlicht und können daher in Ihrem Programm keine öffentliche oder geschützte Barrierefreiheit haben. Sie können C\+\+\-Standardvorlagen selbstverständlich intern im Programm verwenden. Außerdem können Sie eine private Verweisklasse als Vorlage definieren und eine explizit spezialisierte Vorlagenverweisklasse als privaten Member in einer öffentlichen Verweisklasse deklarieren.  
  
## Erstellen von Verweisklassenvorlagen  
 Im folgenden Beispiel wird gezeigt, wie eine private Verweisklasse als Vorlage und wie eine C\+\+\-Standardvorlage deklariert wird und wie beide als Member in einer öffentlichen Verweisklasse deklariert werden. Beachten Sie, dass die C\+\+\-Standardvorlage durch einen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typ, in diesem Fall ein Platform::String^\-Typ, spezialisiert werden kann.  
  
 [!code-cpp[cx_templates#01](../snippets/cpp/VS_Snippets_Misc/cx_templates/cpp/class1.h#01)]  
  
## Siehe auch  
 [Typsystem \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)