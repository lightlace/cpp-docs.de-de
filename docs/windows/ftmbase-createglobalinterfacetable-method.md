---
title: "FtmBase::CreateGlobalInterfaceTable-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateGlobalInterfaceTable-Methode"
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::CreateGlobalInterfaceTable-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine globale Schnittstellentabelle \(GIT\) erstellt.  
  
## Syntax  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### Parameter  
 `git`  
 Wenn dieser Vorgang abgeschlossen ist, ein Zeiger auf einen globalen Schnittstellentabelle.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Weitere Informationen finden Sie, dass das Thema "IGlobalInterfaceTable" im "COM\-Schnittstellen\-" Abschnitt des "COM" Thema in der MSDN Library verweisen.  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [FtmBase\-Klasse](../windows/ftmbase-class.md)