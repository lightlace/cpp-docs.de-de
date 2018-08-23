---
title: 'Platform:: Delegate-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
dev_langs:
- C++
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdee3e432e3482b7f1a2c6e4be4c50abb1a6bfc8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609585"
---
# <a name="platformdelegate-class"></a>Platform::Delegate-Klasse
Darstellen eines Funktionsobjekts.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public delegate void delegate_name();  
```  
  
### <a name="members"></a>Member  
 Die Delegate-Klasse umfasst die Methoden Equals(), GetHashCode() und ToString(), die von der [Platform::Object Class](../cppcx/platform-object-class.md)abgeleitet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie das Schlüsselwort [delegate](../windows/delegate-cpp-component-extensions.md) , um Delegaten zu erstellen. Verwenden Sie nicht explizit „Platform::Delegate“. Weitere Informationen finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md). Ein Beispiel für das Erstellen und Verwenden eines Delegaten, finden Sie unter [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client (Min.):** Windows 8  
  
 **Unterstützter Server (Min.):** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## <a name="see-also"></a>Siehe auch  
 [Platform-namespace](../cppcx/platform-namespace-c-cx.md)