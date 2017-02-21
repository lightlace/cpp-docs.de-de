---
title: "Verbundanweisungen (Bl&#246;cke) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "}"
  - "{"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Blöcke, Informationen über Blöcke"
  - "Verbundanweisungen"
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verbundanweisungen (Bl&#246;cke)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Verbundanweisung besteht aus null oder mehr Anweisungen, eingeschlossen in geschweifte Klammern \(**{ }**\).  Einer Verbundanweisung kann an einer jeder beliebigen Stelle, an der eine Anweisung erwartet wird.  Verbundanweisungen werden im Allgemeinen "Blöcke" genannt.  
  
## Syntax  
  
```  
  
{ [ statement-list ] }  
```  
  
## Hinweise  
 Das folgende Beispiel benutzt eine Verbundanweisung als den *statement*\-Teil der **if**\-Anweisung \(Einzelheiten zur Syntax erhalten Sie unter [Die if\-Anweisung](../cpp/if-else-statement-cpp.md)\):  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
    Balance -= Amount;  
```  
  
> [!NOTE]
>  Da eine Deklaration eine Anweisung ist, kann es sich bei einer Deklaration um eine der Anweisungen in der *statement\-list* handeln.  Folglich verfügen Namen, die innerhalb einer Verbundanweisung deklariert werden, jedoch nicht explizit als statisch deklariert werden, über einen lokalen Gültigkeitsbereich und eine lokale Lebensdauer \(für Objekte\).  Einzelheiten zum Umgang mit Namen mit lokalem Gültigkeitsbereich finden Sie unter [Gültigkeitsbereich](../cpp/scope-visual-cpp.md).  
  
## Siehe auch  
 [Übersicht über C\+\+\-Anweisungen](../cpp/overview-of-cpp-statements.md)