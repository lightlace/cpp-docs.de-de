---
title: "Linkertoolfehler LNK1215"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1215"
ms.assetid: 0774d8e6-f0c1-4efb-8723-7e1be6863d81
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler bei Metadatenoperation \(HRESULT\): Fehler  
  
 Der Linker hat beim Versuch, Metadaten durch .NET Runtime zu aktualisieren, eine Fehlermeldung aus .NET Runtime empfangen.  
  
 `HRESULT` entspricht dem HRESULT aus der .NET Runtime\-Methode.  Der `error` liegt in dem durch .NET bereitgestellten Text.  
  
 Linker und .NET Runtime sind möglicherweise nicht kompatibel; installieren Sie Visual C\+\+ neu.