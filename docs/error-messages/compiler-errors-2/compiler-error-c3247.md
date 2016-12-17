---
title: "Compilerfehler C3247"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3247"
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse1': Eine Co\-Klasse kann nicht von einer anderen Co\-Klasse 'Klasse2' erben.  
  
 Eine Klasse mit dem [coclass](../../windows/coclass.md)\-Attribut gekennzeichnete Klasse kann nicht von einer anderen Klasse erben, die mit dem `coclass`\-Attribut markiert ist.  
  
 Im folgenden Beispiel wird C3247 generiert:  
  
```  
// C3247.cpp [module(name="MyLib")]; [coclass] class a { }; [coclass] class b : public a {   // C3247 }; int main() { }  
```