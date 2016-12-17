---
title: "Unterst&#252;tzen von IDispatch und IErrorInfo"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IErrorInfo"
  - "IDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unterstützung für IDispatch-Klasse in ATL"
  - "IDispatchImpl-Klasse"
  - "Unterstützung für IErrorInfo-Klasse in ATL"
  - "ISupportErrorInfoImpl-Methode"
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: 16
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Unterst&#252;tzen von IDispatch und IErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die Vorlagenklasse [IDispatchImpl](../atl/reference/idispatchimpl-class.md) verwenden, um eine Standardimplementierung des `IDispatch Interface` Teils aller duale Schnittstellen für das Objekt bereitzustellen.  
  
 Wenn das Objekt die `IErrorInfo`\-Schnittstelle verwendet, um Fehler zurück an den Client zu senden, muss das Objekt die Schnittstelle `ISupportErrorInfo Interface` unterstützen.  Die Vorlagenklasse [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) bietet eine einfache Möglichkeit, dies zu implementieren, wenn Sie nur eine einzelne Schnittstelle verfügen, die Fehler für das Objekt generiert.  
  
## Siehe auch  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)