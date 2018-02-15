---
title: 'Platform:: disconnectedexception-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 175d132f2c6734f5f8328baee8cbdc4ea7e1b4c3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="platformdisconnectedexception-class"></a>Platform::DisconnectedException-Klasse
Wird ausgelöst, wenn ein COM-Proxyobjekt versucht, auf einen COM-Server zu verweisen, der nicht mehr vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Klasse A auf eine andere Klasse verweist (Klasse B), die sich in einem gesonderten Prozess befindet, erfordert Klasse A ein Proxyobjekt für die Kommunikation mit dem prozessexternen COM-Server, der die Klasse B enthält. Manchmal kann der Server über keinen Arbeitsspeicher mehr verfügen, ohne dass Klasse A dies bemerkt. In diesem Fall wird die RPC_E_DISCONNECTED-Ausnahme ausgelöst, und sie wird in "Platform::DisconnectedException" übersetzt. Ein Szenario, in dem dies auftritt, ist, wenn eine Ereignisquelle einen Delegaten aufruft, der an sie übergeben wurde, wobei der Delegat aber zu einem Zeitpunkt, nachdem er das Ereignis abonniert hatte, zerstört wurde. Wenn es hierzu kommt, entfernt die Ereignisquelle diesen Delegaten aus ihrer Aufrufliste.  
  
 Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md) -Klasse.  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## <a name="see-also"></a>Siehe auch  
 [Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)