---
title: "FtmBase:::UnmarshalInterface-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::UnmarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnmarshalInterface-Methode"
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase:::UnmarshalInterface-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert einen neu erstellten Proxy und einen Schnittstellenzeiger zu diesem Proxy zurück.  
  
## Syntax  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### Parameter  
 `pStm`  
 Zeiger zum Stream, aus dem von Schnittstellenzeigern das Marshalling rückgängig gemacht werden soll.  
  
 `riid`  
 Verweis auf den Bezeichner der das Marshalling rückgängig gemacht werden Schnittstelle.  
  
 `ppv`  
 Wenn dieser Vorgang abgeschlossen hat, Anwendungstest die Adresse eine Zeigervariable, die den von Schnittstellenzeigern empfängt, in `riid`.  Wenn dieser Vorgang erfolgreich, \*`ppv` enthält den angeforderten Schnittstellenzeiger der das Marshalling rückgängig gemacht werden, Schnittstelle.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_NOINTERFACE oder E\_FAIL.  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [FtmBase\-Klasse](../windows/ftmbase-class.md)