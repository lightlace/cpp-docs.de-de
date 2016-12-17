---
title: "CString Exception Cleanup"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString objects, Ausnahmen"
  - "Ausnahmebehandlung, cleanup code"
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CString Exception Cleanup
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In früheren Versionen von MFC, war es wichtig, dass Sie [CString](../atl-mfc-shared/reference/cstringt-class.md)\-Objektnachgebrauch bereinigen.  Mit MFC\-Version 3.0 und späteren, expliziter Bereinigung ist nicht mehr erforderlich.  
  
 In der C\+\+\-Ausnahmebehandlung, die Mechanismus behandelt, den MFC verwendet jetzt, müssen Sie sich nicht um Bereinigung nach einer Ausnahme beschäftigen.  Eine Beschreibung, wie C\+\+ den Stapel "entlädt" nach einer Ausnahme abgefangen wird, finden Sie unter [der Versuch, die Erfassung und die throw\-Anweisungen](../cpp/try-throw-and-catch-statements-cpp.md).  Auch wenn Sie das MFC **TRY**\/**CATCH**\-Makros anstelle der C\+\+\-Schlüsselwörter **try** und **catch** verwenden, verwendet MFC den C\+\+\-Ausnahme\-Mechanismus unterhalb von, Sie müssen also immer noch nicht, um explizit zu bereinigen.  
  
## Siehe auch  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)   
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)