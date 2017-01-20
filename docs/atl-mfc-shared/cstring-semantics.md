---
title: "CString Semantics"
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
  - "Zuweisungsanweisungen, assigning CString objects"
  - "CString objects, assignment semantics"
  - "semantics in Cstring"
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CString Semantics
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl [CString](../atl-mfc-shared/reference/cstringt-class.md)\-Objekte dynamische Objekte sind, die wachsen können, verhalten sie sich wie integrierte primitive Typen und einfache Klassen.  Jedes Objekt stellt `CString` einen eindeutigen Wert dar.  `CString`\-Objekte sollten für die eigentlichen Zeichenfolgen und nicht als Zeiger bleiben in Zeichenfolgen.  
  
 Sie können ein CString\-Objekt zu anderen zuweisen.  Wenn Sie jedoch eines der beiden `CString`\-Objekte ändern, wird das andere `CString`\-Objekt, wie dargestellt nicht durch das folgende Beispiel geändert:  
  
 [!CODE [NVC_ATLMFC_Utilities#188](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#188)]  
  
 Hinweis im Beispiel, dass die beiden `CString`\-Objekte als "gleich" gelten, da sie die gleiche Zeichenfolge darstellen.  Die Klasse `CString` überlädt den Gleichheitsoperator \(`==`\) um zwei `CString`\-Objekte auf Grundlage der Wert \(Inhalt\) anstatt ihre Identität \(Adresse\) zu vergleichen.  
  
## Siehe auch  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)