---
title: 'Platform:: callbackcontext-Enumeration | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::CallbackContext
dev_langs: C++
helpviewer_keywords: Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ede3cfecadbe87caf5182e0d3df9c25a481f3079
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext-Enumeration
Gibt den Threadkontext an, in dem eine Rückruffunktion (Ereignishandler) ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Member  
  
|Typcode|Beschreibung|  
|---------------|-----------------|  
|Beliebig|Die Rückruffunktion kann in jedem beliebigen Threadkontext ausgeführt werden.|  
|Gleiche Voraussetzung|Die Rückruffunktion kann nur in dem Threadkontext ausgeführt werden, der den asynchronen Vorgang gestartet hat.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd