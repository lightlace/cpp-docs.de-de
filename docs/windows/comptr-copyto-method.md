---
title: "ComPtr::CopyTo-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo-Methode"
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ComPtr::CopyTo-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopiert den aktuellen oder die angegebene Schnittstelle, die diesem ComPtr dem angegebenen Zeiger zugeordnet werden.  
  
## Syntax  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### Parameter  
 `U`  
 Ein Typname.  
  
 `ptr`  
 Wenn dieser Vorgang abgeschlossen ist, ein Zeiger zur angeforderten Schnittstelle.  
  
 `riid`  
 Eine Schnittstelle ID  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das angibt, warum der implizite QueryInterface\-Vorgang fehlgeschlagen ist.  
  
## Hinweise  
 Die erste Funktion gibt eine Kopie eines Zeigers die Schnittstelle aus, die diesem ComPtr zugeordnet ist.  Diese Funktion immer S\_OK zurück.  
  
 Die zweite Funktion führt einen QueryInterface\-Vorgang auf der Schnittstelle aus, die diesem ComPtr für die Schnittstelle zugeordnet wird, die vom `riid`\-Parameter angegeben wurde.  
  
 Die dritte Funktion führt einen QueryInterface\-Vorgang auf der Schnittstelle aus, die diesem ComPtr für die zugrunde liegende Schnittstelle des Parameters `U` zugeordnet ist.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)