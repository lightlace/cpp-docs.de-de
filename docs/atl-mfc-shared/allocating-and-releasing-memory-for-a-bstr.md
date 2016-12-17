---
title: "Allocating and Releasing Memory for a BSTR"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "bstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTRs, Speicherreservierung"
  - "Speicher [C++], Freigeben"
  - "Speicherreservierung, BSTRs"
  - "memory deallocation, BSTR memory"
  - "memory deallocation, string memory"
  - "Zeichenfolgen [C++], Freigeben"
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Allocating and Releasing Memory for a BSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie `BSTR` s erstellen und sie zwischen COM\-Objekten übergeben, müssen Sie darauf achten, wenn Sie den Speicher behandeln, den sie verwenden, um Speicherverluste zu vermeiden.  Wenn `BSTR` innerhalb einer Schnittstelle bleibt, müssen Sie den Speicher freigeben, wenn Sie damit fertig sind.  Wenn `BSTR` übergibt aus einer Schnittstelle out, das empfangende Objekt Verantwortung für die Speicherverwaltung angewendet wird.  
  
 Im Allgemeinen sind die Regeln zum Belegen und Freigeben von Speicher, der für `BSTR` s zugeordnet ist, wie folgt:  
  
-   Wenn Sie in eine Funktion aufrufen, die ein `BSTR`\-Argument erwartet, müssen Sie den Speicher für `BSTR` vor dem Aufruf zuordnen und ihn danach freigeben.  Beispiel:  
  
     [!CODE [NVC_ATLMFC_Utilities#192](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#192)]  
  
     [!CODE [NVC_ATLMFC_Utilities#193](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#193)]  
  
-   Wenn Sie in eine Funktion aufrufen, die `BSTR` zurückgibt, müssen Sie die Zeichenfolge freigeben.  Beispiel:  
  
     [!CODE [NVC_ATLMFC_Utilities#194](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#194)]  
  
     [!CODE [NVC_ATLMFC_Utilities#195](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#195)]  
  
-   Wenn Sie eine Funktion implementieren, die `BSTR` zurückgibt, ordnen Sie zu, die Zeichenfolge jedoch geben Sie diese nicht frei.  Das Empfangen der Funktion gibt den Arbeitsspeicher frei.  Beispiel:  
  
     [!CODE [NVC_ATLMFC_Utilities#196](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#196)]  
  
## Siehe auch  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)   
 [SysAllocString](assetId:///9e0437a2-9b4a-4576-88b0-5cb9d08ca29b)   
 [SysFreeString](assetId:///8f230ee3-5f6e-4cb9-a910-9c90b754dcd3)