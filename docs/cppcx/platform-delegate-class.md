---
title: 'Platform:: Delegate-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Delegate
dev_langs: C++
helpviewer_keywords: Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 661e96cd2455610e6a7f669928d49c915b7d7575
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
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
 Verwenden Sie das Schlüsselwort [delegate](../windows/delegate-cpp-component-extensions.md) , um Delegaten zu erstellen. Verwenden Sie nicht explizit „Platform::Delegate“. Weitere Informationen finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md). Ein Beispiel zum Erstellen und Verwenden eines Delegaten finden Sie unter [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## <a name="see-also"></a>Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)