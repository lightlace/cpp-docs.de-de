---
title: Vorlagenverweisklassen (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b8bb720ef9275f9023cf15986f011573f4c510b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="template-ref-classes-ccx"></a>Vorlagenverweisklassen (C++/CX)
C++-Vorlagen werden nicht in Metadaten veröffentlicht und können daher in Ihrem Programm keine öffentliche oder geschützte Barrierefreiheit haben. Sie können C++-Standardvorlagen selbstverständlich intern im Programm verwenden. Außerdem können Sie eine private Verweisklasse als Vorlage definieren und eine explizit spezialisierte Vorlagenverweisklasse als privaten Member in einer öffentlichen Verweisklasse deklarieren.  
  
## <a name="authoring-ref-class-templates"></a>Erstellen von Verweisklassenvorlagen  
 Im folgenden Beispiel wird gezeigt, wie eine private Verweisklasse als Vorlage und wie eine C++-Standardvorlage deklariert wird und wie beide als Member in einer öffentlichen Verweisklasse deklariert werden. Beachten Sie, dass die C++-Standardvorlage spezialisiert werden kann, von einem Windows-Runtime-Typ, in diesem Fall ein Platform:: String ^.  
  
 [!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)