---
title: "Linkertoolfehler LNK1215 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1215"
ms.assetid: 0774d8e6-f0c1-4efb-8723-7e1be6863d81
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK1215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler bei Metadatenoperation \(HRESULT\): Fehler  
  
 Der Linker hat beim Versuch, Metadaten durch .NET Runtime zu aktualisieren, eine Fehlermeldung aus .NET Runtime empfangen.  
  
 `HRESULT` entspricht dem HRESULT aus der .NET Runtime\-Methode.  Der `error` liegt in dem durch .NET bereitgestellten Text.  
  
 Linker und .NET Runtime sind möglicherweise nicht kompatibel; installieren Sie Visual C\+\+ neu.