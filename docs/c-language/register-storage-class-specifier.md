---
title: "Speicherklassenspezifizierer &quot;register&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Registerspeicherklasse"
  - "Registervariablen"
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherklassenspezifizierer &quot;register&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Der Microsoft C\/C\+\+\-Compiler berücksichtigt keine Benutzeranforderungen für Registervariablen.  Aus Gründen der Portabilität wird jedoch jede andere Semantik, die dem **register**\-Schlüsselwort zugeordnet ist, vom Compiler berücksichtigt.  Sie können z. B. weder den unären Operator "address\-of" \(**&**\) auf ein register\-Objekt anwenden, noch kann das **register**\-Schlüsselwort für Arrays verwendet werden.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md)