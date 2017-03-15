---
title: "Speicherklassenspezifizierer &quot;register&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Registerspeicherklasse"
  - "Registervariablen"
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Speicherklassenspezifizierer &quot;register&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Der Microsoft C\/C\+\+\-Compiler berücksichtigt keine Benutzeranforderungen für Registervariablen.  Aus Gründen der Portabilität wird jedoch jede andere Semantik, die dem **register**\-Schlüsselwort zugeordnet ist, vom Compiler berücksichtigt.  Sie können z. B. weder den unären Operator "address\-of" \(**&**\) auf ein register\-Objekt anwenden, noch kann das **register**\-Schlüsselwort für Arrays verwendet werden.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md)