---
title: "Compilerfehler C3293"
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
  - "C3293"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3293"
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3293
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Accessor': Verwenden Sie 'default', um auf die Standardeigenschaft \(Indexer\) der 'Typ'\-Klasse zuzugreifen.  
  
 Auf eine indizierte Eigenschaft wurde nicht ordnungsgemäß zugegriffen.  Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von indizierten Eigenschaften](../../misc/how-to-use-indexed-properties.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3293 generiert:  
  
```  
// C3293.cpp // compile with: /clr /c using namespace System; ref class IndexerClass { public: // default indexer property int default[int] { int get(int index) { return 0; } void set(int index, int value) {} } }; int main() { IndexerClass ^ ic = gcnew IndexerClass; ic->Item[0] = 21;   // C3293 ic->default[0] = 21;   // OK String ^s = "Hello"; wchar_t wc = s->Chars[0];   // C3293 wchar_t wc2 = s->default[0];   // OK Console::WriteLine(wc2); }  
```