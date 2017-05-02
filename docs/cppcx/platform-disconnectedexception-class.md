---
title: "Platform::DisconnectedException-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::DisconnectedException"
  - "Platform/Platform::DisconnectedException::DisconnectedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::DisconnectedException"
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::DisconnectedException-Klasse
Wird ausgelöst, wenn ein COM\-Proxyobjekt versucht, auf einen COM\-Server zu verweisen, der nicht mehr vorhanden ist.  
  
## Syntax  
  
```  
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## Hinweise  
 Wenn Klasse A auf eine andere Klasse verweist \(Klasse B\), die sich in einem gesonderten Prozess befindet, erfordert Klasse A ein Proxyobjekt für die Kommunikation mit dem prozessexternen COM\-Server, der die Klasse B enthält. Manchmal kann der Server über keinen Arbeitsspeicher mehr verfügen, ohne dass Klasse A dies bemerkt. In diesem Fall wird die RPC\_E\_DISCONNECTED\-Ausnahme ausgelöst, und sie wird in "Platform::DisconnectedException" übersetzt. Ein Szenario, in dem dies auftritt, ist, wenn eine Ereignisquelle einen Delegaten aufruft, der an sie übergeben wurde, wobei der Delegat aber zu einem Zeitpunkt, nachdem er das Ereignis abonniert hatte, zerstört wurde. Wenn es hierzu kommt, entfernt die Ereignisquelle diesen Delegaten aus ihrer Aufrufliste.  
  
 Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md)\-Klasse.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::COMException\-Klasse](../cppcx/platform-comexception-class.md)